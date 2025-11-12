# Tableau Server Topology Planner

This is a standalone HTML web application designed to help Tableau Server administrators plan, design, and validate server topologies.

Based on the official Tableau Server documentation and architecture playbooks, this tool allows you to build a visual plan for your deployment, ensuring it aligns with known best practices.

## Key Features:

* **Dynamic Grid:** Set the number of nodes (from 1 to 20) and the app will instantly build a topology planning grid.

* **Process & Core Planning:** Assign a core count and a specific number of processes (e.g., VizQL Server, Backgrounder, etc.) to each node.

* **Real-time Validation:** A "Best Practices & Alerts" panel automatically checks your configuration against rules from the Tableau Architecture Playbook. It provides instant feedback if a node is over-provisioned, if you're missing a recommended process, or if you exceed limits (e.g., max Cache Servers).

* **Automatic Dependency Logic:** The planner is smart. If you add a process like `vizqlserver`, the app will automatically add and disable the `hyper` (Data Engine) process on that node, mimicking Tableau's real-world co-location behavior.

* **Node Templates & Copying:**
    * Apply pre-built templates (e.g., "Analytics Node," "Backgrounder Node," "HA Main Node") to any node.
    * Instantly copy one node's entire configuration to any other node.

* **Save & Share Configurations:**
    * **Export:** Save your complete topology plan (node count, core counts, and all processes) to a JSON file.
    * **Import:** Load a previously exported JSON file to resume your planning.

* **Two Views:**
    * **Input View:** Use number inputs to design your configuration.
    * **Graphic View:** Toggle to a read-only view that visualizes your process counts with green checkmarks, similar to the topology graphic in Tableau's `workgroup.yml`.

* **Built-in Documentation:** Hover over any process name to see a detailed tooltip with its official **Purpose**, **Licensing** status, and **Notes** from the Tableau Help site.
