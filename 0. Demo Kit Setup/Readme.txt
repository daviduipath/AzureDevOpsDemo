Please visit the formal Atlassian Demo Kit page for all details:

If you have not yet Configured SAP, please follow the instructions here:
https://uipath.atlassian.net/wiki/spaces/FAN/pages/430768758/01+Getting+Started+with+SAP+Automation

You will have to install SAP GUI, setup a connection, and modify your hosts file to allow access to SAP Fiori.

Create following resources in Orchestrator:

Assets:
'SAP Credentials FIN' (credential) => username:S4H_FIN password: Welcome1 
'SAP Credentials SD' (credential) => username:S4H_SD_DEM password: Welcome1
'SAP Fiori URL' (text) => https://vhcals4hci.dummy.nodomain:44300/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=804&sap-language=EN#Shell-home
'SAP WinGui Connection' (text) => SAP S4 HANA 1909
'SAP Order Number' (text) => You can put any number as a placeholder.
'SAP Server IP' (text) => 54.204.119.178
'SAP WinGui Connection' (text) => SAP S4 HANA 1909

Test Data Queue:
'Order Numbers' (from schema TestDataQueueSchema.json)

Change Variables in Workbook:
In '2. WinGui Library/Setup Environment WinGui.xaml', set the value of the Orchestrator folder argument to the name of the Orchestrator folder where you placed all your assets and credentials
In '3. Fiori Library/Setup Environment Fiori.xaml', set the value of the Orchestrator folder argument to the name of the Orchestrator folder where you placed all your assets and credentials

Potential Errors
-> Fail on Add Test Data Queue. If this occurs, make sure that you are connected to the right Orchestrator folder where your test data queue is located.
