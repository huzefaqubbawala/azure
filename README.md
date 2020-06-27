**Overview**

**What is Serverless computing ?**

**Wiki definition -**

[**Serverless computing**]([https://en.wikipedia.org/wiki/Serverless_computing](https://en.wikipedia.org/wiki/Serverless_computing)) is a [cloud computing](https://en.wikipedia.org/wiki/Cloud_computing "Cloud computing")  [execution model](https://en.wikipedia.org/wiki/Execution_model "Execution model") in which the cloud provider runs the [server](https://en.wikipedia.org/wiki/Server_(computing) "Server (computing)"), and dynamically manages the allocation of machine resources. Pricing is based on the actual amount of resources consumed by an application, rather than on pre-purchased units of capacity.

**Definition for humans -**

I personally believe in writing the article in very simple language that anyone can understand. Lets break down and understand what is serverless and how it has evolved over time.

To understand this we need to go back in history and understand few concepts.

- Servers
-  Applications

**Servers** 

Server is nothing but any computing device (Laptop, desktop, mobile, tablet just anything which is capable of compute). In computer world we called this as hardware.

**Applications -**

Applications are nothing but piece of code written to achieve any specific goal. For example a calculator app is written to perform arithmetic operation. In computer world we also referred this as software.


In general to use any application we need to run it on server. Lets say you want to run the calculator app on your machine. You will open the app in your laptop and perform some operations. In background your app (software) is running on your laptop (hardware) to perform something which you desire.

**Web Applications** 

Applications which are accessible over network to be consumed are called as web applications. 

In above example we have seen calculator app in your machine. This app cannot be called as web application since it is not accessible over internet. Now lets say you build a web site which does the same operation which calculator does. You host that app on some server to be available for everyone now this application is available as website to everyone and qualified as web application. Anyone can browse through your website using any browser and perform operations.

**Recap of our learning -**

To build/use any application you need (piece of code - software/app) and hardware (machine, laptop). 

From the above article it is very clear that we need 2 main components the software and hardware to build any application and make it available for consumers.


**Introduction to Serverless ** 

***Before Serverless***

Traditionally the above model was followed for initial years of internet and developers used to write the piece of code (The application) and then used to buy the server (Machine) to deploy the app and make it available as web applications for everyone on internet.

*So what was the problem then ?*
Well many..

Lets say I want to create a website for booking appointments. After I am done with my business logic now I have to buy some server and deploy this application to server. It all worked great for sometime but as time went by they realized the challenges in this approach.

 I have list down few of them below for buying servers and maintaining.

 - Which configuration should  I buy (intel/AMD) , RAM size ? Harddisk ?
 - Upfront cost required to buy servers.
 - Need to run this server 24*7 to make my website available. Electricity cost ?
 - What if my server crashes ? Need a backup server ?
 - Good internet connection ? leased line / static IP ?
 - Protection from natural disaster like flood, earthquake.
 - Server life ? Upgrade cost after 2-3 years ?
 - Sudden increase in traffic, how to scale my server ?

 - 
From above problems you can understand how painful it is to buy and maintain servers and seems like costly affairs. 

***Then came the rent model -***

To give an analogy we can use the real life example of real estate. Should I buy the apartment or rent ?

I am not a expert of real estate so sorry folks but on computers, rent model was immediate hit and many companies started renting the servers and providing it to developers

As a developer it was easy to rent a server since you just have to pay the monthly/quarterly/ yearly rent for the server configuration and get away with all the nightmares of maintaining it in your premise.

So the world continued with this rent model for very long and it is still very popular model for small to medium websites which has predictable workload and incoming traffic.

Out of the above list lets see how many issues we have solved.

 - Which configuration should  I buy (intel/AMD) , RAM size ? Harddisk ?
 Not solved, we still need to decide the configuration and pay rent according to the configuration.
 
 - Upfront cost required.
 Solved, No cost to buy server will pay rent as long as we want to use.
 
 - Need to run this server 24*7 to make my website available. Electricity cost ?
 Solved - As the server is not running on my home the rent cost includes everything.
 
 - What if my server crashes ? Need a backup server ?
 Solved , My provider takes care of backup since i am paying rent.
 
 - Good internet connection ? leased line / static IP ?
 Solved, Provider takes care of it.
 
 - Protection from natural disaster like flood, earthquake.
 Partially Solved - Many providers are not able to cope up with natural disaster and if any unfortunate event happens we may face server down times.
 
 - Server life ? Upgrade cost after 2-3 years ?
 Solved , we can choose a different server anytime and the flexibility is given to us.
 
 - Sudden increase in traffic, how to scale my server ?
 Partially Solved , Since we just have one server on rent if it reaches its capacity we still need to get another server on rent and scale.
 
 
 ***Time to introduce cloud -***

To solve the above problems and many more which is not listed here many providers invested huge money in making there rent model globally available, self-healing, natural-disaster proof, software upgrades, security and auto scaling. 

Then came Azure, Microsoft offering of cloud computing. With Azure you can still just rent a server (a.k.a VM) and deploy your web application. It is the same model as it was before but now you have all the capabilities of cloud like security, disaster management and so on.

This offering is also referred as "Infrastructure as a Service" a.k.a "IaaS" , where the infra is offered to you as a service. So ideally you can rent 1000s of VM and perform computation on it or run applications on it.

But with azure VM you still need to manage the infrastructure, you are the one responsible for that VM. You still need someone to continuously monitor the machine health and do OS upgrades , security patched and so on.

** Entry of Azure App Service .** 
It enables the developers to deploy your web app on the configured server and the VM was hidden from the developers. All the management of machine was off-loaded by azure. So you basically does not need anyone monitoring the VM and doing software, security upgrades for you. One of the huge benefits was no maintenance and the scaling. With simple scaling rules, azure adds the VM when the traffic goes up and removes the additional VM when traffic goes down.

This offering is also referred as "Platform as a Service" where the platform is offered to you as a service. 

So far so good, Then you will ask what is the problem,  life is beautiful with azure app service. Why do we need serverless ?

***WHY SERVERLESS***

Well if you have seen the problems list the first one that was listed intentionally was server configuration ?

With azure app service or renting a VM on cloud you still need to decide on server configuration and pay the rent according to the configuration.

Deciding server configuration is an art in itself because its hard to predict the network traffic , usage patterns , spikes e.t.c..

Also azure app service which auto-scales on the basis of traffic adds the same configuration VM and charges you the same rent for the time that server was up and running. So that means you are paying 24*7 for minimum one server and paying additional money for all the scaled up VM as and when requires.

There are many use cases where I just want to deploy my business applications and needs to pay only when it is consumed. Since I dont know the usage pattern its hard to predict the server configuration and most of the time server will sit idle and I will end up paying rent.

***Here comes Serverless*** 

With Serverless model cloud vendor provides you the ability to run your piece of code (App/software) without knowing about servers (hardware) and charged you only for the usage.

**Wait what ?** 

Serverless - By the word definition it should mean no severs right ?

Yes and no, remember its not possible to run the piece of code without servers. Serverless just mean all the server configuration is hidden from you.
 
***Can you give me real-life example ?***

Telecom industry is the best example.

In current scenario postpaid plans are the best example of what we know as azure app service. We are charged a fixed monthly rental and given some limitations on number of call/sms and internet data. After that we are charged according to the usage.

What if tomorrow the telecom providers start zero rental plans and charges consumer only on pay per usage. This would mean user only pays if he call/sms or use internet. So ideally if I do not use my cell phone I am essentially charged zero. I hope this will come soon. This would be serverless model for telecom industry.

**Serverless Computing**

So in true sense Serverless means all the server configurations are hidden from and you are charged as per your usage.

In nutshell, any offerings has to provide below capabilities to be qualified as Serverless.

- Ability to run the piece of code (software) without configuring servers
- Pay as you go model (No fixed rent)
- Auto scale on the basic of traffic.
- All other cloud benefits (Disaster management, geo-replication, high availability, security)

In Azure , many such offerings are available , to name few popular ones.

- Azure Storage (Blob, Files, Queues)
- Azure Functions (Running APIs)
- Azure Logic Apps. (Running workflows)
- Azure Container Instances. (Run containers)
- Azure SQL server  (Run database)

We will explore all this in more details. Please go to the respective folders in github repository to learn more about this. 


