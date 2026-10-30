C#

█ TOTAL RESULTS

    checks_total.......: 383073  910.537267/s
    checks_succeeded...: 100.00% 383073 out of 383073
    checks_failed......: 0.00%   0 out of 383073

    ✓ metrics: status is 200
    ✓ create: status is 200
    ✓ create: response body matches
    ✓ metrics: valid process resource sample
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
    api_cpu_samples................: 267    0.63464/s
    api_cpu_usage_percent..........: min=6.796549  avg=19.38136   max=22.029198  med=19.805251  p(90)=20.474593  p(95)=20.727054 
    api_memory_rss_mib.............: min=99.757813 avg=166.716097 max=355.402344 med=134.945313 p(90)=272.885938 p(95)=306.246094

    HTTP
    http_req_duration..............: min=415.06µs  avg=978.9ms    max=5.5s       med=407.71ms   p(90)=2.38s      p(95)=2.79s     
      { expected_response:true }...: min=415.06µs  avg=978.9ms    max=5.5s       med=407.71ms   p(90)=2.38s      p(95)=2.79s     
    http_req_failed................: 0.00%  0 out of 191403
    http_reqs......................: 191403 454.951313/s

    EXECUTION
    iteration_duration.............: min=8.76ms    avg=6.8s       max=17.7s      med=3.09s      p(90)=15.09s     p(95)=15.5s     
    iterations.....................: 27573  65.539059/s
    vus............................: 7      min=2           max=1001
    vus_max........................: 1001   min=1001        max=1001

    NETWORK
    data_received..................: 1.3 GB 3.0 MB/s
    data_sent......................: 29 MB  69 kB/s

    
Kotlin

█ TOTAL RESULTS

    checks_total.......: 337950  803.759492/s
    checks_succeeded...: 100.00% 337950 out of 337950
    checks_failed......: 0.00%   0 out of 337950

    ✓ create: status is 200
    ✓ create: response body matches
    ✓ metrics: status is 200
    ✓ metrics: valid process resource sample
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
    api_cpu_samples................: 262    0.623125/s
    api_cpu_usage_percent..........: min=17.518544  avg=19.832389  max=22.949339  med=19.939338 p(90)=20.895752  p(95)=21.451674 
    api_memory_rss_mib.............: min=136.265625 avg=201.557064 max=292.984375 med=175.09375 p(90)=287.015625 p(95)=287.042578

    HTTP
    http_req_duration..............: min=424.44µs   avg=1.1s       max=5.01s      med=995.72ms  p(90)=2.2s       p(95)=2.49s     
      { expected_response:true }...: min=424.44µs   avg=1.1s       max=5.01s      med=995.72ms  p(90)=2.2s       p(95)=2.49s     
    http_req_failed................: 0.00%  0 out of 168844
    http_reqs......................: 168844 401.568184/s

    EXECUTION
    iteration_duration.............: min=100.17ms   avg=7.7s       max=19.79s     med=7.29s     p(90)=15s        p(95)=16.09s    
    iterations.....................: 24346  57.903029/s
    vus............................: 11     min=2           max=1001
    vus_max........................: 1001   min=1001        max=1001

    NETWORK
    data_received..................: 1.2 GB 2.9 MB/s
    data_sent......................: 26 MB  61 kB/s




Rust

█ TOTAL RESULTS

    checks_total.......: 783332  1862.546236/s
    checks_succeeded...: 100.00% 783332 out of 783332
    checks_failed......: 0.00%   0 out of 783332

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
    api_cpu_samples................: 318    0.756116/s
    api_cpu_usage_percent..........: min=16.816907 avg=19.485025 max=23.660223 med=19.435573 p(90)=20.853019 p(95)=20.932168
    api_memory_rss_mib.............: min=7.804688  avg=23.422267 max=42.242188 med=19.296875 p(90)=40.628906 p(95)=41.167969

    HTTP
    http_req_duration..............: min=334.29µs  avg=474.7ms   max=1.97s     med=102.33ms  p(90)=1.39s     p(95)=1.4s     
      { expected_response:true }...: min=334.29µs  avg=474.7ms   max=1.97s     med=102.33ms  p(90)=1.39s     p(95)=1.4s     
    http_req_failed................: 0.00%  0 out of 391507
    http_reqs......................: 391507 930.89506/s

    EXECUTION
    iteration_duration.............: min=7.44ms    avg=3.31s     max=10.59s    med=702.72ms  p(90)=9.49s     p(95)=9.68s    
    iterations.....................: 56203  133.635146/s
    vus............................: 5      min=2           max=1001
    vus_max........................: 1001   min=1001        max=1001

    NETWORK
    data_received..................: 2.0 GB 4.8 MB/s
    data_sent......................: 59 MB  141 kB/s
