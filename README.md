# Airport Runway Priority Arbiter using Verilog HDL

## Overview

This project implements an Airport Runway Priority Arbiter using Verilog HDL. The system allocates runway access based on request priority, ensuring that emergency aircraft always receive immediate access to the runway.

The design was developed and verified using Xilinx ISE 14.7 and ISim Simulator.

---

## Features

- Priority-based runway allocation
- Emergency aircraft handling
- Landing request handling
- Takeoff request handling
- Single-runway arbitration
- Behavioral simulation verification

---

## Priority Order

The runway is allocated according to the following priority:

1. Emergency Landing
2. Normal Landing
3. Takeoff

This ensures that safety-critical operations are always serviced first.

---

## Inputs

| Signal | Description |
|----------|----------|
| clk | System Clock |
| rst | System Reset |
| emergency_req | Emergency Landing Request |
| landing_req | Normal Landing Request |
| takeoff_req | Takeoff Request |

---

## Outputs

| Signal | Description |
|----------|----------|
| emergency_grant | Emergency Landing Approved |
| landing_grant | Landing Approved |
| takeoff_grant | Takeoff Approved |

---

## Working Principle

### Scenario 1: Takeoff Request

Input:

takeoff_req = 1

Output:

takeoff_grant = 1

---

### Scenario 2: Landing Request

Input:

landing_req = 1

Output:

landing_grant = 1

---

### Scenario 3: Emergency Landing

Input:

emergency_req = 1

Output:

emergency_grant = 1

---

### Scenario 4: Simultaneous Requests

Input:

emergency_req = 1
landing_req = 1
takeoff_req = 1

Output:

emergency_grant = 1
landing_grant = 0
takeoff_grant = 0

The emergency aircraft receives immediate runway access.

---

## Tools Used

- Verilog HDL
- Xilinx ISE 14.7
- ISim Simulator

---

## Project Files

- airport_runway_controller.v → RTL Design
- airport_runway_controller_tb.v → Testbench
- waveform.png → Simulation Results

---

## Simulation Results

The design was verified through behavioral simulation.

Verified functionality:

- Emergency request priority
- Landing request servicing
- Takeoff request servicing
- Simultaneous request arbitration
- Reset operation

---

## Concepts Learned

- RTL Design
- Priority Arbitration
- Digital Control Logic
- Sequential Logic
- Verilog HDL
- Functional Verification
- Resource Allocation

---

## Future Improvements

- Runway Busy State
- Aircraft Waiting Queue
- Multiple Runway Support
- Emergency Preemption Logic
- Aircraft Scheduling Algorithm
- Air Traffic Control Integration
- FPGA Hardware Implementation

---

## Author

Abhiram Manoj

Electronics and Communication Engineering
