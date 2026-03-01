# Analog Pilot-Based Noise Degradation Detector

## Overview

This project implements an analog normalized correlation system to estimate signal degradation using a small known pilot tone embedded in the transmitted message.

A predetermined sinusoidal signal is added to the baseband message before transmission. Since the pilot experiences the same channel conditions as the message, its degradation reflects overall signal corruption.

At the receiver, the pilot component is correlated with a locally generated sinusoid of the same frequency. The normalized correlation value is compared against a threshold to determine whether the signal has been degraded beyond an acceptable level.

## Principle

Transmitted signal:

s(t) = m(t) + A sin(ωt)

At the receiver:

Cross term:
C = (1/T) ∫ x(t)y(t) dt

RMS values:
Rx = sqrt[(1/T) ∫ x²(t) dt]
Ry = sqrt[(1/T) ∫ y²(t) dt]

Normalized correlation:
ρ = C / (Rx Ry)

If ρ falls below a predefined threshold, the signal is considered excessively degraded and can be rejected or flagged.

## Implementation

Designed using analog building blocks:

* Analog multiplier
* Integrator
* RMS computation circuits
* Analog divider
* Comparator

Currently implemented and simulated in LTspice.

## Goal

To explore whether signal quality estimation using normalized correlation can be implemented in analog hardware, either as a replacement for or as a preliminary stage before digital processing.

## Future To-Do
1. Optimize gain, delay and power.
2. Simulate the project in Cadence.
