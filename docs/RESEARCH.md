# Research evidence and provenance

## Current campaign

The reviewed HXNS software-in-the-loop validation campaign uses:

- 20 deterministic paired seeds;
- 2 sensor profiles: nominal and degraded;
- 4 mission windows: near Earth, Earth transition, cruise, and Neptune capture;
- 4 sensor suites: IMU only, IMU + optical, IMU + pulsar, and full hybrid; and
- 120 seconds per bounded run.

This produces **640 runs**, all of which were valid with zero reported
non-finite samples in the reviewed campaign.

## Why paired seeds matter

Sensor suites under comparison reuse the same initial state error, sensor-noise
generation order, and fault timing. This common-random-number design reduces the
chance that an apparent difference is merely a different random draw.

## Processed-pulsar contribution

For each scenario, profile, and seed, the full hybrid is compared with the
corresponding IMU + optical run:

| Metric | Full hybrid lower | Equal | Full hybrid higher |
| --- | ---: | ---: | ---: |
| Run-mean position error | 155 | 0 | 5 |
| P95 position error | 125 | 33 | 2 |
| Worst position error | 41 | 119 | 0 |
| Final position error | 149 | 0 | 11 |

The frequent equality in worst error shows why a single peak metric is not
enough to describe contribution: shared injected fault peaks can dominate the
worst sample while timing information still improves typical or final error.

## Transparent anomaly

The reviewed report retains a cruise-window mismatch in which the full hybrid
can underperform a reduced suite under some assumptions. It is treated as an
unresolved optical-model/filter-weighting question, not hidden as a favorable
result. This is a target for sensitivity analysis and later hardware-informed
calibration.

## Provenance

- Validation generated: 2026-08-01T04:06:23Z
- Source report SHA-256:
  `87CF460EC10A137A728840F61DE8D00E4A2F659180E2347C8E178825D084D1A1`
- Reported estimator state size in the host build: 448 bytes
- Reported high-rate replay sample size in the host build: 536 bytes

The complete internal report remains outside this public repository because it
contains full run-level data and local release evidence. The public
[sample summary](../samples/sample-validation-summary.html) and
[technical preprint](../publications/HXNS_Technical_Preprint_EN_v0.3.pdf)
carry the reviewed public claims.

## Interpretation boundary

These results come from deterministic host-side software-in-the-loop modeling
with engineering sensor assumptions. They are not hardware calibration,
LEON5 timing measurements, n-body flight validation, or evidence of flight
certification.
