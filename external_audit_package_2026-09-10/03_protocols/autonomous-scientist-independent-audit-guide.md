# Independent Audit and Provider-Release Guide

The auditor must be independent of the authors and of the autonomous system under
test. The auditor receives the repository, the content-addressed freeze manifest,
and this guide before any primary, ablation, transport, or replication seed is
created. The auditor must not accept author-supplied positive answers in place of
inspection.

## Required review

1. Recompute every frozen source, protocol, and evidence hash and verify the freeze
   identity.
2. Run the frozen test suite and both no-model qualification builders.
3. Inspect the model packet and tool gateways to confirm that hidden hypotheses,
   task state, fault identity, future outcomes, scorer state, and private provider
   material cannot reach any model arm.
4. Confirm byte-identical public tasks, tool schemas, conclusion schemas, model,
   reasoning effort, token ceilings, wall ceilings, and measurement/validator
   ceilings within each matched domain. Confirm that prompt-equated Codex receives
   the public method policy verbatim.
5. Confirm that all arms finish before task authority is used for scoring; an
   interrupted opened block becomes failures; no selective rerun or score-aware
   continuation is possible.
6. Inspect exact McNemar, stratified paired bootstrap, Holm correction, missing-as-
   failure, stratum, false-promotion, autonomy, accounting, recovery, transport,
   ablation, replication, and conjunctive claim-gate implementations.
7. Confirm that each ablation removes only its named Scientist component and that
   transport is labeled a positive-control non-degradation study.
8. Confirm that provider packages reproduce exactly from private entropy, contain
   the committed balanced cells, use disjoint high-entropy seeds, expose no private
   authority in public bundles, and cannot be provisioned without this audit.
9. Confirm that every development task is excluded and all prospective namespaces
   are absent.

Only after all checks pass may the auditor run
`scripts/audit_autonomous_scientist_freeze_v1.py` with every attestation flag and
a signed-attestation text file. The output audit release is public. The signature
may be a detached-signature statement with a separately archived cryptographic
signature, but it must identify the auditor, freeze, date, and reviewed package.

The independent primary provider then runs the adaptive and transport provisioning
scripts. A separate independent laboratory provisions and executes the replication.
Authors must not choose or inspect private entropy, seeds, authorities, or interim
scores. Provider public commitments are released before execution; private bundles
remain withheld until each matched block is terminal and should be disclosed only
under the release plan.
