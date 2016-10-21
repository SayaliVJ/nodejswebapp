# Nodejswebapp

## Purpose:
This project is purely intended to start learning nodejs for building simple web applications. It contains the project demo which will run a server using nodejs and Stormpath.

It is also intended to display how Google API can be integrated within your own websites for authentication.

## What is in it to learn:
1. Learn installation of nodejs, NPM (Node Package Manager) on ubuntu.
2. Learn about the express framework for web apps using nodejs.
3. Installing libraries using npm.
4. Use express framework to create a simple webapp.
5. Create a stormpath account for using authentication.
6. Basic Jade templating.
7. Google API's for authentication.

## Installation of Nodejs:
Follow these three simple commands to install node js and npm:

``` sudo apt-get update
  sudo apt-get install -y nodejs
  sudo apt-get install -y npm
```

## Node.js:
1. Nodejs can be used to power a lot of asynchronous background processes.
2. Nodejs for building a simple server side web application, network applications.
3. Nodejs makes it possible to create highly scalable applications.
4. Nodejs works on event loop which handles the requests asynchronously and returns the results to the registered callback events.

## NPM (Node Package Manager):
1. NPM is fast, robust, and consistent. It helps specifying and installing project dependencies for nodejs applications.
2. It also handles global installs of shell commands and platform-dependent binaries.
3. The libraries that are required for running this sample webapp are included as dependencies within the package.json file.
4. However, these dependencies can also be downloaded and installed using npm by command:

``` npm i express express-stormpath cookie-parser csurf jade forms xtend body-parser --save ```

## Stormpath:
1. Stormpath is an API service that allows developers to create, edit, and securely store user accounts and user account data, and connect them with one or multiple applications.
2. The project example that is provided here will allow Stormpath to be used as an authentication API for the example nodejs webapp.
3. Currently for demo purpose, the Stormpath api keys being used for this sample web project are the ones which are created for me.
4. You can choose to create your own Stormpath account to create the API keys. Following is the URL to create the account and start using it:
https://api.stormpath.com/login

## Usage:
1. Clone the project following the
```git clone https://github.com/varungituser/nodejswebapp.git command: ```
2. Once the project is cloned, change the directory to the nodejswebapp folder, and if you have not already installed the dependencies using npm, proceed to install them with:
```npm install```
This should install all the dependencies from package.json
3. Once all the dependencies are installed, you should be able to see a folder "node_modules".
4. You can also list the dependencies by using:
```npm list```
5. Once the nodejs app is ready to run, use the following for to export the API keys used for Stormpath:
```
export STORMPATH_CLIENT_APIKEY_ID=5NJLYK87BHJIGIY80ZH2PKJX4
export STORMPATH_CLIENT_APIKEY_SECRET=pxDdIlVpSEbkhBz39BgFtmjaLlDkrAYcsxkYyYOp420
export STORMPATH_APPLICATION_HREF=https://api.stormpath.com/v1/applications/5hF5Z7cFHsqLc5tvPXTY7m 
```
6. Now, proceed to run the server.js:
```node server.js```
7. If softlinking is not done, try using:
```nodejs server.js```
8. To softlink use:
```sudo ln –s /usr/bin/nodejs /usr/bin/node```
9. Once server.js runs, it will display a message as: "Stormpath Ready"
10. Now, in your browser, browse the URL: localhost:3000
11. You should be able to see a simple Login Page asking for email and password.
12. Create Account option will allow you to register your email id and set your password.
13. Try login to the application now and it should be authenticated.
14. You could also login by using your Google account username and password by using the 1-click Google login button.

## Google login:
1. The Google API also enables its Google login to be integrated with your nodejs webapp.
2. This can be done by following simple steps for it:
3. Log into Google Developer Console (https://console.developers.google.com/project) and create a new Google Project, enter a name for the project.
4. Once the project is created, click on Google APIs, and from the API Manager, select Library.
5. Select "Google+ API" from Social APIs in the libraries section.
6. Select the "Enable" option to enable google login for this project.
7. Now navigate to Credentials section and select "Create Credentials" for it. Ensure the project selected and displayed on the upper left corner is the one that is newly created.
8. Select OAuth client ID.
9. Select "Configure Consent Screen" and simply enter the display Product name for your project.
10. Now under the Create client ID option, Choose Application type as "Web Application", enter name of the application.
11. Now, enter the redirect URI's as: http://localhost:3000/callbacks/google
12. Once done, login to Stormpath Admin Console: https://api.stormpath.com/
13. Under Directories, choose Create Directory, and choose its type as Google, give it a name.
14. Enter the Google Client ID, Google Client Secret and Google Authorized Redirect URI that was used to create the client ID on Google API.
15. This should now embed a Google Login API button into the login screen for the webapp.
 
## Dockerizing the webapp:
1. Navigate to the cloned nodejswebapp folder.
2. Use the command to create a docker container from the Dockerfile:
```docker build -t <your username>/node-web-app .```
3. Run the webapp by using command:
```docker run -p 49160:3000 -d <your username>/node-web-app```
4. curl -i localhost:49160
5. You can also browse to localhost:49160 on your browser to run the app.

## References:
https://nodejs.org/en/docs/guides/nodejs-docker-webapp/
https://stormpath.com/blog/build-nodejs-express-stormpath-app

