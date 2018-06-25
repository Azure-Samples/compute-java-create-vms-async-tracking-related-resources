---
services: Compute
platforms: java
author: martinsawicki
---

## Getting Started with Compute - Create Virtual Machines Async Tracking Related Resources - in Java ##


  Making use of the reactive pattern in a complex virtual machine creation scenario
 
  This sample shows how the reactive pattern (RXJava's Observables) supported by the Azure Libraries for Java in their asynchronous API
  can be used for handling some more complex real world scenarios involving distributed computation in the cloud with relative ease.
  The specific example here shows how Observables enable real time tracking of the creation of many virtual machines in parallel and
  all their related resources. Since Azure does not support transactional creation of virtual machines (no automatic rollback in case
  of failure), this could be useful for example for the purposes of deleting "orphaned" resources, whenever the creation of some other
  resources fails. Or simply showing real-time progress in some UI to the end user.
 
  The sample goes through the following steps:
 
  1. Define a number of virtual machines and their related required resources (such as virtual networks, etc)
  2. Start the parallel creation of those virtual machines with observer logic keeping track of the created resources and reporting
     them on the console in real time
  3. Clean up the "orphaned" resources, i.e. those that were created successfully but whose associated virtual machine
     failed to be created for some reason.
 

## Running this Sample ##

To run this sample:

Set the environment variable `AZURE_AUTH_LOCATION` with the full path for an auth file. See [how to create an auth file](https://github.com/Azure/azure-libraries-for-java/blob/master/AUTH.md).

    git clone https://github.com/Azure-Samples/compute-java-create-vms-async-tracking-related-resources.git

    cd compute-java-create-vms-async-tracking-related-resources

    mvn clean compile exec:java

## More information ##

[http://azure.com/java](http://azure.com/java)

If you don't have a Microsoft Azure subscription you can get a FREE trial account [here](http://go.microsoft.com/fwlink/?LinkId=330212)

---

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.