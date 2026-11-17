# Vendored anti-slop provenance

- Source: https://github.com/K-Mistele/anti-slop at `b7c1619b4d51b4815e89ba3700a975a6ec54b8c3`; README, install skill, and update procedure reviewed.
- Fresh installation in `edmundmiller/boomerang-notify` from base `8a9118188988dd3f35cdfe9700b926eb5094c567`. No previous rule fork or local customization existed. No source files changed.
- `tools/oxlint/anti-slop/` is byte-identical to that revision's `skills/install-anti-slop/assets/anti-slop/`, plus this record and the upstream root MIT `LICENSE`. Preserve `vendor/eslint-stylistic/LICENSE` and `UPSTREAM.md`.
- `tools/oxlint/oxlint-plugin-jev/` is the unmodified built asset from the same snapshot, identifying fork commit `fd3e4b1ad3b8fa7c0d08cdc92633e33c7e662f9e`. Its MIT license, README, build provenance, and package manifest are retained. Installed as a local development-only file dependency.
- Exact upstream-tested pair: `oxlint` / `@oxlint/plugins` `1.86.0`. Registry latest was 1.94.0 on inspection; the tested pair was selected deliberately. Existing dependency ranges and the product runtime remain unchanged. New npm lockfile records tooling and resolves the existing OpenCode peer.
- Activation: 20 of 22 Core/native checks as errors, seven Fowler AST checks as warnings. Jev is registered only in its explicit overlay; diff review uses the standalone runner. No Effect direct dependency, so no Effect activation or tsgo patch.

## Strict proposal, pending decision

`lint:strict` enables all 22 Core/native rules as errors. It reports **5 errors** on unchanged product source: `require-readable-spacing` 2; `require-safety-comment-for-type-assertion` 3. These two rules are staged here rather than activated in normal/editor lint. No permanent disable or source exemption was added. Decide whether to authorize a scoped source migration before activation.

## Verification / delivery

Fresh remote ownership check found no open PRs, only main, and no active lint owner. Normal lint did not previously exist. New offline lint passes with zero diagnostics; a standalone TypeScript `--noEmit --skipLibCheck --target ES2022 --module NodeNext --moduleResolution NodeNext index.ts` probe passes with the existing peer resolved (there is no project typecheck). Product source is unchanged. Network-denied fake-key ordinary/changed-file checks and in-process mock scope checks pass. See root `ANTI_SLOP.md` for exact disclosure and limits. Rollout evidence and recovery snapshots are retained in the execution thread, not application source.

Edmund authorized shipping this tooling-only adoption. Validation used no product integration calls, live/paid models, credentials, service execution, or CI changes. Strict source migration and full strict acceptance remain separate decisions. Existing base is the recovery point; revert only this focused tooling commit. Accountable owner: https://ampcode.com/threads/T-01a1e6aa-5f11-73a3-b161-b97848780e6b .
