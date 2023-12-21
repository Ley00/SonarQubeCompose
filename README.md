<!-- Emojis - https://emojidb.org/developer-emojis?user_typed_query=1&utm_source=user_search-->
<h1 align="center">
  <br>
    <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/30672542/282470413-beb15261-0a1a-4aa5-b4ca-f7b0d800769a.png" alt="TinDev" width="400">
  <br>
  <br>
  SonarQube Docker-Compose
</h1>

<p align="center">
  <a>
    SonarQube Docker-Compose for the purpose of loading a complete machine configured to analyze jobs locally.
  </a>
</p>

<div align="center">
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/30672542/282473769-b938ca37-dfe3-4ba6-b55e-d0f199fae2f4.png" alt="demo-web" height="200">
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/30672542/282474357-2dfca92b-b264-4af3-b0d2-d54d93233061.png" alt="demo-mobile" height="200">
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/30672542/282475568-ed950604-8cb0-4d03-b0a6-d0a5af337615.png" alt="demo-mobile" height="200">
</div>

<!--<div>
  <img src="https://i.ibb.co/GJfb2X4/web.gif" alt="demo-web" height="425">
  <img src="https://i.ibb.co/zHbFDyd/mobile.gif" alt="demo-mobile" height="425">
</div>-->

<hr />

# Features

This docker-file presents all the tool configurations for using SonarQube.

- 🧊 **SonarQube** - Static code analysis software, being one of the most used in the industry
- 🖥 **Sonar-Scanner** - SonarScanner is the scanner to use when there is no specific scanner for your build system used by SonarQube
- 🛢 **Postgre** - PostgreSQL is a powerful open-source object-relational database system used by sonarqube
<!--- 📱 **Xamarin Forms** - A cross-platform and open-source for iOS, Android, and Windows apps with
- © #️⃣ **CSharp** - A platform back-end
- 🛢 SQLite - Implements a built-in SQL database
- 🌐 WebServices SOAP e REST -Chat Project Development
- ⚛️ **React Js** — A JavaScript library for building user interfaces
- ⚛️ **React Native** — A lib that provides a way to create native apps for Android and iOS
- 💹 **Node Js** — A web framework for Node Js
- 📄 **MongoDB** — A cross-platform and open-source document-oriented database
- ♻️ **Socket IO** — A library for realtime web applications -->

# Getting started

## Tutorial: Creating a Docker Compose with Good Practices
In this tutorial, we will create a Docker Compose file following best practices. We will create an environment for SonarQube, using a PostgreSQL database and a scanner for code analysis.

### **Step 1**: Create the Docker Compose file
Create a new file called docker-compose.yml in the desired directory. You can use any text editor for this. Make sure the file has read and write permissions.
```
version: "3.8"

networks:
   main-network:

services:
   postgres:
     image: postgres
     container_name: MyPostgres
     environment:
       POSTGRES_PASSWORD: mypassword
       POSTGRES_USER: myuser
       POSTGRES_DB: mydatabase
     volumes:
       - /path/to/postgres/data:/var/lib/postgresql/data
     ports:
       - "5432:5432"
     networks:
       - main-network
     privileged: true
     deploy:
       resources:
         limits:
           CPU: '1'
           memory: 512M

   sonarqube:
     image: sonarqube
     container_name: MySonarQube
     environment:
       sonar.jdbc.username: sonar
       sonar.jdbc.password: sonar
       sonar.jdbc.url: jdbc:postgresql://postgres/mydatabase
     volumes:
       - /path/to/sonarqube/data:/opt/SonarQube/data
       - /path/to/sonarqube/logs:/opt/SonarQube/logs
       - /path/to/sonarqube/extensions:/opt/SonarQube/extensions
       - /path/to/sonarqube/plugins:/opt/sonarqube/lib/bundled-plugins
     ports:
       - "9000:9000"
     networks:
       - main-network
     depends_on:
       - postgres
     privileged: true
     deploy:
       resources:
         limits:
           CPU: '1'
           memory: 768M

   sonar-scanner:
     image: sonarsource/sonar-scanner-cli:latest
     container_name: MySonarScanner
     volumes:
       - /path/to/scanner/workspace:/opt/sonar/scanner/workspace
     networks:
       - main-network
     depends_on:
       - sonarqube
     privileged: true
     deploy:
       resources:
         limits:
           CPU: '1'
           memory: 512M

```
This example sets up a basic environment with PostgreSQL, SonarQube, and a scanner for code analysis. Remember to replace /path/to with the desired directory paths on your system.


### **Step 2**: Configure the Network
Make sure you create a network for your containers. In the example, we use the network called main-network. Be sure to replace main-network with a name that is meaningful to your project.

```
networks:
   main-network:
```


### **Step 3**: Customize Services
For each service, customize the following items to your needs:

  - **container_name:** Choose meaningful names for containers.
  
  - **environment:** Configure environment variables as needed.
  
  - **volumes:** Point to the directories where you want to store persistent data.
  
  - **ports:** Map ports as needed.
  
  - **deploy:** Customize service resources such as CPUs and memory.

  - **privileged:** Privileged mode has security implications.


### **Step 4**: Run Docker Compose
After configuring the Docker Compose file, save it and run the following command in the same directory:

```
docker-compose up -d
```

This will start the services defined in the Docker Compose file in the background (-d). Make sure Docker Compose is installed on your system.

## License
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/Ley00/SonarQubeCompose/blob/main/LICENSE)
