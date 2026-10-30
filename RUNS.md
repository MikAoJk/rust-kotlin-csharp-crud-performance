C#

█ TOTAL RESULTS

    checks_total.......: 670044  1594.569186/s
    checks_succeeded...: 100.00% 670044 out of 670044
    checks_failed......: 0.00%   0 out of 670044

    ✓ create: status is 200
    ✓ metrics: status is 200
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
    api_cpu_samples................: 332    0.790093/s
    api_cpu_usage_percent..........: min=2.923991   avg=19.313411  max=21.377512  med=19.872746  p(90)=20.555918  p(95)=20.75076 
    api_memory_rss_mib.............: min=100.089844 avg=140.335468 max=158.765625 med=135.304688 p(90)=157.589844 p(95)=158.09375

    HTTP
    http_req_duration..............: min=342.43µs   avg=304.6ms    max=2.78s      med=119.49ms   p(90)=691.72ms   p(95)=787.67ms 
      { expected_response:true }...: min=342.43µs   avg=304.6ms    max=2.78s      med=119.49ms   p(90)=691.72ms   p(95)=787.67ms 
    http_req_failed................: 0.00%  0 out of 334856
    http_reqs......................: 334856 796.889547/s

    EXECUTION
    iteration_duration.............: min=4.87ms     avg=2.12s      max=7.38s      med=904.41ms   p(90)=4.7s       p(95)=5.19s    
    iterations.....................: 48122  114.520626/s
    vus............................: 3      min=2           max=501
    vus_max........................: 501    min=501         max=501

    NETWORK
    data_received..................: 1.1 GB 2.7 MB/s
    data_sent......................: 51 MB  121 kB/s

    
Kotlin

█ TOTAL RESULTS

    checks_total.......: 601104  1430.031947/s
    checks_succeeded...: 100.00% 601104 out of 601104
    checks_failed......: 0.00%   0 out of 601104

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
    api_cpu_samples................: 340    0.808863/s
    api_cpu_usage_percent..........: min=18.083877  avg=19.856599  max=21.959858  med=19.940062  p(90)=20.917086  p(95)=20.965008 
    api_memory_rss_mib.............: min=137.902344 avg=213.772429 max=280.371094 med=181.792969 p(90)=280.296875 p(95)=280.332031

    HTTP
    http_req_duration..............: min=314.48µs   avg=339.3ms    max=1.99s      med=295.28ms   p(90)=687.85ms   p(95)=710.73ms  
      { expected_response:true }...: min=314.48µs   avg=339.3ms    max=1.99s      med=295.28ms   p(90)=687.85ms   p(95)=710.73ms  
    http_req_failed................: 0.00%  0 out of 300382
    http_reqs......................: 300382 714.611542/s

    EXECUTION
    iteration_duration.............: min=4.63ms     avg=2.36s      max=7.4s       med=1.8s       p(90)=4.5s       p(95)=4.79s     
    iterations.....................: 43204  102.782714/s
    vus............................: 2      min=2           max=501
    vus_max........................: 501    min=501         max=501

    NETWORK
    data_received..................: 1.2 GB 2.7 MB/s
    data_sent......................: 46 MB  108 kB/s



Rust

█ TOTAL RESULTS

    checks_total.......: 818594  1946.353926/s
    checks_succeeded...: 100.00% 818594 out of 818594
    checks_failed......: 0.00%   0 out of 818594

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
    api_cpu_samples................: 396    0.941561/s
    api_cpu_usage_percent..........: min=16.444364 avg=19.184388 max=21.906125 med=19.118409 p(90)=20.784132 p(95)=20.907359
    api_memory_rss_mib.............: min=5.714844  avg=14.272936 max=19.621094 med=12.410156 p(90)=19.478125 p(95)=19.527344

    HTTP
    http_req_duration..............: min=288.01µs  avg=248.49ms  max=993.13ms  med=102.06ms  p(90)=600.64ms  p(95)=618.47ms 
      { expected_response:true }...: min=288.01µs  avg=248.49ms  max=993.13ms  med=102.06ms  p(90)=600.64ms  p(95)=618.47ms 
    http_req_failed................: 0.00%  0 out of 409099
    http_reqs......................: 409099 972.706183/s

    EXECUTION
    iteration_duration.............: min=5ms       avg=1.73s     max=5.2s      med=701.84ms  p(90)=4.19s     p(95)=4.29s    
    iterations.....................: 58783  139.767116/s
    vus............................: 3      min=2           max=501
    vus_max........................: 501    min=501         max=501

    NETWORK
    data_received..................: 1.3 GB 3.0 MB/s
    data_sent......................: 62 MB  147 kB/s