# ft_services

**ft_services** is a project from the 42 curriculum designed to introduce you to **virtualization** and **container orchestration** using **Kubernetes**. The goal is to set up a **multi-service** infrastructure on a single node (via Minikube), where each service runs in its own **Docker container**. You’ll learn how to configure and link these containers to work together, and how to manage networking, storage, and security within a small, self-contained Kubernetes cluster.

---

## Project Overview

### Objectives
- **Discover Kubernetes**: Understand the basics of deployments, services, and load balancing in a containerized environment.
- **Containerization**: Build Docker images for several applications (web server, database, etc.).
- **Networking**: Use MetalLB or a similar load balancer to distribute traffic across different services.
- **Security**: Configure HTTPS (SSL/TLS certificates) and secure communications between components.
- **Automation**: Manage your environment using YAML configuration files for deployments and services.

---

## Main Components

Typically, ft_services involves deploying the following components (though the exact requirements might differ based on your project instructions):

1. **Nginx**  
   - Web server serving as a reverse proxy and load balancer.  
   - Often configured with SSL/TLS certificates for HTTPS.

2. **WordPress**  
   - A popular CMS (Content Management System) running behind Nginx.  
   - Connects to a MySQL or MariaDB database.

3. **phpMyAdmin**  
   - A web interface for managing the MySQL/MariaDB database.  
   - Also runs behind the Nginx reverse proxy.

4. **MySQL or MariaDB**  
   - Relational database used by WordPress and phpMyAdmin.  
   - Typically running in its own container, with persistent storage.

5. **FTP Server (e.g., vsftpd)**  
   - Provides file transfer capabilities.  
   - Configured with proper SSL certificates.

6. **InfluxDB & Telegraf**  
   - Time-series database (InfluxDB) and metric collection (Telegraf) for monitoring.  
   - Stores container performance metrics and system stats.

7. **Grafana**  
   - Visualization tool to monitor and graph data from InfluxDB.  
   - Provides dashboards for CPU usage, memory consumption, etc.
