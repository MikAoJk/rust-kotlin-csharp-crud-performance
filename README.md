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
| HTTP requests              |           96,803 |          283,017 |          354,865 |
| HTTP requests/s            |           230.36 |           673.85 |       **844.92** |
| Completed CRUD iterations  |           13,829 |           40,431 |           50,695 |
| CRUD iterations/s          |            32.91 |            96.26 |       **120.70** |
| Average request latency    |        538.77 ms |        183.40 ms |    **145.79 ms** |
| Median request latency     |        301.28 ms |        195.94 ms |    **105.74 ms** |
| p90 request latency        |           1.69 s |        295.84 ms |    **199.94 ms** |
| p95 request latency        |           2.29 s |        300.52 ms |    **203.74 ms** |
| Maximum request latency    |           7.90 s |       **1.49 s** |          11.39 s |
| Average iteration duration |           3.77 s |           1.28 s |       **1.02 s** |
| p95 iteration duration     |           7.50 s |       **1.79 s** |           2.39 s |
| Successful checks          |   193,606 (100%) |   566,034 (100%) |   709,730 (100%) |
| Failed HTTP requests       |                0 |                0 |                0 |

### Takeaways

- **Rust had the highest throughput:** 3.67 times C#'s requests/s and
  25.4% more than Kotlin's, with the lowest average, median, p90, and p95
  request latency, plus the lowest average iteration duration.
- **Kotlin had the lowest maximum request latency and p95 iteration duration:**
  1.49 s and 1.79 s, respectively, compared with Rust's 11.39 s and 2.39 s.
  Kotlin also handled 2.93 times C#'s requests/s, with lower latency across
  every request and iteration metric in the table.
- **Rust had the largest latency spikes:** its maximum request latency was
  11.39 s, compared with 7.90 s for C# and 1.49 s for Kotlin, despite having
  the lowest p95 request latency.
- **All three passed every check with zero HTTP failures.** These results
  describe the recorded local runs, not a general ranking of the languages.
