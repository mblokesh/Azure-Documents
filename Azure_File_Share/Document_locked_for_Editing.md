# The document is locked for editing by another user: Azure - Clearing the lock on a file within an Azure File Share

This cannot be done with the GUI so PowerShell or Cloud Shell must be used.
    
1. If you do not have the Azure powershell module installed, install it with

    `Install-Module -Name Az -AllowClobber`

* Accept and install any missing pre-requisites

2. Connect to Azure and login with an admin account of sufficient privileges

    `Connect-AzAccount`

3. Select the subscription of the target account

    `Select-AzSubscription -subscriptionid "SubscriptionID"`

* The Subscription ID is shown within the Overview page under the Storage Account you are connecting to

4. Create storage context for the target storage account

    `$Context = New-AzStorageContext -StorageAccountName "StorageAccountName" -StorageAccountKey "StorageAccessKey"`

* The storage account name and storage access key can be obtained from Settings > Access Keys within the Storage Account

5. Get the current open handles of the file share

    `Get-AzStorageFileHandle -Context $Context -ShareName "FileShareName" -Recursive`

* This will return a list of open files within the share and the file you are having trouble with should be shown.

6. Copy the path to the file in question.

7. Close the open handle

    `Close-AzStorageFileHandle -Context $Context -ShareName "FileShareName" -Path 'path to file copied from the list' -CloseAll`

8. Re-run the open handles command to verify it has closed, you should now be able to delete it.


    