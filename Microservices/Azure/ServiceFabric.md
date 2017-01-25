#  ![ServiceFabric](ServiceFabric.png) Azure Service Fabric Knowledge Base

A curated list of helpful material to start learning Modern Development Things :smile:

Project Workflow using [ZenHub](https://www.zenhub.com/) 

Title | Author | Version | Group | Sub-Levels
--- | --- | --- | --- | ---
*Azure Service Fabric Knowledge base* | dtro-devuk | 1.0 | Root | **0**

Azure Service Fabric is a Platform-as-a-Service offering, which promises us a way to build highly reliable, massively scalable cloud based services

* Service Fabric comes in different flavours catering to different requirements. 
* There are two APIs available to us, 
1. Reliable Actors and 
2. Reliable Service(s) API's, 
* and the services we build can be either **stateful** or **stateless**.

### Overview

**Advantages of Service Fabric and Microservices**

* **Create independently deployable microservices:** easier to deploy than n-tier architectures
* **Autonomous experimental teams:** allows creation of nimble, teams that can deliver functionality quicker.
* **Leverage a cloud platform:** minimize writing plumbing code, and maximize feature development, allowing the teams to ship more customer features.


Taken from benefits to TalkTalk TV...

* **Agility:** Rolling upgrades, granular versioning, packaging and deployment to achieve faster delivery cycles and maintain uptime during upgrades.
* **Development environment and programming models:** Developers able to build and run the solutions locally using the Service Fabric SDK using a combination of the reliable actors and reliable services programming models.
* **Scalability:** The granularity of service scaling and versioning enables the system to scale as the number of users, devices, and content grows.

### Intro

* [Martin Fowler - MicroServices](https://martinfowler.com/articles/microservices.html)

* [Service Fabric Patterns and Practices (Learning Plan)](https://mva.microsoft.com/en-US/training-courses/service-fabric-patterns-and-practices-16925?l=mudwqISGD_6005167344)
* [Service Fabric Patterns and Scenarios](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-patterns-and-scenarios)

#### Official

* [Azure Service Fabric - Building MicroServices](https://azure.microsoft.com/en-in/services/service-fabric/)
* [Overview of Azure Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-overview)
* [Cloud Design Patterns](https://msdn.microsoft.com/en-us/library/dn568099.aspx)
* [Model an application in Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-model)

#### Others
* [Microservices based application on the Azure compute platform](https://articles.microservices.com/microservices-based-application-on-the-azure-compute-platform-ea6b12c28782#.r4zirxhxf)
* [Party Clusters](http://tryazureservicefabric.westus.cloudapp.azure.com/)

#### Case Studies
* [Service Fabric Customer Profile: **TalkTalk TV**](https://blogs.msdn.microsoft.com/azureservicefabric/2016/03/15/service-fabric-customer-profile-talktalk-tv/)

##### Actor Frameworks, Patterns etc
* [Service Fabric Reliable Actors](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-reliable-actors-introduction)

#### Actor Model
* [The Actor Model in 10 minutes(see the video, Hewitt, Meijer & Szyperski)](http://www.brianstorti.com/the-actor-model/)
* [What is definition](http://whatis.techtarget.com/definition/Azure-Service-Fabric)
* [A Practical Overview of Actors](https://alexandrebrisebois.wordpress.com/2016/07/09/a-practical-overview-of-actors-in-service-fabric/)
* [Getting to know actors](https://alexandrebrisebois.wordpress.com/2016/07/25/getting-to-know-actors-in-service-fabric/)

#### Reliable Actors

* Actors are single-threaded objects capturing logic and state
* All Actors considered stateful
* Each maps a unique ID (repeated calls to same ID routed to same instance)
* Can maintain state reliably using persistence and replication (after failures, outages, reactivation, garbage collection) or when moved around nodes, depends on how state is persisted:
1. Persisted State (to disk and up to 3+ replicas, most durable and handles complete outage)
2. Volatile State (kept only in  memory and replicated to 3+ replicas (not disk so if all replicas lose then state is lost)
3. No persisted state (not replicated or written to disk)
* Each one simply a configuration for the Reliable Stateful Service, whether written depends on the state provider and replica count.
* Set via an attribute on the Actor
* State objects requested asynchronously directly from memory and cached on first call

see:
* [Reliable Actors state management](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-reliable-actors-state-management)
* [Notes on Service Fabric Reliable Actors type serialization](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-reliable-actors-notes-on-actor-type-serialization)

##### State Clears

* By default, the state is persistent to disks (in addition to replication to 3 nodes), so it should survive the restarts.
* Pressing F5 in Visual Studio, the default behavior is to delete your old application and deploy the current version as a new application. 
* To maintain the state on your dev cluster, you can tick a checkbox in project properties to do upgrades instead of clean deployments.

* You have the same options when deploying to Azure - deploy a new app (and lose the state) or deploy an upgrade to persist the state. 
* The old and new versions of your state class should be compatible, they are based on DataContract to make it a bit easier.

**NB. State Clears on Restart!!!
* [When does Service Fabric restart/ clear state](http://stackoverflow.com/questions/35390664/when-does-service-fabric-restart-clear-state)


### Swagger
* [Swagger for Azure Service Fabric Stateless Web API application](http://stackoverflow.com/questions/40088573/swagger-for-azure-service-fabric-stateless-web-api-application)

### Tutorials

#### Official
* [Create your first Service Fabric App](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-create-your-first-application-in-visual-studio)
* [Get started with deploying and upgrading applications on your local cluster](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-get-started-with-a-local-cluster)
* [Sheepisly Startup app](https://blog.geist.no/azure-service-fabric-introduction-getting-it-running/)

#### Completed
* [Completed Voting Service](https://github.com/toddabel/Service-Fabric-Labs/tree/master/Lab%202/src)

### Official Sample Apps
* [Service Fabric Getting Started Samples](https://azure.microsoft.com/en-gb/resources/samples/service-fabric-dotnet-getting-started/)
* [Azure Samples](https://github.com/Azure-Samples)
* [WordCount WebService](https://github.com/Azure-Samples/service-fabric-dotnet-getting-started/tree/master/Services/WordCount/WordCount.WebService)

### Deployment and Debugging
* [Debug your Service Fabric application by using Visual Studio](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-debugging-your-application)
* [Introduction to the Fault Analysis Service, and Testing Distributed Systems](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-testability-overview)
* [Deploy and remove applications using PowerShell](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-deploy-remove-applications)
* [Monitor and diagnose services in a local machine development setup](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-diagnostics-how-to-monitor-and-diagnose-services-locally)
* [Service Fabric application upgrade](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-upgrade)

### Security
* [Configure security policies for your application](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-runas-security)

### SFX (Service Fabric Explorer)
* [Visualize your cluster with Service Fabric Explorer](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-visualizing-your-cluster)
* [Introduction to Service Fabric health monitoring](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-health-introduction)
* [Use system health reports to troubleshoot](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-understand-and-troubleshoot-with-system-health-reports)

### Azure Symbols
* [Microsoft has Released a Set of Symbols/Icons to Visually Represent Azure Solutions](https://alexandrebrisebois.wordpress.com/2014/02/19/microsoft-has-released-a-set-of-symbolsicons-to-visually-represent-windows-azure-solutions/)