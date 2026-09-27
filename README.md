# FieldFlow research artifact

This repository hosts the research artifact for the ICSOC 2026 paper **“FieldFlow: Member-SSA for Field-Sensitive Taint Analysis of Service Code.”**

[Download the latest release](https://github.com/lifuqin68/FieldFlow-Artifact/releases). The ZIP contains seven pre-built FieldFlow executables, benchmarks, case suites, the three RQ4 production systems, driver scripts, baseline configurations, and reference outputs. Its root `README.md` provides the commands and expected results for every experiment.

## Quick check

Extract the ZIP on **64-bit Windows 10/11 with PowerShell 5.1+**. From the extracted directory, run:

```powershell
powershell -File scripts\verify.ps1
```

In about 90 seconds, this checks RQ2 in Java, Go, and PHP, plus the **FF-Full configuration of RQ3**. It prints `PASS` or `FAIL` for each check. Only the executables included in the ZIP are needed. The ZIP's README gives separate commands for the other RQ3 configurations and the RQ1 and RQ4 experiments.

## Baseline tools

The ZIP includes baseline configurations, scripts, and reference outputs, but **not the baseline tools themselves**. To rerun the baseline comparisons, install the versions and prerequisites documented in the ZIP's README:

- CodeQL 2.23.7;
- FlowDroid 2.13, JDK 21, and a JRE 8 for its boot classpath;
- gosec v2.29.0;
- Docker and the `semgrep/semgrep:1.167.0` image.

The OWASP CodeQL and FlowDroid baselines also require building the included OWASP Benchmark source with Maven. These baseline tools are **not required** for the quick check or the FieldFlow experiments.

## Scope and limitations

FieldFlow is supplied as pre-built Windows executables only; its source code is not included. Reviewers can run the experiments and compare their outputs with the reference results, but cannot inspect the implementation or rebuild the tool from source. No Linux build or container image is provided.

See the ZIP's root `README.md` for the complete reproduction guide, data provenance, known limitations, and licensing information for each artifact component.
