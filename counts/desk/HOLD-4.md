OBSERVATION

# HOLD-4, desk sender log, pre-run 5

> Counts only. The desk's sender log. It is not a chain count. Mini counts the chain.

The pinned minute is the first whole UTC minute whose start is at least 3 minutes after HOLD-3's On origin time. The rate in that minute is the reading.

Payment offer 4,053 tx/s at 150 sompi/gram, from 2 payment senders, one per kept public node. Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder.

## Hop rate per cohort, as built

Floor (families 1–13): 100 sompi/gram per hop. Double (families 14–16): 200 sompi/gram per hop. The rate rides on each hop line to the one builder.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 31 (1,616), 30 (1,583), 32 (1,501), 29 (1,274), 33 (1,258), 34 (896), 28 (707), 35 (633), 27 (501), 36 (449), 26 (357), 37 (262), and 68 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | Double OK / att / rate rej / full rej / waiting | Family stalls logged | Clean |
|---|---:|---:|---:|---:|---:|---|---|---:|---|
| 2026-11-11T18:53 | 413 | 413 | 0 | 0 | 0 | 945 / 1195 / 0 / 0 / 12 | 231 / 274 / 0 / 0 / 3 | 0 | no: ok-off |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

Within 10 percent means 218,862 to 267,498 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender is on node 1. Both cohorts share that node.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). One payment sender per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 620870208 | 177 | 0 | 0 | 56 |
| 5 | yes | 620870208 | 236 | 0 | 0 | 38 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 945 of 945 | 648 | 1035 |
| double | 231 of 231 | 608 | 933 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end.
