# Lesson 01 specification

## STUDIO-001 · Launch a tested calculator on an existing server

**Status:** Scope agreed November 6, 2026 ET; deployment incomplete.
**Next step:** Restore server console access, inspect existing routing, and resolve the occupied QA hostname before deployment.
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

- **Public hostname:** https://j5port-qa.duckdns.org (agreed target, not yet a calculator).
- **New launch or adopted deployment, and reason:** New launch intended; neither launch nor adoption performed.
- **Own issue / feature branch:** Issue draft reviewed by the learner; connector creation refused with HTTP 403. Feature branch: `studio-001-calculator`.
- **Agreed scope or actual access/configuration gap:** Learner agreed to use QA for the supplied image and preserve https://j5port.duckdns.org, existing Docker/Traefik, and unrelated services. Read-only public checks found both hostnames already serving the portfolio. No route may be replaced without resolving this conflict explicitly. Root SSH rejected the available local key; DigitalOcean console access remains unresolved. No proxy network has been verified.

The learner authorized powering on the existing droplet after it was found offline.
DigitalOcean subsequently displayed Active. No container, route, proxy, DNS,
certificate, or operating-system change has been made by this work.

Private SSH targets and configuration stay in ignored local state. Share only
reviewed, selected evidence; never commit credentials or raw server output.

## Evidence to keep

| Evidence | Actual result / link |
|---|---|
| Prepared Black/Pylint/pytest and real-image browser checks | [Full Linux CI passed all three jobs](https://github.com/jakai211/Studio-1-Calculator/actions/runs/42340726893) at template commit `27e8dedefa99866d8dd6d825d0e929a373bf82ef`. Windows fast check: Black passed; Pylint and pytest failed on Linux-only APIs. Focused follow-up: 62 passed, 3 failed on Windows platform limitations. Local Docker E2E not run. |
| Hosted image/commit, trusted HTTPS, valid and rejected API cases | Not verified; export selected evidence with `report` |
| Preservation of unrelated services | Both public roots returned HTTP 200 with trusted HTTPS after power-on and identical portfolio content. Baseline SHA-256: `d37c42fdd2eb8e147caeadc68c936c782dc844e2337b794444032ce3bb69fed6`. Container-level preservation is not yet verified. |
| Own prediction, check interpretation, browser observation and keep/revise reason | [LEARNING.md](LEARNING.md), Pending; disclose assistance |
| Accuracy review before publishing learner excerpts | Pending |
| Actual PR, latest CI, merge and issue closure | Pending |

[Current sanitized inspection evidence](studio/evidence.json) records incomplete
work, not a successful CLI deployment report. Replace it with the prepared
`report` export only after real runtime verification. The deadline passed before
deployment; no completion timestamp is backdated.

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
