NOT MET

# RETURN, desk sender log, pre-run 5

> Counts only. The desk's sender log. It is not a chain count. Mini counts the chain.

Payment offer 1,013 tx/s at 150 sompi/gram, from 2 payment senders, one per kept public node. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder.

## Hop rate per cohort, as built

Floor (families 1–13): 100 sompi/gram per hop. Double (families 14–16): 200 sompi/gram per hop. The rate rides on each hop line to the one builder.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 30 (1,578), 29 (1,418), 31 (1,389), 28 (1,220), 32 (1,096), 27 (864), 33 (819), 26 (629), 34 (625), 25 (458), 35 (414), 36 (279), and 68 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Family stalls logged | Clean |
|---|---:|---:|---:|---:|---:|---|---|---:|---|
| 2026-11-11T18:55 | 413 | 413 | 0 | 0 | 0 | 943 / 1216 / 0 / 0 / 12 | 229 / 282 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T18:56 | 413 | 413 | 0 | 0 | 0 | 1009 / 1217 / 0 / 0 / 13 | 242 / 276 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T18:57 | 413 | 413 | 0 | 0 | 0 | 955 / 1187 / 0 / 0 / 18 | 232 / 275 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T18:58 | 413 | 413 | 0 | 0 | 0 | 977 / 1164 / 0 / 0 / 13 | 236 / 269 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T18:59 | 413 | 413 | 0 | 0 | 0 | 914 / 1202 / 0 / 0 / 8 | 226 / 285 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T19:00 | 413 | 413 | 0 | 0 | 0 | 999 / 1220 / 0 / 0 / 6 | 243 / 284 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T19:02 | 29,913 | 29,913 | 0 | 0 | 0 | 828 / 1195 / 0 / 0 / 13 | 218 / 288 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T19:03 | 29,913 | 29,913 | 0 | 0 | 0 | 818 / 1161 / 0 / 0 / 13 | 212 / 276 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T19:04 | 29,913 | 29,913 | 0 | 0 | 0 | 799 / 1176 / 0 / 0 / 13 | 205 / 279 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T19:05 | 29,913 | 29,913 | 0 | 0 | 0 | 798 / 1177 / 0 / 0 / 12 | 207 / 276 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T19:06 | 29,913 | 29,913 | 0 | 0 | 0 | 783 / 1163 / 0 / 0 / 12 | 206 / 275 / 0 / 0 / 3 | 0 | no: ok-off |
| 2026-11-11T19:07 | 29,913 | 29,913 | 0 | 0 | 0 | 836 / 1209 / 0 / 0 / 7 | 213 / 279 / 0 / 0 / 0 | 0 | no: ok-off |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

Within 10 percent means 54,702 to 66,858 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender is on node 1. Both cohorts share that node.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). One payment sender per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 620878773 | 1,416 | 0 | 0 | 54 |
| 5 | yes | 620878773 | 180,540 | 0 | 0 | 40 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 11451 of 11451 | 661 | 1316 |
| double | 2883 of 2883 | 604 | 1163 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end.
