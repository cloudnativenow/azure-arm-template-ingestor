# ARM-Template-Ingestor
Automatically creates ServiceNow catalog items based on ARM template ingestion

CPG contains a facility to point to a URL annd read an existing Azure ARM template and ultimately create a catalog item with the inputs to support the template.

This utlity serves to replicate that functionality outside of CPG with some additional features not found in CPG.

Through the execution of the supporting flow, the automation will read an existing ARM temaplte from a URL and process the template and supporting metadata to create a catalog item with input variables. The utility will read and process variable metadata to set various properties on the inptus such as max length, description, min and max value.

The utlity will also check for the presense of a UI definition file and if found, process additional variable attributes . These are commonly used when presenting ARM templates in the Azure Catalog.

More information on Azure ARM UI definition files and related syntax can be found <a href="https://docs.microsoft.com/en-us/azure/azure-resource-manager/managed-applications/create-uidefinition-elements">here</a>. Most of Azure's sample ARM templates have supporting UI definition files that can be referenced as examples. These deifnition files allow us to do define variable attributes such as set variable type (Text field, drop down, etc), set tool tips, set default values, set constraints, and more.

More information on the structure and syntax of Azure ARM templates can be found <a href="https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/syntax">here</a>.


The process is initiated by executing a sub flow called "Process ARM Template" with a single input called URL. URL points to a location containg an ARM template.

<img width="1389" alt="image" src="https://user-images.githubusercontent.com/48064904/178052088-01a2fb05-eb06-4da0-a163-98c725f38982.png">

The resulting catalog item will contain the variables and key attributes as defined in the ARM template and if provided further in the UI definition file. You can see in the image below that in this example a drop down field with available values was created. Attributes such as tooltips and mandatory and read only were set as well base don the template definition and supporting UI defintiion file parsing.

![image](https://user-images.githubusercontent.com/48064904/178052488-c47d026f-e4f0-4626-bd00-e0fc507ccfdf.png)

The update set includes the following files
<img width="1658" alt="image" src="https://user-images.githubusercontent.com/48064904/178053178-5c58962d-1522-4274-b645-a328607f4801.png">


