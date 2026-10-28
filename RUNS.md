C#

█ TOTAL RESULTS

    checks_total.......: 193606  460.715262/s
    checks_succeeded...: 100.00% 193606 out of 193606
    checks_failed......: 0.00%   0 out of 193606

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

    HTTP
    http_req_duration..............: avg=538.77ms min=794.29µs med=301.28ms max=7.9s   p(90)=1.69s p(95)=2.29s
      { expected_response:true }...: avg=538.77ms min=794.29µs med=301.28ms max=7.9s   p(90)=1.69s p(95)=2.29s
    http_req_failed................: 0.00%  0 out of 96803
    http_reqs......................: 96803  230.357631/s

    EXECUTION
    iteration_duration.............: avg=3.77s    min=14.23ms  med=3.59s    max=16.19s p(90)=6.8s  p(95)=7.5s 
    iterations.....................: 13829  32.908233/s
    vus............................: 8      min=1          max=200
    vus_max........................: 200    min=200        max=200

    NETWORK
    data_received..................: 291 MB 692 kB/s
    data_sent......................: 15 MB  35 kB/s

    
Kotlin

█ TOTAL RESULTS

    checks_total.......: 636902  1516.260049/s
    checks_succeeded...: 100.00% 636902 out of 636902
    checks_failed......: 0.00%   0 out of 636902

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

    HTTP
    http_req_duration..............: avg=162.96ms min=247.55µs med=188.97ms max=1.29s p(90)=289.79ms p(95)=296.98ms
      { expected_response:true }...: avg=162.96ms min=247.55µs med=188.97ms max=1.29s p(90)=289.79ms p(95)=296.98ms
    http_req_failed................: 0.00%  0 out of 318451
    http_reqs......................: 318451 758.130025/s

    EXECUTION
    iteration_duration.............: avg=1.14s    min=4.04ms   med=1.19s    max=2.69s p(90)=1.59s    p(95)=1.69s   
    iterations.....................: 45493  108.304289/s
    vus............................: 1      min=1           max=200
    vus_max........................: 200    min=200         max=200

    NETWORK
    data_received..................: 646 MB 1.5 MB/s
    data_sent......................: 48 MB  115 kB/s


Rust

█ TOTAL RESULTS

    checks_total.......: 862834  2054.363831/s
    checks_succeeded...: 100.00% 862834 out of 862834
    checks_failed......: 0.00%   0 out of 862834

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

    HTTP
    http_req_duration..............: avg=120.01ms min=285.36µs med=100.64ms max=15.68s p(90)=194.12ms p(95)=196.63ms
      { expected_response:true }...: avg=120.01ms min=285.36µs med=100.64ms max=15.68s p(90)=194.12ms p(95)=196.63ms
    http_req_failed................: 0.00%  0 out of 431417
    http_reqs......................: 431417 1027.181915/s

    EXECUTION
    iteration_duration.............: avg=842.69ms min=4.95ms   med=701.16ms max=17.39s p(90)=1.09s    p(95)=2.01s   
    iterations.....................: 61631  146.740274/s
    vus............................: 1      min=1           max=200
    vus_max........................: 200    min=200         max=200

    NETWORK
    data_received..................: 767 MB 1.8 MB/s
    data_sent......................: 65 MB  156 kB/s

