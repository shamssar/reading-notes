# AWS: Cloud Servers
## Review, Research, and Discussion
Describe the Web-Request-Response-Cycle

* an HTML request is made from a client to a server, typically using a RESTful method (GET, POST, PUT, PATCH, DELETE). Based on the request method, the server performs a certain set of actions with the request, and sends a reponse back to the client, which can contain a status code as well as objects, or a message.
Explain what a “server” is, as it relates to the WRRC

* In the WRRC the server is what takes the request from the client and performs all of the actions to formulate a response.
What does it mean to “deploy” an application?

* Deploying an application is typically hosting production version of your code on a server that is then available to the public to access.
* here is a real description: Application Deployment (also referred to as Software Deployment) is the process of installing, configuring, and enabling a specific application or set of applications, usually through an application manager (app manager) or software management system, to a specific URL on a server. Once the process of deploying the application(s) has been completed it becomes publicly accessible on the URL. source
### Vocab
Server

* A computer or dedicated piece of hardware that runs continuously recieving requests, or listening to events, and providing reponses from clients (other computers).
Pub/Sub

* Publish/Subscriber is a design pattern that allows for dynamic built around messages and a message broker. The publisher (host) will send out a message (event) and subscribers can sign up to listen to this event.source
WRRC

* Web Request Response Cycle defines HTTP requests that go out to a server from a client, where some action is taken to formualate a reponse, which is then sent back to the originating client.

Resources:
* [AWS EC2](https://aws.amazon.com/ec2/)
* [EC2 for Humans](https://www.youtube.com/watch?v=lZMkgOMYYIg)
* [Elastic Beanstalk](https://www.youtube.com/watch?v=SrwxAScdyT0)
