# Code 301 Reading Notes

## Read 05 HEROKU

**NPM: Node Package Manager**

### Getting Started
- The first step in being able to use HEROKU is to install it onto your machine Depending on your platform there is a specific way to install it onto your computer. After you have installed HEROKU you then use the `heroku login` command within your terminal to login to HEROKU CLI.

- The install will look something like this:

`heroku login`
`heroku: Press any key to open up the browser to login or q to exit`
 `›   Warning: If browser does not open, visit`
 `›   https://cli-auth.heroku.com/auth/browser/***`
`heroku: Waiting for login...`
`Logging in... done`
`Logged in as me@example.com`

- As a quick note if you have not created an account with HEROKU now would be a great time to do so. Once you have logged in now you can return back to your terminal. 

### Check for updates
- Before we move forward let’s check to make sure you have the most current version of node on your computer. 

- In your terminal type in: `node --verison` It should return something similar to *v14.15.4*. If not we can run an update and address that fairly quickly. 

### Preparing the App
- In the next steps you will prepare a sample application that is ready to be deployed to HEROKU.

- In your terminal run the following command:

`git clone https://github.com/heroku/node-js-getting-started.git`
`cd node-js-getting-started`

### Deploy the App
- Now we can create a HEROKU app. This will prepare HERKO to receive the source code. 

- In your terminal run the following command:

`heroku create`
`Creating sharp-rain-871... done, stack is heroku-18`
`http://sharp-rain-871.herokuapp.com/ | https://git.heroku.com/sharp-rain-871.git`
`Git remote heroku added`

- A few things to note: HERKO will generate a random name for your app so if it does not match the name within the HTTPS that is okay.

- Now we deploy the code by running a command of `git push herko main`
- Congrats the application has been deployed and now we check for at least once instance of the app running within the terminal.

- In your terminal run the following command:

`heroku ps:scale web=1`

- Next we visit the app with the URL that was generated. Within the terminal run the following command: 

`heroku open`

### View Logs
- HERKO treats logs as streams of time ordered events aggregated from the output streams of all your app and HEROKU components. To veiw that information about your app run this command in your terminal. 

`heroku logs --tail`

- To stop the streaming press control+c. 

### Define a Proficle 
- Using a **Proficle** a text file is the root directory of your application, to explicitly declare what command should be executed to start your app.

### Scaling the app
- At the moment your app is running a single web dyno. Think of a dyno as a lightweight contain that runs the command specified in Proficle. 

- In your terminal run the following command:

`heroku ps`

- By default the app is deployed on a free dyno, the free dyno will sleep after an hour of inactivity. This will cause a brief delay of a few seconds for the first request upon waking. 

Lets move on to **scale** the app

- In your terminal run the following command:

`heroku ps:scale web=0`

### Declare app Dependencies
- HEROKU recognizes an app as Node.js by the existence of a package.json file in the root directory. For your app you can create one by running `npm init --yes` in your terminal. The demo app you deployed will have a package.json and look something like this. 

`{
  "name": "node-js-getting-started",
  "version": "0.3.0",
  ...
  "engines": {
    "node": "14.x"
  },
  "dependencies": {
    "ejs": "^3.1.5",
    "express": "^4.17.1"
  },
  ...
}`

- A pacakge.json file determines both the version of Node.js that will be used to run your application on Heroku and the dependencies. 

- Now we run a command of `npm install` in the local directory to install the dependencies. This will allow us to run the app locally. 

### Running the app locally
- We can start your application by using `heroku local` command. 

- In your terminal run the following command: 
  * We will click on http://localhost:5000 to open the web browser once we have run the command below. 

`heroku local web`

- To stop the app from running locally press Ctrl+c to exit. 

### Pushing our changes to local
- Now we can push the changes to local. We will learn how to propagate a local change to the application through to HEROKU. We begin by adding a dependency for `cool-ascii-faces` within the package.json. Run the following common to do so.

`npm install cool-ascii-faces`

- Now we modify index.js so it requires this module at the start. 

`const cool = require('cool-ascii-faces');`
`const express = require('express');`
`const path = require('path');`
`const PORT = process.env.PORT || 5000;`

`express()`
  `.use(express.static(path.join(__dirname, 'public')))`
  `.set('views', path.join(__dirname, 'views'))`
  `.set('view engine', 'ejs')`
  `.get('/', (req, res) => res.render('pages/index'))`
  `.get('/cool', (req, res) => res.send(cool()))`
  `.listen(PORT, () => console.log(`Listening on ${ PORT }`));`

Now we test locally 

- In your terminal run the following command:

`npm install`
`heroku local`

- Now we deploy by doing our ACP process. 
  * git add .
  * git commit -m "Added cool faces API"
  * git push heroku main
  * heroku open cool

### Provision Add-Ons
- Add-ons are third party cloud services that provide out-of the box additional services for your application. By default, HEROKU stores 1500 lines of logs from your application. In the next steps you will provision one of these logging add-ons, Papertrail. 

- In your terminal run the following command:

`heroku addons: create papertrail`

- To prevent abuse prevention, provisioning an add-on requires account verification. If your account has not been verified, you will be direction to visit the verification site. 

- In your terminal run the following command:

`heroku addons`

- To see particular add-on in action, visit your applications URL a few times. 

- In your terminal run the following command:

`heroku addons:open papertrail`

### Start a console
- To get a feel for how dynos work, you can create another one-off dyno and run the **bash** command, which opens up a shell on that dyno.

- In your terminal run the following command:

`heroku run bash`

- If you run into an error like `Error connecting to process` you may need to configure your firewall. 

https://devcenter.heroku.com/articles/one-off-dynos#timeout-awaiting-process

### Define config vars
- HEROKU lets you externalize configuration - storing data such as encryption keys addresses config vars. 

- Next we want to modify our app.js 
  *  `.get('/times', (req, res) => res.send(showTimes()))`

- Next we add a new function `showTimes()`

`showTimes = () => {
  let result = '';
  const times = process.env.TIMES || 5;
  for (i = 0; i < times; i++) {
    result += i + ' ';
  }
  return result;
}`

- This will automatically set up the environment based on the content of the .env file in the local directory.

### Provisioning a Database
- The add-ons marketplace has a large number of data stores. In this step you will add a free Heroku Postgress Starter Tier dev database to your app. 

- In your terminal run the following command:

`heroku addons:create heroku-postgresql:hobby-dev`

- Next we use NOM to add the node-postgres

- Now we edit our index.js file to use this module to connect to the database. Add the code bellow near the top. 

`const { Pool } = require('pg');`
`const pool = new Pool({
  connectionString: process.env.DATABASE_URL,
  ssl: {
    rejectUnauthorized: false
  }
});`

- Now add another route, /db, by adding the following just after the existing .get('/', ...):

`.get('/db', async (req, res) => {
    try {
      const client = await pool.connect();
      const result = await client.query('SELECT * FROM test_table');
      const results = { 'results': (result) ? result.rows : null};
      res.render('pages/db', results );
      client.release();
    } catch (err) {
      console.error(err);
      res.send("Error " + err);
    }
  })`

- Now we can deploy the Heroku so go to your terminal and run this code. 

`heroku pg:psql`

### Next Steps
- Congrats we delpoyed an app, changes it configuration, veiwed logs, scaled, and attached add-ons. 

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)