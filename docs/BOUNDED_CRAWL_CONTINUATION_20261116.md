# Bounded unread-page reporting and linked continuation

16 November 2026. Candidate for review; existing published engine remains PR38 and public website PR33. No paid API or client-site change.

## Resulting behavior

New website audits retain the actual bounded frontier: discovered URL, link provenance, branch/catalog role and reason it remained unread. The report distinguishes request-limit candidates from robots, infrastructure, product-boundary and already-seen exclusions. Discovery truncation remains explicit; an empty list is not proof of full coverage. Historical reports are not backfilled or rewritten.

An authenticated owner/editor can request one separately persisted continuation of a completed base audit. The request supplies only its parent run ID; URLs, budgets and provider settings are not accepted from the caller. The child authorizes at most 30 additional page attempts, with a base of at most 30 and chain ceiling 60. It cannot itself be continued, and its job executes only once; repeated submissions return the same child. Existing normal job retries remain unchanged. Robots, sitemap-policy requests and redirects retain existing transport bounds and are not represented as separate content pages.

The entity lock, tenant/RLS context, confirmed website/profile version, immutable parent hash, role, CSRF, idempotence and active-job guards apply before queueing. The worker revalidates the persisted contract and parent before fetching. A changed profile/report or legacy report without the new state requires a fresh base audit; caller-provided pending URLs cannot bypass SSRF, current robots, product boundaries or the hard ceiling.

The child records only newly read pages and explicitly references its unchanged parent/time/hash. Known visited/final URLs are not deliberately reselected. A redirect may resolve to a known final page under existing bounded transport; its duplicate body is not counted again. Cross-batch duplicate metadata may use old hashed page records, clearly labelled as not freshly refetched. Earlier findings remain available in the original history; the child is not a replacement all-clear for the whole business.

## UI and privacy

The existing Studio/legacy report surfaces show a native disclosure, filtering and a maximum of 20 mounted list rows per page. The server frontier is bounded to 500 candidates. Large 100/1,000-record response fixtures exercise frontend mounting/focus/overflow, not actual business audits or an increased backend limit. Empty state adds no unnecessary panel to compact owner plans. The same DE/EN/SQ copy and unread evidence appear in the private HTML export; JSON originals retain full bounded provenance.

Existing product surfaces, controls, fonts and tokens are preserved. The working footer reuses the established legal destinations, local Manrope asset and small accessible by RediON signature at the natural content end; it is not fixed/sticky. Legacy pale report cards retain their surface with readable existing dark ink. No new framework, provider, dependency, schema, public endpoint access policy or marketing redesign.

The external development case, its URLs/results/captures/screenshots and report stay PRIVATE_ONLY and outside public Git/showcase/portfolio/media index. Synthetic UI captures are explicitly labelled. No complete-coverage, ranking/indexing, engineering certification or first-check-finds-every-error claim is made.

## Verification and publication

Published baseline: PR38, app source `5e8dacbc77c057181eaea6b396a049ad41463b6e`, main merge `84981173e829ff68576d63a01144980ffae413a4`. Public website remains PR33. Candidate app source: `0f5416bfe2f83bc2d40c86dd6cbaa9bbf57af24c`. Documentation-only review commits do not change these runtime bytes.

| Check | Verified source and result |
| --- | --- |
| Unit/typecheck | 473 tests PASS on backend `00280d5`, full-suite UI `65862ec` and final app `0f5416b` |
| Isolated queue/worker/RLS integration | 59 PASS on `00280d513b0c38a56e7990bf13427175955951ec`; all backend/integration bytes identical in final app source |
| Full browser suite | 24 PASS on `65862ec`: desktop/tablet/mobile, including delayed-poll navigation regression |
| Final small navigation delta | PASS on final app `0f5416b`: six focused desktop/tablet/mobile navigation and real workflow cases, plus 473 unit/typecheck/build/security/source readback. The unchanged remainder of the full 24-case suite remains bound to `65862ec` |
| Real public-page component regressions | Six owner cases: 44 original page bodies/findings unchanged; intentional noindex preserved. Additional private external case retained outside public materials. No production enqueue or persisted native run |
| Private report rendering | 18 DE/EN/SQ desktop/mobile renders PASS; no overflow or external requests. Three phases remain separately identified |
| Security | Production dependency audit: zero vulnerabilities; paid API activation/calls zero |
| Preservation | 2,163 original artifacts SHA256 verified. Counts and original rows in 32 non-session tables unchanged; encrypted keys/config/finance unchanged. Fresh backup archive readback PASS; independent restore NOT_RUN |

One bounded Linux runner job is used on the authorized mini-PC, 4 CPU/4 GiB. The separately owned synthetic Postgres container has its own CPU/memory/tmpfs/PID limits and teardown trap. No client/live DB or real key is used in fixtures. Source-input manifests distinguish tracked code/config/fixtures/assets from historical generated `evidence/v07-*` outputs overwritten by E2E. Canonical Git LF bytes are verified directly; Windows archive CRLF conversion is not treated as tested source. The existing runner distribution remains separate from current skill-source loading.

Browser tests use synthetic large collections (20 mounted rows, zero image elements in the list, no horizontal overflow), short landscape and 200% CSS text sizing, keyboard focus, current OS light/dark preferences and existing Studio tokens. This is not a new theme switch or physical-device/native zoom/on-screen-keyboard acceptance. Those layers remain NOT_VERIFIED. Owned headless contexts/servers close after testing; no owner desktop capture is required.

Retained diagnostic history includes early type/formatter/CSS-import failures, a foreign-tenant fixture referring to an already deleted test tenant, Windows source-byte EOL mismatch, and harness preparation/source-manifest errors. An earlier 21-test suite crossed the existing 20-logins/IP limit; the production limiter was preserved and new visual-only sessions are now mocked. A later full run exposed a genuine legacy navigation race: background polling could reopen an old report while entering a new profile. Poll responses now respect navigation/cancellation, and navigation waits for an active save/audit action; a delayed-response browser regression preserves entered text. No failed attempt was relabelled as a pass.

Required browser/persistence checks, real-page component tests, Git source publication and native production rechecks are separate. This development case is not a blind independent benchmark. Unknown pages, JavaScript-only navigation, external profiles, semantic relevance, engineering/legal accuracy, actual indexing/ranking and provider answers are not certified by a bounded static crawl.

Publication requires exact owner approval, only for Studio/worker. After approval, verify fresh backup/runtime identity, deploy the exact reviewed candidate, then run a new normal base and its single linked continuation plus previous-client native regressions. Historical exports are immutable; legacy runs require a fresh base. No public website/client-site change, paid API or automatic further development follows from this candidate.

Native presentation, About, portfolio card and public media: NO_CONTENT_CHANGE while unpublished. The assisted Beta/readiness-70 description remains accurate. Companion documentation PRs record candidate status without private external-client identities, results, URLs or captures.
