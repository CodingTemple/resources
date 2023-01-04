# React - Hosting on Firebase
## _Hosting your React App on Google Firebase_

What you will need:

- a React application
- a Google account
- ✨Magic ✨       (just kidding..)

In this guide, we will start from scratch.

## Setting up your React Application
#### Set Up

React requires [Node.js](https://nodejs.org/) v14+ to run.

Install the dependencies and devDependencies and start the server.

```sh
npx create-react-app my-project
cd my-project
npm start
```

You should see the basic React App Template.
Now that we have a react app, let's get it hosted!
## Setting up your Firebase Project
#### Console Set Up (On firebase.google.com)

Log into your Google account then head over to the [Firebase Console](https://console.firebase.google.com/).

1. Add a new project,
2. Pick a valid name.
3. Turn off Google Analytics (we don't need it)

After your project is created, register your Web App by clicking on the </> icon.
Follow the steps for registering your app:
1. Give your app a nickname
2. Check "Also set up Firebase Hosting" option
3. Add the Firebase SDK to your project (The next 2 steps should be done inside of your React App's Code editor/terminal)
4. Run the install ```npm install firebase``` and copy and paste the given code your your React App's index.js
5. Install the Firebase CLI. ```npm install -g firebase-tools```

#### Using the Firebase CLI
Now back in your React App Terminal, install and use the Firebase CLI (a command line tool)
```sh
npm install -g firebase-tools
firebase login
firebase init
```
You should follow the instructions on how to login to Firebase from the terminal.
Next, follow instructions to initialize your folder to be ready for hosting.
1. When it asks which Firebase features you want to set up, select : "Hosting: Configure files for Firebase hosting.."
2. Next, select "Use an existing project" and pick the project name you created on the Firebase console.
3. Aftewards, it will ask you what you want to use as the oublic directory.. DO NOT use the default option, instead type: "build"
4. Then, it will ask if you would like to configure the app as a "single-page app". Select yes (y)
5. Finally, do not set up automatic builds and deploys with GitHub. This is the final step for you firebase configurations.

#### Deploy!
Now we are basically ready to deploy.
1. First we will compile our React App into a optimized production build using the ```npm run build``` command.
2. Then we can deploy using the ```firebase deploy``` command.

Happy hosting!

[//]: # (Thanks for following along! Shoha, out--)

