# HXNS Customer Evaluation

HXNS Customer Evaluation is a bounded software-in-the-loop engineering service.
It lets a prospective user test processed-sensor assumptions against the same
flight-oriented estimator used by the HXNS host validation campaign.

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

### 3. Custom feasibility pilot

A customer-specific trajectory, body set, camera model, pulsar catalogue,
fault schedule, or hardware interface requires a separate scoped engineering
change. It is not represented as a checkbox in the standard console.

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

To start with a non-confidential fit check, use the
[evaluation-request form](https://github.com/thanatchatharmx-eng/hxns/issues/new?template=evaluation-request.yml).
