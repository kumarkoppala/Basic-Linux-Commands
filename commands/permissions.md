# 🔒 Permissions & Ownership

Commands crucial for enforcing security policies, fixing execution bugs, and setting proper access layers.

## 1. chmod (Change Mode)
* **Purpose:** Changes the access permissions of file system objects (read, write, execute).
* **DevOps Context:** Making automation shell scripts (`.sh`) executable before running them in a CI/CD pipeline stage.
* **Syntax:** `chmod <permissions> <filename>`
* **Examples:**
  ```bash
  # Give execution permission (+x) to the user/owner
  chmod +x deploy.sh
  chmod -R u+rwx,g+r-x,o+r /path/to/your/folder

  # Explicit permission setting (Read/Write for owner, Read for group/others)
  chmod 644 config.json
  ```

## 2. chown (Change Owner)
* **Purpose:** Changes the user and/or group ownership of a file or directory.
* **DevOps Context:** Correcting file access rights for web servers (e.g., Nginx running as user `www-data`) or container storage paths.
* **Syntax:** `chown [options] user:group <path>`
* **Example:**
  ```bash
  # Recursively (-R) change ownership to nginx user and group
  sudo chown -R www-data:www-data /var/www/html
  ```
