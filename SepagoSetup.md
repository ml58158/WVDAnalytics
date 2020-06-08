# Sepago Monitoring Agent for WVD Installation Guide 

## Installation of the Sepago Monitoring Agent for WVD into Log Analytics Workspace


1.	From the Azure Portal, you select create a resource and search for Azure Monitor for RDS and Windows Virtual Desktop.
2.	After selecting Azure Monitor for RDS and Windows Virtual Desktop, 
    select the Create button to deploy the application.
3.	Download the Sepago Agent files from the Sepago site onto the image or session hosts.
4.	Extract the entire folder into C:\Program Files.
5.	Open the ITPC-LogAnalyticsAgent.exe.config file located inside the extracted folder in Notepad.
6.	Edit the CustomerId line to include the Log Analytics Workspace ID between the quotes.
7.	Edit the SharedKey line to include the Primary Key between the quotes.
8.	Save changes to the file.

## Deploy the Sepago Monitoring Agent for WVD onto your Image

1.	Open a Command “CMD” Window as Administrator. 
    Change directory to where the agent has been extracted. (C:\Program Files\...)
2.	Run the following command to test the configuration: ITPC-LogAnalyticsAgent.exe -test
3.	Check for any errors that may be preventing the data from uploading to Azure.
4.	If the test was successful, then proceed to install/deploy the agent.
5.	Run the following command to deploy: ITPC-LogAnalyticsAgent.exe -install 
    This creates the scheduled task required to send the data to the Azure Log Analytics Workspace.
6.	Allow 2-3 hours for data to populate in the workspace, then use the queries in the next section to test for data validation. 
