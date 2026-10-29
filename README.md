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
200 CRUD virtual users before ramping down, with an additional virtual user
collecting process CPU and memory metrics (201 virtual users in total).
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
| HTTP requests              |          379,001 |          319,079 |          419,801 |
| HTTP requests/s            |           902.16 |           759.26 |       **998.99** |
| Completed iterations       |           54,461 |           45,905 |           60,287 |
| Iterations/s               |           129.64 |           109.23 |       **143.46** |
| Average request latency    |        137.02 ms |        162.76 ms |    **123.44 ms** |
| Median request latency     |        110.12 ms |        188.11 ms |    **100.91 ms** |
| p90 request latency        |        209.05 ms |        290.97 ms |    **197.51 ms** |
| p95 request latency        |        225.32 ms |        298.26 ms |    **200.78 ms** |
| Maximum request latency    |       **2.10 s** |           2.35 s |           5.40 s |
| Average iteration duration |        961.21 ms |           1.14 s |    **868.39 ms** |
| p95 iteration duration     |       **1.57 s** |           1.70 s |           2.10 s |
| Average process CPU usage  |           19.59% |           19.94% |       **18.85%** |
| Average process RSS        |       135.28 MiB |       213.19 MiB |    **12.49 MiB** |
| Maximum process RSS        |       143.79 MiB |       280.28 MiB |    **15.25 MiB** |
| Successful checks          |   758,372 (100%) |   638,533 (100%) |   839,969 (100%) |
| Failed HTTP requests       |                0 |                0 |                0 |

### Takeaways

- **Rust had the highest throughput:** 10.7% more requests/s than C# and
  31.6% more than Kotlin, with the lowest average, median, p90, and p95
  request latency, plus the lowest average iteration duration.
- **C# ranked second on throughput and led p95 iteration duration:**
  1.57 s, compared with Kotlin's 1.70 s and Rust's 2.10 s. C# also handled
  18.8% more requests/s than Kotlin and had the lowest maximum request
  latency (2.10 s).
- **Kotlin had lower latency spikes than Rust, but the lowest throughput:**
  its maximum request latency was 2.35 s, compared with Rust's 5.40 s.
  Rust's low p95 request latency did not prevent large latency spikes.
- **Rust had the smallest memory footprint:** average process RSS was
  12.49 MiB, compared with 135.28 MiB for C# and 213.19 MiB for Kotlin.
  Average reported process CPU usage was similar across all three
  (18.85% to 19.94%).
- **All three passed every check with zero HTTP failures.** These results
  describe the recorded local runs, not a general ranking of the languages.
