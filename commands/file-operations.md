# 📂 File Operations

Essential commands for navigating, creating, modifying, and cleaning the Linux filesystem.
## 1. ls
* **Purpose:** To list the files and direcotories
* **Devops Context:** Verifies build artifacts, checks deployment files, and inspects script permissions inside CI/CD pipelines.
* **Syntax:** ls [options] [directory]
* **Example:**
  ``bash
  # to list all the files including hidden
  ls -a
  # to list the files in reverse timestap with latest accessed/modified at the bottom
  
## 1. touch
* **Purpose:** Creates an empty file or updates the access/modification timestamp of an existing file.
* **DevOps Context:** Creating configuration templates or empty flag files in automation scripts.
* **Syntax:** `touch <filename>`
* **Example:**
  ```bash
  touch template.env
  ```

## 2. mkdir
* **Purpose:** Creates one or more directories.
* **DevOps Context:** Setting up structured deployment paths or log directories during pipeline execution.
* **Syntax:** `mkdir [options] <directory_name>`
* **Example:**
  ```
  ```bash
  # -p creates nested parent directories if they don't exist
  mkdir -p /opt/myapp/logs/archive
  ```

## 3. cp
* **Purpose:** Copies files or directories.
* **DevOps Context:** Backing up production configurations before modifying them.
* **Syntax:** `cp [options] <source> <destination>`
* **Examples:**
  ```bash
  # Backup a single file
  cp nginx.conf nginx.conf.bak

  # Copy a directory recursively (-r)
  cp -r /var/www/html /var/www/html_backup
  ```

## 4. mv
* **Purpose:** Moves or renames files and directories.
* **DevOps Context:** Archiving old builds, renaming context files, or shifting artifacts to target deployment folders.
* **Syntax:** `mv <source> <destination>`
* **Example:**
  ```bash
  mv target/app-v1.0.jar /opt/production/app.jar
  ```

## 5. rm
* **Purpose:** Removes (deletes) files or directories.
* **DevOps Context:** Clearing out temporary caches or workspace directories post-build to save disk space.
* **⚠️ Warning:** Always check paths before executing recursive force deletes.
* **Examples:**
  ```bash
  # Delete a specific file
  rm debug.log

  # Force delete a directory recursively (-rf)
  rm -rf /tmp/workspace/

  # For deleting empty directory
  rmdir workspace/
  ```
  
