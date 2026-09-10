# Independent audit attestation template

The independent auditor must complete this from their own clean extraction of
`autonomous-scientist-independent-audit-freeze-27a53ce-r2.tar.gz`. Do not sign
this template without performing the automated and manual review in the bundled
audit guide. Findings and exceptions must be reported even if they prevent
release.

## Auditor identity

- Auditor or organization:
- Professional affiliation:
- Contact:
- Audit date:
- Relationship to the authors, system developers and proposed task providers:
- Basis for independence:

## Package identity

- Freeze identity: `27a53ce49129ca44dd45f1120241b5b7e7c4674759f95666ec714c42e0bdce95`
- Archive filename: `autonomous-scientist-independent-audit-freeze-27a53ce-r2.tar.gz`
- Expected archive SHA-256: `b4bda6e280e51c9fcbcbb3caed4bfd752f9cc5ec300be4046b361e8db3d34ca1`
- Observed archive SHA-256:
- Clean extraction location or environment reference:
- Automated audit report identity:
- Test count and result:

## Required attestations

For each item, record PASS or FAIL and briefly state what was inspected.

1. **Auditor independence:**
2. **Answer separation:** neither research arm can access private task authority,
   sealed outcomes or scorer state before all matched terminal records are
   immutable.
3. **Matched resources:** model, reasoning setting, public packet, tool surface,
   token ceiling, wall-time ceiling and measurement budget are arm-matched.
4. **Interruption semantics:** opening a matched or ablation block prevents
   selective rerun; missing and invalid episodes are failures.
5. **Statistical implementation:** paired design, exact McNemar calculations,
   stratified bootstrap, simultaneous intervals, Holm adjustment and conjunctive
   gates implement the prospective protocol.
6. **Ablation isolation:** each removal changes only its named authority component,
   uses the outcome-blind preselected subset and cannot be chosen post-outcome.
7. **Provider sequestration:** fresh entropy and private authorities are created
   only after release and remain outside author/model access until scoring.
8. **Frozen-byte integrity:** all frozen source, protocol and evidence hashes
   match; no confirmatory namespace, seed, authority or outcome predates release.

## Exceptions or limitations

[List every exception. If none, write “None observed.”]

## Signed statement

I attest that I performed the audit described above on the identified archive and
that this record accurately reports my findings. I understand that this
attestation authorizes task provision only when every required item passes; it
does not endorse future results or their interpretation.

- Name:
- Signature or verifiable digital-signature reference:
- Date:

