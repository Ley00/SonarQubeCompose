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
    SonarQube Compose DockerFile for the purpose of uploading a complete machine configured to analyze jobs locally.
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

## Features

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

## Getting started

1. Clone this repo using `git clone git@github.com:Ley00/AppsAndroidiOSUWP-XamarinForms.git`
2. Move yourself to the appropriate directory: `cd AppsAndroidiOSUWP-XamarinForms`<br />
3. Instale o Docker em sua máquina;
4. Run docker-compose.yml to download the images and create docker;
5 - Command to Run Windows:
  ``` 
docker run --network=host `
    --rm `
    -e SONAR_HOST_URL="http://localhost:9000" `
    -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=Projeto-Teste" `
    -e SONAR_TOKEN="sqp_865b5dd48f297d29f47f328cd89fddec16c897cc" `
    -v "${PWD}:/usr/src" `
    sonarsource/sonar-scanner-cli -X

  ```
   
ou

5 - Comando para executar linux:
```
docker run --network=host \
    --rm \
    -e SONAR_HOST_URL="http://127.0.0.1:9000" \
    -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=Projeto-Teste" \
    -e SONAR_TOKEN="sqp_6800ce2b7828abb5b9d0089ddb2cccd293b623b9" \
    -v "${PWD}:/usr/src" \
    sonarsource/sonar-scanner-cli -X
```
    
<!--3. Run `yarn` to install dependencies<br />
4. Run `lerna bootstrap` to install the packages dependecies-->

<!--### Getting started with the backend server

1. Move yourself to the backend folder: `cd backend`
2. Create a `.env` file and add the MongoDB url connection in MONGO_URL field
3. Run `yarn dev` to start the server

### Getting started with the frontend app

1. Move yourself to the frontend folder: `cd frontend`
2. Run `yarn start` to start the web application

### Getting started with the mobile app

1. Move yourself to the mobile folder: `cd mobile`
2. Run `react-native run-ios` (or `run-android` if your prefer) to start the mobile app

Note: If you choose to start the mobile app in the android emulator, you will have to start the emulator before using
the `run-android` command.-->

## License
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/Ley00/SonarQubeCompose/blob/main/LICENSE)
