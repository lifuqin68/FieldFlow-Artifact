# FieldFlow research artifact

Download the current artifact ZIP (SHA-256 `279524d6b5316a7f2fb6aa1cf490f976b6a245e71fff601309ba5adb0fa0511d`). Extract on
64-bit Windows 10/11 with PowerShell 5.1+. Nothing needs to be built or
installed for the core experiments — the seven FieldFlow executables ship in
`tool/`.

```powershell
powershell -File scripts\verify.ps1
```

That reproduces four of the paper's experiments — RQ2 in Java, Go and PHP, plus
RQ3 — checks each against the figure the main paper reports, and prints `PASS`
or `FAIL` per line in about 90 seconds.

The ZIP also carries the two public benchmarks for RQ1 (SecuriBench Micro, 123
cases; OWASP Benchmark v1.2, 945 No-CP cases), the three production systems at
the exact revisions analysed for RQ4 (Train-Ticket, mall-swarm, Apache OFBiz),
every case suite and baseline configuration, and the reference output of every
reported run — so any run can be diffed against what the paper reports.

The four baseline comparisons (CodeQL, FlowDroid, gosec, Semgrep) are **not**
redistributed. They need those toolchains installed at the versions the README
pins, plus a JRE 8 for FlowDroid's boot classpath, and a Maven build of the OWASP
benchmark. RQ1 and RQ4 then take from a few minutes to about an hour.

The prototype is delivered **as pre-built binaries only** — no source and no
build step — so the reported results are reproducible and verifiable, but the
implementation cannot be inspected or rebuilt. The executables are Windows PE
binaries; there is no Linux build and no container image.

See the README inside the ZIP for the step-by-step guide, the expected number
for every suite, tool prerequisites, licensing and data provenance.

