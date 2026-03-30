# Jaguar F-Type CAN Bus Senior Research Project

## Overview

This repository contains materials, notes, code, documentation, and research artifacts for my senior research project focused on the **reverse engineering of CAN bus communication in a Jaguar F-Type**. The project investigates how Electronic Control Units (ECUs) communicate across the vehicle network and aims to identify, characterize, and document selected CAN signals in a safe, structured, and academically rigorous way.

The broader motivation for this work is to better understand the communication architecture of modern vehicles and evaluate the feasibility of integrating or emulating vehicle systems in future custom applications, diagnostics workflows, or controlled research environments.

---

## Project Title

**Reverse Engineering Automotive Control Units and In-Vehicle CAN Communication Protocols**

---

## Research Objective

The primary objective of this project is to **infer, validate, and document a subset of CAN bus signals** present in a Jaguar F-Type by observing network traffic and correlating message behavior with known vehicle events.

This includes:

- Identifying active CAN message IDs on selected vehicle networks
- Observing how traffic changes under different operating conditions
- Inferring the likely function of unknown messages and payload fields
- Validating candidate signals through controlled observation and comparison with known vehicle behavior
- Building a structured documentation set for the decoded signals and related findings

A longer-term practical motivation is to assess how existing vehicle systems might interact with third-party or custom electronic control solutions in a research setting.

---

## Vehicle Platform

- **Vehicle:** 2015 Jaguar F-Type S
- **Architecture of Interest:** In-vehicle Controller Area Network (CAN)
- **Relevant Systems:** Powertrain, body control, chassis, infotainment, and gateway-mediated communication where applicable

---

## Background

Modern vehicles rely on dozens of distributed ECUs to manage engine control, transmission behavior, traction and stability systems, body electronics, infotainment, and other features. These modules commonly communicate over the **Controller Area Network (CAN)**, a broadcast-based serial communication protocol standardized under **ISO 11898**.

CAN is designed for:

- Real-time communication
- High reliability in electrically noisy environments
- Efficient arbitration among multiple nodes
- Reduced wiring complexity compared to point-to-point systems

Because CAN messages generally do not contain self-describing application-layer metadata, understanding a vehicle’s CAN traffic often requires empirical analysis. This project applies passive logging, differential observation, and signal inference techniques to study those communications within the Jaguar F-Type platform.

---

## Research Questions

This project is guided by the following questions:

1. What CAN messages are observable on the selected Jaguar F-Type network segments?
2. Which messages appear to correspond to specific driver inputs, vehicle states, or subsystem behaviors?
3. How can unknown payload bytes be mapped to meaningful signals through repeated observation and correlation?
4. What patterns, counters, timing characteristics, or message structures can be documented reliably?
5. To what extent can a subset of the vehicle’s communication behavior be understood without manufacturer documentation?

---

## Methodology

The project follows a primarily **observational and analytical** methodology.

### 1. Network Observation
CAN traffic is collected from accessible vehicle network segments using compatible CAN interfaces and logging tools. Data collection emphasizes passive monitoring.

### 2. Controlled Event Testing
Logs are recorded while known vehicle events occur, such as:
- Ignition state changes
- Door, lighting, or body function changes
- Steering wheel inputs
- Pedal or gear-selection events where safely observable
- Other non-destructive state changes relevant to analysis

### 3. Differential Analysis
Traffic captures are compared across test conditions to identify:
- Message IDs that appear or change
- Byte-level payload differences
- Timing changes or cyclical behavior
- Repeating counters, checksums, or structured fields

### 4. Signal Inference
Candidate signals are inferred by correlating payload variation with known vehicle actions or sensor behavior. Where possible, suspected meanings are cross-checked against:
- Diagnostic readouts
- Ground-truth sensor values
- Repeated trials under similar conditions

### 5. Documentation
Findings are organized into a structured reference including:
- Message ID
- Observed frequency or timing
- Byte/bit locations of interest
- Hypothesized signal meaning
- Supporting evidence
- Confidence level
- Notes on validation status

---

## Safety and Ethical Considerations

This project is conducted with a strong emphasis on **safety, legality, and responsible research practice**.

### Safety Principles
- Favor **passive logging** over active transmission whenever possible
- Avoid any testing that could compromise vehicle control or road safety
- Do not perform intrusive experimentation while the vehicle is in motion
- Conduct any higher-risk testing only in controlled environments and only when necessary
- Preserve the integrity of critical vehicle systems

### Ethical and Legal Principles
- Research is limited to the user’s own vehicle or properly authorized equipment
- The project is intended for academic study, system understanding, and interoperability research
- Findings will be documented responsibly and without facilitating unsafe misuse

---

## Expected Deliverables

The final project is expected to include some or all of the following:

- Literature review on CAN, ECU communication, and vehicle security research
- Background section on CAN protocol and Jaguar vehicle network context
- Experimental methodology and logging workflow
- Annotated CAN logs and analysis notes
- A partial CAN signal database or documentation table
- Validation results for inferred signals
- Final written report
- Presentation slides summarizing the project and findings

---

## Repository Structure

```text
.
├── README.md
├── docs/
│   ├── proposal/
│   ├── literature-review/
│   ├── final-report/
│   └── presentations/
├── data/
│   ├── raw-logs/
│   ├── processed-logs/
│   └── notes/
├── scripts/
│   ├── parsing/
│   ├── analysis/
│   └── visualization/
├── references/
│   ├── papers/
│   └── standards/
└── results/
    ├── signal-maps/
    ├── figures/
    └── tables/