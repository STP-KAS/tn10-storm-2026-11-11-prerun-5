> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is the playbook for pre-run 5.** It is not Wednesday. It is not Tuesday. It is not pre-run 1, 2, 3, or 4. It does not start a machine and it does not arm one. A read of this page is not a paste.

# Playbook

This page states who does what, and the gates before each machine may start, so Mini, the desk (Build), and the bot do not guess. The plan is [plan/PLAN.md](plan/PLAN.md), the locks are [locks/LOCKED.md](locks/LOCKED.md), and the pastes are the three go files. This page does not override them.

Pre-run 1 is [tn10-storm-2026-11-11-prerun](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun). Pre-run 2 is [tn10-storm-2026-11-11-prerun-2](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-2). Pre-run 3 is [tn10-storm-2026-11-11-prerun-3](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-3). Pre-run 4 is [tn10-storm-2026-11-11-prerun-4](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-4). All four failed and are closed. Their files are history. None of them is a live gate here.

## Oversight

TN10 ops oversees this rehearsal end to end: Mini, the desk (Build), and the bot. TN10 only. Never mainnet. Keep disk safe. Do not edit the Tuesday repo, the Wednesday repo, or pre-run 1's, 2's, 3's, or 4's go files. Do not write `REVIEW_CLOSED`.

For pre-run 5 the operator does not paste. On 2026-11-11 he said to start everything, with no pastes, and to execute until successful. That instruction is the arm. The agents on the desk, Mini, and the bot start their own runners once the gates are facts. A sentence in chat still does not write `PRE-RUN-OPEN`: the desk runner writes it after its gates. Oversight does not arm a machine by itself.

What oversight checks:

- Nodes: the existing TN10 process is the one that is up on Mini and on the desk, data is not wiped, each node is synced with DAA moving before we count or send. The desk node is started with PowerShell 7, never Windows PowerShell 5.1. `KaspaPublicNode` is not started. The desk devnet is left alone.
- Hashes: `hashes/SIXTEEN.md` with sixteen family rows and an On origin line, before the first family submit. Not the old 8- or 32-family publisher. No On origin line, no send. The covenant id stays off the repo.
- Senders: one family-sender on the desk, payments only as the plan allows, the bot only in the HOLD-4 minute on a leftover synced public node, or a legal `NO SEND`. No second runner. No waiter left over from a dead run.
- Files: desk, Mini, and bot each write only their own folder in this repo. HOLD-4 is the pinned minute after desk HOLD-3 is on origin.
- Disk and abort: do not start if the lane would fall under 2,500 coins or 18,000 usable tKAS. Do not print balances or secrets.

## Start gates

There is no clock. Each gate is a fact read from a node or from origin, in this order.

1. **Mini node synced.** Existing TN10 kaspad, existing data, no wipe. `isSynced` true, DAA moving. Mini notifies Build and TN10 ops.
2. **Desk node synced.** Existing private TN10 kaspad, existing data, loopback only, started with `pwsh`. No wipe. Synced, DAA moving.
3. **No other runner.** No Tuesday, Wednesday, pre-run 1, 2, 3, or 4 runner or waiter on any machine. Lane above the abort line.
4. **Hashes.** The desk pushes `hashes/SIXTEEN.md` with [tools/sixteen](tools/sixteen/README.md): sixteen rows and an On origin line. It is not an arm and not a send, and it does not wait for the paste.
5. **Arm.** The operator's instruction to start everything. No paste. The agents start the runners.
6. **Open.** The desk pushes `logs/PRE-RUN-OPEN.md` here. Mini then pushes `logs/MINI-ARMED.md` here.
7. **Families, then senders.** The genesis transactions come from the bundle that wrote `hashes/SIXTEEN.md`. Nothing rebuilds it. Families start. Then 1,013, 2,027, 3,040, the HOLD-4 minute, and RETURN.

## Who does what

