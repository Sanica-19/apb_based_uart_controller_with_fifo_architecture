# APB-Based UART Controller with FIFO Architecture

## **Overview**

This project presents the RTL design and functional verification of an APB-Based UART Controller integrated with TX and RX FIFO architecture using Verilog HDL. The design enables reliable asynchronous serial communication between a processor and peripheral devices through the AMBA APB protocol while improving throughput and minimizing data loss using FIFO buffering.

The complete design was developed as a major academic project and functionally verified through simulation using Icarus Verilog and GTKWave. The modular architecture emphasizes scalability, efficient data handling, and ease of integration into embedded and SoC-based applications.

## **Project Objective**

- Design and verify an APB-based UART Controller using Verilog HDL.
- Enable efficient serial communication through dedicated TX and RX modules.
- Implement baud-rate generation for synchronized UART operation.
- Utilize FIFO architecture to improve throughput and minimize data loss.
- Validate end-to-end functionality using simulation and waveform analysis.
- Create a modular RTL design suitable for integration into modern FPGA and SoC platforms.

  ## **Design Highlights**

- APB-based communication interface
- UART Transmitter and Receiver implementation
- FIFO-based data buffering
- Accurate baud-rate generation
- Modular RTL design
- Functional verification through simulation

  ## **System Architecture**

The APB-Based UART Controller is composed of the following core modules:

- APB Slave Interface
- Baud Rate Generator
- UART Transmitter
- UART Receiver
- TX FIFO Buffer
- RX FIFO Buffer
- Top-Level Integration Module

The architecture seamlessly integrates APB communication, UART transmission/reception, baud-rate generation, and FIFO buffering to ensure reliable and efficient serial data transfer.

**Block Diagram**
![image alt](https://github.com/Sanica-19/apb_based_uart_controller_with_fifo_architecture/blob/aa712f7608571819b30f5305b59011fb2cb6a187/block%20diagram.jpeg)

## Data Flow

**Transmit Path:**

CPU → APB Slave → TX FIFO → UART TX → TXD

**Receive Path:**

RXD → UART RX → RX FIFO → APB Slave → CPU

**TX/RX Flowchart**
![image alt](https://github.com/Sanica-19/apb_based_uart_controller_with_fifo_architecture/blob/94133b29b9d865a17e3979be076d6d4df1a9ad9f/Tx%20and%20Rx%20flowchart.jpeg)

## **Module Overview**

### 1. APB Slave Interface

The APB Slave Interface serves as the communication bridge between the processor and the UART subsystem. It manages APB read and write transactions, decodes addresses, generates the required control signals, and coordinates data movement between the processor and internal modules.

---

### 2. Baud Rate Generator

The Baud Rate Generator produces timing pulses required for UART communication by dividing the system clock to the configured baud rate.

Working:
A clock divider divides the system clock according to:

Baud Divisor = Clock Frequency / Baud Rate

Example:

Clock Frequency = 50 MHz
Baud Rate = 115200
Divisor ≈ 434

The baud generator produces one baud_tick every 434 clock cycles

---

### 3. UART Transmitter (TX)

The UART Transmitter converts 8-bit parallel data into a serial bit stream following the UART communication protocol. It transmits the start bit, data bits, and stop bit in sequence while operating under the control of a finite state machine and baud-rate timing.

---

### 4. UART Receiver (RX)

The UART Receiver monitors incoming serial data, detects the start bit, samples the incoming bits at the appropriate baud intervals, and reconstructs the original parallel data. The received data is then forwarded to the receive FIFO for further processing.

---

### 5. TX FIFO Buffer

The TX FIFO acts as a temporary storage buffer for outgoing data before transmission. 

FIFO Configuration

- Data Width: 8 bits
- FIFO Depth: 16 entries
---

### 6. RX FIFO Buffer

The RX FIFO temporarily stores received data until it is accessed by the processor. This buffering mechanism improves communication reliability, prevents data loss, and supports efficient handling of continuous incoming data streams.

---

### 7. Top-Level Integration

The top-level module integrates all functional blocks into a unified architecture. It coordinates communication between the APB interface, baud generator, UART transmitter, UART receiver, and FIFO buffers to enable complete end-to-end serial data transfer and functional verification.

## Verification Summary

The implemented design was functionally verified through simulation to ensure reliable communication across all integrated modules. The validation process included:

* ✔ APB Read and Write Transactions
* ✔ Baud Rate Generation
* ✔ UART Data Transmission
* ✔ UART Data Reception
* ✔ TX/RX FIFO Operations
* ✔ End-to-End System Integration
* ✔ Waveform-Based Functional Analysis

---

## Potential Applications

The proposed architecture can be utilized in a variety of embedded and communication systems, including:

* Embedded SoC Platforms
* FPGA-Based Designs
* Industrial Automation Systems
* Biomedical Monitoring Devices
* Sensor Data Acquisition Systems
* Low-Power Communication Interfaces
* Serial Peripheral Communication Modules

---

## Development Environment

| Tool           | Purpose                      |
| -------------- | ---------------------------- |
| Verilog HDL    | RTL Design                   |
| ModelSim       | Functional Simulation        |
| Icarus Verilog | RTL Compilation & Simulation |
| GTKWave        | Waveform Analysis            |
| Git            | Version Control              |
| GitHub         | Source Code Management       |

---

## Future Enhancements

* Configurable UART Parameters
* Parity Error Detection
* Interrupt-Driven Communication
* Variable FIFO Depth
* FPGA Hardware Implementation
* UVM-Based Verification
* Multi-UART Support
* SoC-Level Integration

---

## Project Outcome

This project provided practical exposure to RTL design, APB protocol implementation, UART communication, FIFO architecture, finite state machine design, and functional verification. It also strengthened understanding of modular hardware design and waveform-based debugging techniques.



