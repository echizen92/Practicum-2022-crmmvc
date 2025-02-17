# Content Management System MVC

This is a simple Spring MVC 5.x application project built with Maven, incorporating dependencies such Bootstrap, J2EE and Spring Security Module. Originally built for an interview coding assignment even though the author did not eventually work for that company. Full source code is released under GNU GPL v3.

P.S. The project is misnamed CRMMVC, should be CMSMVC but it was too late to change :)

## Setup Database

1. Connect to MySQL Server 8.x or MariaDB on MySQL Workbench using DBAdmin User database credentials located in db/db.env.
2. Under Navigator panel, select Management tab, select _Data Import/Restore_.
3. Under _Import from Self-Contained File_, locate the _Database.sql_ inside `db/` directory.
4. Under _Default Schema to be Imported to_ section, click _New_ to create new schema.
5. Ensure 'Dump Structure and Data' is selected, click _Start Import_.

## Build Project

- Using IntelliJ
1. Open in Spring MVC source project in IntelliJ IDE.
2. Open up src/main/resources/application.properties in the source project.
3. Ensure database credentials _jdbc.url, jdbc.username and jdbc.password_ are correct. Save for any change.
4. Open the Maven tab located on the right-hand side of the IDE, and go to `CRMMVC Maven Webapp` >  `Lifecycle` > `package`.
5. CRMMVC.war should appear under `target/` directory of the project root.

- Using Maven
1. Ensure Maven is installed in the system and added into System Environmental PATH (Refer to https://maven.apache.org/install.html).
2. In the terminal, change the working directory to <Project Root>.
  ```
  $ cd ~/2022-group3-crmmvc/
  ```
3. Run Maven to clean and package the project into a web archive. CRMMVC.war should appear under `target/` directory of the project root.
  ```
  $ mvn clean package
  ```
## Run Source Code in IDE

1. Set up a Tomcat 9.x installation by downloading and unzip the archive from https://tomcat.apache.org/download-90.cgi. Ensure JRE > 8.x is installed.
2. In IntelliJ, go to `Run` > `Edit Configurations`.
3. In the `Run/Debug Configurations` dialog, click `+` and select `Tomcat Server` > `Local`.
4. In Server tab, click `Configure` button beside `Application Server`.
5. In Application Server dialog, click on `+`. Ensure Tomcat Home and Tomcat base directory is pointing to the unzipped Tomcat installation (e.g. /usr/share/tomcat9/).  Click OK.
6. In the `Run/Debug Configurations`, go to Deployment tab and click `+`. Select artifact `CRMMVC.WAR`. Specify the `Application Context` (e.g. /CRMMVC), then click OK.
7. Go to `Run` > `Run...` or press Shift+F10 to run project in Tomcat server.
  
## Run Source Code using Docker
  
1. Ensure Docker is installed in the system. See https://docs.docker.com/get-docker/ for details.
2. In the terminal, change the working directory to <Project Root>, then run Docker Compose.
  ```
  $ cd ~/2022-group3-crmmvc/
  $ docker-compose up --build
  ```

## Deploy WAR to Tomcat
  
1. Copy target/CRMMVC.war to _\<your tomcat directory\>_/webapps/ of your Tomcat server installation. Restart Tomcat server if necessary.
2. Open up web browser and access the URL http://<hostname>:8080/CRMMVC/.
