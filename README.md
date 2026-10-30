# rust-kotlin-csharp-crud-performance
A repo that sums up the performance result of 3 CRUD applications

## Applications
#### C#
https://github.com/MikAoJk/csharp-crud-rest-api

#### Kotlin
https://github.com/MikAoJk/kotlin-ktor-crud-rest-api

#### Rust
https://github.com/MikAoJk/rust-crud-rest-api



### Performance runs
All the application above have been run with the same performance-test suit, see:
- C# https://github.com/MikAoJk/csharp-crud-rest-api/tree/main/performance-test
- Kotlin https://github.com/MikAoJk/rust-crud-rest-api/tree/main/performance-test
- Rust https://github.com/MikAoJk/kotlin-ktor-crud-rest-api/tree/main/performance-test

The runs have been done locally on my machine.
[RUNS](RUNS.md)

### Workload

Each application ran the same k6 workload for seven minutes, ramping up to
1,000 CRUD virtual users before ramping down, with an additional virtual user
collecting process CPU and memory metrics (1,001 virtual users in total).
Each completed CRUD iteration made seven
requests: create, list, read, update, read updated, delete, and read deleted.
The final request expected a 404 response, which counted as a successful check,
not an HTTP failure.

### Results

Throughput is the average across the whole test, including ramp-up and ramp-down.
Higher throughput is better; lower latency is better. Request latency refers to
k6's `http_req_duration`. HTTP and execution metrics are the aggregate values
reported by k6, including monitoring requests and iterations, so completed
iterations are not exclusively CRUD cycles. CPU and resident memory (RSS)
figures are sampled process metrics.

| Metric                     |               C# |           Kotlin |             Rust |
|----------------------------|-----------------:|-----------------:|-----------------:|
| HTTP requests              |          191,403 |          168,844 |          391,507 |
| HTTP requests/s            |           454.95 |           401.57 |       **930.90** |
| Completed iterations       |           27,573 |           24,346 |           56,203 |
| Iterations/s               |            65.54 |            57.90 |       **133.64** |
| Average request latency    |        978.90 ms |           1.10 s |    **474.70 ms** |
| Median request latency     |        407.71 ms |        995.72 ms |    **102.33 ms** |
| p90 request latency        |           2.38 s |           2.20 s |       **1.39 s** |
| p95 request latency        |           2.79 s |           2.49 s |       **1.40 s** |
| Maximum request latency    |           5.50 s |           5.01 s |       **1.97 s** |
| Average iteration duration |           6.80 s |           7.70 s |       **3.31 s** |
| p95 iteration duration     |          15.50 s |          16.09 s |       **9.68 s** |
| Average process CPU usage  |       **19.38%** |           19.83% |           19.49% |
| Average process RSS        |       166.72 MiB |       201.56 MiB |    **23.42 MiB** |
| Maximum process RSS        |       355.40 MiB |       292.98 MiB |    **42.24 MiB** |
| Successful checks          |   383,073 (100%) |   337,950 (100%) |   783,332 (100%) |
| Failed HTTP requests       |                0 |                0 |                0 |

### Takeaways

- **Rust had the highest throughput:** 104.6% more requests/s than C# and
  131.8% more than Kotlin, with the lowest average, median, p90, p95, and
  maximum request latency, plus the lowest average and p95 iteration duration.
- **C# ranked second on throughput:** it handled 13.3% more requests/s than
  Kotlin, with lower average and median request latency and a lower average
  iteration duration. Its p95 iteration duration was also lower
  (15.50 s versus Kotlin's 16.09 s).
- **Kotlin had lower request tail latency than C#, but the lowest throughput:**
  its p90 and p95 request latency were lower, and its maximum request latency
  was 5.01 s versus C#'s 5.50 s. Rust led all of these latency metrics.
- **Rust had the smallest memory footprint:** average process RSS was
  23.42 MiB, compared with 166.72 MiB for C# and 201.56 MiB for Kotlin.
  C# had lower average RSS than Kotlin, but higher maximum RSS
  (355.40 MiB versus 292.98 MiB).
  Average reported process CPU usage was similar across all three
  (19.38% to 19.83%).
- **All three passed every check with zero HTTP failures.** These results
  describe the recorded local runs, not a general ranking of the languages.
