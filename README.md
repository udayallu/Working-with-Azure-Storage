# Working-with-Azure-Storage
Azure Storage is a general purpose storage service for storing data in Azure. It is widely used by applications and can provide distributed storage services for Big Data technologies.

### Download the Lab Files
The files you’ll need for this lab are provided in a zip file at https://aka.ms/edx-dat229x-labs. Download and extract the lab files to a folder on your local computer.

## Exercise 1: Working with Azure Storage
- Azure Storage is a general purpose storage service for storing data in Azure.
- It is widely used by applications and can provide distributed storage services for Big Data technologies.
In this exercise, you will create an Azure Storage account and use it to store files.

### Provision an Azure Storage Account and a Blob Container
- You will use an Azure storage account to store data files.
- The files will be stored as binary large objects (BLOBs) in a blob store container that is hosted in your storage account.
###  Steps 1
1. In a web browser, navigate to http://portal.azure.com, and if prompted, sign in using the Microsoft account that is associated with your Azure subscription.
2. In the Microsoft Azure portal, in the Hub Menu (on the left edge of the page), click New. Then in the Storage menu, click Storage account.
![alt text]()
3. In the Create storage account blade, enter the following settings, and then click Create:
- Name: Enter a unique name for your storage account (and make a note of it!)
- Deployment model: Resource manager
- Account kind: General purpose
- Performance: Standard
- Replication: Select Locally redundant storage (LRS)
- Secure transfer required: Disabled
- Subscription: Your subscription
- Resource group: Select Create New and enter a name for a new resource group (and make a note of it!)
- Location: Select any available region
- Pin to dashboard: Unselected
![alt text]()
4. At the top of the page, click Notifications and verify that deployment has started. Wait until your storage account has been created. This should take a few minutes.

### Steps 2
1. In the Hub menu, click All resources, and then click your storage account.
2. In the blade for your storage account, click the Blobs tile, and note that you don’t have any containers yet.
![alt text]()
3. In the blob service blade, **click +Container**, and create a **new container** with the following properties:
- Name: bigdata
- Access type: Private
4. After the bigdata blob container has been created, click it and verify that it contains no blobs.
5. In the bigdata blade, click Properties and view the URL for the blob container, which should be in the form https://<your_account_name>.blob.core.windows.net/bigdata. This is the URL that client applications can use to access your blob container using HTTP protocol.
6. Return to the blade for your storage account, and under **Settings**, click **Access keys**. Then on the **Access Keys** page, note that two keys have been generated. These are used to authenticate client applications that connect to your storage account.

### Use the Azure Portal to Upload a File to Azure Storage
1. The Azure portal includes a rudimentary graphical interface that you can use to work with your Azure storage account.
2. You can use this to transfer files between your local computer and your blob containers, and to browse the data in your storage account.

### Steps
1. In the blade for your **storage account**, view the **Overview page**, and then click the **Blobs tile**.
2. Click the **bigdata** container that you created previously, and then click Upload.
![alt text]()
3. In the **Upload blob blade**, browse to the folder where you extracted the **lab files for this course**, and **select products.txt**. Then verify the following settings and click Upload:
- Files: “products.txt”
- Blob type: Block blob
- Block size: 100 MB
4. After the blob has been uploaded, note that it is listed in the bigdata container blade. Then click the **Products.txt blob** and in the **Blob properties blade**, note its **URL**, which should be similar to https://<your_account_name>.blob.core.windows.net/bigdata/products.txt.
![alt text]()

