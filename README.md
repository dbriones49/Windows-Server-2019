# Windows Server 2019( in progress)


## Introduction


In today's dynamic IT landscape, Active Directory Domain Services (AD DS) plays a crucial role in managing and securing network resources within organizations. By providing a centralized framework for user authentication, authorization, and resource management, AD DS simplifies administrative tasks and enhances security protocols. This project showcases the configuration of Windows Server 2019 as an AD DS server. After the domain controler is intsalled, the following will be completed.

- Add standard OUs.
- Add Firewall GPO on the DC for DISABLE firewall
- Allow inboud AD, File and Print Sharing, and WMI.
- Allow Outbound AD, File and Print Sharing, And WMI.
- Allow inbound Custom Ping ICMPv4.

Adding firewall Group Policy Objects (GPOs) on the domain controller to disable the firewall is essential for ensuring that critical services such as Active Directory, file and print sharing, and Windows Management Instrumentation (WMI) can communicate effectively without being blocked. Additionally, configuring specific rules to allow inbound and outbound traffic for these services, along with permitting inbound custom Ping and ICMPv4, facilitates necessary network operations and monitoring while maintaining a controlled security posture.


# Active Directory installation
During deployment, the server must be promoted as a Domain controller and a new forest should be created. 


![image](https://github.com/user-attachments/assets/a49795fa-ab40-46ec-9843-e65b6b69bc53)


![image](https://github.com/user-attachments/assets/10625837-2931-420a-93da-4dee0ffd1740)

![image](https://github.com/user-attachments/assets/7c2fc30d-a506-48f9-a5c1-7259aa209994)


The VM connection will be established through Bridge Adapter and the IP Scope will be confirmed accordingly to ensure a static IP address will be used.


![image](https://github.com/user-attachments/assets/cf445dc0-628e-4bea-b4ab-602352897c28)



We can confirm the domain controller has been deployed and all the domains with the forest.

![image](https://github.com/user-attachments/assets/91931188-5c74-4708-9d6b-ebfe5bcf20d5)




Our internet connectivity has now also been confirmed.



![image](https://github.com/user-attachments/assets/2ac065b6-f7eb-4413-bc38-c9a063e53878)



Now, the Orgainization Units must be set up. This can be configured by going to Tools>Users and Computers.  Creating Organizational Units (OUs) in Active Directory is essential for managing and organizing network resources, as they allow administrators to group users, computers, and other objects based on specific criteria such as department, location, or function. This hierarchical structure not only simplifies delegation of administrative tasks and application of Group Policies but also enhances security and operational efficiency.




![image](https://github.com/user-attachments/assets/500f34df-1a24-406d-aac3-636c2f2310a4)






![image](https://github.com/user-attachments/assets/aee3d643-6ab7-4e84-af6a-b441b492e4b4)



Next, we will configure group Policy Management. This can be configured by going to Tools>Group Policy Management, and then creating it in the domain. For this example we will create a Firewall Group Policy.

![image](https://github.com/user-attachments/assets/45919401-ef80-4ff0-9b45-d42d43a7a861)



Right click on Firewall and click edit. The in the Management editor go to Computer Configuration>Policies>Windows Settings>Security Seetings. From here we can enter the Windows Defender Settings, and adjust the inbound and outbound rules.




![image](https://github.com/user-attachments/assets/d1f9caaa-6c1d-4a9e-9b03-e26484ab0263)






![image](https://github.com/user-attachments/assets/58a3de42-9626-47c4-a026-ce61408caab1)





![image](https://github.com/user-attachments/assets/b8c3d2f4-a77b-4566-b52f-ff3223e2b7be)







Here we are allowing the inbound traffic.



![image](https://github.com/user-attachments/assets/bf9549b1-7109-4128-ab42-4162c21faf1f)




To create the inbound new rule, go to Inbound>New Rule, and then select Predefined ADDS, and allow the connection.






![image](https://github.com/user-attachments/assets/b43ab740-9669-4d34-994b-6a52c4032eb4)




We repeat this step to create the predefined rules for File and Print Sharing and WMI.





![image](https://github.com/user-attachments/assets/9ed20f90-5cdf-4bf9-986c-498b48c4fa0a)




![image](https://github.com/user-attachments/assets/daf366d2-b675-48ae-8eb1-10233bd398f6)


The steps are then repeated for the outbound predefined rules for ADDS,  File and Print sharing, and WMI.







![image](https://github.com/user-attachments/assets/2599803b-a012-49d7-96e2-519d8193095f)



Lastly, the custom ping inboud rule can be configured by Selecting a custom rule and then chosing ICMPV4





![image](https://github.com/user-attachments/assets/1e2e173a-1e73-49dc-8f44-c90988a72865)





![image](https://github.com/user-attachments/assets/9badb348-afea-4525-9509-dd4e17a9bffe)



In a command prompt, the command gpdate /force will complete the group policy update and force the policy to take effect.




![image](https://github.com/user-attachments/assets/5b35bc29-3275-40f6-aa10-878122e798dd)


To view the results, the CMD command gpresult /r can be used.




![image](https://github.com/user-attachments/assets/26a68d58-9ce9-49b6-ba45-4ee898865adf)




![image](https://github.com/user-attachments/assets/9168880e-f3c1-4f0e-9f21-f351d731ca4b)





# Deploy and Configure DNS Server

Setting up a new DNS server is crucial in a newly engineered network as it facilitates the resolution of domain names to IP addresses, enabling seamless communication between devices. Additionally, integrating DNS with Active Directory Domain Services (ADDS) ensures efficient resource location and management, enhancing overall network performance and reliability. Here we will configure a new DNS server. 


 

Once the server has beeen renamed, and a static IP address is used, we launch the Add roles and features wizzard.

![image](https://github.com/user-attachments/assets/603a03a8-b953-4d24-b9a9-e0abba8ca0c8)



![image](https://github.com/user-attachments/assets/1ffd04d6-d493-47aa-9fa0-7cace6d3e37c)



# Conclusion

Deploying a domain controller like Active Directory Domain Services (ADDS) is crucial for managing user authentication and authorization within a network, ensuring that only authorized users can access specific resources. From a security standpoint, it centralizes identity management, enabling robust policy enforcement, streamlined access control, and enhanced auditing capabilities, which collectively help mitigate risks and protect sensitive data




