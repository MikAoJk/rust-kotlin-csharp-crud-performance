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
500 CRUD virtual users before ramping down, with an additional virtual user
collecting process CPU and memory metrics (501 virtual users in total).
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
| HTTP requests              |          334,856 |          300,382 |          409,099 |
| HTTP requests/s            |           796.89 |           714.61 |       **972.71** |
| Completed iterations       |           48,122 |           43,204 |           58,783 |
| Iterations/s               |           114.52 |           102.78 |       **139.77** |
| Average request latency    |        304.60 ms |        339.30 ms |    **248.49 ms** |
| Median request latency     |        119.49 ms |        295.28 ms |    **102.06 ms** |
| p90 request latency        |        691.72 ms |        687.85 ms |    **600.64 ms** |
| p95 request latency        |        787.67 ms |        710.73 ms |    **618.47 ms** |
| Maximum request latency    |           2.78 s |           1.99 s |    **993.13 ms** |
| Average iteration duration |           2.12 s |           2.36 s |       **1.73 s** |
| p95 iteration duration     |           5.19 s |           4.79 s |       **4.29 s** |
| Average process CPU usage  |           19.31% |           19.86% |       **19.18%** |
| Average process RSS        |       140.34 MiB |       213.77 MiB |    **14.27 MiB** |
| Maximum process RSS        |       158.77 MiB |       280.37 MiB |    **19.62 MiB** |
| Successful checks          |   670,044 (100%) |   601,104 (100%) |   818,594 (100%) |
| Failed HTTP requests       |                0 |                0 |                0 |

### Takeaways

- **Rust had the highest throughput:** 22.1% more requests/s than C# and
  36.1% more than Kotlin, with the lowest average, median, p90, p95, and
  maximum request latency, plus the lowest average and p95 iteration duration.
- **C# ranked second on throughput:** it handled 11.5% more requests/s than
  Kotlin, with lower average and median request latency and a lower average
  iteration duration.
- **Kotlin had lower tail latency than C#, but the lowest throughput:**
  its p90 and p95 request latency were lower, its maximum request latency
  was 1.99 s versus C#'s 2.78 s, and its p95 iteration duration was 4.79 s
  versus C#'s 5.19 s. Rust led all of these latency metrics.
- **Rust had the smallest memory footprint:** average process RSS was
  14.27 MiB, compared with 140.34 MiB for C# and 213.77 MiB for Kotlin.
  Average reported process CPU usage was similar across all three
  (19.18% to 19.86%).
- **All three passed every check with zero HTTP failures.** These results
  describe the recorded local runs, not a general ranking of the languages.
