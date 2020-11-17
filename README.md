# Azure Windows Virtual Desktop - WVD

Compilation of good links and references related to the new version of Azure WVD ARM. 
<br>
<br>

| Topic    	| Recommendation    	| References  	|
|-	|-	|-	|
| **WVD Spring Update - News and Updates**    	| Novidades sobre   Virtualização de Desktops no Azure    	| - Novidades sobre Virtualização de Desktops no Azure    <br>From    <https://www.youtube.com/watch?v=WlQKvJQD6m4&feature=youtu.be><br><br>- New Windows Virtual Desktop capabilities now generally available    <br>From    <https://azure.microsoft.com/en-us/blog/new-windows-virtual-desktop-capabilities-now-generally-available/> 	|
| **WVD Spring Update - Planning**    	| Network   recommendations<br>     	| - Network guidelines <br>From    <https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/network-guidance?context=/azure/virtual-desktop/context/context>    <br>    <br>  - Remote Desktop Protocol (RDP) bandwidth requirements
<br>From <https://docs.microsoft.com/en-us/azure/virtual-desktop/rdp-bandwidth>  <br>    <br>     	|
|    <br>     	|    Recommendations of Windows Virtual Desktop for the enterprise | - Windows Virtual Desktop for the enterprise <br> From <https://docs.microsoft.com/en-us/azure/architecture/example-scenario/wvd/windows-virtual-desktop> 
|    <br>     	|    Workload types and VM sizing recommendations    	|    - Remote Desktop workloads    <br>From    <https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/remote-desktop-workloads>    <br><br>- Virtual machine sizing guidelines    <br>From    <https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs?context=/azure/virtual-desktop/context/context>    <br>        	|
|    **WVD Spring Update - Setup**    	|    Passo a   passo para subir um ambiente de Windows Virtual Desktop, mantido pelo Christiaan Brinkhoff (Microsoft Global Black Belt de WVD)    	|    - Windows Virtual Desktop technical (2020 – ARM-based model – generally         available) deployment walkthrough. It covers all you need to know and         beyond!    <br>From    <https://christiaanbrinkhoff.com/2020/05/01/windows-virtual-desktop-technical-2020-spring-update-arm-based-model-deployment-walkthrough/#teamsoptimizations>    <br>        	|
|    <br>     	|    Videos   com passo a passo    	| - Windows Virtual Desktop (WVD) Spring Update    <br>From    <https://www.youtube.com/watch?v=AKBa7kLhghI>    <br><br> - New WVD Admin Portal - Windows Virtual Desktop - #20    <br>From    <https://www.youtube.com/watch?v=DrkQFSVD9Ik&list=PL-V4YVm6AmwXGvQ46W8mHkpvm6S5IIitK&index=21>    <br>        	|
|    **WVD Spring Update - Image Management** | Image   management using Shared Image Gallery<br>![Shared Image Gallery](https://github.com/marcusgaspar/Azure-WVD/blob/master/images/Shared%20Gallery%20Image.png) <br> -My image: You cannot instant update host pools created based on Azure Managed images (images under My images) as part of the host pool. So in case of an image update, you have to re-create the host pool.<br>    <br>- Shared images (SIG). It’s most likely that you want to keep using the existing host pool due to the fact of all the Remote Applications and Desktops – Applications groups and assignments. This is the part where the Azure shared image        gallery (SIG) comes in very handy due to the support for versioning, read the benefits again here. It will automatically pick and select the latest image version.       	|    - Windows Virtual Desktop - #23 - Update Session Hosts from Latest Image    <br>From    <https://www.youtube.com/watch?v=2LxvwR9LGWQ>    <br><br> - Create an Azure Shared Image Gallery (SIG)    <br>From <https://christiaanbrinkhoff.com/2020/05/01/windows-virtual-desktop-technical-2020-spring-update-arm-based-model-deployment-walkthrough/#teamsoptimizations>    <br>        	|
|    <br>     	|    Image   preparation and recommendations    	|    - Prepare and customize a master VHD image    <br>From    <https://docs.microsoft.com/en-us/azure/virtual-desktop/set-up-customize-master-image>    <br>        	|
|    <br>     	|    Install   Language Pack    	|    - Add language packs to a Windows 10 multi-session image    <br>From    <https://docs.microsoft.com/en-us/azure/virtual-desktop/language-packs>    <br>        	|
|    **Windows Virtual Desktop Optimization tool**    	|    Virtual   Desktop Optimization tool    	|    - (Windows) Virtual Desktop Optimization Tool now available        <br>From    <https://techcommunity.microsoft.com/t5/windows-virtual-desktop/windows-virtual-desktop-optimization-tool-now-available/m-p/1558614#M5056>    <br><br> - Virtual Desktop Optimization tool    <br>From <https://christiaanbrinkhoff.com/2020/05/01/windows-virtual-desktop-technical-2020-spring-update-arm-based-model-deployment-walkthrough/#teamsoptimizations>    <br>https://techcommunity.microsoft.com/t5/windows-virtual-desktop/windows-virtual-desktop-optimization-tool-now-available/m-p/1558614#M5056<br><br> - Windows Virtual Desktop Optimizations Nuff Said! -#29    <br>From    <https://www.youtube.com/watch?v=tm2dSd695x8&feature=youtu.be> <br>          	|
| **Use Microsoft Teams on Windows Virtual desktop** |  Media optimization for Microsoft Teams is only available for the Windows Desktop client on Windows 10 machines. Media optimizations require Windows Desktop client version 1.2.1026.0 or later. | - Use Microsoft Teams on Windows Virtual desktop <br> From <https://docs.microsoft.com/en-us/azure/virtual-desktop/teams-on-wvd> <br><br> - Prepare your organization's network for Microsoft Teams <br> From <https://docs.microsoft.com/en-us/microsoftteams/prepare-network> <br> |
| **WVD Spring Update - Monitoring** <br>    	|    <br>     	|    - Proactively monitor ARM-based Windows Virtual Desktop with Azure Log Analytics and Azure Monitor    <br>    <br>https://techcommunity.microsoft.com/t5/windows-it-pro-blog/proactively-monitor-arm-based-windows-virtual-desktop-with-azure/ba-p/1508735<br>    <br>        	|
|    **WVD Spring Update - Auto Scale**    	|    O   processo de auto escale, atualizado para o WVD Spring Update. <br>- This means shutting down and deallocating session host VMs during off-peak usage hours, then turning them back on and reallocating them during peak hours:<br> -- Schedule VMs to start and stop based on Peak and Off-Peak business hours.<br>-- Scale out VMs based on number of sessions per CPU core.<br> -- Scale down VMs during Off-Peak hours, leaving the minimum number of session host VMs running.<br>- Scale out only based on session per CPU.<br>- It can't scale down during peak hours.<br>- "Maximum number of sessions per CPU threshold used to determine when a new RDSH server needs to be started" (Default is 1)<br>- During the off peak hours, to decide which node to drain and shut down, it picks the VMs from list of session hosts sorted by number of sessions (active + disconnected) in ascending order.       	| - Scale session hosts using Azure Automation <br>From    <https://docs.microsoft.com/en-us/azure/virtual-desktop/set-up-scaling-script>    <br>        	|
|    **WVD Spring Update - Profile / FSLogix**    	|    Storage Options: Azure Files, Azure NetApp Files and Storage Spaces Direct    	|    - Storage options for FSLogix profile containers in Windows Virtual Desktop    <br>From    <https://docs.microsoft.com/en-us/azure/virtual-desktop/store-fslogix-profile>           	|
|    <br>     	|    This article provides insights on designing, sizing, and implementing a Microsoft FSLogix Profile Container solution for large enterprises, as well as shows how to avoid performance problems in production. This article is an extension of the Windows Virtual Desktop at enterprise scale article.<br>   | - Microsoft FSLogix for the enterprise <br>From    <https://docs.microsoft.com/en-us/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix>    <br>        	|
|    <br>     	|    “Scale Azure Files – storage accounts based on AD   Groups<br>   When you implement Windows Virtual Desktop on a larger scale – you could run into   limitations of Azure Files. Premium storage accounts have up to max 100k IOPS per share with 5 GBps per share at about 3 ms latency. The rule of the thumb is that one user consumes between 5 and 15 IOPs (depending on the type of   workload). <br>To work around this limit and stack up more Azure File shares to create more capacity – there is an option to create filters based on Active Directory groups. You must create an additional registry hive with the SID of that specific group after Software\FSLogix\Profiles and in that hive, you can create all the settings that must overrule the standard Profiles hive settings. This creates the option to filter/overrule settings for users that are members of the Active Directory Group – with effectively increasing on capacity – you can stack as much as storage accounts as you need to accommodate more IOPs.<br>   <br>HKLM\SOFTWARE\FSLogix\Profiles\ObjectSpecific\S-1-5-21-306146113-3061682913-806882557-2166\<br>   Create in the registry hive a REG_SZ value name “VHDLocations” and enter the new (extra)Azure Files network file share path (e.g. \\fslogixwvddemo2.file.core.windows.net\fslogixprofiles).   Repeat this for every group you create.<br> Read here more about the FSLogix ObjectSpecific settings:<br>   <https://docs.microsoft.com/en-us/fslogix/configure-per-user-per-group-ht>" <br>    	|    - Configure Profile Container and Office Container for per-user or per-group    <br>From    <https://docs.microsoft.com/en-us/fslogix/configure-per-user-per-group-ht>    <br><br> - Learn here how to configure Azure Files with Active Directory (AD) authentication for         Windows Virtual Desktop – FSLogix Profile Container and MSIX app attach    <br>From    <https://www.christiaanbrinkhoff.com/2020/03/01/learn-here-how-to-configure-azure-files-with-active-directory-ad-authentication-for-fslogix-profile-container-and-msix-app-attach/>    <br>        	|
|    <br>     	|    Azure Files Premium available in Brazil.<br>   Compartilhamentos com até 100TB/cada, chegando a 307.200 IOPS (IOPS Bursting).<br>     	|    - How to         create an premium Azure file share    <br>https://docs.microsoft.com/en-us/azure/storage/files/storage-how-to-create-premium-fileshare     <br><br> - Premium FileStorage account limits    <br>https://docs.microsoft.com/en-us/azure/storage/files/storage-files-scale-targets#premium-filestorage-account-limits<br><br> - Part one: enable AD DS authentication for your Azure file shares    <br>https://docs.microsoft.com/en-us/azure/storage/files/storage-files-identity-ad-ds-enable<br>          	|
|    <br>     	|    Azure   NetApp Files    	|    - Service levels for Azure NetApp Files    <br>https://docs.microsoft.com/en-us/azure/azure-netapp-files/azure-netapp-files-service-levels<br>            	|
|    **WVD Spring Update - Tunning / Performance**    	|    Ferramenta gratuita para otimizar o seu ambiente de WVD.<br>   |    - Windows Virtual Desktop Optimization Tool now available    <br>    https://techcommunity.microsoft.com/t5/windows-virtual-desktop/windows-virtual-desktop-optimization-tool-now-available/m-p/1558614#M5056       	|
|    <br>     	|    Orientações para grandes implementações (acima de 1.000 VMs)    	|    - Windows Virtual Desktop at enterprise scale    <br>From    <https://docs.microsoft.com/en-us/azure/architecture/example-scenario/wvd/windows-virtual-desktop>    <br>        	|
|    **WVD Spring Update - Tools**    	|    WVDAdmin   Client Admin Tool    	| - Windows Virtual Desktop - Spring Release / Spring Update with WVDAdmin    <br>https://blog.itprocloud.de/Windows-Virtual-Desktop-Spring-Update,-Spring-Release/<br>            	|
|    <br>     	|    Deploy a WVD environment via Infrastructure-as-Code from Azure DevOps    	|    - Deploy a WVD environment via Infrastructure-as-Code from Azure DevOps    <br>https://xenithit.blogspot.com/2020/03/how-to-deploy-windows-virtual-dekstop.html<br>        	|
