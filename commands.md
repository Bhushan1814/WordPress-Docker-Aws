# Docker WordPress Project — Commands

## 1. Update the System

```bash
sudo dnf update -y
```

## 2. Install Docker

```bash
sudo dnf install docker -y
sudo systemctl enable --now docker
sudo systemctl status docker
```

## 3. Verify Docker

```bash
docker --version
sudo docker ps
```

## 4. Download the Images

```bash
sudo docker pull mysql:8.0
sudo docker pull wordpress:latest
```

## 5. Check Containers

```bash
sudo docker ps
sudo docker ps -a
```

## 6. Check Docker Networks

```bash
sudo docker network ls
```

## 7. Check Docker Images

```bash
sudo docker images
```

## 8. Check Container Logs

```bash
sudo docker logs <container_name>
```

## 9. Stop and Start Containers

```bash
sudo docker stop <container_name>
sudo docker start <container_name>
```

## 10. Verify Docker Networking

```bash
sudo docker inspect <container_name>
```

## Important Notes

* Replace `<container_name>` with your actual container name.
* These are reference and troubleshooting commands, not a complete deployment script.
* Document the actual container creation commands you used in your project.
* Never upload database passwords, private keys, AWS access keys, or other secrets.

