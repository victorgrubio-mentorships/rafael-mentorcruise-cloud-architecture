# Cloud Architecture Mentorship
Repo to store data and documents related to Rafael's mentorship

## Azure
### Exercise 1 - Blob Container creation

Create a Storage Account and a blob container. Upload an image to the container.

**Issue** 

#### Instructions
- Create an storage account in Azure
- Create a blob container to store files
- Upload file to the storage

#### Progress
- [x] An image should be uploaded to the blob container

#### Resources
- [Azure Blob Storage documentation](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blob-dotnet-get-started)

### Exercise 2 - Blob Lifecycle Management

Configure a lifecycle management policy to send deleted files in a container to cold storage.

**Issue**

You have a blob container that stores images for your website. You want to reduce the storage costs by moving the deleted files to a lower-cost tier. You also want to retain the deleted files for 30 days before deleting them permanently.

#### Instructions
- Create a lifecycle management policy for your storage account
- Define a rule to filter the blobs by prefix and delete status
- Set the action to move the filtered blobs to Archive tier
- Set the expiration time to 30 days

#### Progress
- [x] A lifecycle management policy should be applied to your storage account
- [x] Deleted files in the container should be moved to Archive tier
- [x] Deleted files in the Archive tier should be deleted after 30 days

#### Resources
- [Azure Blob Storage lifecycle management documentation](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-policy-configure?tabs=azure-portal)

## Exercise 3 - Archive non-accessed Files

Create a lifecycle management rule to send a file to another blob storage account if it has not been accessed in one day.

**Issue**

You have a storage account with a blob container that stores images for your website. You want to optimize the storage costs by moving the files that are not frequently accessed to another storage account with lower pricing tier.

#### Instructions
- Create another storage account with a lower pricing tier than the original one
- Create a blob container in the new storage account
- Create a lifecycle management rule in the original storage account to move the files that have not been accessed in one day to the new storage account
- Verify that the rule works by checking the destination blob container

#### Progress
- [ ] A lifecycle management rule should be created and applied to the original storage account
- [ ] The files that have not been accessed in one day should be moved to the new storage account

#### Resources
- [Azure Blob Storage Lifecycle Management documentation](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-policy-configure?tabs=azure-portal)


### Exercise 4 - Email Notification on Upload

Create a logic app that sends an email notification when an image is uploaded to the blob container.

**Issue**

You want to receive an email alert whenever a new image is uploaded to your blob container in Azure.

#### Instructions
- Create a logic app in Azure
- Add a trigger for when a blob is added or modified in your container
- Add an action to send an email using Office 365 Outlook connector
- Configure the email details such as subject, body and recipients

#### Progress
- [ ] An email should be sent to you when an image is uploaded to the blob container

