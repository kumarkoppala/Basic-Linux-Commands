# 🌐 Networking Tools

Commands used to check server communication, test API endpoints, download assets, and verify port listeners.

## 1. curl
* **Purpose:** Transfers data from or to a server using supported protocols (HTTP, HTTPS, FTP, etc.).
* **DevOps Context:** Testing REST APIs, validating ingress rules, or running health checks on endpoints.
* **Syntax:** `curl [options] <URL>`
* **Examples:**
  ```bash
  # Test an endpoint and get raw body
  curl https://github.com

  # View only HTTP response headers (-I)
  curl -I https://example.com
  ```

## 2. wget
* **Purpose:** Non-interactive network downloader.
* **DevOps Context:** Downloading software binaries, tarballs, or installer scripts directly inside Dockerfiles or VM provisioning scripts.
* **Syntax:** `wget [options] <URL>`
* **Example:**
  ```bash
  wget https://hashicorp.com
  ```

## 3. netstat
* **Purpose:** Displays network connections, routing tables, and interface statistics.
* **DevOps Context:** Finding out which process or service is blocking a required port (like 80 or 8080).
* **Syntax:** `netstat [options]`
* **Example:**
  ```bash
  # List all listening ports (-l) with numeric addresses (-n) and process IDs (-p)
  sudo netstat -tlnp
  ```

## 4. ping
* **Purpose:** Sends ICMP ECHO_REQUEST packets to network hosts to test reachability.
* **DevOps Context:** Quick checks to confirm if an internal database server or external API gateway is live.
* **Syntax:** `ping [options] <host>`
* **Example:**
  ```bash
  # Send exactly 4 packets (-c) to a domain
  ping -c 4 google.com
  ```
