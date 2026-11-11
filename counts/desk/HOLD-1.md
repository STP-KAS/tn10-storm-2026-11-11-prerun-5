MET

# HOLD-1, desk sender log, pre-run 5

> Counts only. The desk's sender log. It is not a chain count. Mini counts the chain.

Payment offer 1,013 tx/s at 150 sompi/gram, from 2 payment senders, one per kept public node. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder.

## Hop rate per cohort, as built

Floor (families 1–13): 100 sompi/gram per hop. Double (families 14–16): 200 sompi/gram per hop. The rate rides on each hop line to the one builder.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 32 (1,732), 31 (1,682), 33 (1,580), 30 (1,348), 34 (1,301), 35 (963), 29 (681), 36 (661), 37 (471), 28 (372), 38 (229), 27 (217), and 67 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Family stalls logged | Clean |
|---|---:|---:|---:|---:|---:|---|---|---:|---|
| 2026-11-11T18:27 | 59,767 | 59,767 | 0 | 0 | 0 | 356 / 1039 / 0 / 0 / 13 | 107 / 244 / 0 / 0 / 3 | 0 | yes |
| 2026-11-11T18:28 | 59,767 | 59,767 | 0 | 0 | 0 | 374 / 1042 / 0 / 0 / 12 | 113 / 246 / 0 / 0 / 3 | 0 | yes |
| 2026-11-11T18:29 | 59,767 | 59,767 | 0 | 0 | 0 | 475 / 1126 / 0 / 0 / 13 | 128 / 250 / 0 / 0 / 3 | 0 | no: node-1-unread |
| 2026-11-11T18:30 | 59,767 | 59,767 | 0 | 0 | 0 | 542 / 1121 / 0 / 0 / 13 | 136 / 269 / 0 / 0 / 3 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

Within 10 percent means 54,702 to 66,858 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender is on node 1. Both cohorts share that node.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). One payment sender per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | no | 620856912 | 119,652 | 0 | 0 | 40 |
| 5 | yes | 620856907 | 119,416 | 0 | 0 | 42 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 1747 of 1747 | 1306 | 3197 |
| double | 484 of 484 | 1117 | 2472 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end.
