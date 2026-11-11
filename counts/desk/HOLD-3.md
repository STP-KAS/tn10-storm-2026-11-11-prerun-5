NOT MET

# HOLD-3, desk sender log, pre-run 5

> Counts only. The desk's sender log. It is not a chain count. Mini counts the chain.

Payment offer 3,040 tx/s at 150 sompi/gram, from 2 payment senders, one per kept public node. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder.

## Hop rate per cohort, as built

Floor (families 1–13): 100 sompi/gram per hop. Double (families 14–16): 200 sompi/gram per hop. The rate rides on each hop line to the one builder.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 31 (1,686), 32 (1,606), 30 (1,519), 33 (1,392), 29 (1,040), 34 (1,030), 35 (773), 28 (572), 36 (548), 27 (343), 37 (340), 26 (285), and 68 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Family stalls logged | Clean |
|---|---:|---:|---:|---:|---:|---|---|---:|---|
| 2026-11-11T18:36 | 118,000 | 118,000 | 0 | 0 | 0 | 9 / 923 / 0 / 0 / 13 | 13 / 215 / 0 / 0 / 3 | 5 | no: ok-off |
| 2026-11-11T18:37 | 118,000 | 118,000 | 0 | 0 | 0 | 6 / 924 / 0 / 0 / 13 | 8 / 216 / 0 / 0 / 3 | 7 | no: ok-off |
| 2026-11-11T18:38 | 115,023 | 117,023 | 0 | 0 | 2000 | 11 / 922 / 0 / 0 / 13 | 14 / 216 / 0 / 0 / 3 | 1 | no: ok-off;node-5-unread |
| 2026-11-11T18:39 | 118,000 | 118,000 | 0 | 0 | 0 | 3 / 920 / 0 / 0 / 13 | 15 / 218 / 0 / 0 / 3 | 4 | no: ok-off |
| 2026-11-11T18:40 | 118,000 | 118,000 | 0 | 0 | 0 | 4 / 920 / 0 / 0 / 13 | 17 / 218 / 0 / 0 / 3 | 3 | no: ok-off |
| 2026-11-11T18:41 | 118,046 | 118,046 | 0 | 0 | 0 | 10 / 917 / 0 / 0 / 13 | 15 / 218 / 0 / 0 / 3 | 2 | no: ok-off |
| 2026-11-11T18:43 | 449 | 507 | 0 | 0 | 58 | 967 / 1208 / 0 / 0 / 13 | 232 / 279 / 0 / 0 / 3 | 0 | no: ok-off;pay_stop;pay_exit;proc_exit |
| 2026-11-11T18:44 | 413 | 413 | 0 | 0 | 0 | 972 / 1180 / 0 / 0 / 13 | 230 / 276 / 0 / 0 / 3 | 0 | no: ok-off;proc-row-missing |
| 2026-11-11T18:45 | 413 | 413 | 0 | 0 | 0 | 976 / 1180 / 0 / 0 / 5 | 238 / 275 / 0 / 0 / 2 | 0 | no: ok-off;proc-row-missing |
| 2026-11-11T18:46 | 413 | 413 | 0 | 0 | 0 | 989 / 1224 / 0 / 0 / 13 | 242 / 287 / 0 / 0 / 3 | 0 | no: ok-off;proc-row-missing |
| 2026-11-11T18:47 | 413 | 413 | 0 | 0 | 0 | 966 / 1210 / 0 / 0 / 12 | 240 / 283 / 0 / 0 / 3 | 0 | no: ok-off;proc-row-missing |
| 2026-11-11T18:48 | 413 | 413 | 0 | 0 | 0 | 896 / 1235 / 0 / 0 / 13 | 222 / 297 / 0 / 0 / 3 | 0 | no: ok-off;proc-row-missing |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

Within 10 percent means 164,160 to 200,640 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender is on node 1. Both cohorts share that node.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). One payment sender per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 620867038 | 342,963 | 1035 | 0 | 60 |
| 5 | no | 620867038 | 364,620 | 1023 | 0 | 41 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 6157 of 6157 | 609 | 1154 |
| double | 1581 of 1581 | 587 | 2226 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end.
