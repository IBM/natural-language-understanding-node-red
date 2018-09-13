# Natural-Language-Understanding-in-Node-RED

Save Lives with Natural Language Understanding and Node-RED - Call for Code Hands on Lab

## Hands-On Lab

JeanCarl Bisson | jbisson@us.ibm.com | @dothewww

Helen Lam | helen.lam@ibm.com | @helennnsays

Anamita Guha | anamita.guha@ibm.com | @anamitag

### Introduction

The Natural Language Understanding service analyzes text to extract meta-data from content such as concepts, entities, keywords, categories, sentiment, emotion, relations, semantic roles, using natural language understanding. This tutorial uses the Node-RED boilerplate in IBM Cloud with the Natural Language Understanding service found under the **Starter Kit** section of the IBM Cloud
catalog. To get started using the Natural Language Understanding service, you’ll need to create service credentials. A digital copy of this lab and code snippets can be found at: https://github.com/helenlam100/Natural-Language-Understanding-NodeRed-Lab.

### Learning Objectives

After completing this tutorial you will be able to:

* Instantiate a Node Red Starter Kit and a Watson Cloud service (Natural Language Understanding API) on IBM's Cloud
* Bind a Watson service to a Node Red application
* Send a news article URL to the NLU API, and retrieve a table of the response in a table containing the concepts, entities, keywords,categories, sentiment, emotion, relations, and semantic roles

### Prerequisites

* Create an [IBM Cloud Account](https://console.bluemix.net/).
* Log into [IBM Cloud](https://console.bluemix.net/login).

### Estimated Time

You should be able to complete in 45 - 60 minutes.

### Step 1 - Set Up Your Node Red Boilerplate**

1. Log in and click on Catalog in the top right nav. bar.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536802926926_Hello1.png)

2. Click on “Starter Kits” in the left hand menu. Then click on the “Node Red Starter” option for the boilerplate. The boilerplate comes with:
* a Cloudant database instance to store your flow configuration.
* a collection of nodes that make it easy to access various IBM Cloud services, including Watson, IoT and Blockchain services to name just a few.
3. Write a name for your Node Red Boilerplate. You can write “node red” somewhere in the title, so you will not confuse with your other future IBM Cloud applications.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803109239_Screen+Shot+2018-09-12+at+9.44.16+PM.png)

4. It will take a few minutes (5–15 minutes) to instantiate. Once it is finished instantiating, you will see the green circle beside the name of your app where it will state “running.” 

Click on “Visit App URL” to get to your new Node Red boilerplate.

![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803327692_Screen+Shot+2018-09-12+at+9.46.10+PM.png)

5. Once you click on Visit App URL, you will be taken to your new Node Red app with a few set up instructions. You can choose to add a username or password, or leave unsecured. It is up to you. 
![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803369768_Screen+Shot+2018-09-12+at+9.46.59+PM.png)

A few other options are available, just keep clicking “next” until you get to this final page. Click “Go to your Node-RED flow editor.” 

![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803420258_Screen+Shot+2018-09-12+at+9.47.09+PM.png)

6. You will see your first flow. You are ready to begin your first Node Red flow. Congrats!
![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803441275_Screen+Shot+2018-09-12+at+9.47.20+PM.png)

### Step 2 - Add Natural Language Understanding Service in IBM Cloud

1. Click on the **Catalog** link in the top-right of the IBM Cloud Dashboard. Under the AI section, click on the **Natural Language Understanding** tile.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536804959347_Screen+Shot+2018-09-12+at+10.15.19+PM.png)

1. You can optionally give the service a custom name or leave it as the one given. Click **Create**.
2. Click on **Connections** in the menu on the left.
3. Click **Create connection** on the right. 
![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536805456519_Screen+Shot+2018-09-12+at+10.23.50+PM.png)

4. Click **Connect** next to the Node-RED application you created earlier.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536805617386_Screen+Shot+2018-09-12+at+10.26.18+PM.png)

5. IBM Cloud will prompt to restage the application. Click on **Restage**. The application will restart and include the new service credentials in the environment.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536806011226_Screen+Shot+2018-09-12+at+10.33.06+PM.png)

6. When the application has finished restaging, open the Node-RED Flow Editor. If you already have Node-RED open, refresh the page.

### Step 3 - Analyze a News Article in Node-RED

The Watson Natural Language Understanding service takes either a body of text or a publicly-accessible URL to content which the service can analyze. In this section, we will analyze a news article that is accessible via an URL. You can also choose to analyze other URLs that contain a body of text.

![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536806457518_Screen+Shot+2018-09-12+at+10.39.41+PM.png)

![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536806931827_Screen+Shot+2018-09-12+at+10.48.27+PM.png)

![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536806986130_Screen+Shot+2018-09-12+at+10.49.21+PM.png)

![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536807062869_Screen+Shot+2018-09-12+at+10.50.12+PM.png)

![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536807319985_Screen+Shot+2018-09-12+at+10.54.53+PM.png)

Get the code snippet here: ibm.biz/BdiBpU

![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536807372581_Screen+Shot+2018-09-12+at+10.55.53+PM.png)

10. Open a browser tab and visit your application’s endpoint, passing in the URL to the content:
    http://<<MY-APP>>.mybluemix.net/analyze?url=<<URL-TO-STORY>>
- Replace <> with the host of the Node-RED application you chose to name your app.
- Replace <> with the URL of the content.
11. Depending on the content located at the URL, you may see a list of attributes including concepts, entities, keywords, categories, sentiment, emotion, relations, semantic roles and more mentioned within the text.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536807797612_Screen+Shot+2018-09-12+at+11.01.00+PM.png)

12.  To  see the JSON representation of the content insert format=json in the url query string.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_1AEB3DBAF25785993FDC403B0E2B8B399A989E775A0079D55BFA837929CCB61B_1536808333678_Screen+Shot+2018-09-12+at+11.11.42+PM.png)

13. Return to Step #3 and experiment by disabling some of the features to see how the results change. Try analyzing other URLs and see what results are returned.