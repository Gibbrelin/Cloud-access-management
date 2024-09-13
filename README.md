
# Cloud Access Management - Setup Guide

This guide walks you through the process of setting up user access and user groups for cloud access management using AWS Identity and Access Management (IAM). IAM allows you to manage access to AWS resources securely and efficiently. We will cover how to create users, user groups, and attach permissions to both users and groups.

# Table of Contents

Prerequisites

Step 1: Creating a User

Step 2: Creating User Groups

Step 3: Managing User Credentials

actively testing Group policies

Best Practices

References

# Prerequisites

Before you begin:

. You need an AWS account with Administrator Access privileges.

. Basic understanding of AWS Identity and Access Management (IAM).

# Step 1: Creating a User

1.1 Sign in to AWS Management Console
 . Go to the AWS Management Console and sign in with an account that has permissions to create IAM users.

1.2 Open the IAM Console
 . In the AWS console, search for and select IAM.

1.3 Add a New User
 . In the IAM dashboard, click Users on the left sidebar.
![Screenshot 2024-09-12 150840](https://github.com/user-attachments/assets/4e2cdb7d-90ae-4c7d-ae82-0dfd47f8971c)

 . Click Create user.
![Screenshot 2024-09-13 141004](https://github.com/user-attachments/assets/8b53c2c1-dee5-4c07-abae-9e5063f5b987)

 . Enter a unique User name.
![Screenshot 2024-09-12 174548](https://github.com/user-attachments/assets/1ee5f9c3-9049-4938-930e-e9d902d86d2c)

 . Under Access type, choose the required type:
Programmatic access: For users who need to interact with AWS via the AWS CLI, SDK, or API.
AWS Management Console access: For users who will access the AWS Console via a web browser.

 . Set the Console password (for console access) and choose whether the user must create a new password at next sign-in.
![Screenshot 2024-09-13 141751](https://github.com/user-attachments/assets/d95a320a-f96e-41b4-aad7-45f1a0f57cfd)

 . Click Next: Permissions.
![Screenshot 2024-09-12 174701](https://github.com/user-attachments/assets/8f21604d-16dc-452b-9802-54032da7b4e2)
. You can assign permissions in three ways:

Add user to group: Assign the user to a group with predefined permissions.

Attach policies directly: Assign specific policies to the user.

Copy permissions from an existing user.


# Step 2: Creating User Groups

2.1 Navigate to User Groups

 . In the IAM dashboard, click User groups in the left-hand sidebar.
 ![Screenshot 2024-09-12 150840](https://github.com/user-attachments/assets/4e2cdb7d-90ae-4c7d-ae82-0dfd47f8971c)

 . Click the Create group button.
![Screenshot 2024-09-13 143032](https://github.com/user-attachments/assets/d2349ad0-eafd-4f8d-a714-80d26abc20e5)

2.2 Define Group Settings

 . Provide a Group name (e.g., "Developers", "Admins", "HR", etc.).
![Screenshot 2024-09-12 151749](https://github.com/user-attachments/assets/55b2bae2-f363-44e6-9664-8c2f16d01eed)

 . Optionally, attach users to the Group. This step can also be done later.
![Screenshot 2024-09-12 151830](https://github.com/user-attachments/assets/dbe13276-f75e-4538-bf77-e3ba35b61e81) 

 . Optionally, attach predefined permissions to the group by selecting one or more IAM Policies. This step can also be done later.
![Screenshot 2024-09-12 151848](https://github.com/user-attachments/assets/5f0a9232-f1ad-4389-86d5-5dd29b0e171c)

2.3 Finalize and Create Group

 . Review the group settings.

 . Click Create group to save the new group.


# Step 3: Managing User Credentials

3.1 Accessing User Credentials

. Once you create a user with programmatic access, AWS generates Access Keys and Secret Keys for API/CLI use. Ensure that these credentials are securely stored.

. To download the access keys:

. After creating the user, you'll have the option to download a .csv file containing the access key ID and secret access key.

IMPORTANT: This is the only time the secret key will be available. If lost, you will need to regenerate new keys.

3.2 Enabling Multi-Factor Authentication (MFA)

. For added security, enable Multi-Factor Authentication (MFA) for users.

. In the IAM dashboard, click Users.

. Select the user and click on the Security credentials tab.

. Under Multi-Factor Authentication (MFA), click Assign MFA device.

. Follow the on-screen steps to associate an MFA device (e.g., a virtual MFA app like Google Authenticator or a hardware MFA device).

# Actively Testing Group Policies 
For the testing process i created Two Groups with difference Policies and added users to them

ACCOUNTING AND HR DEPARTMENT 
and added user Alice and John respectively

# Best Practices

. Follow the Principle of Least Privilege: Assign users the minimal level of access they need to perform their tasks.

. Use Groups Over Individual Users: Apply policies to groups rather than directly to users to streamline management.

. Enable MFA for All Users: Require multi-factor authentication for users to protect sensitive resources.

. Rotate Credentials Regularly: Ensure that users regularly rotate their passwords and access keys to reduce security risks.

. Audit User Permissions: Periodically review user permissions and remove any unnecessary access rights.

# References

AWS IAM Documentation

Best Practices for IAM

AWS Identity and Access Management (IAM) Pricing
