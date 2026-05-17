# ⚙️ Process Management & System Performance

Essential commands for monitoring system resources, viewing running processes, and terminating misbehaving applications.

## 1. top
* **Purpose:** Displays a real-time, dynamic view of running system processes, CPU usage, memory consumption, and system load averages.
* **DevOps Context:** Diagnosing which microservice or container is causing high server load or running out of memory (OOM).
* **Syntax:** `top`
* **Interactive Shortcuts (Press while top is running):**
  * `M` - Sort processes by Memory usage.
  * `P` - Sort processes by CPU usage.
  * `q` - Quit the interactive view.
* **💡 Pro DevOps Tip:** Many engineers prefer `htop` if it is installed, as it provides a colorful, more user-friendly interface.

## 2. kill
* **Purpose:** Sends a specific termination signal to a process (usually to stop it) using its Process ID (PID).
* **DevOps Context:** Gracefully shutting down a stuck deployment worker or forcefully stopping a runaway script that refuses to close.
* **Syntax:** `kill [signal_option] <PID>`
* **Common Signals:**
  * `SIGTERM` (15): The default signal. Requests a clean, graceful shutdown so the app can save its state.
  * `SIGKILL` (9): Forceful termination. Instantly kills the process without letting it clean up. Use with caution.
* **Examples:**
  ```bash
  # Gracefully terminate a process with PID 1234
  kill 1234

  # Forcefully kill a frozen background process with PID 5678
  kill -9 5678
  ```
