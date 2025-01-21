# ft_services

Hey there! Welcome to **ft_services**, a 42 project where **you** get hands-on with **virtualization** and **container orchestration** using **Kubernetes**. You’ll set up a **multi-service** infrastructure on a single node (via Minikube), with each service running in its own **Docker container**. By the end, you’ll have a functioning mini cluster, complete with networking, storage, and security configurations—all living in containers that work together seamlessly.

---

## Project Overview

### Objectives
- **Discover Kubernetes**: Learn the basics of deployments, services, and load balancing in a containerized environment.  
- **Containerization**: Build Docker images for several applications (web server, database, etc.).  
- **Networking**: Use MetalLB or a similar load balancer to manage traffic across different services.  
- **Security**: Configure HTTPS (SSL/TLS certificates) and protect communications between components.  
- **Automation**: Manage the environment through YAML configuration files for deployments and services.

---

## Main Components

You’ll typically deploy and configure the following (depending on your subject requirements):

1. **Nginx**  
   - Web server acting as a reverse proxy and load balancer.  
   - Often set up with SSL/TLS certificates for HTTPS.

2. **WordPress**  
   - A popular CMS running behind Nginx.  
   - Connects to a MySQL or MariaDB database.

3. **phpMyAdmin**  
   - Web interface to manage the MySQL/MariaDB database.  
   - Also runs behind the Nginx reverse proxy.

4. **MySQL or MariaDB**  
   - Relational database used by WordPress and phpMyAdmin.  
   - Deployed in its own container with persistent storage.

5. **FTP Server (e.g., vsftpd)**  
   - Provides file transfer capabilities.  
   - Can be configured with SSL certificates.

6. **InfluxDB & Telegraf**  
   - InfluxDB is a time-series database; Telegraf collects metrics.  
   - Useful for monitoring container performance data.

7. **Grafana**  
   - Visualization platform that reads data from InfluxDB.  
   - Creates dashboards for CPU usage, memory consumption, etc.
