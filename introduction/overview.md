# Background

For years, Ritense has worked on building custom process management solutions, solving the same problems with every project. Every project needed a task list, a solution for storing data, an answer to access and entitlement. Valtimo is the result of bundling this knowledge and code into one platform. It is an opinionated Business Process Implementation, based on the accumulated experience from working on BPMN projects for the past years.

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

2.	**Service Orchestration**. In large scale micro service landscapes, communication between services can be a challenge. To step away from point to point connections, communication can be handled with a choreography-pattern with a message bus solution like Kafka, AWS SQS or RabbitMQ. The alternative option is to use an Orchestration pattern using a BPMN-engine. These types of processes typically are seen enterprise environments, focussing on eliminating manual work. Typically high volume processes with no or minimal manual work. Using Valtimo for service Orchestration is not recommended. Using a scalable BPMN-engine is advised. 

3.	**Case Management**. This is a more complex form of business process automation. Typically, the course of a Case is not predictable. Based on events that take place the handling of the case differs. Typically there will be a mix of automated and user tasks and often complex and event based processes. Multiple processes can work with one case. Valtimo has been designed for this scenario. 

