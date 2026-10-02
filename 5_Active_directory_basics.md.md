- A **Windows domain** is a group of users and computers under the administration of a given business.
- The main idea behind a domain is to centralize the administration of common components of a Windows computer network in a single repository called **Active Directory (AD)**. 
- The server that runs the Active Directory services is known as a **Domain Controller (DC)**.
- The core of any Windows Domain is the **Active Directory Domain Service (AD DS)**. It's a catalogue of "objects" in the system. Various objects could be:
	- Users are objects(security principal) that can act upon resources in the network. There are two types: People and Services.
	- Machines are the type of objects that get added whenever a new computer is added to the AD. They are also considered security principals (can be authenticated by the domain and can be assigned privileges over **resources** like files or printers) and are assigned an account.
		- Name is made up of computer's name with a $ sign at the end.
- Security groups ease active directory operations such as, assigning privileges, managing permissions, and distributing resources. Important groups include:
![[Screenshot 2026-06-21 204432.png]]
- **Organizational Units (OUs)** are container objects that allows us to classify users and machines. 
![[678ecc92c80aa206339f0f23-1751295060689.png]]
Here is a typical OU screenshot. OUs and Security groups serve different purposes. OU is used to applying different policies to users and computers, whereas, security groups are used to grant permission over the resources. One user can only be part of one OU but multiple security groups.

- One cannot delete an OU by default. The following steps must be followed:
	- Click 'View' at the top, select 'Advanced Features', and go to 'Objects'
	- Unselect the accidental deletion option at the bottom.
	- Click 'Apply' and then Delete the OU after confirmation.
- Delegation: This is the process of granting privileges to a user over some OU or other AD Object.

**Group Policy Objects (GPO):**
- A collection of settings that can be applied to OUs.
	- GPOs are configured using the Group Policy Management tool.
- GPO Distribution: GPOs are distributed to the network via a network share called `SYSVOL`, which is stored in the DC. 
- There is usually a delay between changing a policy and the domain controllers syncing the PCs. However, if we want to invoke the changes immediately, we can do so by using: `gpupdate /force`
- GPOs can be used to apply very specific settings and implementations of on objects in our AD.

**Authentication methods:**
When a user wants to request a service on the network, they have to authenticate using one of the two methods below:
- Kerberos: New
	- User encrypts their username and timestamp using a key made from their password, send it to the KDC (Key Distribution Center), which is a service that makes tickets.
	- The KDC responds to this by creating **Ticket Granting Ticket (TGT)** and a **session key**. 
		- Note: TGT itself contains a copy of the session key, but it sends an additional unencrypted copy to the user for use in the next step.
		- Note: TGT is encrypted using krbgtg's (the KDC's account) password, so the user can't access it's contents.
	- To request a specific service, the user then encrypts their username and timestamp using their **session key**, and sends it to the KDC along with the TGT and Service Principal Name (SPN).
	- This results in the KDC sending a TGS along with a Service Session Key. 
		- Note: The TGS is encrypted using a key derived from the **Service Owner Hash.**
	- The TGS is then sent to the service, which authenticates by validating the Service Session Key. 
- NetNTLM: Old
	- The client sends an authentication request to the server they want to access.
	- The server generates a random number and sends it as a challenge to the client.
	- The client combines their NTLM password hash with the challenge (and other known data) to generate a response to the challenge and sends it back to the server for verification.
	- The server forwards the challenge and the response to the Domain Controller for verification.
	- The domain controller uses the challenge to recalculate the response and compares it to the original response sent by the client. If they both match, the client is authenticated; otherwise, access is denied. The authentication result is sent back to the server.
	- The server forwards the authentication result to the client.
Note: The user's password is never sent through the network for any of the authentication methods. 

**Trees and forests**:
Domain: A system of users, services, and a DC.
Tree: Comprised of multiple domains.
Forests: Comprised of multiple trees/namespaces.
Trust relationships: A relationship that can be established either one-way or two-way to allow users from one domain to access resources from another domain.
Enterprise Admins: The **Enterprise Admins** group can grant a user administrative privileges over all of an enterprise's domains.