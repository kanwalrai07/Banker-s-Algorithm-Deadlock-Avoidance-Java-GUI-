# Banker's Algorithm – Deadlock Avoidance (Java, GUI)

This repository contains a Java implementation of the **Banker's Algorithm** for deadlock avoidance in operating systems.  
It includes a simple GUI to visualize processes, resources, allocation, maximum demand, and safe/unsafe states.

---

### 📌 Features

- **Implementation of Banker's Algorithm**
  - Checks whether a given resource allocation state is **safe** or **unsafe**
  - Simulates resource **request** operations
- **GUI Frontend**
  - Forms/windows for:
    - Main control (`OSDC`, `OSD2`)
    - Need matrix visualization (`NeedMatrix`)
    - Resource request handling (`RequestWindow`)
- **Jar Distribution**
  - Runnable `.jar` located in the `dist` folder (`OSDC3.jar`)

---

### 📂 Project Structure

- `src/`
  - `BankersAlgorithm.java` – core implementation of the Banker's Algorithm
  - `OSDC.java`, `OSD2.java` – main GUI windows / control logic
  - `NeedMatrix.java` – GUI for displaying the need matrix
  - `RequestWindow.java` – GUI for handling resource requests
- `build/` – compiled `.class` files (generated)
- `dist/OSDC3.jar` – packaged runnable JAR
- `nbproject/` – NetBeans project configuration
- `build.xml` – Ant build script
- `manifest.mf` – manifest for JAR packaging

---

### ✅ Prerequisites

- **JDK 8+** installed  
- (Optional but recommended) **NetBeans** or any Java IDE that supports Ant projects

---

### 🚀 How to Run

#### Option 1: Run the JAR directly

1. Open a terminal / command prompt in the project folder:
  
   cd Implementation-of-Bankers-Algorithm-main
   2. Go into `dist` and run:
  
   cd dist
   java -jar OSDC3.jar
   3. The GUI should open. Use the interface to:
   - Set the number of processes and resources
   - Enter Allocation / Maximum / Available
   - Check for **safe state**
   - Simulate **resource requests**

#### Option 2: Open in NetBeans

1. Open **NetBeans**.
2. Use **File → Open Project...**.
3. Select the `Implementation-of-Bankers-Algorithm-main` directory.
4. Clean and build the project.
5. Run the main project (usually `OSDC` or the configured main class).

---

### 🧠 About Banker's Algorithm

Banker's Algorithm is a resource allocation and deadlock avoidance algorithm.  
It tests **“safety”** by checking whether all processes can finish without leading to a deadlock, given:
- Current **Allocation**
- **Maximum** demand
- Currently **Available** resources

The main steps:
1. Compute **Need = Max – Allocation**.
2. Try to find a sequence of processes such that:
   - Each process’s `Need` can be satisfied by current `Available` resources.
   - After a process finishes, its `Allocation` is added back to `Available`.
3. If such an ordering exists → **Safe State**; otherwise → **Unsafe State**.

---

### 🧪 Example Usage (Conceptual)

Define:
- `n` processes, `m` resource types
- Matrices:
  - `Allocation[n][m]`
  - `Max[n][m]`
  - `Available[m]`

Use the UI to:
- Input `Allocation`, `Max`, and `Available`
- Click the **Check Safe State** button (or equivalent)
- Observe whether the system is **SAFE** and the safe sequence (if implemented in the GUI)
- Use the **Request** window to simulate a process requesting additional resources and re-check if the state is safe

---

### 🛠️ Build from Source (Ant)

If you have Ant installed (often handled by NetBeans):

cd Implementation-of-Bankers-Algorithm-main
ant clean
ant jarThe updated runnable jar will appear in the `dist` folder.

---

### 📖 Related Material

This project is related to deadlock avoidance algorithms in Operating Systems.  
You may also find the included presentation helpful:

- `Deadlock-Avoidance-Algorithms-A-Java-Implementation.pptx`

---

### 📜 License

Add your preferred license here, for example:

This project is licensed under the MIT License – see the LICENSE file for details.(If you do not have a `LICENSE` file yet, you can create one on GitHub when publishing the repository.)

---

### 🙌 Contributions

Feel free to:
- Fork this repository
- Open issues for bugs or suggestions
- Submit pull requests to improve the GUI, documentation, or algorithm implementation
