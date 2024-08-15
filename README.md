# ActiveDirectoryProject

# Active Directory Project: User and Group Management with Group Policy Implementation

## Objective
Set up an Active Directory environment focusing on user and group management tasks.

## Overview:
This project involves configuring an Active Directory environment to handle basic user and group management tasks. The server is hosted on Amazon EC2, dedicated home lab environment.

## Tasks Completed
1. **Organizational Units (OUs) Creation**
   - Created OUs: Marketing, IT, Sales, HR.

2. **User Accounts Creation**
   - Created three user accounts within each OU:
     - Marketing: Sandesh
     - Sales: James
     - HR: Jack
     - IT: Help Desk

3. **Group Creation**
   - Created a group called "Employee".

4. **Group Membership**
   - Added all user accounts from the Marketing, Sales, HR, and IT OUs to the "Employee" group.

5. **Password Policy Implementation**
   - Set a password policy with:
     - Minimum length of 10 characters
     - Combination of uppercase and lowercase letters
     - At least one number
     - At least one special character (e.g., !, @, #)
   - Configured lockout policy:
     - 5 incorrect attempts
     - Account locked for 30 minutes
    
6. **Testing and Validation**
   - Tested a user account with sample passwords to ensure the password policy is effective.
   - Verified the "Help Desk" user account privileges.

## Screenshots 
Here are screenshots showing the completion of the project. I've kept the explanation simple and easy to follow, without going into too much detail. The steps are straightforward and easy to understand.
1. Start by creating a Windows Server EC2 instance using your AWS account. This step is quite simple, and there are plenty of tutorials and videos available online to guide you through the process. Plus, it's free to use.
2. Download the "Microsoft Remote Desktop" application and use it to connect to your Windows Server EC2 instance.
   ![rdp](https://github.com/user-attachments/assets/784ef952-6267-4d29-a0d7-e87370de7796)
3. After logging into the server, open Server Manager, navigate to "Add Roles and Features," and install "Active Directory Domain Services".
  ![install AD](https://github.com/user-attachments/assets/f158804f-21f7-4b15-b74c-086b76fb36dd)
4. Promote the server to a domain controller, enabling you to establish domains within the network.
  ![prmote DC](https://github.com/user-attachments/assets/d2c00b0d-ea23-4758-a607-cfafa47ef27a)
5. Create a new forest and specify the root domain name.
   ![new forest](https://github.com/user-attachments/assets/4da82501-9d8d-4566-b79e-a9cecce99d21)
6. You can follow these steps to create Organizational Units within the domain.
  ![create OU](https://github.com/user-attachments/assets/b3aafaeb-b3c9-44cc-89b5-69df4b049e04)
7. You can follow these steps to create Users within the domain.
  ![create user](https://github.com/user-attachments/assets/913cd206-4677-4d79-b589-d79653f92768)
  ![create user 2](https://github.com/user-attachments/assets/4dcdc464-f3e2-4899-a59a-597f80d12f89)
9. You can follow these steps to create Group within the domain.
  ![create group](https://github.com/user-attachments/assets/06670e73-f18d-4a04-b0d8-f0a6c4a0928f)
10. You can use these steps to add user accounts to the newly created group.
  ![group properties](https://github.com/user-attachments/assets/d21bc230-6c16-46c3-b800-dd0433273e20)
  ![add users to group](https://github.com/user-attachments/assets/467b2c3f-4d17-4f7a-87bc-e6232f4a8cc7)
11. You can modify user privileges; for example, the Helpdesk user account has been granted administrative privileges.
  ![admin to helpdesk](https://github.com/user-attachments/assets/f90d687d-3d05-481d-8462-a2b103ca018b)
12. To configure group policies, navigate to **Tools** and select **Group Policy Management**.
  ![group policy](https://github.com/user-attachments/assets/1f83b3cc-bd69-46ba-84ab-0ecb04ad8e65)
13. Choose the policy option as displayed in the image, then click **Edit**.
  ![edit policy](https://github.com/user-attachments/assets/15d87453-d617-40cc-bc68-5318f260069e)
14. After the **Group Policy Management Editor** opens, navigate to the **Account Policies** section to make your changes.
  ![account policies](https://github.com/user-attachments/assets/b3bdd6bb-fd7f-4d51-b49d-c336e700a3b3)
15. Adjust the policy settings, including the minimum password length and the account lockout policies.
  ![password characters](https://github.com/user-attachments/assets/8b5e6011-2ef5-48b3-861a-1bfa8fd98dc6)
  ![account lockout](https://github.com/user-attachments/assets/8ac52468-e4c9-4025-bdde-accd0ef6269e)
  ![lockout time](https://github.com/user-attachments/assets/7b54f945-b85b-4beb-91a6-b0cc3c2ff1fe)
16. Open Command Prompt and verify that the policies have been implemented by using the command `net accounts`.
  ![policy imp check](https://github.com/user-attachments/assets/6d8713f0-1642-4778-891e-6623885d708f)
17. Enter the command `gpupdate /force` to enforce the policy updates, and then verify the implementation again.
  ![policy imp verified](https://github.com/user-attachments/assets/99023e48-f97e-4dd1-b80c-7dc57969b978)

It's essential to verify the policy implementation and domain member assignments from the client side. I conducted this project in my home lab environment. You can set up your own home lab or use a virtual machine to do the same.

Feel free to practice on your own to explore additional features in Active Directory, such as resetting account passwords, unlocking locked accounts, disabling and enabling accounts, changing group memberships, and modifying privileges.

