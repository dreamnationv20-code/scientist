# Independent audit runbook

Run these steps on a fresh copy of the package using a machine and account under
your control. The commands assume a POSIX shell on macOS or Linux.

## Step 1 Record the environment

Create a separate output directory outside the extraction and record:

```bash
mkdir audit-return
uname -a > audit-return/environment.txt
python3 --version >> audit-return/environment.txt 2>&1
uv --version >> audit-return/environment.txt 2>&1
```

Python 3.9 or newer is required. Install `uv` through its official distribution
if it is not already available. The automated audit uses the locked dependency
file and does not require GPU hardware or a model account.

## Step 2 Verify the archive before extraction

The archive is:

`05_frozen_audit_bundle/autonomous-scientist-independent-audit-freeze-27a53ce-r2.tar.gz`

Expected SHA-256:

`b4bda6e280e51c9fcbcbb3caed4bfd752f9cc5ec300be4046b361e8db3d34ca1`

On macOS:

```bash
shasum -a 256 05_frozen_audit_bundle/autonomous-scientist-independent-audit-freeze-27a53ce-r2.tar.gz \
  > audit-return/observed-archive-sha256.txt
```

On Linux:

```bash
sha256sum 05_frozen_audit_bundle/autonomous-scientist-independent-audit-freeze-27a53ce-r2.tar.gz \
  > audit-return/observed-archive-sha256.txt
```

Stop and report a failure if the digest differs. Do not extract or audit a
non-matching archive.

## Step 3 Extract into a clean directory

```bash
mkdir scientist-audit-clean
tar -xzf 05_frozen_audit_bundle/autonomous-scientist-independent-audit-freeze-27a53ce-r2.tar.gz \
  -C scientist-audit-clean
cd scientist-audit-clean
```

Do not copy files from another checkout into this directory. Do not edit any file
inside it.

## Step 4 Recreate the locked environment

```bash
uv sync --frozen
uv run python --version >> ../audit-return/environment.txt 2>&1
uv tree > ../audit-return/dependency-tree.txt
```

If dependency creation fails, preserve the complete error output and report the
audit as incomplete. Do not change dependency versions to obtain a pass.

## Step 5 Run the automated audit

```bash
env PYTHONPATH=src .venv/bin/python scripts/audit_autonomous_scientist_freeze_v1.py \
  --freeze runs/autonomy_closure_v1/implementation_freeze_v1/artifacts/manifests/autonomous-scientist-implementation-freeze-v1.json \
  > ../audit-return/automated-audit-report.json
```

Record the shell exit code immediately:

```bash
echo $? > ../audit-return/automated-audit-exit-code.txt
```

A machine pass requires exit code zero, `all_checks_passed` equal to `true`, all
seven automated checks equal to `true`, the frozen test suite passing, and both
qualification identities reproducing. Preserve the generated report unchanged.

## Step 6 Perform the human review

Read `docs/autonomous-scientist-independent-audit-guide-2026-09-09.md` inside the
clean extraction. Inspect every required domain; the following files are useful
entry points and do not limit the scope of review.

### Answer separation

- `src/scientist/autonomy/adaptive_confirmatory_provider_v1.py`
- `src/scientist/autonomy/adaptive_confirmatory_runner_v1.py`
- `src/scientist/autonomy/adaptive_codex_runner_v1.py`
- `src/scientist/autonomy/adaptive_worlds_v1.py`

Confirm that models receive only public task material and cannot access generating
hypotheses, private task state, fault identity, future outcomes or scorer state
before every matched terminal is immutable.

### Matched resources

- `src/scientist/autonomy/confirmatory_runtime_commitment_v1.py`
- `src/scientist/autonomy/adaptive_three_arm_v1.py`
- `src/scientist/autonomy/adaptive_confirmatory_runner_v1.py`

Confirm matched public packets, tools, model snapshot, reasoning setting, token
ceiling, wall-time ceiling and measurement budget. Confirm that the prompt-equated
control receives the declared method policy without acquiring external authority.

