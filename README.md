# IAM

# EXPERIMENT 06

# NAME : mohan m

# REGISTER NUMBER : 212224220064

#DATE: 03/09/2026

## EXPERIMENT NO. 6 Login into AWS and Implement Identity Management Using Amazon IAM

## Aim

To create and configure IAM users and groups in AWS, assign permissions using IAM policies, enable console access, and verify role-based access to Amazon S3.

## Requirements

• AWS Account

• Internet connection

• Web browser

• Amazon S3 bucket

Procedure

## Step 1: Login to AWS Management Console

Open a web browser.

Go to the AWS Management Console.

Sign in using the AWS account credentials.

Search for IAM using the AWS search bar.

Open IAM (Identity and Access Management).

<img width="1535" height="954" alt="Screenshot 2026-09-17 211016" src="https://github.com/user-attachments/assets/07ac6015-a7fe-4f07-aa8c-bea450e77d29" />

## Step 2: Create an IAM Group

In the IAM dashboard, select User groups from the left-side menu.

Click Create group.

Enter the group name:

cloudSecurity_2026

Do not add users at this stage if the user will be created separately.

Click Create user group.

The group cloudSecurity_2026 is now created.

<img width="1535" height="959" alt="Screenshot 2026-09-17 211122" src="https://github.com/user-attachments/assets/6f091b0b-59a4-4e94-8598-c3acfa85fe83" />

## Step 3: Attach an IAM Policy to the Group

Open the cloudSecurity_2026 group.

Select the Permissions tab.

Click Add permissions.

Select Attach policies directly.

Search for:

AmazonS3ReadOnlyAccess

Select the checkbox for AmazonS3ReadOnlyAccess.

Click Next and then Add permissions.

The group now has read-only access to Amazon S3.

<img width="1534" height="959" alt="Screenshot 2026-09-17 211328" src="https://github.com/user-attachments/assets/9fe05fd2-03e5-4bf7-9b4d-0b7fda1dbde4" />

## Step 4: Create an IAM User

From the IAM navigation menu, select Users.

Click Create user.

Enter the username:

student01

Click Next.

<img width="1534" height="959" alt="Screenshot 2026-09-17 211459" src="https://github.com/user-attachments/assets/53cb3aa4-9c4c-4d61-875d-f735a6261141" />

## Step 5: Add the User to the IAM Group

On the Permissions page, select Add user to group.

Select: cloudSecurity_2026

Click Next.

Review the configuration.

Click Create user.

The user is now a member of the cloudSecurity_2026 group.

<img width="1535" height="958" alt="Screenshot 2026-09-17 211657" src="https://github.com/user-attachments/assets/3326a6a5-5219-43ed-869b-5d0b47c20dde" />

## Step 6: Verify User Permissions

Open IAM → Users.

Click student01.

Open the Permissions tab.

Verify that the following policy is displayed:

AmazonS3ReadOnlyAccess

<img width="1535" height="959" alt="Screenshot 2026-09-17 211801" src="https://github.com/user-attachments/assets/b7f9c831-4d95-434c-9232-56d7e7f12e2e" />

Check the Attached via column.

It should indicate that the policy is attached through:

Group: cloudSecurity_2026

This demonstrates:

student01

↓

cloudSecurity_2026

↓

AmazonS3ReadOnlyAccess

↓

Amazon S3 Read-only Access

Step 7: Enable Console Access

Initially, console access for student01 may be disabled.

Open IAM → Users → student01.

Select Security credentials.

Locate Console access / AWS Management Console access.

Enable console access.

Create a console password for student01.

Complete the configuration.

Note: Do not share the password with other users.

<img width="1535" height="958" alt="Screenshot 2026-09-17 211905" src="https://github.com/user-attachments/assets/b8ca0bce-91bf-4cf4-b9f2-6e6f2c1f145e" />

## Step 8: Obtain the AWS Account

The IAM user login requires the AWS account ID.

Your AWS account ID is a 12-digit number.

It can be found in the AWS account information.

For the demonstration account used in this experiment, the account ID was:

360416501079

Students should use their own AWS account ID when performing the experiment.

<img width="1531" height="959" alt="Screenshot 2026-09-17 211922" src="https://github.com/user-attachments/assets/291e99ea-857f-4bf7-b9c4-66a90342b33d" />

## Step 9: Login as the IAM User

Sign out from the current AWS administrator/root session.

Open a new browser window or Incognito/Private window.

Open the AWS sign-in page.

Select IAM user login.

Enter the AWS account ID.

Enter the IAM username:

student01

Enter the password created in Step 7.

Click Sign in.

The AWS Management Console should now open under the IAM user student01.




## Step 10: Verify Amazon S3 Access

After logging in as student01, search for S3.

Open Amazon S3.

Select General purpose buckets.

Verify that the previously created S3 bucket is visible.

Open the bucket.

Verify that the user can view the bucket and its objects.

This confirms that the IAM policy is providing S3 read access.

## Step 11: Verify Least-Privilege Access

The user student01 has been assigned:

AmazonS3ReadOnlyAccess

Therefore, the user should have read access but should not have permission to perform S3 write/delete operations.

For testing:

Open the S3 bucket as student01.

Observe the available operations.

Do not delete any existing object.

If you test an upload operation, do not use an important file.

The actual permission check occurs when AWS attempts the S3 operation.

A read-only user should receive an Access Denied response for unauthorized write/delete operations.

Important: The S3 console may display an Upload button even when the user does not have permission to complete the upload. The presence of the button alone does not prove that upload permission exists.




Expected Result

The IAM group cloudSecurity_2026 is successfully created and assigned the AmazonS3ReadOnlyAccess policy. The IAM user student01 is successfully created, added to the group, and provided with AWS Management Console access. The user can log in to AWS and access the assigned S3 resources according to the permissions inherited from the group.

Result

Thus, Identity and Access Management (IAM) was successfully implemented in AWS by creating an IAM group, assigning an S3 read-only policy, creating an IAM user, ena
