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

    checks_total.......: 566034  1347.698242/s
    checks_succeeded...: 100.00% 566034 out of 566034
    checks_failed......: 0.00%   0 out of 566034

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
    http_req_duration..............: avg=183.4ms min=254.56µs med=195.94ms max=1.49s p(90)=295.84ms p(95)=300.52ms
      { expected_response:true }...: avg=183.4ms min=254.56µs med=195.94ms max=1.49s p(90)=295.84ms p(95)=300.52ms
    http_req_failed................: 0.00%  0 out of 283017
    http_reqs......................: 283017 673.849121/s

    EXECUTION
    iteration_duration.............: avg=1.28s   min=4.07ms   med=1.3s     max=3.7s  p(90)=1.69s    p(95)=1.79s   
    iterations.....................: 40431  96.26416/s
    vus............................: 1      min=1           max=200
    vus_max........................: 200    min=200         max=200

    NETWORK
    data_received..................: 599 MB 1.4 MB/s
    data_sent......................: 43 MB  103 kB/s

Rust

█ TOTAL RESULTS

    checks_total.......: 709730  1689.831087/s
    checks_succeeded...: 100.00% 709730 out of 709730
    checks_failed......: 0.00%   0 out of 709730

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
    http_req_duration..............: avg=145.79ms min=263.53µs med=105.74ms max=11.39s p(90)=199.94ms p(95)=203.74ms
      { expected_response:true }...: avg=145.79ms min=263.53µs med=105.74ms max=11.39s p(90)=199.94ms p(95)=203.74ms
    http_req_failed................: 0.00%  0 out of 354865
    http_reqs......................: 354865 844.915543/s

    EXECUTION
    iteration_duration.............: avg=1.02s    min=4.96ms   med=897.68ms max=14.5s  p(90)=1.39s    p(95)=2.39s   
    iterations.....................: 50695  120.70222/s
    vus............................: 1      min=1           max=200
    vus_max........................: 200    min=200         max=200

    NETWORK
    data_received..................: 619 MB 1.5 MB/s
    data_sent......................: 54 MB  128 kB/s
