# Create your first virtual machine in Azure

In this exercise, you will be creating a **Windows** virtual machine using Azure Portal. Let us get started.

1. Click on the **Create a resource** in the upper left corner of the Azure portal and select the  **Windows Server**.

   
2. In the basics tab under the **Virtual machine details**, make sure the existing **Subscription** and existing  **Resource group** named **linux-empty-XXXX** is selected.

   
3. Under the **Instance details**, Enter the **Virtual machine name** of your choice, choose your **Region**, select **Windows Server 2016** image and select the virtual machine **size** as **Standard D2s v3**. Please note that all VM sizes are not allowed in the lab environment, Please ensure to choose the defined VM size only.
   
   
4. Under the **Administrator account**, Provide the **Username** and **password** of your choice.


5. Leave the remaining options default and select the **Review + create** button at the bottom of the page.

6. On the **Create a virtual machine page**, you can review all configurations of the VM you are about to create. When you are ready, select **Create**.

   
7. It will take about 2 to 4 minutes for the VM to be deployed. Once deployed, you can review the Virtual machine details on the overview page. 

   
8. You have now successfully created a **Ubuntu Virtual Machine** on Azure. 

### 1.3 RDP to VM using Public IP
In this exercise, You will be accessing the Windows virtual machine deployed earlier through SSH. We will be using **Cloud Shell** for this.

1. Launch **Cloud Shell** if not running already and run following command to list down the VMs running in your lab environment.

       az vm list -o table       
   
   ![](images/linux4.png)
   
2. Now, let us find out the public IP of your recently created Virtual Machine. Execute the following command in **cloud shell**, Please ensure to replace the resource group name **linux-empty-XXXX** and **VM name** with your lab environment values, you can review those from the output of last step.

       az vm show -d -g linux-empty-XXXX -n <VM name>  --query publicIps -o tsv

3. Now connect to this virtual machine using "Remote Desktop Connection" from your jump VM. 

4. Once completed, Click "Next" to continue
