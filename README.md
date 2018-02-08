# Tone-Analyzer-Node-RED
Node-RED is an open source visual flow-based programming tool used for wiring not only Internet of Things (IoT) components, but also integrating an ensemble of service APIs, including ones provided by IBM Cloud.

This repository provides an example of a Node-RED application that grabs Tweets and analyzes the tone using the Tone Analyzer service available on IBM Cloud. Based on the tone, the developer then posts something on Twitter. In this repository, we keep it simple by just posting one of two types of messages (based on whether the tone of the grabbed tweet is positive or negative).

## How does the system work?


## Architecture overview


## Pre-requisite
An IBM Cloud account - A lite account, which is a free of charge account that doesn’t expire, can be created through going to [IBM Cloud](http://ibm.biz/SheraaAIFeb18).



## Creating the Node-RED application
To simplify things, a boilerplate called **Node-RED Starter** is used. It can be found by going to **Catalog** followed by selecting **Boilerplates**, which will be seen on the menu available on the left-hand side. The user is then required to enter a unique name for the application being created, which is also used as the hostname. If the user is using a lite account, the region is set to that chosen while applying for the account. After clicking on **create**, an instance of the Node-RED application (which uses Node.js to create a server-side JavaScript applications) is created to which both a **Cloudant NoSQL database** is bound. It will take some time for the application status to change to awake, indicating that it is running.

![Alt Text](https://j.gifs.com/59WvjB.gif)

























