# Files to return after the independent audit

Please return one directory named `audit-return` containing the following files.

## Required for every audit outcome

- `environment.txt`
- `dependency-tree.txt`, or the dependency error log if environment creation failed
- `observed-archive-sha256.txt`
- `automated-audit-report.json`, or the complete automated-audit error log
- `automated-audit-exit-code.txt`
- `auditor-findings.md`
- `INDEPENDENT_AUDIT_ATTESTATION_COMPLETED.md`

The findings file must list every failure, limitation, ambiguity and deviation. If
none were observed, state that explicitly.

## Required only when every check passes

- `external-audit-release.json`
- `audit-release-console.txt`
- A detached digital signature or verifiable signature reference, if used

Do not create or return `external-audit-release.json` after a partial pass, an
unresolved check or a failed check.

## Expected identities

- Freeze identity:
  `27a53ce49129ca44dd45f1120241b5b7e7c4674759f95666ec714c42e0bdce95`
- Audit archive SHA-256:
  `b4bda6e280e51c9fcbcbb3caed4bfd752f9cc5ec300be4046b361e8db3d34ca1`

The returned release is authorization to begin independent task provisioning. It
is not a result, a replication, a manuscript endorsement or permission to expose
private task authority to the authors.

