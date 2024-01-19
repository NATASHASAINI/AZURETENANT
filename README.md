
# Configuring Azure Active Directory (Tenant Level-Logging &Monitoring)and analyzing logs using KQL
![AAD-Logging& Monitoring ](https://github.com/NATASHASAINI/AZURETENANT/assets/156629309/59a50e19-33ad-48ab-8e44-18fba036c2f0)

## Introduction
In this project,AosCyberGroup a fictional company, deployed an Azure-based honeynet open to the Internet to attract hackers. Log sources from various instances are collected in a Log Analytics workspace, enabling Microsoft Sentinel to generate attack maps, alerts, and incidents. Initial security metrics were measured over 24 hours in the insecure environment. Subsequently, security controls were implemented to fortify the environment, and metrics were measured for another 24 hours. One of those logs was Azure Active Directory Logs. Azure Active Directory Logs capture the complete sign-in activity history and maintain an audit trail of all activities and changes within Azure AD for a specific tenant. These logs encompass sign-in and audit logs, detailing the activities and modifications that occur within the Active Directory. To seamlessly transmit these sign-in and audit logs to the Log Analytics workspace, I will configure the AAD diagnostic setting accordingly.

## Stepwise Configuration of Azure AD Logging

![image](https://github.com/NATASHASAINI/AZURETENANT/assets/156629309/8aa8a261-a5ed-46ca-9b5d-c5435335cacd)


1.From the Azure home page, search for Azure Active Directory in the search bar<br>
2.Click to open the Azure Active Directory from the drop-down menu.<br>
3.From the Azure Active Directory page<br>
4.Click Diagnostic setting and then<br>
5.Click Add diagnostic setting to configure the Diagnostic setting<br>

![image](https://github.com/NATASHASAINI/AZURETENANT/assets/156629309/69e5e045-177b-4bbd-b276-5f2574517abc)

6.Give the Diagnostic setting a name by entering a name. In this case, the name is "AAD-Logs"<br>

7.Select from the Logs categories which Logs you want to collect i.e.: AuditLogs, Signinlogs, ManagedIdentitySigninLogs, RiskyUsers, etc...<br>

8.Select the destination for the selected logs. In this case, they are sent to the Log Analytics workspace<br>

9.Select the appropriate Subscription. In this case "Azure Subscription 1"<br>

10.Select the appropriate Logs Analytics workspace. In this case, "new-Law-Cyber-lab -090" which resides in the east US 2<br>

![image](https://github.com/NATASHASAINI/AZURETENANT/assets/156629309/b8134526-ff56-45a4-a6e8-ba0eeaddd386)


11.Click Save to create the Diagnostic setting for Azure Active Directory Tenant<br>

12From the Azure home page, search for Log Analytics workspace in the search bar<br>

13.Click to open the Log Analytics workspace from the drop-down menu<br>

![image](https://github.com/NATASHASAINI/AZURETENANT/assets/156629309/f9c851c5-f704-41ac-858e-52e61180c4e1)


14.From the Log Analytics workspace page<br>

15.Click Logs to access the query page<br>

16.Type AuditLogs ( AuditLogs is one of the Logs categories selected to be sent to the Log Analytics workspace)<br>

17.Click Run to run the AudiLogs query<br>

18.The results of the query are populated in the Log Analytics workspace<br>

19.Press Enter twice then type SigninLogs (SigninLogs is one of the Logs categories selected to be sent to the Log Analytics workspace<br>

20.Click Run to run the SigninLogs query<br>

![image](https://github.com/NATASHASAINI/AZURETENANT/assets/156629309/2279c392-1ab5-484f-b317-390f995255fb)

21.The results of the query are populated in the Log Analytics workspace<br>

## Conclusion

The configuration of the Azure Active Directory logs ingestion into the Log Analytics workspace was successful. Now, these logs are being efficiently collected and stored for analysis. This configuration enables the monitoring of Azure tenant-level logs through both the Log Analytics workspace and Microsoft Sentinel. By centralizing the logs in the Log Analytics workspace, organizations gain a comprehensive view of their Azure Active Directory activities and can leverage the powerful capabilities of Microsoft Sentinel for advanced threat detection and response. This integrated setup enhances the security and visibility of the Azure environment, enabling proactive monitoring and efficient incident management.



