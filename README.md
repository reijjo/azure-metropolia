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
