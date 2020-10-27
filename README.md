Create Azure Cloud Service Remote Desktop Connection Manager Group File (.rdg)
==============================================================================

            

**WHAT **


Creates a Remote Desktop Connection Manager 2.7 group file (.rdg) containing all the VMs from a cloud service.


Uses the Azure PowerShell cmdlets to obtain remote connectivity information for each VM in a cloud service. Uses this information to create a .rdg file for the targeted cloud service. This file can then be opened in Remote Desktop Connection Manager 2.7
 to provide consolidated RDP access.
  
Remote Desktop Connection Manager 2.7 can be found here:
   

    [http://www.microsoft.com/en-gb/download/details.aspx?id=44989](http://www.microsoft.com/en-gb/download/details.aspx?id=44989)

  
  
**EXAMPLE 1 **
Create-AzureServiceRdgFile -ServiceName FredCLoud -FolderPath 'c:\users\fred\rdg_files\' -Verbose

 
Creates a Remote Desktop Configuration Manager configuration file called FREDCLOUD.rdg in the c:\users\fred\rdg_files directory for all the VMs in the FredCloud cloud service. Provides verbose output.
 

  

**EXAMPLE 2**
 

    Get-AzureService | ForEach-Object {

        Create-AzureServiceRdgFile -ServiceName $_.ServiceName -FolderPath 'c:\users\fred\rdg_files\' -Verbose

    }

 
Get's each cloud service in the current Azure subscription. Create's a configuration file called <ServiceName>.rdg for each service in the cloud service. Saves each .rdg file to 'c:\users\fred\rdg_files' directory so they can be loaded by Remote
 Desktop Connection Manager. Provides verbose output.
 

 


 








        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
