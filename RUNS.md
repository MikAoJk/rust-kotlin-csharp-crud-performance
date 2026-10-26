C#

█ TOTAL RESULTS

    checks_total.......: 6773256 16126.532301/s
    checks_succeeded...: 100.00% 6773256 out of 6773256
    checks_failed......: 0.00%   0 out of 6773256

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
    http_req_duration..............: avg=15.05ms  min=291.99µs med=13.2ms  max=360.83ms p(90)=27.6ms   p(95)=32.72ms
      { expected_response:true }...: avg=15.05ms  min=291.99µs med=13.2ms  max=360.83ms p(90)=27.6ms   p(95)=32.72ms
    http_req_failed................: 0.00%   0 out of 3386628
    http_reqs......................: 3386628 8063.266151/s

    EXECUTION
    iteration_duration.............: avg=107.18ms min=4.81ms   med=94.28ms max=450.57ms p(90)=174.91ms p(95)=189.66ms
    iterations.....................: 483804  1151.895164/s
    vus............................: 1       min=1            max=200
    vus_max........................: 200     min=200          max=200

    
Kotlin

█ TOTAL RESULTS

    checks_total.......: 1747172 4159.895719/s
    checks_succeeded...: 100.00% 1747172 out of 1747172
    checks_failed......: 0.00%   0 out of 1747172

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
    http_req_duration..............: avg=59.29ms  min=186.47µs med=56.68ms  max=346.86ms p(90)=129.63ms p(95)=145.06ms
      { expected_response:true }...: avg=59.29ms  min=186.47µs med=56.68ms  max=346.86ms p(90)=129.63ms p(95)=145.06ms
    http_req_failed................: 0.00%  0 out of 873586
    http_reqs......................: 873586 2079.94786/s

    EXECUTION
    iteration_duration.............: avg=415.88ms min=3.75ms   med=412.57ms max=1.21s    p(90)=864.76ms p(95)=908.13ms
    iterations.....................: 124798 297.135409/s
    vus............................: 1      min=1           max=200
    vus_max........................: 200    min=200         max=200

Rust

█ TOTAL RESULTS

    checks_total.......: 2065518 4917.778968/s
    checks_succeeded...: 100.00% 2065518 out of 2065518
    checks_failed......: 0.00%   0 out of 2065518

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
    http_req_duration..............: avg=48.42ms  min=312.77µs med=39.98ms  max=4.37s p(90)=65.46ms  p(95)=70.7ms  
      { expected_response:true }...: avg=48.42ms  min=312.77µs med=39.98ms  max=4.37s p(90)=65.46ms  p(95)=70.7ms  
    http_req_failed................: 0.00%   0 out of 1032759
    http_reqs......................: 1032759 2458.889484/s

    EXECUTION
    iteration_duration.............: avg=351.69ms min=9.45ms   med=273.09ms max=5.53s p(90)=446.13ms p(95)=491.11ms
    iterations.....................: 147537  351.269926/s
    vus............................: 1       min=1            max=200
    vus_max........................: 200     min=200          max=200