| Who | Role | When to start | What not to do |
|---|---|---|---|
| **Desk (Build)** | Sends the sixteen families and the payment offers. Does not count the chain. Publishes `hashes/SIXTEEN.md` first, then `logs/PRE-RUN-OPEN.md`, then `counts/desk/` as each step closes. | After gates 1–4. First sentence: `DESK. I send on pre-run 5. I do not count. This is not Wednesday.` No family submit before `hashes/SIXTEEN.md` has an On origin line and `MINI-ARMED` is on origin. | Do not start from a chat sentence. Do not count. Do not stop or wipe the desk TN10 node. Do not use Windows PowerShell 5.1 or start `KaspaPublicNode`. Do not touch the desk devnet. Do not use the 8- or 32-family publisher. Do not drop a HOLD-3 node to free one for the bot. Do not start a second runner. |
| **Mini** | The only chain counter. Does not send, mine, or hold a key. Publishes `logs/MINI-ARMED.md` after `PRE-RUN-OPEN` is on origin here, then `counts/mini/` when the matching desk file is on origin. | Node synced and Build notified first. Arms only after the operator pastes [GO-MINI.md](GO-MINI.md) and this repo's `PRE-RUN-OPEN` is on origin. First sentence: `MINI. I count pre-run 5. I do not send. This is not Wednesday.` | Do not send. Do not wipe chain data. Do not resume pre-run 1 or start its runner tasks or Tuesday's. Do not count before the gate file. |
| **Bot (TN10 ops)** | Sends payments in the HOLD-4 minute only, on one leftover synced public node outside the desk HOLD-3 set, or publishes a legal `NO SEND`. Publishes `counts/bot/HOLD-4.md`. Does not count the chain. No local node. | After the operator pastes [GO-BOT.md](GO-BOT.md). Sends only after `PRE-RUN-OPEN`, `hashes/SIXTEEN.md`, and desk `counts/desk/HOLD-3.md` are on origin here, in the pinned HOLD-4 minute. First sentence: `GROKBOT. I send payments on the pre-run 5 HOLD-4 only. I do not count. This is not Wednesday.` Stops on this repo's `logs/BOT-HALT.md` or `logs/FAILED.md`. | Do not send on HOLD-1, HOLD-2, HOLD-3, or RETURN. Do not start a second waiter. Do not treat chat or a pre-run 1, 2, 3, or 4 file as the start. |

## Status when this repo was opened

Not a gate. A status line, so nobody guesses.

- Mini: existing TN10 kaspad 2.1.0 up since 2026-11-11T07:31:03Z, no wipe, synced, DAA moving.
- Desk: existing private TN10 kaspad 2.1.0 up since 2026-11-11T07:44:58Z with `pwsh`, no wipe, synced, DAA moving.
- Box: no local TN10 node. No bot waiter running.
- Hashes: `hashes/SIXTEEN.md` is absent. Pre-run 4's genesis coins are spent. Keys 1–15 were given one fresh genesis coin each from the family lane (key 0); the lane stayed above the abort line. A local check build on those coins gave sixteen rows and pushed nothing; the published file is a fresh build at publish time.
- Runner: passed a no-undef lint and the offline rehearsal on the desk (faked submit and payment logs, a local origin, no live send), through HOLD-1 scoring and a count-file render. Rehearsal readings:
  - Five candidate hostnames: two did not answer, two answered with one node id. Kept nodes 1 and 5; node 4 was dropped as the same kaspad as node 1. Two payment senders, one per kaspad.
  - HOLD-1 met: one minute dirty for a sender-off mark (not a stall), then three clean minutes with family stalls logged in each. The count file rendered.
  - HOLD-2 met at 117,410 a minute, three clean minutes.
  - HOLD-3 not met at about 118,000 a minute. The one repair stopped both payment senders, waited until they were gone, started both again, and both logged their start (`REPAIR_RESTART started=2 running=2/2`). The minutes after the repair kept sending about 118,000. `FIXES.md` recorded it.
  - HOLD-4 observation and RETURN met, then `METHOD.md`.
  - Git failure: with the local origin moved away after the first HOLD-1 minute, the HOLD-1 push was retried and failed, `logs/FAILED.local.md` was written first, every child stopped, the FAILED push was retried and failed, and the runner logged that the operator must publish the local file. In a second check the local origin came back during the FAILED retries, and the third FAILED push landed on origin.
- Known risks, not fixed mid-run:
  - Two payment senders reached the same ceiling as three did in pre-run 4: about 118,000 submit-OK a minute. That ceiling tracks the 2,000-coin payment pile (each coin is re-used about once a second, about 59 sends a minute), not the sender count. HOLD-3's window is 164,160–200,640 a minute, so HOLD-3 is expected `NOT MET` at this pile. The pile is not enlarged for this pre-run.
  - Unique kaspads: in the last check the desk's candidates and the bot's extra endpoints answered as two kaspads. The bot is expected to write `NO SEND` and `no-free-node` unless another kaspad is free and synced in its pass.
  - A long git outage makes the runner's fetches slow and can delay a minute's node samples; a missed sample marks that minute dirty as unread.
  - After a sender restart, a restarted sender reloads its coins from the desk node and does not know which of them are already spent in the mempool; some first submits may be rejected as other.
- Arm: the operator's instruction to start everything. Nothing has sent from this repo.

## When something breaks

Append a worked fix to [locks/LOCKED.md](locks/LOCKED.md) in the form that page shows, and a repair line to `logs/FIXES.md`. If the run dies before RETURN, write `logs/FAILED.md`, stop every runner and waiter, and do not resume. The next attempt is a new repo that starts from this repo's lock file. Do not rewrite the go files in this repo to match the result.
