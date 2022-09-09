# Background

For years we have been building custom process management solutions. Over and over again, we were solving the same problems. Projects needed a proper task list. A solution for storing data. An answer to access & entitlement. The solution was bundeling our knowledge and code into a platform: Valtimo. An opinionated Business Process Implementation, based on all the BPMN projects we did the past years. We made a lot of design mistakes - the knowledge is in the platform. And actually we still have new and better insights with every new project we are doing - and the knowledge flows into Valtimo. 

# Philosophy
Valtimo does not strive to support a broad techstack: it is an opinionated BPA-implementation - often following trends in the market.  

The core team uses the following guide lines: 

1. Use before make. Try to prevent inventing wheels. 
2. Use micro services with a thin integration layer, making them replaceable in the future. 
3. Keep things simple. 
4. Use upcoming but proven technology. 

# When to use Valtimo? 

There is no universal, broadly excepted definition of Business Process Automation categories. A possible categorization in types is: 

1.	**Workflow**. Being the simplest form of BPA, often largely consisting sequential steps in a predefined process. Examples are the approval flow for holidays-requests or onboarding new employees. Using Valtimo for these types of processes is not recommended. Using a point solution is often the better option. 

2.	On the other side of the spectrum there is **Service Orchestration**. In large scale micro service landscapes, communication between services can be a challenge. To step away from point to point connections, communication can be handled with a choreography-pattern with a message bus solution like Kafka, AWS SQS or RabbitMQ. The alternative option is to use an Orchestration pattern using a BPMN-engine.These types of processes typically are seen enterprise environments, focussing on eliminating manual work. Typically high volume processes with no or minimal manual work. Using Valtimo for service Orchestration is not recommended. Using a scalable BPMN-engine is advised. 

3.	**Case Management**. This is a more complex form of business process automation. Typically, the course of a Case is not predictable. Based on Events that take place the handling of the case differs. Typically there will be a mix of automated and user tasks and often complex and event based processes. Multiple processes can work with one case. Valtimo has been designed for this scenario. 

