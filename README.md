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
