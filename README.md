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
| HTTP requests              |           96,803 |          283,017 |          229,607 |
| HTTP requests/s            |           230.36 |       **673.85** |           546.68 |
| Completed CRUD iterations  |           13,829 |           40,431 |           32,801 |
| CRUD iterations/s          |            32.91 |        **96.26** |            78.10 |
| Average request latency    |        538.77 ms |    **183.40 ms** |        225.45 ms |
| Median request latency     |        301.28 ms |    **195.94 ms** |        198.78 ms |
| p90 request latency        |           1.69 s |    **295.84 ms** |        299.84 ms |
| p95 request latency        |           2.29 s |    **300.52 ms** |        321.24 ms |
| Maximum request latency    |           7.90 s |       **1.49 s** |          13.99 s |
| Average iteration duration |           3.77 s |       **1.28 s** |           1.58 s |
| p95 iteration duration     |           7.50 s |       **1.79 s** |           3.79 s |
| Successful checks          |   193,606 (100%) |   566,034 (100%) |   459,214 (100%) |
| Failed HTTP requests       |                0 |                0 |                0 |

### Takeaways

- **Kotlin had the highest throughput:** 2.93 times C#'s requests/s and
  1.23 times Rust's, with the lowest average, median, p90, p95, and maximum
  request latency, plus the lowest average and p95 iteration duration.
- **Rust outperformed C# on throughput and typical request latency:** it handled
  137.3% more requests/s, with lower average, median, p90, and p95 request
  latency and lower average and p95 iteration durations.
- **Rust had the largest latency spikes:** its maximum request latency was
  13.99 s, compared with 7.90 s for C# and 1.49 s for Kotlin, despite its
  lower p95 request latency and iteration duration than C#.
- **All three passed every check with zero HTTP failures.** These results
  describe the recorded local runs, not a general ranking of the languages.
