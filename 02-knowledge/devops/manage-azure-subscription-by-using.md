---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/azure
  - topic/networking
  - topic/project
---

# Manage Azure subscription by using

Azure Active Directory (Azure AD)
Manage access to Azure AD resources, such as user accounts and passwords.

**Azure role-based access control (RBAC)** 
Roles are used to manage access to virtual machines, storage, and other Azure resources.

A role might be described as a collection of permissions.

Roles:
		**Owner**: Has full access to all resources, including the ability to delegate access to other users.
		**Contributor**: Can create and manage Azure resources.
		**Reader**: Can view only existing Azure resources.
		**User Access Administrator**: Can manage access to Azure resources

Azure RBAC roles at four levels of scope:
Management groups
Subscriptions
Resource groups
Resources

![[attachments/2-scope-levels-example.png]]

subscription can have a different billing and payment setup, so you can have different subscriptions and plans by office, department, project
 A resource group includes those resources that you want to manage as a group

Azure AD also has its own set of roles, which apply mostly to users, passwords, and domains.

Global Administrator
User Administrator
Billing Administrator:

Global Administrator doesn't have access to Azure resources. 
The Global Administrator for Azure Active Directory (Azure AD) can temporarily elevate their permissions to the Azure role-based access control (RBAC) role of User Access Administrator.

Global Administrator can view when their permissions are elevated to User Access Administrator.

![[attachments/2-globaladmin-user-access-admin.png]]

## Related
- [[devops-moc]]
- [[nat-instances-and-nat-gateways-network-address-translation]]
- [[network-access-control-lists-vs-security-groups]]
- [[questions-power-user-access-allows]]
