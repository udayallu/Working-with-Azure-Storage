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
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img1.PNG)
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
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img2.PNG)
4. At the top of the page, click Notifications and verify that deployment has started. Wait until your storage account has been created. This should take a few minutes.

### Steps 2
1. In the Hub menu, click All resources, and then click your storage account.
2. In the blade for your storage account, click the Blobs tile, and note that you don’t have any containers yet.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img3.PNG)
3. In the blob service blade, **click +Container**, and create a **new container** with the following properties:
- Name: bigdata
- Access type: Private
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img4.PNG)
4. After the bigdata blob container has been created, click it and verify that it contains no blobs.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img5.PNG)
5. In the bigdata blade, click Properties and view the URL for the blob container, which should be in the form https://<your_account_name>.blob.core.windows.net/bigdata. This is the URL that client applications can use to access your blob container using HTTP protocol.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img6.PNG)
6. Return to the blade for your storage account, and under **Settings**, click **Access keys**. Then on the **Access Keys** page, note that two keys have been generated. These are used to authenticate client applications that connect to your storage account.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img7.PNG)
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img8.PNG)

### Use the Azure Portal to Upload a File to Azure Storage
1. The Azure portal includes a rudimentary graphical interface that you can use to work with your Azure storage account.
2. You can use this to transfer files between your local computer and your blob containers, and to browse the data in your storage account.

### Steps
1. In the blade for your **storage account**, view the **Overview page**, and then click the **Blobs tile**.
2. Click the **bigdata** container that you created previously, and then click Upload.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img9.PNG)
3. In the **Upload blob blade**, browse to the folder where you extracted the **lab files for this course**, and **select products.txt**. Then verify the following settings and click Upload:
- Files: “products.txt”
- Blob type: Block blob
- Block size: 100 MB
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img10.PNG)
4. After the blob has been uploaded, note that it is listed in the bigdata container blade. Then click the **Products.txt blob** and in the **Blob properties blade**, note its **URL**, which should be similar to https://<your_account_name>.blob.core.windows.net/bigdata/products.txt.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img11.PNG)

## Use Azure Storage Explorer to Upload files to Azure Storage
- The blob container interface in the Azure portal enables you to upload, browse, and download blobs; but it lacks many of the features expected in a modern file management tool.
- There are various graphical Azure storage management tools available, including support for exploring your Azure storage in Microsoft Visual Studio.
1. Open a new browser tab and browse to http://storageexplorer.com.
2. Download and install the latest version of Azure Storage Explorer for your operating system (Windows, Mac OSX, or Linux).
3. When the application is installed, launch it. Then add your Azure account, signing in with your Azure credentials when prompted, and configure Storage Explorer to show resources from the Azure subscription in which you created your storage account.
4. After your subscription has been added to the Explorer pane expand your storage account, expand Blob Containers, and select the bigdata container. Note that the products.txt file you uploaded previously is listed.
5. In the Upload drop-down menu, note that you can choose to upload individual files or folders. Then select Upload Folder and browse to the folder where you extracted the lab files for this course and select the data folder, and upload it as a block blob.
6. After the upload operation is complete, double-click the data folder in your blob container to open it, and verify that it contains files named customers.txt and reviews.txt.
7. Click the  button to navigate back up to the root of the bigdata container, and select the products.txt file. Then click Copy.
8. Open the data folder, and then click Paste to copy the product.txt file to this folder.
9. Navigate back up to the root of the bigdata container, and select the products.txt file. Then click Delete, and when prompted to confirm the deletion, click Yes.
10. Verify that the bigdata container now contains only a folder named data, which in turn contains files named customers.txt, products.txt, and reviews.txt.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img12.png)

## Exercise 2: Working with Azure Data Lake Store
- Azure Data Lake Store is a storage service in Azure that is optimized for big data workloads. 
- It supports unlimited numbers of files of unlimited size and can be used to organize and secure files in folder hierarchies.
In this exercise, you will provision Azure Data Lake Store and upload some files to it.

### Provision Azure Data Lake Store
To get started, you must provision Azure Data Lake Store.
1. In the Microsoft Azure portal, in the Hub Menu (on the left edge of the page), click New. Then in the Storage menu, click **Data Lake Store**.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img13.PNG)
2. In the **New Data Lake Store blade**, enter the following settings, and then click Create:
- Name: Enter a unique name for your storage account (and make a note of it!)
- Resource group: Select Use existing and select the resource group you created previously.
- Location: Select any available region
- Pricing: Pay-as-you-go
- Encryption Settings: Enabled
- Pin to dashboard: Unselected
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img14.PNG)
3. At the top of the page, click Notifications and verify that deployment has started. Wait until your storage account has been created. This should take a few minutes.

### Upload Files to Azure Data Lake Store
Now that you have provisioned Azure Data Lake Store, you can use the Data Explorer in the Azure Portal to upload files.
1. In the Hub menu, click **All resources**, and then click your Data Lake Store.
2. In the blade for your Data Lake Store, click **Data Explorer**.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img15.PNG)
3. In the Data Explorer blade, click **New Folder**. Then create a folder named **data**.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img16.PNG)
4. Click the data folder to open it.
5. Click Folder Properties; and in the Properties blade, view the PATH property. This is the folder URL, and should be similar to adl://<your_account_name>.azuredatalakestore.net/data/
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img17.PNG)
6. In the blade for the data folder, **click Upload**.
7. In the Upload files blade, browse to the folder where you extracted the lab files for this course and view the contents of the data folder. Then select all the files it contains (hold the CTRL key to select multiple files) and click Add selected files to upload them to the data folder in your Azure Data Lake Store.
8. After the files have been uploaded, close the Upload files blade and verify that the data folder in your **Azure Data Lake Store** now contains **customers.txt** and **reviews.txt**.
![alt text](https://github.com/udayallu/Working-with-Azure-Storage/blob/master/images/img18.PNG)
9. Click reviews.txt and view the preview of the data. Note that the tab-delimiter has been detected and the data is shown as a table with multiple columns.
