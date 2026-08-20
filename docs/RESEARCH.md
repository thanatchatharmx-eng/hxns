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
| Run-mean position error | 150 | 0 | 10 |
| P95 position error | 118 | 39 | 3 |
| Worst position error | 44 | 116 | 0 |
| Final position error | 148 | 0 | 12 |

The frequent equality in worst error shows why a single peak metric is not
enough to describe contribution: shared injected fault peaks can dominate the
worst sample while timing information still improves typical or final error.

## Tracking-prior correction

Version 0.3 replaces the earlier fixed-offset/wide-covariance cold start with a
paired covariance-consistent tracking prior. The earlier cruise inversion was
traced to a fixed 26.926 km injected error being paired with a declared 2,000 km
position covariance. The 2,000 km case remains an acquisition-stress diagnostic
and is not reported as current bounded tracking performance.

## Provenance

- Validation generated: 2026-08-10T06:24:41Z
- HXNS core version: `0.1.0`
- Customer Evaluation version: `0.3.0-beta.1`
- Source report SHA-256:
  `D2BCE4EF3FBDC7DFCBFABEB96F76543D8F2030C42142C29426F82F13D814A14A`
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
