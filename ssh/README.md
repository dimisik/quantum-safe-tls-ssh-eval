# quantum-safe-tls-ssh-eval

## Overview

This repository contains scripts for evaluating Post-Quantum (PQ) authentication and key exchange mechanisms in SSH. These scripts automate the installation, configuration, and testing of quantum-safe cryptographic algorithms in SSH environments.

## Scripts

### 1. **auto_install_ssh**

- **Description:** Automates the installation of `liboqs` and OQS `openssh`.
- **Purpose:** Simplifies the setup process for integrating PQ algorithms into the SSH protocol.

### 2. **loop_ssh_client_control**

- **Description:** Runs a client loop for SSH establishment.
- **Input:** Number of iterations.
- **Purpose:** Acts as a control group for benchmarking SSH handshake times without PQ algorithms.

### 3. **loop_ssh_client_x_y**

- **Description:** Runs a client loop for SSH establishment using specified PQ algorithms.
- **Input:** Number of iterations, PQ authentication algorithm (x), PQ key exchange algorithm (y).
- **Purpose:** Tests SSH handshake times with different combinations of PQ authentication and key exchange algorithms.

### 4. **other_procedures_notes_x**

- **Description:** Contains commands for key generation at the server and client.
- **Input:** PQ authentication algorithm (x).
- **Purpose:** Provides necessary commands and procedures for generating keys using specified PQ algorithms.

### 5. **tshark_config_run_ssh**

- **Description:** Contains the `tshark` command for packet capture during SSH sessions.
- **Purpose:** Captures network packets to analyze SSH handshakes and other relevant metrics.

### 6. **handshake_time_ssh**

- **Description:** A Python script for measuring SSH handshake time by parsing `tshark` trace files.
- **Purpose:** Automates the analysis of handshake times to evaluate the performance of different PQ algorithms.

## Usage

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/quantum-safe-tls-ssh-eval.git
    cd quantum-safe-tls-ssh-eval
    ```

2. Run the automated installation script:
    ```bash
    ./auto_install_ssh
    ```

### Running Tests

1. **Control Group:**
    ```bash
    ./loop_ssh_client_control --iterations 100
    ```

2. **With PQ Algorithms:**
    ```bash
    ./loop_ssh_client_x_y --iterations 100 --auth_alg pq_auth_alg --kex_alg pq_kex_alg
    ```

3. **Key Generation:**
    ```bash
    ./other_procedures_notes_x --auth_alg pq_auth_alg
    ```

### Packet Capture

1. Start the packet capture:
    ```bash
    ./tshark_config_run_ssh --file capture.pcap --port 2221
    ```

### Analyzing Handshake Times

1. Measure SSH handshake times:
    ```bash
    ./handshake_time_ssh --file capture.pcap
    ```
