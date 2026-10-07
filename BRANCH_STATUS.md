# Branch status: `perf/moe-cross-layer-prefetch`

**Verdict: NO-GO — do not merge to `main`.**

This branch is an opt-in L→L+1 expert prefetch experiment (default off).
On Qwen3.8-Flash-Next (qwen4_exp hyper-connections), the cross-layer
linker path did not deliver a tok/s win: when links are live, OFF ≥ ON
on matched MBP benches. Unguarded earlier PRs were already NO-GO.

**Product tip for Apple Silicon paging remains stock oMLX `main`
(and the measured KEEP work documented in https://github.com/yavarb/moefit):**

- Exact routing-replay sidecar on *repeated* prompts (moefit T2 KEEP)
- Default IO worker pool / staged IO (already on in oMLX 0.7.0)
- Contiguous coalescer SSD useful-BW only (not a merge claim here)

Do not treat this branch as the fastest or shipping tip. Kept for
history / future linker work only.
