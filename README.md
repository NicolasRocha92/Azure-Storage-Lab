<div align="center">

# ☁️ Microsoft Azure Storage

### Creating, Uploading, and Editing a Text File in Azure Blob Storage

</div>

## Project Overview

In this lab, I used Microsoft Azure Blob Storage to organize cloud resources, upload a text file, and edit its contents through the Azure portal. The steps cover creating Azure resources, uploading and editing a text file, verifying the downloaded changes, and cleaning up the lab environment.

## Environments and Technologies

* Microsoft Azure portal
* Azure Resource Groups
* Azure Storage account (general-purpose v2)
* Azure Blob Storage
* Windows and Notepad (or another plain-text editor)

## Prerequisites

* An Azure account and an active subscription, such as [Azure Free](https://azure.microsoft.com/en-us/free/) or Pay As You Go
* Permission to create Azure resources and upload or edit blobs (for example, suitable management permissions and the **Storage Blob Data Contributor** role)
* A web browser and a local plain-text editor

> \*\*Cost note:\*\* Azure resources may incur charges. Delete unused lab resources after completing the exercise.

## Lab Objectives

1. Explore the Azure portal and create a resource group.
2. Create a storage account and blob container.
3. Upload and edit a text file in Azure Blob Storage.
4. Download the modified file and verify its contents locally.
5. Delete the lab resource group and verify deletion.

## Step-by-Step Instructions

### Step 1 — Sign In and Explore the Azure Portal

1. If needed, create an [Azure Free account](https://azure.microsoft.com/en-us/free/) or choose a Pay As You Go subscription.
2. Sign in to the [Azure portal](https://portal.azure.com).
3. Use the portal search bar to locate **Resource groups**, **Virtual machines**, and **Microsoft Entra ID**. Observe where these services are found; this lab does not require creating a virtual machine or changing Entra ID settings.

### Step 2 — Create a Resource Group

1. Search for **Resource groups** in the portal and open it.
2. Select **Create**, choose your subscription, and enter `Lab-User` as the resource group name.
3. Choose an Azure region, select **Review + create**, and then **Create**.
4. Return to **Resource groups** and confirm that `Lab-User` appears.

**Expected result:** The resource group is available to contain the lab resources.

!\[Azure portal Resource groups page before creating the lab resource group](01-Screenshot%202026-10-11%20094128.png)

### Step 3 — Create a Storage Account

1. Open the `Lab-User` resource group and select **Create**.
2. Search for **Storage account** and open its creation form.
3. Select your subscription and the `Lab-User` resource group.
4. Enter a globally unique storage account name using **3–24 lowercase letters and numbers**.
5. Choose a region. For a basic lab, select **Standard** performance and **Locally-redundant storage (LRS)** if appropriate and available.
6. Review the remaining settings, select **Review + create**, and then **Create**. Wait for deployment to complete.
7. Open the storage account from the resource group's **Resources** list.

**Expected result:** A storage account appears within `Lab-User`.

!\[Lab-User resource group showing its storage account](02-Screenshot%202026-10-11%20095437.png)

### Step 4 — Create a Blob Container

1. In the storage account, select **Data storage → Containers**.
2. Select **+ Container**, enter `azuretest`, and choose **Private (no anonymous access)**.
3. Select **Create**, then open the new container.

**Expected result:** The `azuretest` container is ready for a file upload.

### Step 5 — Create and Upload a Text File

1. On your computer, open Notepad and type:

```text
   Hello
   ```

2. Save the file as `Azure-lab.txt`. In Notepad, choose **Save as type: All files** if necessary to avoid a duplicate `.txt` extension. On a Mac, ensure the editor is set to plain-text mode before saving.
3. In the Azure portal, open the `azuretest` container and select **Upload**.
4. Choose `Azure-lab.txt`, complete the upload, and confirm it appears in the blob list.

**Expected result:** The file is stored in the container.

!\[azuretest container displaying the uploaded Azure-lab.txt blob](03-Screenshot%202026-10-11%20101120.png)

### Step 6 — Open the Text File in Azure

1. Select `Azure-lab.txt` in the container.
2. Open the **Edit** tab, if available in the portal.
3. Confirm the editor displays the original text, `Hello`.

!\[Azure-lab.txt opened in the Azure portal editor with Hello](04-Screenshot%202026-10-11%20102035.png)

### Step 7 — Edit and Save the File

1. Add `Goodbye` on a new line so the text reads:

```text
   Hello
   Goodbye
   ```

2. Select **Save** and wait for the operation to finish without an error.

!\[Azure-lab.txt editor showing Hello and Goodbye](05-Screenshot%202026-10-11%20102207.png)

### Step 8 — Download and Verify the Edited File

1. Return to the `azuretest` container and select `Azure-lab.txt`.
2. Choose **Download** from the blob's available actions.
3. Open the downloaded file in Notepad or another plain-text editor on your computer.
4. Confirm the downloaded copy contains both `Hello` and `Goodbye`.

**Expected result:** The downloaded file contains the changes made in Azure.

### Step 9 — Delete the Lab Resource Group

1. In the Azure portal, open **Resource groups** and select `Lab-User`.
2. Review the listed resources carefully to ensure the group contains nothing you need to keep.
3. Select **Delete resource group**, follow the confirmation prompts, and submit the deletion.
4. Wait until Azure reports that the deletion operation is complete. Deleting a resource group permanently deletes its contained resources.

### Step 10 — Verify Resource Group Deletion

1. Return to **Resource groups** and refresh the list.
2. Confirm `Lab-User` no longer appears under the correct subscription and filters.
3. If it is still present, check the deletion operation status and allow additional time for completion.

**Expected result:** The lab resource group no longer appears in the selected subscription.

## Skills Practiced

* Navigating the Azure portal
* Creating resource groups and storage accounts
* Working with blob containers and files
* Editing, downloading, and verifying cloud-stored text files
* Cleaning up cloud resources to avoid unnecessary costs

## Project Outcome

Practiced creating and managing Azure Blob Storage resources, editing a text file in the portal, verifying a downloaded copy, and removing temporary resources.

