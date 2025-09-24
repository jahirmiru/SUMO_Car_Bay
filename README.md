# 🚗 SUMO Car Bay Simulator
Simulating a dynamic car bay environment using SUMO with randomly generated vehicle routes.


## ✨ Features

*   🛣️ **Dynamic Route Generation:** Automatically creates random vehicle routes for a diverse simulation experience.
*   🚦 **SUMO Integration:** Leverages the powerful SUMO (Simulation of Urban MObility) platform for realistic traffic flow and behavior.
*   🔄 **Configurable Environment:** Easily adjust network and simulation parameters through XML configuration files.
*   📈 **Scalable Simulation:** Designed to handle varying numbers of vehicles and complex traffic scenarios within the defined corridor.
*   🐍 **Python-driven Logic:** Utilizes Python for route generation, offering flexibility and extensibility for custom scenarios.


## 🚀 Installation Guide

To get this project up and running, you'll need Python and SUMO installed on your system.

### Prerequisites

*   **Python 3.x:** Ensure you have Python installed. You can download it from [python.org](https://www.python.org/downloads/).
*   **SUMO:** Download and install SUMO from the official website: [sumo.dlr.de](https://sumo.dlr.de/docs/Installing.html). Make sure `SUMO_HOME` environment variable is set correctly, pointing to your SUMO installation directory.

### Step-by-Step Setup

1.  **Clone the Repository:**
    First, clone the project repository to your local machine using Git:

    ```bash
    git clone https://github.com/jahirmiru/SUMO_Car_Bay.git
    cd SUMO_Car_Bay
    ```

2.  **Install Python Dependencies:**
    This project primarily uses `sumolib` and `traci` which are part of the SUMO distribution. Ensure your `PYTHONPATH` includes the `tools` directory of your SUMO installation.

    ```bash
    # Example for Linux/macOS (add to your .bashrc or .zshrc)
    export SUMO_HOME="/path/to/your/sumo/installation"
    export PYTHONPATH="$PYTHONPATH:$SUMO_HOME/tools"

    # Example for Windows (set via System Properties -> Environment Variables)
    # SUMO_HOME = C:\path\to\your\sumo\installation
    # PYTHONPATH = %PYTHONPATH%;%SUMO_HOME%\tools
    ```

    You might also need to install `lxml` if your SUMO tools rely on it and it's not pre-installed:

    ```bash
    pip install lxml
    ```


## 🎮 Usage Examples

This project involves two main steps: generating the vehicle routes and then running the SUMO simulation.

1.  **Generate Random Routes:**
    Execute the Python script to create the `trips.rou.xml` file, which defines the vehicle routes for the simulation.

    ```bash
    python generate_routes.py
    ```
    This script will output a `trips.rou.xml` file based on the `corridor.net.xml` network.

2.  **Run the SUMO Simulation:**
    Once the routes are generated, you can start the SUMO simulation using the provided configuration file.

    ```bash
    sumo-gui -c sumo_config.sumocfg
    ```
    This command will open the SUMO-GUI, allowing you to visualize the car bay simulation in real-time. If you prefer a command-line simulation without GUI, use `sumo -c sumo_config.sumocfg`.

### Project Files

*   `corridor.net.xml`: Defines the road network for the car bay.
*   `generate_routes.py`: Python script to create random vehicle routes.
*   `sumo_config.sumocfg`: Main SUMO configuration file that links the network and routes.
*   `sumo_options.xml`: Additional SUMO simulation options.
*   `trips.rou.xml`: (Generated) Contains the randomly created vehicle routes.


## 🗺️ Project Roadmap

Our goal is to continually enhance the realism and utility of the SUMO Car Bay simulation.

*   **Version 1.1 (Planned):**
    *   Add basic traffic light logic within the corridor.
    *   Implement more sophisticated random route generation, including variable departure times.
    *   Introduce basic parking logic within the car bay area.
*   **Future Enhancements:**
    *   Integrate demand modeling for more realistic traffic patterns.
    *   Develop a web-based visualization dashboard for real-time monitoring.
    *   Explore reinforcement learning agents for dynamic traffic management.
    *   Expand the network to include multiple car bay entrances/exits.


## 🤝 Contribution Guidelines

We welcome contributions from the community! To ensure a smooth collaboration, please follow these guidelines:

*   **Fork the Repository:** Start by forking the `SUMO_Car_Bay` repository to your GitHub account.
*   **Create a Feature Branch:** For any new feature or bug fix, create a dedicated branch from `main`. Use descriptive names like `feature/add-parking-logic` or `bugfix/fix-route-bug`.
*   **Code Style:** Adhere to PEP 8 for Python code. Ensure your code is clean, well-commented, and easy to understand.
*   **Commit Messages:** Write clear and concise commit messages that explain the purpose of your changes.
*   **Pull Request Process:**
    *   Open a Pull Request (PR) to the `main` branch of this repository.
    *   Provide a detailed description of your changes, including any relevant screenshots or usage examples.
    *   Link to any related issues if applicable.
    *   Ensure all existing tests pass, and add new tests for new features if appropriate.
*   **Testing:** Before submitting a PR, please run the simulation locally to verify your changes work as expected.


## 📄 License Information

This project is currently released without a specific license.

**No License:** This means that by default, all rights are reserved by the copyright holder (`jahirmiru`). You are not permitted to use, modify, or distribute this software without explicit permission.

For any inquiries regarding usage or licensing, please contact the main contributor.

---
Copyright © 2025 jahirmiru. All rights reserved.
