# Add user to Directory

Before you can send instant messages, pictures, and documents, or setup a new poll or survey, you'll have to add/create Kaizala users in your Organization. You can add users individually or in bulk. For managing users in groups, check out [Kaizala groups](groups.md).

Organization Admin(s) can create/add new users in Organization Directory networks. However, users when added by group admin(s) in any Org group(s) also become a part of Organization Directory.

User can be added to 'Employee' network in any of the following ways:

* Users added by an organization admin as Employees, either in bulk or individually
* Users synced automatically from Azure Active Directory (Azure AD)
* Users who have signed in to their Kaizala mobile app using an Office 365 account

Similarly, users can be added to 'Others' network:
* Non-employee users added by a group admin to their organization groups
* Users added by an organization admin as Others, either in bulk or individually

However tenant admin(s) can always move a user between network(s)
  
## Add users in bulk to your organization directory

If you want to add several users at once, you can do so using **Import Users** option. 
  
- Click **Directory** \. Open 'Employee' or 'Others' network tab
- Select **Import Users** 
    
- On the **Import Users** dialog, download the CSV template.[Add several users at the same time to Office 365 - Admin Help](https://support.office.com/article/1f5767ed-e717-4f24-969c-6ea9d412ca88#__toc316652088).
    
- Follow the template to add your users and their phone numbers to Kaizala. Save the file in .csv format.
    
- Click **Select a File** and choose the file you saved above. Finally click **Upload**. 
    
  
- On the **Upload Users History** page, you can check the status of the uploaded file. Click **Refresh** to get the latest status. If the status is **Completed**, you can find the updated user list under the earlier selected network - Employee or Others. 
    
> [!NOTE]
> You can update info for an existing user by re-uploading the file with updated data for that user. 
  
## Find history of all user upload operations


- Click **Directory**. Then select **View csv import history** from the drop-down. 
- On the **View Import History** page, you can find a list of all user upload operations. Each list item has the following info: 
    
  - **File Name**
    
  - **Uploaded by**
    
  - **Date** - timestamp when the file was uploaded. 
    
  - **Status** of the uploaded file. This can be one of the following values : 
    
  - **Processing** - the file has been sent for processing and hasn't been uploaded yet. 
    
  - **Completed** - the file has either been successfully uploaded, or partially uploaded  due to some errors. 
    
  - **Failed** - the file hasn't been uploaded successfully. Download the error log file for the upload to check out any issues. 
    
  - **Download** - clicking the icon downloads the originally uploaded file. 
    
## Export users' data for your organization


- Click **Directory** \> **Export Users**. Then select **Create New Request**. 
  
- On the **Export History** page, you can check the status of the export request. Click **Refresh** to get the latest status. If the status is Completed, you can download the requested file by clicking on the download icon beside the specific request. 
    
## Find history of all export users operation


- Click **Directory** \> **Export Users**. Then select **View Export History**. 
    
- On the **Export History** page, you can find a list of all user upload operations. Each list-item has following info 
  
  - File Name
    
  - Exported by
    
  - Date - timestamp when the file was uploaded.
    
  - **Status** of the exported file. This can be one of the following values : 
    
    - **Queued** - the request has been queued. 
    
    - **Completed** - the file has either been successfully exported, or partially exported due to some errors. 
    
    - **Failed** - the file wasn't exported successfully. Download the error log file for the upload to check out any issues. 
    
  - **Download** - Clicking the icon downloads the requested export file. 
    
## Find a detailed view of user's profile in the organization


To find a detailed view of a user's profile:
  
- Click **Directory**. Then select a user from the user list for your organization. 
    
- Click on the user to see user's details.
    
