> **Experimental. We are just trying this.** [Disclaimer](../../DISCLAIMER.md) · Kaspa Testnet-10 only. No key, id, address, host, or port in these files.

# Desk runner, pre-run 5

- `preflight.mjs`: read-only. Desk node synced, UTXO index, DAA moving; family lane against the abort line; payment pile count; every bundle funding coin live; each public node checked (version, synced, DAA gap, UTXO index, answer time, node id). Two hostnames that answer with one node id are one kaspad: the lowest local number is kept, the other is dropped as same-kaspad. A node whose id cannot be read is dropped. Writes the kept list to the private run folder (the id only as a short private hash). Prints counts only.
- `desk-runner.mjs --mode open`: gates, then `logs/PRE-RUN-OPEN.md` once. Not a send.
- `desk-runner.mjs --mode run`: gates (`PRE-RUN-OPEN` and `MINI-ARMED` on origin), the sixteen genesis transactions from the published bundle (`tools/sixteen/submit-sixteen.mjs`), the families on kit16 and the patched builder (100/200 per hop), then the payment offers, the HOLD-4 minute, RETURN, and `logs/METHOD.md`. A missing gate is `HELD` and an exit, never a wait.
- `pay2.mjs`: one payment sender per kept kaspad, fee 150, the offer split evenly, change re-used at once.

The runner starts its children detached (WMI), outside its own process tree, so they survive the parent. It is never restarted mid-run. A family STALL is logged per minute and is not dirt.

## Pre-run 4 lessons in this runner

- **Repair restarts the senders.** The one payment-sender repair stops the senders, waits until each stopped process is gone, takes them off its list itself, starts the missing ones, and waits for each one's `PAY_START`. It logs `REPAIR_RESTART` with how many are running again. A sender named in the list but no longer alive is started again; the list alone never counts as running.
- **Git errors do not hide a dead run.** Every git call has a time limit. A fetch is tried three times. A HOLD file, `METHOD.md`, or `FAILED.md` push is retried several times, some seconds apart. A count file is also written to the run folder before its push. If the run fails, `logs/FAILED.local.md` is written in the run folder first, then pushed with retries. If origin still refuses, the runner says so and leaves a marker for the operator, who publishes that file.
- **Unique kaspads.** The kept list comes from the preflight above. The count file says how many passing hostnames were how many kaspads. If a kept node later answers with another node id, that is logged once as data. It is not dirt.
