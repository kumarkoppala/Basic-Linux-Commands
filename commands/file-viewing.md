# 📄 File Content Viewing & Log Inspection

Commands used to view, monitor, and inspect file outputs—critical for debugging microservices and applications.

## 1. cat
* **Purpose:** Concatenates and displays the full contents of a file to the standard output.
* **DevOps Context:** Quickly viewing small configuration files or verifying environment variables.
* **Syntax:** `cat <filename>`
* **Example:**
  ```bash
  cat /etc/hostname
  ```

## 2. head
* **Purpose:** Displays the first few lines (default is 10) of a file.
* **DevOps Context:** Checking headers of a CSV file or the initial initialization logs of a process.
* **Syntax:** `head [options] <filename>`
* **Example:**
  ```bash
  # View the first 20 lines of a script
  head -n 20 setup.sh
  ```

## 3. tail
* **Purpose:** Displays the last few lines (default is 10) of a file.
* **DevOps Context:** Live debugging of application errors by streaming log updates.
* **Syntax:** `tail [options] <filename>`
* **Examples:**
  ```bash
  # View the last 50 lines of an error log
  tail -n 50 error.log

  # Follow/stream new log entries in real-time (-f)
  tail -f /var/log/nginx/access.log
  # Both head and tail combined example
  #Strip both a header and a footer from a file
   tail -n +3 file.txt | head -n -3

  ```

## 4. less
* **Purpose:** Opens file content page-by-page, allowing backward and forward navigation without loading the entire large file into memory.
* **DevOps Context:** Reading massive server or system logs safely.
* **Syntax:** `less <filename>`
* **Controls:** `Space` (Page Down), `B` (Page Up), `/text` (Search for text), `Q` (Quit).
* **Example:**
  ```bash
  less /var/log/syslog
  ```
