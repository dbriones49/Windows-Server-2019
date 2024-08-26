# Windows Server 2019( in progress)


## Introduction


In today's dynamic IT landscape, Active Directory Domain Services (AD DS) plays a crucial role in managing and securing network resources within organizations. By providing a centralized framework for user authentication, authorization, and resource management, AD DS simplifies administrative tasks and enhances security protocols. This project showcases the configuration of Windows Server 2019 as an AD DS server. After the domain controler is intsalled, the following will be completed.

- Add standard OUs.
- Add Firewall GPO on the DC for DISABLE firewall
- Allow inboud AD, File and Print Sharing, and WMI.
- Allow OUtbound AD<L File and Print Sharing, And WMI.
- Allw inbound Custom Ping ICMPv4.


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



Next, we will configure group Policy Management. This can be configured by going to Tools>Group Policy Management.






# Stats









 




# Conclusion






