# Frequently asked questions

## Is HXNS flight ready?

No. HXNS currently provides research-grade software-in-the-loop evidence and an
embedded-oriented Rust `no_std` boundary. Real sensor calibration, target-board
integration, hardware-in-the-loop timing, radiation and fault-containment work,
mission-grade dynamics, independent review, and qualification remain future
work.

## Is HXNS open source?

No. The source core, simulator, and Customer Evaluation Console are proprietary
and remain in a private repository. This public repository contains reviewed
technical and evaluation material only.

## Does HXNS process camera images?

Not in the flight core. A camera front end is expected to supply an identified
body, centroid/line of sight, apparent diameter, quality, and calibration
metadata. HXNS consumes the processed navigation product.

## Does HXNS count every pulsar pulse as an EKF measurement?

No. The receiver integration produces one processed TOA residual and
uncertainty. Raw pulse count is diagnostic and is not treated as multiple
independent measurements.

## Are 1, 5, and 10 Hz pulsar update rates?

No. They are adaptive navigation-output rates selected using mission geometry.
IMU, camera, processed pulsar TOA, and navigation output each have distinct
cadences.

## Can one pulsar determine the full spacecraft position?

No. One processed pulsar timing observable constrains the state primarily along
its line of sight. HXNS combines that directionally distinct information with
optical geometry, inertial propagation, clock correlation, and prior state.

## Can the console accept any mission trajectory?

Not in the standard interface. It supports four established validation windows.
A customer trajectory or different body set is a scoped feasibility pilot.

## What does a standard evaluation return?

An auditable `.hxns` configuration, offline HTML report, JSON, per-run CSV, and
aggregate CSV. The report records the declared assumptions and limitations.

## Is customer data uploaded by the console?

The current Windows evaluation console runs locally and binds to `127.0.0.1`.
Entered values and output remain on that computer. Distribution and support are
handled under separate evaluation terms.

## How should an organization make first contact?

HXNS is currently at **R0 — Research Evidence Baseline**. To volunteer bounded
expert feedback, use the public
[technical-review form](https://github.com/thanatchatharmx-eng/hxns/issues/new?template=technical-review.yml).
To explore future paid work or a defined sponsored R&D milestone, use the
[sponsored-evaluation fit check](https://github.com/thanatchatharmx-eng/hxns/issues/new?template=sponsored-evaluation.yml).
A sponsored fit check does not mean that C1 delivery is open or that work has
begun. Do not post proprietary specifications publicly; a private channel can
be established only after the initial fit check.
