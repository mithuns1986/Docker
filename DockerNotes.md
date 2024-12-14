# Mithun'S Docker Notes

## Installing Docker on any Linux Based OS

1. **Download and Install Docker**:
   ```bash
   curl -fsSL get.docker.com | bash
   ```

2. **Verify Docker Installation**:
   ```bash
   sudo docker -v
   sudo docker --version
   ```

---

## Basic Docker Commands

1. **Create and Navigate Directories**:
   ```bash
   mkdir docker
   cd docker/
   ```

2. **Check Docker Images**:
   ```bash
   sudo docker images
   ```

3. **Check Docker Service Status**:
   ```bash
   sudo systemctl status docker
   ```

4. **Start Docker Service**:
   ```bash
   sudo systemctl start docker
   ```

5. **Enable Docker Service on Boot**:
   ```bash
   sudo systemctl enable docker
   ```

6. **Pull an Image from Docker Hub**:
   ```bash
   sudo docker pull httpd:2.4
   ```

---

## Running and Managing Containers

1. **Run a Container**:
   ```bash
   sudo docker run -it --name webserver1 -p80:80 494b2b45fd74
   ```

2. **List Running Containers**:
   ```bash
   sudo docker ps
   ```

3. **List All Containers**:
   ```bash
   sudo docker ps -a
   ```

4. **Start a Stopped Container**:
   ```bash
   sudo docker start webserver1
   ```

5. **Stop a Running Container**:
   ```bash
   sudo docker stop webserver1
   ```

6. **Remove a Container**:
   ```bash
   sudo docker rm webserver1
   ```

---

## Networking in Docker

1. **List Docker Networks**:
   ```bash
   sudo docker network ls
   ```

2. **Inspect a Container’s Network**:
   ```bash
   sudo docker inspect webserver2 | grep -i network
   ```

---

## Building and Running Java Applications with Docker

1. **Navigate to Application Directory**:
   ```bash
   cd my-java-app/
   ```

2. **Build the Application**:
   ```bash
   mvn clean install
   ```

3. **Build a Docker Image**:
   ```bash
   vim Dockerfile
   sudo docker image build -t javaapp:maven .
   ```

4. **Run the Application in a Docker Container**:
   ```bash
   sudo docker run -itd --name javaapp -p8081:8080 javaapp:maven
   ```

5. **Tag and Push the Image to Docker Hub**:
   ```bash
   sudo docker image tag javaapp:maven mithundevopsaws/javaapp:1.0
   sudo docker login
   sudo docker push mithundevopsaws/javaapp:1.0
   ```

---

## Managing Docker Volumes

1. **List Docker Volumes**:
   ```bash
   sudo docker volume ls
   ```

2. **Create a Volume**:
   ```bash
   sudo docker volume create mydb
   ```

3. **Run a Container with Volume Mounted**:
   ```bash
   sudo docker run -itd --name app1 -p3000:3000 --mount type=volume,src=mydb,target=/etc/todos gsa:1.0
   ```

---

## Cleaning Up Docker Resources

1. **Remove All Stopped Containers**:
   ```bash
   sudo docker rm `sudo docker ps -a | awk -F" " '{print $1}'`
   ```

2. **Remove All Unused Images**:
   ```bash
   sudo docker image prune
   ```

3. **Remove Specific Image**:
   ```bash
   sudo docker rmi <IMAGE_ID>
   ```

4. **System-Wide Cleanup**:
   ```bash
   sudo docker system prune
   ```

---

## Additional Tips

1. **Check Disk Usage**:
   ```bash
   df -h
   ```

2. **Clone a Repository for Docker Practice**:
   ```bash
   git clone https://github.com/docker/getting-started-app.git
   ```

3. **Navigate and Explore Files**:
   ```bash
   cd getting-started-app/
   ls
   ```