#### Resources
- [Azure Logic Apps documentation](https://docs.microsoft.com/en-us/azure/logic-apps/logic-apps-overview)
- [Create a logic app that sends email](https://learn.microsoft.com/en-us/azure/app-service/tutorial-send-email?tabs=dotnet)

## Exercise 5 - Azure Storage encryption

Enable encryption for your storage account and verify that it works.

**Issue**

You want to protect your data from unauthorized access or theft. You need to enable encryption for your storage account and make sure that it is applied to your blob container.

#### Instructions
- Go to your storage account in the Azure portal
- Under Settings, select Encryption
- Turn on Encryption for data at rest
- Select Microsoft-managed keys as the encryption type
- Save your changes
- Go to your blob container and download the image you uploaded
- Open the image with a hex editor or a tool that can show binary data
- Look for the magic number of the image format (e.g. PNG, JPEG, etc.)
- If the magic number is not present, it means that the image is encrypted

#### Progress
- [ ] Encryption is enabled for your storage account
- [ ] The image in your blob container is encrypted

#### Resources
- [Azure Storage encryption overview](https://docs.microsoft.com/en-us/azure/storage/common/storage-service-encryption)
- [How to enable Azure Storage encryption](https://docs.microsoft.com/en-us/azure/storage/common/storage-service-encryption-enable?tabs=portal)
  

## Exercise 6 - Storage Account Access Control

Enable Azure Storage access control (IAM) for your storage account and assign a role to a user.

**Issue**

You want to grant access to your storage account to a colleague who needs to view and download the files in the blob container. You don't want to share your storage account key or generate a shared access signature (SAS). Instead, you want to use Azure Storage access control (IAM) to assign a role to your colleague's Azure account.

#### Instructions
- Go to the Azure portal and navigate to your storage account
- Click on the Access control (IAM) tab on the left menu
- Click on the + Add button and select Add role assignment
- Choose the Storage Blob Data Reader role from the drop-down list
- Search for your colleague's email address or name and select it
- Click Save

#### Progress
- [ ] Your colleague should be able to view and download the files in the blob container using their own Azure account

#### Resources
- [Azure Storage access control (IAM) documentation](https://docs.microsoft.com/en-us/azure/storage/common/storage-auth-aad)

## Exercise 7 - CDN Integration

Integrate the blob container with a Content Delivery Network (CDN) to improve the performance and availability of the image.

**Issue**

#### Instructions
- Create a CDN profile and endpoint in Azure
- Link the CDN endpoint to the blob container
- Test the CDN functionality by accessing the image URL

#### Progress
- [ ] The image should be accessible from the CDN endpoint URL

#### Resources
- [Azure CDN documentation](https://docs.microsoft.com/en-us/azure/cdn/cdn-overview)


## Exercise 8 - Use Azure Storage Explorer

**Exercise:** Use Azure Storage Explorer to view the storage analytics data.

**Issue**

**Instructions:**

1. Download and install Azure Storage Explorer from https://azure.microsoft.com/en-us/features/storage-explorer/.
2. Launch Azure Storage Explorer and sign in with your Azure account.
3. Expand the Storage Accounts node and select the storage account that you want to view the analytics data for.
4. Right-click the Blob Containers node and select View Blob Analytics Logs.
5. Select the time range and the log level that you want to view.
6. Click Refresh to load the logs.
7. You can also export the logs to a CSV file or a blob container by clicking Export.

**Progress:**

* [ ] Did you download and install Azure Storage Explorer?
* [ ] Did you sign in with your Azure account?
* [ ] Did you select the storage account that you want to view the analytics data for?
* [ ] Did you view the blob analytics logs?
* [ ] Did you export the logs to a CSV file or a blob container?

**Resources:**

* Azure Storage Explorer documentation: https://docs.microsoft.com/en-us/azure/vs-azure-tools-storage-explorer-blobs
* Azure Storage Analytics documentation: https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-analytics

**Additional notes:**

* You can also view the analytics data for queues, tables, and file shares by right-clicking the corresponding nodes and selecting View Analytics Logs.
* You can also enable or disable analytics logging for each service by right-clicking the service node and selecting Configure Analytics Logging.

## File Share

### Exercise 1 - File Share Setup

Create a file share in Azure and connect to it from your local laptop.

**Issue**

You want to store and access files in the cloud using a familiar interface and protocol. You also want to be able to mount the file share on your local machine and use it as a regular folder.

#### Instructions
- Create a file share in the storage account
- Install Azure Storage Explorer on your laptop
- Connect to your storage account using Azure Storage Explorer
- Mount the file share on your laptop as a network drive
- Create a text file in the file share and verify that it is accessible from both Azure Storage Explorer and your laptop

#### Progress
- [ ] A file share should be created in Azure
- [ ] Azure Storage Explorer should be installed and connected to your storage account
- [ ] The file share should be mounted as a network drive on your laptop
- [ ] A text file should be created in the file share and accessible from both locations

#### Resources
- [Azure File Shares documentation](https://docs.microsoft.com/en-us/azure/storage/files/storage-files-introduction)
- [Azure Storage Explorer download](https://azure.microsoft.com/en-us/features/storage-explorer/)

### Exercise 2 - Azure Files Sync

Create a sync group and a cloud endpoint to sync files from a blob container to an Azure file share.

**Issue**

You want to use Azure Files to access your files from anywhere, but you also want to keep a local copy of your files for performance and compatibility reasons. You can use Azure Files Sync to synchronize your files between a blob container and an Azure file share.

#### Instructions
- Create an Azure file share in the same storage account as the blob container
- Install the Azure File Sync agent on your local machine
- Create a sync group and a cloud endpoint for the blob container
- Create a server endpoint for the Azure file share
- Wait for the initial sync to complete

#### Progress
- [ ] A sync group and a cloud endpoint should be created
- [ ] A server endpoint should be created
- [ ] The files from the blob container should be synced to the Azure file share

#### Resources
- [Azure Files Sync documentation](https://docs.microsoft.com/en-us/azure/storage/files/storage-sync-files-deployment-guide?tabs=azure-portal)


### Exercise 3 - File Share creation and authentication

Create a file share in Azure Storage and configure Azure Active Directory (AAD) authentication for it. Test the functionality using a local laptop.

**Issue**

You want to create a file share in Azure Storage that can be accessed by users who have AAD credentials. You also want to test the functionality of the file share using a local laptop.

#### Instructions
- Create a file share in Azure Storage
- Enable AAD authentication for the file share
- Assign roles to users who can access the file share
- Connect to the file share from a local laptop using AAD credentials

#### Progress
- [ ] A file share should be created in Azure Storage
- [ ] AAD authentication should be enabled for the file share
- [ ] Roles should be assigned to users who can access the file share
- [ ] The file share should be accessible from a local laptop using AAD credentials

#### Resources
- [Azure File Share documentation](https://docs.microsoft.com/en-us/azure/storage/files/storage-files-introduction)
- [Azure File Share AAD authentication documentation](https://docs.microsoft.com/en-us/azure/storage/files/storage-files-active-directory-enable)
- 

## Special Exercises

These exercises are more complex and target special use cases. Recommended for the end of the course.

### Special Exercise 1 - Azure Storage Disaster Recovery

Enable Azure Storage Disaster Recovery for your storage account and run a test failover.

**Issue**

You want to ensure that your storage account can recover from a regional outage or disaster. You need to configure disaster recovery for your storage account and verify that it works as expected.

#### Instructions
- Enable geo-replication for your storage account
- Configure the secondary region for disaster recovery
- Initiate a test failover and check the status
- Restore the primary region and resume normal operations

#### Progress
- [ ] Your storage account should have geo-replication enabled
- [ ] Your secondary region should be ready for failover
- [ ] Your test failover should be successful and your data should be accessible in the secondary region
- [ ] Your primary region should be restored and your data should be synced back

#### Resources
- [Azure Storage Disaster Recovery documentation](https://docs.microsoft.com/en-us/azure/storage/common/storage-disaster-recovery-guidance)

### Additional Exercises

Exercise: Create a file share in Azure Storage and configure Azure Active Directory (AAD) authentication for it.
