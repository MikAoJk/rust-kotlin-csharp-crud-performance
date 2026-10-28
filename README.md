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
https://github.com/MikAoJk/csharp-crud-rest-api/tree/main/performance-test
https://github.com/MikAoJk/rust-crud-rest-api/tree/main/performance-test
https://github.com/MikAoJk/kotlin-ktor-crud-rest-api/tree/main/performance-test

The runs have been done locally on my machine.
[RUNS](RUNS.md)

### Workload

Each application ran the same k6 workload for seven minutes, ramping up to
200 virtual users before ramping down. Each completed iteration made seven
requests: create, list, read, update, read updated, delete, and read deleted.
The final request expected a 404 response, which counted as a successful check,
not an HTTP failure.

### Results

Throughput is the average across the whole test, including ramp-up and ramp-down.
Higher throughput is better; lower latency is better. Request latency refers to
k6's `http_req_duration`; iteration duration covers the full seven-request cycle.

| Metric                     |               C# |           Kotlin |             Rust |
|----------------------------|-----------------:|-----------------:|-----------------:|
| HTTP requests              |           96,803 |          318,451 |          431,417 |
| HTTP requests/s            |           230.36 |           758.13 |     **1,027.18** |
| Completed CRUD iterations  |           13,829 |           45,493 |           61,631 |
| CRUD iterations/s          |            32.91 |           108.30 |       **146.74** |
| Average request latency    |        538.77 ms |        162.96 ms |    **120.01 ms** |
| Median request latency     |        301.28 ms |        188.97 ms |    **100.64 ms** |
| p90 request latency        |           1.69 s |        289.79 ms |    **194.12 ms** |
| p95 request latency        |           2.29 s |        296.98 ms |    **196.63 ms** |
| Maximum request latency    |           7.90 s |       **1.29 s** |          15.68 s |
| Average iteration duration |           3.77 s |           1.14 s |    **842.69 ms** |
| p95 iteration duration     |           7.50 s |       **1.69 s** |           2.01 s |
| Successful checks          |   193,606 (100%) |   636,902 (100%) |   862,834 (100%) |
| Failed HTTP requests       |                0 |                0 |                0 |

### Takeaways

- **Rust had the highest throughput:** 4.46 times C#'s requests/s and
  35.5% more than Kotlin's, with the lowest average, median, p90, and p95
  request latency, plus the lowest average iteration duration.
- **Kotlin had the lowest maximum request latency and p95 iteration duration:**
  1.29 s and 1.69 s, respectively, compared with Rust's 15.68 s and 2.01 s.
  Kotlin also handled 3.29 times C#'s requests/s, with lower latency across
  every request and iteration metric in the table.
- **Rust had the largest latency spikes:** its maximum request latency was
  15.68 s, compared with 7.90 s for C# and 1.29 s for Kotlin, despite having
  the lowest p95 request latency.
- **All three passed every check with zero HTTP failures.** These results
  describe the recorded local runs, not a general ranking of the languages.
