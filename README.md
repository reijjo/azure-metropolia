# Azure-Metropolia
Azure basics

## Module 2
<summary>Create a Virtual Machine using Azure Portal
  <details>
    
    * Virtual machines -> Create
    * Set subscription -> Create new Resource group 'VM1'
    * Virtual machine name 'virtualmachine1'
    * Availibility options -> No infrastructure redundance required
    * Image -> Windows 10 Pro -> Select size -> set Username and Password
    * Select inbound ports -> allow all -> use existing Windows Server license -> next
    * Leave everything else as default and go to Review + create -> Create
    * When deployment is done -> Go to 'Resource groups' -> VM1 -> virtualmachine1
    * Connect -> Native RDP -> Download RDP file -> Open -> give your Username and Password
    
    And now you have a fully functional Virtual Machine
    * Shut down the virtual machine because it costs you money -> Delete Research group VM1
  </details>
</summary>

<summary>Create Blob storage
  <details>

    * Storage accounts -> Create storage account
    * Set subscription -> Create new Resource group 'blobrg1'
    * Storage account name 'YOURSTORAGEACCOUNTNAME'
    * Leave everything else af default and go Review -> Create
    * After deployment -> 'Resource groups' -> 'blobrg1' -> 'YOURSTORAGEACCOUNTNAME'
    * 'Settings' from the left navbar -> 'Allow Blob anonymous access' -> Enabled -> Save
    * 'Data storage' from the left navbar -> 'Containers' -> '+ Container' from the top
    * Name -> 'blobcontainer' -> Anonymous access level -> 'Container ...' -> Create
    * Select 'blobcontainer' -> Upload a file from the top -> Upload
    * Click on the '...'
      * 'View/edit' to see the file
      * 'Properties' -> Copy the URL and paste it to browser -> TADAA! 
  </details>
</summary>

<summary>Create a SQL database
  <details>

    * SQL databases -> Create SQL database
    * Set subscription -> Create new Resource group 'sqldb1-rg1'
    * Server -> Create new -> 'YOURDBACCOUNTNAME'
    * Set Azure AD admin -> Users -> You should find your name there -> OK
    * Compute + storage -> I chose the cheapest
    * Networking tab -> Public endpoint??
    * Additional settings tab -> Use existing data -> Sample -> AdventureWorksLT
    * Review + create -> 'Create'
    * When deployment is done -> Go to 'Resource groups' -> 'db1'
    * 'Configure access' on 'Getting started' tab -> 'Configure'
    * Firewall rules -> 'Add your client IPv4 ...' -> 'Save'
    * Go to 'db1' -> 'Query editor (preview)' from the left -> 'Continue as [your@email.com]'
    * Make a query 
    ```
      SELECT TOP 20 pc.Name as CategoryName, p.name as ProductName
      FROM SalesLT.ProductCategory pc
      JOIN SalesLT.Product p
      ON pc.productcategoryid = p.productcategoryid;
    ```
    just to see that everything works.
    * Delete this research group so you don't get any extra costs.
  </details>
</summary>

<summary>Working with Azure CLI
  <details>

    * Install client with brew -> 'brew update && brew install azure-cli'
    * Login -> 'az login' -> Check version -> 'az --version'
    * Create research group -> 'az group create --name [yourgroupname] --location eastus2'
    * Before deploying a Virtual Machine we will validate the template and command by running 
    the following Azure CLI command, substituting the values with your own, specifying a username and 
    password and a unique name for the virtual machine DNS label prefix value. 
    The command should run successfully without error, identify what is causing the error, 
    modify it and run the command again until it does validate successfully.
    ```
    az deployment group validate \
    --resource-group < resource group created earlier > \
    --template-uri https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/quickstarts/microsoft.compute/vm-simple-windows/azuredeploy.json \
    --parameters adminUsername=$USERNAME \
    --parameters adminPassword=$PASSWORD \
    --parameters dnsLabelPrefix=$DNS_LABEL_PREFIX
    ```
    getting a quota error because you are trying to deploy a VM size that exceeds your current limit. Ok Skip this.
  </details>
</summary>