### Interruption and rerun semantics

- `src/scientist/autonomy/sequential_receipt_runner.py`
- `src/scientist/autonomy/receipt_journal.py`
- `src/scientist/autonomy/adaptive_confirmatory_runner_v1.py`
- `src/scientist/autonomy/adaptive_ablation_runner_v1.py`

Confirm that completed calls are not reissued, resource usage is reconstructed,
orphaned effects remain visible, interrupted opened blocks cannot be selectively
rerun and missing or invalid episodes count as failures.

### Statistical and claim logic

- `src/scientist/autonomy/adaptive_confirmatory_analysis_v1.py`
- `src/scientist/autonomy/adaptive_ablation_analysis_v1.py`
- `src/scientist/autonomy/causalab_transport_analysis_v1.py`
- `src/scientist/autonomy/adaptive_replication_analysis_v1.py`
- `src/scientist/autonomy/nature_evidence_integration_v1.py`

Confirm the paired estimand, exact McNemar calculation, stratified bootstrap,
simultaneous intervals, Holm adjustment, false-promotion rule, autonomy and
accounting gates, and fail-closed conjunctive claim integration.

### Ablation isolation

- `src/scientist/autonomy/adaptive_ablation_runner_v1.py`
- `src/scientist/autonomy/adaptive_ablation_analysis_v1.py`

Confirm that each ablation removes only its named authority component and uses the
preselected outcome-blind task subset.

### Provider sequestration

- `src/scientist/autonomy/adaptive_confirmatory_provider_v1.py`
- `src/scientist/autonomy/causalab_transport_provider_v1.py`
- `src/scientist/autonomy/adaptive_confirmatory_runner_v1.py`

Confirm that fresh entropy and private authority can be generated only after a
valid audit release and remain outside author and model access until matched
terminals are immutable.

Record evidence, commands, concerns and unresolved questions in
`../audit-return/auditor-findings.md`. A check that cannot be established is a
failure, not an assumed pass.

## Step 7 Complete and sign the attestation

Copy the template from the outer package into `audit-return`, complete every
field, mark each required item PASS or FAIL and identify what you inspected.

```bash
cp ../06_AUDITOR_ACTION_REQUIRED/INDEPENDENT_AUDIT_ATTESTATION_TEMPLATE.md \
  ../audit-return/INDEPENDENT_AUDIT_ATTESTATION_COMPLETED.md
```

Sign the completed statement. A verifiable detached digital signature may be
returned separately. Disclose all relationships to the authors and proposed
providers.

## Step 8 Issue the release only after a complete pass

Run this command only when the automated audit passed, every human check passed,
the attestation is complete and the proposed release file does not already exist.
Replace the two bracketed values.

```bash
env PYTHONPATH=src .venv/bin/python scripts/audit_autonomous_scientist_freeze_v1.py \
  --freeze runs/autonomy_closure_v1/implementation_freeze_v1/artifacts/manifests/autonomous-scientist-implementation-freeze-v1.json \
  --auditor-ref '<auditor or organization>' \
  --audit-date '<YYYY-MM-DD>' \
  --signed-attestation-file ../audit-return/INDEPENDENT_AUDIT_ATTESTATION_COMPLETED.md \
  --release-output ../audit-return/external-audit-release.json \
  --auditor-independent \
  --attest-answer-separation \
  --attest-matched-resources \
  --attest-interruption-semantics \
  --attest-statistical-code \
  --attest-ablation-isolation \
  --attest-provider-sequestration \
  > ../audit-return/audit-release-console.txt
```

The script reruns the automated checks and refuses release if a frozen byte changed,
a prospective namespace exists or a required attestation flag is absent. Do not
pass an attestation flag for a check that you did not independently establish.

## Step 9 Return the audit record

Return the complete `audit-return` directory. Use `RETURN_CHECKLIST.md` to verify
its contents. Retain your clean extraction and any detached signatures until the
authors confirm receipt and verify the release identity.

