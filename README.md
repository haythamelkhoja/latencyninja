# Latency Ninja

Latency Ninja is a versatile wrapper tool built around `tc/netem`, designed to empower you with the ability to finely simulate network conditions on a specified network interface for a destination IP address. It goes beyond standard network emulation, allowing you to introduce latency, jitter, corruption, duplication, reordering, and packet loss to both ingress and egress traffic. The key advantage of Latency Ninja is its capacity to circumvent the limitations of `tc/netem` which natively applies network conditions only on egress to be able to simulate real life egress and ingress network conditions.

## Key Features

- **Latency Simulation**: Precisely control network delay, enabling you to mimic real-world scenarios with adjustable latency settings.
- **Jitter**: Introduce variability to latency, replicating the unpredictable nature of network traffic.
- **Corruption**: Safely corrupt a defined percentage of packets to assess network resilience.
- **Duplication**: Duplicate packets to evaluate network performance under data replication scenarios.
- **Reordering**: Test how your applications handle out-of-sequence packets with customizable reordering.
- **Packet Loss**: Simulate packet loss, a crucial factor in assessing application robustness.
- **Ingress and Egress Traffic**: Apply conditions to both incoming and outgoing traffic for comprehensive testing.

## Getting Started

To get started, clone this repository and follow the installation instructions in the provided [README](#link-to-readme). Latency Ninja is compatible with Red Hat/CentOS/Fedora/Debian/Ubuntu Linux-based systems and requires superuser privileges to run.


## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

1. Make sure you have `tc` and `netem` installed on your system.
3. Root or superuser privileges are required to run the script.

## Installation

1. Clone this repository:

    git clone https://github.com/haythamelkhoja/latencyninja
    
2. Navigate to the directory

	cd latencyninja

3. Give executable permissions to the script
    chmod +x latency_ninja.sh

 ## Usage

    ./latency_ninja.sh [OPTIONS]
        
    Options:
    -i: The network interface (e.g., eth0). This is mandatory.
    -d: Destination IP address. This is mandatory if latency or jitter are applied.
    -l: Latency in milliseconds.
    -j: Jitter in milliseconds.
    -c: Corruption in percentage.
    -u: Duplication in percentage.
    -r: Reorder in percentage.
    -p: Packet loss in percentage.
    -R: Rollback/Revert the applied network conditions.

## Example
Example: To simulate 100ms latency, 10ms jitter, and 5% packet loss on the eth0 interface for traffic going to 192.168.1.10, run:

    ./latency_ninja.sh -i eth0 -d 192.168.1.10 -l 100 -j 10 -p 5

## Troubleshooting
 - Permission Denied: Make sure you're running the script with superuser privileges.
 - Interface Error: Ensure that the provided network interface exists and is up.
 - Missing Parameters: Always ensure that mandatory parameters like -i and -d are provided, especially when using -l or -j.

## Contributing
We welcome contributions! If you'd like to contribute, please create a pull request with your changes.

## License
This project is licensed under the GNU General Public License v2.0. Please refer to the LICENSE file for more details.

