# Active-Directory-Security-Analytics

## Objective

The aim of the project was to generate alerts for brute force attacks targeting endpoints within an Active Directory Domain environment and forward these triggered events to a central Cybersecurity Analyst channel. Splunk, Windows Active Directory DC, Shuffle and Slack were use to complete the telemetry cycle.

### Tools Used

- Splunk Enterprise for Windows Security log ingestion, data analysis and alert creation.
- Shuffle for automation and the integration of Slack into the workflow.
- Windows Server to act as the domain controller within the Active Directory environment.
- Slack for communication and recieving triggered alerts.

## Summary

<img width="542" height="344" alt="Diagram" src="https://github.com/user-attachments/assets/a077f298-f61e-4344-8af0-04ac1453115b" />

*Ref 1: Network Diagram*

Three main virtual machines were used; the first VM hosted the Windows Server, the second hosted the Splunk Enterprise Server and the third hosted the Windows 10 client machine which acted as the endpoint. All VM’s are within the same network environment, hence the green square. Essentially, an alert for multiple failed login attempts is triggered and the device name as well as a link to the alert is sent into a preconfigured channel in Slack for investigation.

Brute force attacks generate multiple log events of “failed log in attempts” and Windows logs this in its Security group as Event ID 4625. This Event ID is crucial when creating an alert on Splunk. A service called Splunk Universal forwarder is installed onto the Windows endpoint pointing to the IP address that is hosting Splunk Enterprise. This service forwards the Security logs which can be viewed on Splunk’s Dashboard on a browser. 


<img width="700" height="472" alt="Screenshot 2026-06-27 164319" src="https://github.com/user-attachments/assets/66733f58-b4a4-427c-9687-7ce96a444718" />

*Ref 2: Windows Server Domain*

Before creating an Active Directory environment, Active Directory Domain Services(AD DS) had to be installed and configured. This is so that we could utilise the Domain feature and create users and groups. As seen above, we created a user named Kulle KO. Otsuka and added him to the Tech Team security group. Now we are able to sign into the domain using the credentials that we have associated with Kulle's account. The Windows 10 Client uses this account to sign into the domain "splunklab.local".
