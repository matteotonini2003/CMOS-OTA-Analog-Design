# CMOS OTA Analog Design

This repository contains the full-custom analog design of a p-type CMOS Operational Transconductance Amplifier (OTA) developed in PSM025 technology.

The project includes transistor sizing, LTspice simulations, operating point analysis, short-circuit output current simulation, open-loop voltage gain estimation, and layout/verification documentation.

The final project report is included in the `doc/` folder. The report is written in Italian.

## Project overview

The designed circuit is a CMOS OTA with a pMOS differential input pair, current mirrors and a high-impedance output stage.

The OTA converts a differential input voltage into an output current. For small signals, the short-circuit output current can be approximated as:

```text
iOCC = -gm * KI * vd
```

where `gm` is the transconductance of the input differential pair, `KI` is the current mirror ratio, and `vd` is the differential input voltage.

## Main specifications

```text
Circuit type:          p-type CMOS OTA
Technology:            PSM025
Supply voltage:        VDD = 2.5 V
Reference current:     IB = 9 uA
Bias current:          I0 = 18 uA
Main mirror ratio:     KI = 2
MOSFET length:         L = 1 um
Target overdrive:      |VGS - Vth| ≈ 200 mV
```

## Repository structure

```text
CMOS-OTA-Analog-Design/
├── ltspice/     LTspice schematic and simulation files
├── doc/         Final project report
├── README.md    Project documentation
├── .gitignore   Files excluded from version control
└── LICENSE      License file
```

## Folder description

### `ltspice/`

This folder contains the LTspice files used for schematic simulation and verification of the OTA.

The simulations include:

* operating point analysis;
* MOSFET overdrive verification;
* saturation condition verification;
* short-circuit output current simulation;
* open-output voltage transfer characteristic;
* voltage gain estimation.

### `doc/`

This folder contains the final project report.

The report documents:

* project specifications;
* transistor sizing;
* LTspice simulation results;
* layout implementation;
* DRC verification;
* layout extraction;
* LVS verification;
* final conclusions.

The report is written in Italian.

## Simulation results

The LTspice simulations confirmed the correct biasing of the OTA and the expected transconductive behavior.

The open-output simulation was used to estimate the voltage gain of the OTA. The obtained gain is approximately:

```text
Av ≈ -60
```

corresponding to approximately:

```text
Av ≈ 35.6 dB
```

## Layout and verification

The layout was designed and verified using Glade. The original Glade layout database is not included in this repository.

Layout, DRC, extraction and LVS results are documented in the final project report. The DRC verification was completed without errors. The LVS verification showed a mismatch related to the nMOS substrate connection, which was analyzed and attributed to a software extraction/verification issue rather than to an actual layout error.

## Tools used

* LTspice
* Glade
* PSM025 technology
* LaTeX

## Notes

Generated simulation files are excluded from the repository. The repository is intended to contain only the relevant LTspice source files and the final documentation.

Technology files, PDK files or third-party model files are not included unless redistribution is explicitly allowed.

## Authors

Matteo Tonini

Antonio Tuma
