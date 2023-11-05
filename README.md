# docusaurus-codespaces-memory-heap-error-repro

This is a test repo to reproduce memory heap issue when starting Docusaurus project in Codespaces. For some reasons, when using Yarn 3.6.4 with `nodeLinker: pnpm`, running `docusaurus start` would cause high CPU and memory usage, until eventually the command crashes.

```
<--- Last few GCs --->

[14519:0x645b500]    40108 ms: Scavenge 1987.9 (2021.7) -> 1972.2 (2021.7) MB, 0.3 / 0.0 ms  (average mu = 0.592, current mu = 0.695) allocation failure;
[14519:0x645b500]    40124 ms: Scavenge 1987.9 (2021.7) -> 1972.2 (2021.7) MB, 0.3 / 0.0 ms  (average mu = 0.592, current mu = 0.695) allocation failure;
[14519:0x645b500]    42472 ms: Mark-sweep 2839.3 (2882.4) -> 2259.1 (2299.6) MB, 1934.3 / 0.0 ms  (average mu = 0.453, current mu = 0.280) allocation failure; scavenge might not succeed


<--- JS stacktrace --->

FATAL ERROR: Reached heap limit Allocation failed - JavaScript heap out of memory
 1: 0xb7a940 node::Abort() [/usr/local/bin/node]
```
