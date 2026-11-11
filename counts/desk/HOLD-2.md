MET

# HOLD-2, desk sender log, pre-run 5

> Counts only. The desk's sender log. It is not a chain count. Mini counts the chain.

Payment offer 2,027 tx/s at 150 sompi/gram, from 2 payment senders, one per kept public node. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder.

## Hop rate per cohort, as built

Floor (families 1–13): 100 sompi/gram per hop. Double (families 14–16): 200 sompi/gram per hop. The rate rides on each hop line to the one builder.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 32 (1,723), 31 (1,688), 33 (1,580), 30 (1,352), 34 (1,292), 35 (960), 29 (700), 36 (654), 37 (468), 28 (375), 38 (229), 27 (214), and 67 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Family stalls logged | Clean |
|---|---:|---:|---:|---:|---:|---|---|---:|---|
| 2026-11-11T18:32 | 117,410 | 117,410 | 0 | 0 | 0 | 21 / 925 / 0 / 0 / 13 | 13 / 217 / 0 / 0 / 3 | 2 | yes |
| 2026-11-11T18:33 | 117,410 | 117,410 | 0 | 0 | 0 | 10 / 924 / 0 / 0 / 13 | 16 / 216 / 0 / 0 / 3 | 6 | yes |
| 2026-11-11T18:34 | 116,433 | 116,433 | 0 | 0 | 0 | 8 / 917 / 0 / 0 / 13 | 15 / 217 / 0 / 0 / 3 | 7 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

Within 10 percent means 109,458 to 133,782 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender is on node 1. Both cohorts share that node.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). One payment sender per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 620859001 | 171,952 | 0 | 0 | 254 |
| 5 | yes | 620859000 | 179,301 | 0 | 0 | 44 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 29 of 39 | 37181 | 128263 |
| double | 44 of 44 | 6306 | 39048 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end.
