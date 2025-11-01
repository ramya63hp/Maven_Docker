# 🚀 Dockerized Maven Java Web Application

Step-by-step guide to containerize and run a **Maven-based Java web application** using **Docker** and **Tomcat 9**.
The generated `.war` file is deployed as the **ROOT application**, accessible directly at [http://localhost:8080].

---

## **Prerequisites**

* Docker installed on your system
* Maven (for building the WAR locally) or use multi-stage Docker build
* Compatible JDK (example uses JDK 11)

---

## **Typical Project Structure**

```
pom.xml  
src/main/java  
src/main/resources  
src/main/webapp     # web content (JSPs, WEB-INF, etc.)  
target/             # build output (WAR file)
```

---

## **Deployment Procedure**

**1. Push your project to GitHub**

```bash
git push origin main
```

**2. Pull the project on the server**

```bash
git pull origin main
```

**3. Build the WAR file using Maven**

```bash
mvn clean package
```

**4. Build the Docker image**

```bash
docker build -t javaweb_image .
```

**5. Run the Docker container**

```bash
docker run -d -p 8080:8080 --name javaweb_container javaweb_image
```

✅ Access your application at:
👉 [http://localhost:8080](http://localhost:8080)

---

## **Using Docker Compose (Optional)**

**To build and start the container**

```bash
docker-compose up -d --build
```

**To stop and remove the container**

```bash
docker-compose down
```

---

**Description:**
Fully containerized Maven-based Java web application on Tomcat 9. Built and deployed using Docker and Docker Compose for a consistent, portable development and deployment workflow.
