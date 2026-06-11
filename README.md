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

