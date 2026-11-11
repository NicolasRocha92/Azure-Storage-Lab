<div align="center">

# ☁️ Microsoft Azure Storage

### Creating, Uploading, and Editing a Text File in Azure Blob Storage

</div>

## Project Overview

This lab explores Azure Blob Storage through the Azure portal. It explains how to prepare a resource group and storage account, create a container, upload a text file, edit the file, and check whether the change was saved. The five original screenshots document selected stages of my hands-on work; setup steps without screenshots are included so a reader can reproduce the entire workflow.

> \*\*Screenshot accuracy:\*\* The first screenshot shows an empty resource-group list; the second shows the `Lab-User` resource group with a storage account; the third shows a container containing a text blob; and the final two show the blob editor before and after the text was changed. The screenshots do \*\*not\*\* separately show creation of the storage account, creation of the container, the initial file upload, or a successful save-and-reopen verification.

## Environment and Technologies

* Microsoft Azure portal and an Azure subscription
* Azure Resource Groups
* Azure Storage account (general-purpose v2 / StorageV2)
* Azure Blob Storage and a private blob container
* A Windows computer and web browser
* A plain-text editor (for example, Notepad)

## Prerequisites and Permissions

* An Azure account with an active subscription and permission to create a resource group and storage account, or access to existing resources.
* Permission to manage containers and upload/edit blobs. Azure management permissions and blob data permissions are different; **Storage Blob Data Contributor** at the appropriate scope is one way to grant blob write access. Depending on portal authentication, additional permissions may be required to navigate using the account key.
* A unique storage account name: **3–24 lowercase letters and numbers**, globally unique across Azure.
* A small local text file to upload. This tutorial uses `Azure-lab.txt` containing `Hello`.

**Costs:** Storage accounts and stored data can incur charges. Use your own subscription's pricing information and delete lab resources when no longer needed.

## Lab Objectives

1. Create or locate a resource group and storage account.
2. Create or locate a blob container.
3. Upload and open a text blob.
4. Change the blob's text content in the portal.
5. Save, reopen, and verify the updated content.

## Step-by-Step Instructions

### Step 1 — Open Azure Resource Groups

