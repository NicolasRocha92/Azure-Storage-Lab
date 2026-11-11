<div align="center">

# ☁️ Microsoft Azure Storage

### Creating, Uploading, and Editing a Text File in Azure Blob Storage

</div>

## Project Overview

In this lab, I worked with Microsoft Azure Blob Storage to organize cloud resources, upload a text file, and edit its contents through the Azure portal. This guide explains the setup and provides step-by-step instructions to repeat the process.

## Environments and Technologies

* Microsoft Azure portal
* Azure Resource Groups
* Azure Storage account (general-purpose v2)
* Azure Blob Storage
* Windows and Notepad (or another plain-text editor)

## Prerequisites

* An Azure account with an active subscription
* Permission to create Azure resources and upload or edit blobs (for example, the appropriate Azure management permissions and the **Storage Blob Data Contributor** role)
* A web browser and a local text editor

> \\\*\\\*Note:\\\*\\\* Azure resources can incur charges. Choose settings appropriate to your subscription and remove unused lab resources afterward.

## Lab Objectives

1. Create a resource group and storage account.
2. Create a blob container.
3. Upload a text file to Azure Blob Storage.
4. Edit the file in the Azure portal.
5. Save and verify the updated contents.

## Step-by-Step Instructions

### Step 1 — Create a Resource Group

1. Sign in to the [Azure portal](https://portal.azure.com).
2. In the top search bar, search for **Resource groups** and open it.
3. Select **Create**.
4. Choose your Azure subscription.
5. Enter `Lab-User` for the resource group name and select a region.
6. Select **Review + create**, then **Create**.
7. Return to **Resource groups** and confirm `Lab-User` appears.

**Expected result:** A resource group named `Lab-User` is available for the lab resources.

!\[Azure portal Resource groups page before creating the lab resource group](01-Screenshot%202026-10-11%20094128.png)

### Step 2 — Create a Storage Account

1. Open the `Lab-User` resource group.
2. Select **Create**, search for **Storage account**, and open its creation form.
3. Select the correct subscription and `Lab-User` resource group.
4. Enter a globally unique storage account name containing **3–24 lowercase letters and numbers**.
5. Choose a region. For a simple practice lab, select **Standard** performance and **Locally-redundant storage (LRS)** if available.
6. Review the other settings, retaining appropriate defaults for your subscription.
7. Select **Review + create**, then **Create**. Wait for deployment to finish.
8. Return to `Lab-User` and open the storage account from its **Resources** list.

**Expected result:** The storage account appears inside the `Lab-User` resource group.

!\[Lab-User resource group showing its storage account](02-Screenshot%202026-10-11%20095437.png)

### Step 3 — Create a Blob Container

1. Open your storage account in the Azure portal.
2. Under **Data storage**, select **Containers**.
3. Select **+ Container**.
4. Name the container `azuretest`.
5. Choose **Private (no anonymous access)** and select **Create**.
6. Open the new `azuretest` container.

**Expected result:** The container opens and is ready to store blobs.

### Step 4 — Create and Upload a Text File

1. Open **Notepad** on your computer.
2. Enter the following text:

```text
   Hello
   ```

3. Select **File > Save As** and save the file as `Azure-lab.txt`. If necessary, set **Save as type** to **All files** to avoid adding a second `.txt` extension.
4. Return to the `azuretest` container in the Azure portal.
5. Select **Upload**, browse to `Azure-lab.txt`, and confirm the upload in the upload pane.
6. Refresh the blob list if necessary and confirm the file appears.

**Expected result:** `Azure-lab.txt` is listed in the container.

!\[azuretest container displaying the uploaded Azure-lab.txt blob](03-Screenshot%202026-10-11%20101120.png)

### Step 5 — Open the Text File

1. Select `Azure-lab.txt` from the container's blob list.
2. Open the **Edit** tab in the blob details pane.
3. Confirm the file contains `Hello`.

**Expected result:** The file opens in the portal's text editor.

!\[Azure-lab.txt opened in the Azure portal editor with Hello](04-Screenshot%202026-10-11%20102035.png)

### Step 6 — Edit and Save the File

1. Place the cursor at the end of `Hello` and press **Enter**.
2. Type `Goodbye` on the next line. The file should now read:

```text
   Hello
   Goodbye
   ```

3. Select **Save** in the blob editor and wait for the save operation to finish.

**Expected result:** The editor contains both lines and the save completes without an error.

!\[Azure-lab.txt editor showing Hello and Goodbye](05-Screenshot%202026-10-11%20102207.png)

### Step 7 — Verify the Updated File

1. Return to the `azuretest` container.
2. Open `Azure-lab.txt` again and select **Edit**. Alternatively, download the blob and open it in Notepad.
3. Confirm the file still contains both `Hello` and `Goodbye`.

**Expected result:** The changes remain after reopening the file.

## Troubleshooting

|Problem|Suggested fix|
|-|-|
|Storage account name is unavailable|Choose another globally unique name using lowercase letters and numbers.|
|Resource group or account does not appear|Check the selected subscription, directory, filters, and permissions.|
|Container or blob access is denied|Check your blob data permissions; new role assignments may take time to apply.|
|Uploaded file does not appear|Check the upload status and selected container, then refresh the list.|
|Edit or Save is unavailable|Confirm your write permissions and whether the blob is locked or restricted.|
|Changes disappear after reopening|Repeat the edit, confirm the save completes, and check for errors.|

## Skills Practiced

* Navigating the Microsoft Azure portal
* Organizing resources with resource groups
* Creating and managing Azure storage accounts and blob containers
* Uploading and editing blobs
* Verifying stored file contents
* Troubleshooting basic cloud storage access and file operations

## Conclusion

This lab helped me practice using Azure Blob Storage to store and edit a text file in the cloud. I worked with resource groups, a storage account, a blob container, and the portal's text editor, strengthening my understanding of basic cloud storage administration.

## Cleanup

When the lab is no longer needed, open **Resource groups**, select `Lab-User`, review the resources it contains, and choose **Delete resource group**. **This permanently deletes all resources in that group**, so confirm that none are still needed before proceeding.

