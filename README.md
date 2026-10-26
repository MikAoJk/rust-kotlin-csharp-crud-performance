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
| HTTP requests              |        3,386,628 |          873,586 |        1,032,759 |
| HTTP requests/s            |     **8,063.27** |         2,079.95 |         2,458.89 |
| Completed CRUD iterations  |          483,804 |          124,798 |          147,537 |
| CRUD iterations/s          |     **1,151.90** |           297.14 |           351.27 |
| Average request latency    |     **15.05 ms** |         59.29 ms |         48.42 ms |
| Median request latency     |     **13.20 ms** |         56.68 ms |         39.98 ms |
| p90 request latency        |     **27.60 ms** |        129.63 ms |         65.46 ms |
| p95 request latency        |     **32.72 ms** |        145.06 ms |         70.70 ms |
| Maximum request latency    |        360.83 ms |    **346.86 ms** |           4.37 s |
| Average iteration duration |    **107.18 ms** |        415.88 ms |        351.69 ms |
| p95 iteration duration     |    **189.66 ms** |        908.13 ms |        491.11 ms |
| Successful checks          | 6,773,256 (100%) | 1,747,172 (100%) | 2,065,518 (100%) |
| Failed HTTP requests       |                0 |                0 |                0 |

### Takeaways

- **C# had the highest throughput:** 3.88 times Kotlin's requests/s and
  3.28 times Rust's, with the lowest average, median, p90, and p95 request
  latency, plus the lowest average and p95 iteration duration.
- **Rust outperformed Kotlin on throughput and typical latency:** it handled
  18.2% more requests/s, with lower average, median, p90, and p95 request
  latency, but had the highest maximum request latency (4.37 s).
- **Kotlin had the lowest maximum request latency:** 346.86 ms, compared with
  360.83 ms for C#, despite having the lowest throughput.
- **All three passed every check with zero HTTP failures.** These results
  describe the recorded local runs, not a general ranking of the languages.
