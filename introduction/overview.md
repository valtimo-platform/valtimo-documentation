# Background

For years we have been building custom process management solutions. Over and over again, we were solving the same problems. Projects needed a proper task list. A solution for storing data. An answer to access & entitlement. The solution was bundeling our knowledge and code into a platform: Valtimo. An opinionated Business Process Implementation, based on all the BPMN projects we did the past years. We made a lot of design mistakes - the knowledge is in the platform. And actually we still have new and better insights with every new project we are doing - and the knowledge flows into Valtimo. 

# Philosophy
We do not strive to support a broad techstack: the core team is too small. Valtimo is an opinionated BPA-implementation - often following the trends in the market.  

Principles we follow:

1. Use before make. We try to prevent inventing wheels. 
2. Use micro services with a thin integration layer, making them replaceable in the future. 
3. Keep things simple. 
4. Use upcoming but proven technology. 

# When to use Valtimo? 

There is no universal, broadly excepted definition of BPA-categeries. We distinguish three types of business process automation (BPA). 

First **Workflow**. This is the most simple form of BPA, often largely sequential steps in a predefined process. Think of an approval flow for holidays or onboarding new employees. Using Valtimo for these types of processes is overkill. Look for a point solution. 

On the other side of the spectrum there is **Service Orchestration**. This is basically connecting (micro) services by means of BPMN models. You would see these types of processes in enterprise environments, focussing on eliminating manual work. Typically very high volume. Think of Amazon (the webshop): processing your order is fully automated, unless something goes wrong. We'd advice to use bare BPMN-engine for these projects, combined with an experienced Java development team. 

And last we have **Case Management**. This is a more complex form of business process automation. Typically, the course of a Case is not predictable. Based on Events that take place the handling of the case differs. Typically there will be a mix of automated and user tasks and often complex and event based processes. Take a spin with Valtimo.  
