# Tone-Analyzer-Node-RED
This repository provides an example of a Node-RED application that grabs Tweets and analyzes the tone using the Tone Analyzer service available on IBM Cloud. Based on the tone, the developer then posts something on Twitter. In this repository, we keep it simple by just posting one of two types of messages (based on whether the tone of the grabbed tweet is positive or negative).

## Node-RED on IBM Cloud
Node-RED is an open source visual flow-based programming tool used for wiring not only Internet of Things (IoT) components, but also integrating an ensemble of service APIs, including ones provided by IBM Cloud.

## Tone Analyzer service on IBM Cloud
Tone Analyzer leverages cognitive linguistic analysis to identify a variety of tones at both the sentence and document level. This insight can then used to refine and improve communications. It detects three types of tones, including emotion (anger, disgust, fear, joy and sadness), social propensities (openness, conscientiousness, extroversion, agreeableness, and emotional range), and language styles (analytical, confident and tentative) from text.

## Architecture overview
An architecture overview of the system can be found below.
![Architecture overview of the system]()

## Pre-requisite
An IBM Cloud account - A lite account, which is a free of charge account that doesn’t expire, can be created through going to [IBM Cloud](http://ibm.biz/SheraaAIFeb18).

## Creating the Node-RED application
- To simplify things, a boilerplate called **Node-RED Starter** is used. It can be found by going to **Catalog** followed by selecting **Boilerplates**, which will be seen on the menu available on the left-hand side under **Platform**. 
- The user is then required to enter a unique name for the application being created, which is also used as the hostname. If the user is using a lite account, the region is set to that chosen while applying for the account. 
- After clicking on **create**, an instance of the Node-RED application (which uses Node.js to create server-side JavaScript applications) is created to which a **Cloudant NoSQL database** is bound. It will take some time for the application status to change to awake, indicating that it is running.

![Creating the Node-RED application]()

Next, we need to create an instance of the Tone Analyzer service and bind it to the Node-RED application. 

## Creating and binding the Tone Analyzer service
- Click on **Catalog** at the top of the page followed by selecting **Watson**, which will be seen on the menu available on the left-hand side under **Platform**.
- Click on **Tone Analyzer** and enter what you want to call the service (in this case, we called "<i>ToneAnalyzerService-Tweets</i>")
 - After clicking on **create**, an instance of the service will be created.

![Creating the Tone Analyzer service]()

- Within the created service, go to **Connections** and click on the **connect** next to the name corresponding to the Node-Red application we just created (you will see it under **Cloud Foundry apps**.

![Binding the Tone Analyzer service to the Node-Red Application]()

- A window will pop up saying that **Your 'NodeRED-TA-Tweets' app needs to be restaged. Do you want to restage it now?**. Click on **restage**.

## Setting up Cloudant NoSQL database
- Go back to the **Dashboard** (can be done from the hamburger menu at the top left of the page). The **Dashboard** allows the user to see all the applications and services that have been created.
- Click on on <app-name>-cloudantNoSQLDB (in our case, it is called "<i>NodeRED-TA-Tweets-cloudantNoSQLDB</i>"). This will take us to the page with the details about the Cloudant NoSQL DB service.
- Go to **Manage** and then click on **Launch**. This will launch an interface through which we can interact with the Cloudant NoSQL DB. 
- Click on **Databases** from the menu available on the left. By default, a database called **nodered** can be found, which we are not going to touch. 
- Now, click on **Create Database** at the top of the page to create a new Database and give it a name (here, we called it "<i>tweet-tone</i>") and click **create**. Here, we will be saving any data we will be receiving/generating. Whenever we want to store something, we store that data in a document in a NoSQL database.

![After creating a new database to store Tweets and the tone analysis]()

## Setting up the Node-RED application
- Go back to the **Dashboard** and click on the application you created earlier (we called "<i>NodeRED-TA-Tweets</i>").
- In order to access the Node-RED editor used to build the application, click on **Visit App URL**. 
- Follow the directions to access the Node-RED editor (you are encouraged to secure your Node-RED editor to ensure that only authorized users can access it). 
- Click on **Go to your Node-RED flow editor**.

![Node-RED flow editor]()


## Overall Node-RED flow
The following diagram provides an overview of the finalize Node-RED flow. If you are not interested in starting from scratch, you can import the final version of the flow from the file **Node-RED_flow_Full.json**, which can be found in this repository.

![Overall Node-RED flow]()

## Building the Node-RED flow












