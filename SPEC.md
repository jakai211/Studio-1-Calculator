# Lesson 01 specification

## STUDIO-001 · Launch a tested calculator on an existing server

**Status:** Calculator deployed November 7, 2026; hosted verification passed again November 17, 2026. Learner observations/review and final GitHub completion remain pending.
**Next step:** Learner tries the public calculator and explains one actual result; review the learning summary before publication and finish the PR.
**Instructor implementation:** [issue #9](https://github.com/kaw393939/373_hosting/issues/9).
Create your own issue from the [lesson template](.github/ISSUE_TEMPLATE/studio-calculator.md).

## Agreed result

Launch the supplied published calculator image through your existing Traefik
network and a nonconflicting HTTPS hostname. Preserve unrelated services and
host access. Do not add another proxy/updater or build a substitute image.
The [release selection](studio/calculator-release.json) supplies the expected
commit and multi-platform digest independently of the running website.
An explicitly agreed adoption of a matching existing deployment is recorded
as adoption, not a fresh launch. This bounded lesson does not certify the whole
server baseline or a vulnerability-free image.

- **Public hostname:** https://j5port-qa.duckdns.org — working calculator.
- **New launch or adopted deployment, and reason:** New launch on November 7; [original launch report](studio/launch-evidence.json) preserves `new_launch: true`. The [latest verification report](studio/evidence.json) says `already-managed` because it checks that existing deployment.
- **Own issue / feature branch / PR:** [Issue #1](https://github.com/jakai211/Studio-1-Calculator/issues/1), `studio-001-calculator`, [PR #2](https://github.com/jakai211/Studio-1-Calculator/pull/2).
- **Agreed scope and replacement deviation:** Initial agreement was QA for the supplied image and preservation of the portfolio at https://j5port.duckdns.org. The learner subsequently deleted the original droplet and explicitly approved a replacement Ubuntu server, Docker/Traefik setup, portfolio restoration, and calculator deployment. The original server was NOT preserved. The two unchanged containers reported by verification belong to the replacement hosting setup, not the deleted droplet. The calculator uses the replacement's `hosting-web` network and Traefik HTTPS routing.

The learner approved the replacement's $6/month plan and existing SSH key.
The captured portfolio HTML was restored, both DNS hostnames were updated, and
the prepared calculator was launched after checks. No claim is made that this
restoration recovered every service or file on the deleted server.

Private SSH targets and configuration stay in ignored local state. Share only
reviewed, selected evidence; never commit credentials or raw server output.

## Evidence to keep

| Evidence | Actual result / link |
|---|---|
| Prepared Black/Pylint/pytest and real-image browser checks | [Full Linux CI passed all three jobs](https://github.com/jakai211/Studio-1-Calculator/actions/runs/42340726893) at template commit `27e8dedefa99866d8dd6d825d0e929a373bf82ef`. Windows fast check: Black passed; Pylint and pytest failed on Linux-only APIs. Focused follow-up: 62 passed, 3 failed on Windows platform limitations. Local Docker E2E not run. |
| Hosted image/commit, trusted HTTPS, valid and rejected API cases | November 17 prepared `verify` and `report` passed: expected pinned image and app commit match; trusted HTTPS; multiply 6 × 7 returns HTTP 200/result 42; division by zero returns 400; numeric string returns 422. See [sanitized evidence](studio/evidence.json). |
| Preservation of unrelated services | Original server deleted by learner; see deviation above. On November 7, restored portfolio HTTP 200 and HTML SHA-256 matched the pre-deletion capture: `d37c42fdd2eb8e147caeadc68c936c782dc844e2337b794444032ce3bb69fed6`. Latest verification reports two replacement hosting containers unchanged in identity, state, and published ports. |
| AI browser review | November 7: browser and API both displayed 42 for 6 × 7; division by zero showed an error. [Calculation screenshot](studio/screenshots/calculator-42.png), [rejected calculation](studio/screenshots/calculator-invalid.png). These are AI observations, not learner observations. |
| Own prediction, check interpretation, browser observation and keep/revise reason | [LEARNING.md](LEARNING.md), Pending; disclose assistance |
| Accuracy review before publishing learner excerpts | Pending |
| Actual PR, latest CI, merge and issue closure | [PR #2](https://github.com/jakai211/Studio-1-Calculator/pull/2); [previous branch CI passed](https://github.com/jakai211/Studio-1-Calculator/actions/runs/42368304243). Updated-commit CI, merge, and issue closure pending. |

[Current sanitized runtime evidence](studio/evidence.json) is the actual prepared
`report` export after November 17 verification. The November 7 launch report is
retained separately. The original deadline passed before deployment; no timestamp
is backdated. On November 17 the learner shared instructor feedback inviting
completion and resubmission without a late penalty.

Link the exported `studio/evidence.json`, actual CI and issue/PR when available.
CI does not deploy this server. A fixture, green check, timestamp, closed issue
or AI assertion alone does not establish the full result. `status` reports
recorded evidence and readiness for instructor review; it does not grade,
certify authorship or establish understanding.

## Optional instructor history

The records below are background, not steps to repeat. Their original anchors
remain here so earlier links continue to work.

## HOST-001 · Keep the Traefik dashboard private

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-001--keep-the-traefik-dashboard-private).

## HOST-002 · Controlled host maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-002--controlled-host-maintenance).

## HOST-003 · Companion image security maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-003--companion-image-security-maintenance).
