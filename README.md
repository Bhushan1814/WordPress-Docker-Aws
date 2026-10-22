# WordPress Application Deployment Using Docker on AWS EC2

## 📌 Project Overview

This project demonstrates how to deploy a WordPress application on an AWS EC2 instance using Docker containers. WordPress and MySQL are deployed in separate containers, allowing the application and database to run independently and communicate through Docker networking.

The project provides hands-on experience with containerization, cloud infrastructure, Linux administration, Docker networking, and application deployment.

## 🎯 Objectives

* Deploy a WordPress application on AWS EC2.
* Run WordPress and MySQL in separate Docker containers.
* Configure container-to-container communication.
* Expose the WordPress website through the EC2 public IP.
* Understand Docker port mapping, networking, and container management.
* Document the deployment process using GitHub.

## 🛠️ Technologies Used

| Technology        | Purpose                                    |
| ----------------- | ------------------------------------------ |
| AWS EC2           | Cloud server for hosting the application   |
| Amazon Linux 2023 | Operating system                           |
| Docker            | Containerization platform                  |
| WordPress         | Website and content management application |
| MySQL             | Database for WordPress                     |
| Docker Networking | Communication between containers           |
| Git & GitHub      | Version control and project documentation  |

## ⚙️ Implementation Steps

### 1. Launch an AWS EC2 Instance

* Launch an EC2 instance using Amazon Linux 2023.
* Configure SSH access for administration.
* Configure the security group to allow SSH from your trusted IP and HTTP traffic on port 80.

### 2. Install and Start Docker

Update the system and install Docker using the appropriate package commands for your EC2 instance.

```bash
sudo dnf update -y
sudo dnf install docker -y
sudo systemctl enable --now docker
sudo systemctl status docker
```

### 3. Download the Required Docker Images

```bash
sudo docker pull wordpress:latest
sudo docker pull mysql:8.0
```

### 4. Configure the Containers

* Create the MySQL container with the required database and credentials.
* Create the WordPress container with the appropriate database connection settings.
* Configure a Docker network so both containers can communicate.
* Map host port 80 to the WordPress container's port 80.
* Keep MySQL port 3306 private to the Docker network.

> Use secure passwords and never publish database credentials, `.env` files, SSH private keys, or AWS access keys to GitHub.

### 5. Verify the Deployment

Check the running containers:

```bash
sudo docker ps
```

Check Docker networks:

```bash
sudo docker network ls
```

Check container logs when troubleshooting:

```bash
sudo docker logs <container_name>
```

### 6. Access WordPress

Open the following URL in your browser, replacing the placeholder with your EC2 instance's public IPv4 address:

```text
http://<EC2-Public-IP>
```

Complete the WordPress installation through the browser if it has not already been completed.

## 💡 Key Learnings

* Launching and configuring AWS EC2 instances.
* Installing and managing Docker on Linux.
* Working with Docker images and containers.
* Connecting WordPress with a MySQL database.
* Understanding Docker bridge networking and port mapping.
* Troubleshooting application and container issues.
* Documenting cloud projects using GitHub.

## 🔐 Security Considerations

* Restrict SSH access to trusted IP addresses.
* Do not expose MySQL port 3306 publicly.
* Use strong database credentials.
* Avoid committing secrets or private keys to version control.
* Use HTTPS and appropriate security controls for production deployments.

## 🚀 Future Improvements

* Use Docker Compose to manage multiple containers.
* Configure persistent Docker volumes for application and database data.
* Add an Application Load Balancer and Auto Scaling.
* Configure HTTPS using a valid TLS certificate.
* Implement monitoring and logging.
* Automate deployment using Jenkins CI/CD.

## 👨‍💻 Author

**Bhushan Jagtap**

Aspiring AWS Cloud / DevOps Engineer

* LinkedIn: [Bhushan Jagtap](https://www.linkedin.com/in/bhushansjagtap)
* GitHub: [Bhushan1814](https://github.com/Bhushan1814)

## ⭐ Conclusion

This project demonstrates practical experience deploying a WordPress application with Docker on AWS EC2. It helped build foundational skills in cloud computing, Linux, containerization, networking, and application deployment.
