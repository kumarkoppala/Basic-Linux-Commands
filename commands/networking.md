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
  
## 5. ip addr (Modern) / ifconfig (Legacy)
* **Purpose:** Displays and configures network interfaces, IP addresses, and routing properties.
* **DevOps Context:** Checking the private or public IP addresses assigned to a Virtual Machine or container environment.
* **⚠️ DevOps Note:** `ifconfig` belongs to the deprecated `net-tools` package. Modern enterprise environments expect you to use `ip addr` (from `iproute2`).
* **Examples:**
  ```bash
  # The modern standard to view all active network interfaces and IPs
  ip addr show
  
  # The legacy command (may require installing net-tools)
  ifconfig
  ```
## 6. traceroute
* **Purpose:** Tracks and prints the route (the sequence of network routers/hops) that packets take to reach a destination host.
* **DevOps Context:** Troubleshooting complex network routing drops, finding network bottlenecks, or debugging AWS VPC peering and VPN tunnel connections.
* **Syntax:** `traceroute <host>`
* **Example:**
  ```bash
  traceroute api.production.internal
  ```

## 7. ssh (Secure Shell)
* **Purpose:** A secure protocol to log into and execute commands on a remote Linux server or virtual instance.
* **DevOps Context:** Accessing cloud instances (like AWS EC2, GCP VMs) manually to debug environment states or manage configuration patches.
* **Syntax:** `ssh -i <private_key.pem> user@remote_host`
* **Examples:**
  ```bash
  # Connect to a remote server using password authentication or default keys
  ssh ubuntu@192.168.1.50

  # Connect to a cloud instance securely using a specific private SSH identity key file (-i)
  ssh -i ~/.ssh/production-key.pem ec2-user@10.0.1.25
  ```
## 8. nslookup (Name Server Lookup)
* **Purpose:** Queries internet name servers interactively or non-interactively to find IP addresses associated with a hostname, or vice versa.
* **DevOps Context:** Double-checking internal DNS resolution within virtual private clouds (VPCs) or performing a quick reverse IP lookup.
* **Syntax:** `nslookup <domain_name>`
* **Examples:**
  ```bash
  # Standard DNS lookup to find the IP of a domain
  nslookup application.local
  
  # Reverse DNS lookup (finding the hostname from a known IP)
  nslookup 192.168.1.10
  ```
## 9. dig (Domain Information Groper)
* **Purpose:** Queries DNS name servers for information about host addresses, mail exchanges, and name servers.
* **DevOps Context:** Diagnosing DNS propagation issues, verifying Route 53 records, or checking if a new domain points to the correct load balancer IP.
* **Syntax:** `dig <domain_name> [record_type]`
* **Examples:**
  ```bash
  # Look up the standard A record (IP address) for a domain
  dig google.com
  
  # Check for specific record types like TXT (used for verification) or MX (mail)
  dig google.com TXT
  ```

## 10. telnet
* **Purpose:** An old protocol used for interactive bidirectional text-oriented communication, now mostly used to test raw port connectivity.
* **DevOps Context:** A quick, reliable way to check if a specific firewall port is open on a target server before configuring complex application traffic.
* **Syntax:** `telnet <host> <port>`
* **Example:**
  ```bash
  # Test if a remote database port (MySQL) is reachable and open
  telnet database.internal.net 3306
  ```

