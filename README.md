<div align="center">

# ☁️ Microsoft Azure Storage

### Creating and Editing a Text File in Azure Blob Storage

</div>

## Project Overview

This tutorial documents my hands-on practice using the Microsoft Azure portal to explore cloud resources, access an Azure Storage account and blob container, and edit a text file stored in the cloud.

## Environments and Technologies Used

- Microsoft Azure Portal
- Azure Resource Groups
- Azure Storage Account
- Azure Blob Storage

## Operating Systems Used

- Windows (web browser used to access Azure Portal)

## Objectives

- Navigate the Azure portal and locate cloud resources.
- Explore a storage account and its blob container.
- Open and edit a text file stored as a blob.
- Verify that the updated text appears in the file editor.

## Steps and Screenshots

### Step 1: Open the Azure Resource Groups page

I opened **Resource groups** in the Azure portal to begin navigating the cloud environment. The screenshot shows the resource groups page before any resource groups are displayed.

![Azure Resource Groups](01-Screenshot%202026-10-11%20094128.png)

### Step 2: Locate the lab resources

I opened the **Lab-User** resource group and viewed its resources, including the storage account used for this exercise.

![Lab Resources](02-Screenshot%202026-10-11%20095437.png)

### Step 3: View the blob container

Inside the storage account, I navigated to the **azuretest** container and located the uploaded text file, **Azure-lab.txt**.

![Azure Blob Container](03-Screenshot%202026-10-11%20101120.png)

### Step 4: Open the text file in the Azure portal

I selected **Azure-lab.txt** and opened the **Edit** tab to view its contents. The file initially displayed `Hello`.

![Text File Before Editing](04-Screenshot%202026-10-11%20102035.png)

### Step 5: Edit the file contents

I added `Goodbye` beneath `Hello` in the text editor. The final screenshot shows both lines in the editor. This screenshot documents the edit; it does not independently confirm that the change was saved.

![Text File After Editing](05-Screenshot%202026-10-11%20102207.png)

## Skills Demonstrated

- Navigating Microsoft Azure resources
- Understanding the relationship between resource groups, storage accounts, containers, and blobs
- Accessing cloud-hosted files through the Azure portal
- Editing text content in Azure Blob Storage

## Conclusion

This lab gave me practical experience exploring Azure Storage and working with a text file through the Azure portal. It strengthened my familiarity with cloud resource organization and basic storage management.
