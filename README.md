# Perf Metric Analysis Pages

HTML pages used for perf metric analysis, to help visualize and understand the differences between various perf timings (i.e., `domInteractive`, `domContentLoaded`, `onload`, `LCP`, `TTI`, and so on).


## Usage

Can access the latest page at: https://brophdawg11.github.io/perf-metric-analysis/

For local development, run `npx http-server docs/`


## Notes

* `First Paint`
  * Document parsed + blocking stylesheets downloaded
* `domInteractive`
  * `First Paint` + blocking scripts downloaded
* `DOMContentLoaded`
  * `domInteractive` + `defer` scripts downloaded/executed
  * Does not include any synchronous or asynchronous waterfall scripts from `defer`
  * _Does not_ include images completing
* `domComplete`
  * `DOMContentLoaded` + images + `async` scripts downloaded/executed
  * Does include any synchronous or asynchronous waterfall scripts from `async`
  * Effectively when the load event fires
* `load`
  * `domComplete` + synchronous code that runs as part of the load event
  * Does not include any additional scripts added during the load event listener
