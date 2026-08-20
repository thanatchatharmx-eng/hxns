# HXNS Customer Evaluation

HXNS Customer Evaluation is a bounded software-in-the-loop engineering service.
It lets a prospective user test processed-sensor assumptions against the same
flight-oriented estimator used by the HXNS host validation campaign.

Academic technical review and sponsored evaluation are separate paths. A
technical review asks an expert to examine a bounded claim or method without an
implied purchase. A sponsored evaluation is paid, scoped engineering work with
agreed deliverables and a payment schedule.

## Current product stage

HXNS is currently at **R0 — Research Evidence Baseline**. The commercial
transition is:

`R0 -> external feedback -> R1 -> readiness gates -> C1`

Non-confidential sponsored fit checks may be submitted during R0 so that a
decision question and budget path can be understood. This does not mean that C1
delivery is open. A C1 Standard Sponsored Evaluation can begin only after the
external-feedback, R1 integration, and readiness-gate steps are complete.

## Evaluation levels

### 1. Public sample

Use the public validation summary and preprint to inspect the method, outputs,
limitations, and representative results. No customer configuration is run.

### 2. Standard sensor evaluation

The existing campaign can be configured for:

- one or more established mission windows;
- nominal or degraded baseline assumptions;
- processed optical range and bearing uncertainty;
- IMU noise, bias, and sample rate;
- processed pulsar TOA uncertainty, interval, and integration window;
- atomic-clock initial bias and drift;
- paired-seed count; and
- the standard fault campaign or a clean run.

This existing boundary is the planned basis for C1. A non-confidential fit check
can be submitted now, but a fixed-quote C1 engagement cannot begin until the
readiness gates have passed and written commercial terms are agreed.

### 3. Custom feasibility pilot

A customer-specific trajectory, body set, camera model, pulsar catalogue,
fault schedule, or hardware interface requires a separate scoped engineering
change. It is not represented as a checkbox in the standard console.

Custom work is quoted as one or more milestones. Examples include a new
trajectory, body set, sensor-product model, interface adapter, catalogue,
cadence, or fault schedule.

### 4. Sponsored R&D milestone

An organization may fund the next evidence step rather than request a completed
standard study. Candidate milestones include hardware-in-the-loop integration,
LEON5 integration work, ephemeris extension, or mission-specific validation.
Each milestone requires written acceptance criteria and deliverables before work
begins.

## Standard workflow

1. **Fit check** - establish the public use case without exchanging sensitive
   technical data.
2. **Private intake** - agree on the processed products, units, uncertainty,
   cadence, mission window, deliverables, and data-handling boundary.
3. **Configuration review** - validate a human-readable `.hxns` configuration
   before execution.
4. **Paired-seed campaign** - run selected sensor suites under common seeds and
   fault timing.
5. **Engineering report** - deliver HTML, JSON, CSV, and the exact configuration.
6. **Interpretation** - distinguish estimator behavior from uncalibrated
   hardware claims and identify the next integration experiment.

## Input contract

The standard interface consumes processed sensor-product assumptions, not raw
camera pixels or raw X-ray photon events. Inputs include:

- range uncertainty in metres;
- bearing uncertainty in microradians;
- acceleration noise and bias in SI units;
- IMU sample rate in hertz;
- processed pulsar TOA uncertainty in nanoseconds;
- TOA interval and integration window in seconds; and
- atomic-clock bias in nanoseconds and drift in parts per billion.

The 1/5/10 Hz values reported by HXNS are navigation-output rates selected by
mission geometry. They are not the raw pulse rate or the processed-pulsar TOA
cadence.

## Deliverables

A completed standard evaluation can include:

- exact reviewed `.hxns` configuration;
- standalone offline HTML report;
- machine-readable JSON;
- per-run CSV;
- aggregate-summary CSV; and
- short engineering interpretation with assumptions and unresolved risks.

## Deliberate limitations

- Results are deterministic host software-in-the-loop outputs under declared
  engineering assumptions.
- The current trajectory context is a DE442-backed Earth-Jupiter-Neptune model
  with bounded validation windows.
- Results are not hardware calibration, LEON5 timing certification, n-body
  flight validation, or evidence of flight qualification.
- Public GitHub issues must contain no proprietary mission, sensor, export-
  controlled, personal, or security-sensitive data.

To volunteer bounded expert feedback, use the
[technical-review form](https://github.com/thanatchatharmx-eng/hxns/issues/new?template=technical-review.yml).
To submit a non-confidential fit check for future paid work or a defined
sponsored R&D milestone, use the
[sponsored-evaluation fit check](https://github.com/thanatchatharmx-eng/hxns/issues/new?template=sponsored-evaluation.yml).
Both forms are public and must contain non-confidential information only.
