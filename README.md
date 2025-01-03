# Intra-Domain Routing Protocol Implementation

This project implements variants of intra-domain routing protocols (Distance Vector and Link-State) for a network simulator.

## Features

1. **Distance Vector Protocol (DV)**:
    - Implements the poison reverse variant.
    - Supports periodic and triggered updates.
    - Handles link failures and recovers on reconnections.

2. **Link-State Protocol (LS)**:
    - Implements flooding of link-state updates with sequence number management.
    - Computes shortest paths using Dijkstra's algorithm.
    - Manages periodic and triggered updates efficiently.

3. **Neighbor Detection**:
    - Uses PING and PONG packets to identify neighbors and measure round-trip time.
    - Automatically updates neighbor statuses and handles timeouts.

4. **Packet Handling**:
    - Supports DATA, PING, PONG, DV, and LS packets.
    - Updates a forwarding table dynamically to forward DATA packets efficiently.

## Project Structure

- **RoutingProtocolImpl.h / RoutingProtocolImpl.cc**: Contains the implementation of the routing protocols.
- **Node.h**: Interfaces for interacting with the network simulator.
- **global.h**: Defines constants and utility functions.
- **Makefile**: For compiling the simulator and the protocol implementation.
- **Test Files**: Configuration and output files for testing.

## How to Compile

1. Extract the project files:
   ```bash
   tar xf Intra-Domain-RoutingProtocol.tar
   ```
2. Navigate to the project directory:
   ```bash
   cd project3
   ```
3. Compile the code using the provided Makefile:
   ```bash
   make
   ```

## How to Run

1. Use the simulator executable with a configuration file and the desired protocol:
   ```bash
   ./simulator <config-file> DV|LS
   ```
- Replace <config_file> with the path to a configuration file.
- Use **DV** for the Distance Vector protocol and **LS** for the Link-State protocol.

2. **Example**: To run the simulator with the simpletest1 configuration using the DV protocol:
    ```bash
    ./simulator simpletest1 DV
    ```

3. Redirect the output for easier debugging:
   ```bash
   ./simulator simpletest1 DV > output.txt
   ```

## Testing

- **Included Tests**:
    - `simpletest1` and `simpletest2` configurations are provided for basic verification.

- **Custom Tests**:
    - Create new configurations to simulate complex scenarios such as link failures or delay changes.
    - Test the robustness of routing protocols in dynamic network environments.

## File Descriptions

- **RoutingProtocolImpl.h / RoutingProtocolImpl.cc**:
    - Contains the main implementation for handling routing logic.
    - Includes methods for sending PING/PONG, computing shortest paths, and maintaining routing tables.

- **global.h**:
    - Defines constants for packet types, protocol types, and other utilities.

- **Makefile**:
    - Automates the build process.

- **Test Configurations**:
    - Used to simulate different network topologies and events.

## Notes

- Ensure the implementation conforms to the provided specifications for message formats, timing, and behavior.
- The Makefile ensures that the code compiles without warnings on supported systems.
