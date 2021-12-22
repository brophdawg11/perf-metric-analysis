# Perf Metric Analysis Pages

HTML pages used for perf metric analysis, to help visualize and understand the differences between various perf timings (i.e., `domInteractive`, `domContentLoaded`, `onload`, `LCP`, `TTI`, and so on).

Available at: https://brophdawg11.github.io/perf-metric-analysis/


## Notes

* `First Paint`
  * Document parsed + blocking stylesheets downloaded
* `domInteractive`
  * `First Paint` + blocking scripts downloaded
* `domContentLoaded`
  * `domInteractive` + `defer` scripts downloaded  + executed
  * _Does not_ include images completing
  * _Does not_ include `async` scripts
* `domComplete`
  * `DOMContentLoaded` + images + `async` scripts + script execution
  * Effectively when the load event fires
* `load`
  * `domComplete` + synchronous code that runs as part of the load event
  * Does not include any additional scripts added during the load event listener
