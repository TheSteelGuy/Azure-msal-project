# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

For **both** a VM or App Service solution for the CMS app:
- Analyze costs, scalability, availability, and workflow
- Choose the appropriate solution (VM or App Service) for deploying the app
- Justify your choice


**Azure VMs**

**Costs**
- Azure Vms tend to be much more expensive than Azure App services.
- The underlying reason why this is so is becuase of the flexibility offred with virtual machines
as well us the freedom of confugurations possiblities offered by azure vms, furthermore costs come in form of additional computational power which comes with the needs of an app

**Scalability**
- Azure VMS are highly scalable as more than one VM can be spawn to allow horizontal sacaling
- They can be used with load balancers to control instances multiple instances depending on the amount of traffic
- According to ms documentation from https://docs.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree Platform image: 1000 nodes per scale set, Custom image: 600 nodes per scale set are the scaling limit for vms

**Availability**

- Since Scaling and load balancing is possible with VMs, Apps running on vms can be highly available as load balncers are bale to
route traffic to fully functional Vm instance, leading to very minimal app downtime.
- At the same time availabilty level there might be cases when your application becomes slightly unvailable especially when you have to do  upgrades on or vm cleaning, or problems with your virtual machine can cause some downtimes.

**WorkFlow**
- The process of creating Vms has a lot of configurations in it since as much as alot is abstracted, one still need to do basic configarations such as those of nginx(if deploying an app with uses nginx as a server)
- Azure vms gives total control about the  application configuration management

## App Service ##

**Costs** 

 - Cheaper compared to Vms, tis comes as a possibility offred by app service to run multiple stack such as python dot NET;
 Therefore its possible to combine multiple apps to save money
 - Finaly testing on free tiers are possible with app service as opposed to Azure VMs

**Scalability**

 - Vertical scaling possible(but up to a certain limit). If Horizontal scaling is needed, the use of VMS will be needed

**Availability**
- High availability and auto-scaling, futhermore, since azure cloud does all the inhouse maintainace of the containers, breaking the enviroments is less as compared to azure vms. this is possible factor to high availabilty of Azure app services.

**Workflow**

 - Minimal configurations, Continuos  deployment  possible with for example github actions, at the same time since the developer have less control of the enviroment, they have to use the workflow that is already defined .

 My Choice is  ```App Service```.

 I choose app service due to the fact that this is a small and basic web app, therefore using a VM would be an overkill
 Secondly With the App service, most of the configarations have already been done for me, just have to focus on the app deployment.
 Furthermore, looking at the cost aspect of it, App swrvice wins.



### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

To Switch to Vms, the app would have to have grown in size and user base have increased to the extent of needing to use tools like load balancers.
Also if the needs of an the app as diversified to the extent that i need custom app, developed in lanaguages not supported with app service, finally if i need multiple instances for the purpose of horizontal scaling