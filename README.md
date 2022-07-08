# ARM-Template-Ingestor
Automatically creates ServiceNow catalog items based on ARM template ingestion

CPG contains a facility to point to a URL annd read an existing Azure ARM template and ultimately create a catalog item with the inputs to support the template.

This utlity serves to replicate that functionality outside of CPG with some additional features not found in CPG.

Through the execution of the supporting flow, the automation will read an existing ARM temaplte from a URL and process the template and supporting metadata to create a catalog item with input variables. The utility will read and process variable metadata to set various properties on the inptus such as max length, description, min and max value.

The utlity will also check for the presense of a UI definition file and if found process adiditonal more details variable details to further refine catalog item variable definitions.

More information on Azure ARM UI definition files and related syntax can be found <a href="https://docs.microsoft.com/en-us/azure/azure-resource-manager/managed-applications/create-uidefinition-elements">here</a>. All of Azure's sample ARM templates have supporting UI definition files and can be referenced as examples. These deifnition files allow us to do things such as set variable type (Text field, drop down, etc), set tool tips, set default values, set constraints, and more.

More information on the structure and syntax of Azure ARM templates can be found <a href="https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/syntax">here</a>.
