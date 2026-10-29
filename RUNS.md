C#

█ TOTAL RESULTS

    checks_total.......: 758372  1805.197158/s
    checks_succeeded...: 100.00% 758372 out of 758372
    checks_failed......: 0.00%   0 out of 758372

    ✓ metrics: status is 200
    ✓ metrics: valid process resource sample
    ✓ create: status is 200
    ✓ create: response body matches
    ✓ list: status is 200
    ✓ list: created user has a unique ID
    ✓ read: status is 200
    ✓ read: user matches
    ✓ update: status is 200
    ✓ update: response body matches
    ✓ read updated: status is 200
    ✓ read updated: user matches
    ✓ delete: status is 200
    ✓ delete: response body matches
    ✓ read deleted: status is 404
    ✓ read deleted: response body matches
    ✓ metrics: same process and increasing counters

    CUSTOM
    api_cpu_samples................: 370    0.880733/s
    api_cpu_usage_percent..........: min=2.211123 avg=19.591532  max=21.48618   med=19.896633  p(90)=20.597363 p(95)=20.790782 
    api_memory_rss_mib.............: min=100.125  avg=135.279134 max=143.792969 med=134.957031 p(90)=142.90625 p(95)=142.957031

    HTTP
    http_req_duration..............: min=155.18µs avg=137.02ms   max=2.1s       med=110.12ms   p(90)=209.05ms  p(95)=225.32ms  
      { expected_response:true }...: min=155.18µs avg=137.02ms   max=2.1s       med=110.12ms   p(90)=209.05ms  p(95)=225.32ms  
    http_req_failed................: 0.00%  0 out of 379001
    http_reqs......................: 379001 902.158212/s

    EXECUTION
    iteration_duration.............: min=2.63ms   avg=961.21ms   max=3.19s      med=877.75ms   p(90)=1.41s     p(95)=1.57s     
    iterations.....................: 54461  129.636699/s
    vus............................: 2      min=2           max=201
    vus_max........................: 201    min=201         max=201

    NETWORK
    data_received..................: 744 MB 1.8 MB/s
    data_sent......................: 57 MB  137 kB/s

    
Kotlin

█ TOTAL RESULTS

    checks_total.......: 638533  1519.410715/s
    checks_succeeded...: 100.00% 638533 out of 638533
    checks_failed......: 0.00%   0 out of 638533

    ✓ create: status is 200
    ✓ create: response body matches
    ✓ list: status is 200
    ✓ list: created user has a unique ID
    ✓ metrics: status is 200
    ✓ metrics: valid process resource sample
    ✓ read: status is 200
    ✓ read: user matches
    ✓ update: status is 200
    ✓ update: response body matches
    ✓ read updated: status is 200
    ✓ read updated: user matches
    ✓ delete: status is 200
    ✓ delete: response body matches
    ✓ read deleted: status is 404
    ✓ read deleted: response body matches
    ✓ metrics: same process and increasing counters

    CUSTOM
    api_cpu_samples................: 375    0.892325/s
    api_cpu_usage_percent..........: min=17.537467  avg=19.940198  max=22.862746  med=19.972306  p(90)=20.956533  p(95)=21.626474 
    api_memory_rss_mib.............: min=140.054688 avg=213.189744 max=280.277344 med=182.685547 p(90)=280.207031 p(95)=280.242188

    HTTP
    http_req_duration..............: min=224.81µs   avg=162.76ms   max=2.35s      med=188.11ms   p(90)=290.97ms   p(95)=298.26ms  
      { expected_response:true }...: min=224.81µs   avg=162.76ms   max=2.35s      med=188.11ms   p(90)=290.97ms   p(95)=298.26ms  
    http_req_failed................: 0.00%  0 out of 319079
    http_reqs......................: 319079 759.259195/s

    EXECUTION
    iteration_duration.............: min=3.76ms     avg=1.14s      max=3.59s      med=1.18s      p(90)=1.59s      p(95)=1.7s      
    iterations.....................: 45905  109.232489/s
    vus............................: 2      min=2           max=201
    vus_max........................: 201    min=201         max=201

    NETWORK
    data_received..................: 644 MB 1.5 MB/s
    data_sent......................: 48 MB  115 kB/s



Rust

█ TOTAL RESULTS

    checks_total.......: 872340  2076.453366/s
    checks_succeeded...: 100.00% 872340 out of 872340
    checks_failed......: 0.00%   0 out of 872340

    ✓ metrics: status is 200
    ✓ metrics: valid process resource sample
    ✓ create: status is 200
    ✓ create: response body matches
    ✓ list: status is 200
    ✓ list: created user has a unique ID
    ✓ read: status is 200
    ✓ read: user matches
    ✓ update: status is 200
    ✓ update: response body matches
    ✓ read updated: status is 200
    ✓ read updated: user matches
    ✓ delete: status is 200
    ✓ delete: response body matches
    ✓ read deleted: status is 404
    ✓ read deleted: response body matches
    ✓ metrics: same process and increasing counters

    CUSTOM
    api_cpu_samples................: 368    0.87596/s
    api_cpu_usage_percent..........: min=16.727839 avg=19.202879 max=21.74212 med=19.132687 p(90)=20.071424 p(95)=20.81231
    api_memory_rss_mib.............: min=4.832031  avg=8.214833  max=9.632813 med=8.113281  p(90)=9.625     p(95)=9.632813

    HTTP
    http_req_duration..............: min=255.37µs  avg=118.84ms  max=15.5s    med=101.11ms  p(90)=193.9ms   p(95)=196.55ms
      { expected_response:true }...: min=255.37µs  avg=118.84ms  max=15.5s    med=101.11ms  p(90)=193.9ms   p(95)=196.55ms
    http_req_failed................: 0.00%  0 out of 435986
    http_reqs......................: 435986 1037.788703/s

    EXECUTION
    iteration_duration.............: min=4.76ms    avg=836.13ms  max=17.4s    med=701.21ms  p(90)=1.09s     p(95)=2s      
    iterations.....................: 62600  149.008392/s
    vus............................: 2      min=2           max=201
    vus_max........................: 201    min=201         max=201

    NETWORK
    data_received..................: 773 MB 1.8 MB/s
    data_sent......................: 66 MB  157 kB/s