1. Go to [https://portal.azure.com](https://portal.azure.com) and sign in.
2. Search for **Resource groups** in the portal search bar and select the service.
3. Confirm that the correct subscription and filters are selected. An empty list can mean no groups exist or that the current filters or permissions hide them.
4. If you already have a suitable resource group, select it and continue to Step 2. Otherwise, select **Create**.
5. Choose your subscription, enter **Lab-User** as the resource group name (or another available name), and choose an Azure region.
6. Select **Review + create**, review the settings, then **Create**. Return to **Resource groups** and open the new group.

**Expected result:** Your resource group appears in the list and opens successfully.

**Original screenshot 1:** This shows the Resource groups page with no groups displayed at that moment, **before** the later screenshot of `Lab-User`.

!\[Original screenshot 1: Azure Resource groups page with no resource groups displayed](01-Screenshot%202026-10-11%20094128.png)

### Step 2 — Create or Open a Storage Account

1. Open the **Lab-User** resource group.
2. If a storage account is already listed under **Resources**, select it. Otherwise select **Create**, search for **Storage account**, and choose **Create**.
3. Select your subscription and the **Lab-User** resource group.
4. Enter a globally unique storage account name (for example, a name you choose using lowercase letters and numbers only). **Do not use a sample name unless Azure confirms it is available.**
5. Select the region appropriate for your lab, **Standard** performance, and **Locally-redundant storage (LRS)** for a basic demonstration if available. Leave other settings at their defaults unless your organization or subscription requires different options.
6. Review the remaining tabs, then select **Review + create** and **Create**. Wait for deployment to finish and open the storage account.
7. If the storage account was already present, skip the creation actions and open that existing account instead.

**Expected result:** The resource group's **Resources** list contains a resource of type **Storage account**.

**Original screenshot 2:** This shows `Lab-User` and a storage account in its resources list; it does not show the account-creation wizard.

!\[Original screenshot 2: Lab-User resource group containing a storage account](02-Screenshot%202026-10-11%20095437.png)

### Step 3 — Create or Open a Blob Container

1. In the storage account's left menu, under **Data storage**, select **Containers**.
2. If a container named **azuretest** already exists, open it. Otherwise select **+ Container**.
3. Enter **azuretest** as the container name, choose **Private (no anonymous access)**, and select **Create**.
4. Open the **azuretest** container. If you see an authorization error, verify your blob data permissions and refresh after role assignments propagate.

**Expected result:** The container opens and displays its list of blobs (which may initially be empty).

### Step 4 — Create and Upload the Text File

1. On your computer, open **Notepad** or another plain-text editor.
2. Type the following line:

```text
Hello
```

3. Save the file as **Azure-lab.txt**. In Notepad, choose **Save as type: All files** if needed to avoid accidentally creating `Azure-lab.txt.txt`.
4. Return to the **azuretest** container in the Azure portal.
5. Select **Upload**, browse to **Azure-lab.txt**, and select **Upload** to complete the operation. Depending on the portal layout, you may need to confirm the upload in a side pane.
6. Confirm **Azure-lab.txt** appears in the container's blob list.

**Expected result:** A blob named **Azure-lab.txt** appears in **azuretest**.

**Original screenshot 3:** This shows the container with a text blob already listed. It documents the result, not the upload action itself.

!\[Original screenshot 3: azuretest blob container with text file listed](03-Screenshot%202026-10-11%20101120.png)

### Step 5 — Open the Text Blob in the Portal Editor

1. Select **Azure-lab.txt** in the container's blob list.
2. Open the blob's **Edit** tab in the portal, if available for this file and your permissions.
3. Confirm the editor contains:

```text
Hello
```

**Expected result:** The text editor displays the original content.

**Original screenshot 4:** The blob editor shows `Hello` before the second line is added.

!\[Original screenshot 4: Azure blob editor displaying Hello](04-Screenshot%202026-10-11%20102035.png)

### Step 6 — Edit and Save the Blob

1. Place the cursor after `Hello` and press **Enter**.
2. Type `Goodbye` on the new line. The full content should now be:

```text
Hello
Goodbye
```

3. Select **Save** in the blob editor. Wait for the portal to indicate that the operation completed; do not navigate away while the save is pending.
4. If saving fails, check your blob write permissions and whether the blob is locked, leased, or otherwise restricted.

**Expected result:** The portal accepts the updated text and completes the save.

**Original screenshot 5:** The editor shows both lines, but the image alone does **not** prove that the Save operation succeeded.

!\[Original screenshot 5: Azure blob editor displaying Hello and Goodbye](05-Screenshot%202026-10-11%20102207.png)

### Step 7 — Verify the Saved Change

1. Close the editor or return to the container's blob list.
2. Reopen **Azure-lab.txt** and select **Edit** again (or download the blob and open it in a text editor).
3. Verify that the saved file contains **both** `Hello` and `Goodbye`.
4. If the content reverted, repeat the save and check for any error messages or missing permissions.

**Expected result:** The reopened or downloaded file retains both lines. **No separate verification screenshot was provided**, so this is a reproducibility check, not a claim established by the original photos.

## Troubleshooting

|Issue|What to check|
|-|-|
|Resource group or storage account not visible|Confirm subscription, directory, portal filters, and access permissions.|
|Storage account name rejected|Use a globally unique name with 3–24 lowercase letters and numbers.|
|Container or blob access denied|Check Azure RBAC blob data permissions and allow time for role changes to propagate.|
|File does not appear after upload|Refresh the blob list; check the selected container and upload status.|
|Edit tab or Save action unavailable|Check file type, portal support, blob state, and write permissions.|
|Edited text disappears|Reopen/download the blob and confirm the save completed successfully.|

## Skills Practiced

* Navigating Azure resources and understanding resource groups
* Working with Azure Storage accounts and blob containers
* Uploading and editing plain-text blobs
* Recognizing the difference between an edit visible in an editor and a persisted change
* Checking permissions and verifying results

## Conclusion

This project documents my hands-on work locating Azure storage resources and editing a text blob through the Azure portal. The additional setup and verification instructions make the workflow repeatable for a beginner. The original screenshots show the resource list, container contents, and editor states; they do not independently prove every setup or save operation.

## Cleanup (Optional)

To avoid unnecessary charges, remove the lab resources **only if they are no longer needed**. In the Azure portal, open **Resource groups**, select the lab-specific resource group, choose **Delete resource group**, and follow the confirmation prompts. **Deleting a resource group permanently deletes the resources it contains**, so check the list carefully before confirming.

