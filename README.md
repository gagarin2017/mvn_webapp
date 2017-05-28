# mvn_webapp
Simplest maven webapp

Make sure that you have installed locally:
* Git cli
* Maven 3 cli
* Heroku cli

Create project on the GitHub and clone it to you local:

* git clone https://github.com/gagarin2017/mvn_webapp.git

On your local go to the parent directory of the cloned project. For example, if you cloned your project into /dev/sandbox/mvn_webapp, then you should go to the /dev/sandbox and create the simplest Maven web application using maven command:

* mvn archetype:generate -DarchetypeArtifactId=maven-archetype-webapp

Define value for property 'groupId': : com.greenland
Define value for property 'artifactId': : mvn_webapp
Define value for property 'version':  1.0-SNAPSHOT: :    <just hit Enter here to keep the default value>
Define value for property 'package':  com.greenland: :	<just hit Enter here to keep the default value>
Y: : Y  	<input N here if you want to rekey the inputs above>

Now you should have your very basic maven web project created. Go to the project's directory:

* cd mvn_webapp

/********** Project structure ***************
|
--src
  |
  ---main
     |
     --- resources
     |
     --- webapp
     		|
     		--- WEB-INF
     				|
     				--- web.xml
     		|
     		--- index.jsp
|
--pom.xml
|
--README.md
/********************************************

Update <build> section of the pom.xml file by adding webapp-runner plugin.

Package the project by executing

* mvn package

Now you can test this locally by executing

* java -jar target/dependency/webapp-runner.jar target/*.war

Open your browser and go to the address: localhost:8080
Hit Ctrl+C on windows to stop the local server.

Now to deploy it to Heroku

Create a Procfile
/************* Contents of the Procfile ***************

web:    java $JAVA_OPTS -jar target/dependency/webapp-runner.jar --port $PORT target/*.war

/*******************************************************

Add your changes to the Github
$ git add .
$ git commit -m "Ready to deploy"

Open Heroku CLI

* heroku login
* heroku create

No go the web interface of the Heroku app. Link the Github resources to the heroku application and deploy the app either automatically or manually through the Heroku web interface.

Resources:<br>
  <t>visit www.heroku.com for more details.</t><br>
  <t>https://devcenter.heroku.com/articles/java-webapp-runner<t>
  
