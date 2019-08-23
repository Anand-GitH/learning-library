
## Table of Contents

[Overview](#overview)

[Pre-Requisites](#pre-requisites)

[Sign in to OCI Console and create ADW instance](#sign-in-to-oci-console-and-create-adw-instance)

[Create Auth token for the user connect to ADW and load data](#create-auth-token-for-the-user-connect-to-adw-and-load-data)

[Delete the resources](#delete-the-resources)

## Overview

Oracle Autonomous Data Warehouse Cloud provides an easy-to-use, fully autonomous database that scales elastically, delivers fast query performance and requires no database administration. In this hands on lab, you will deploy an Autonomous Data Warehouse instance, and load a table using a text file that is stored in object storage. Using the data table, and a Zeppelin Notebook, you'll apply Machine Learning algorithms to select a good wine that costs less than $20 to bring to a party.

**Some Key points**

**We recommend using Chrome or Edge as the broswer. Also set your browser zoom to 80%**

- All screen shots are examples ONLY. Screen shots can be enlarged by Clicking on them

- Login credentials are provided later in the guide (scroll down). Every User MUST keep these credentials handy.

- Do NOT use compartment name and other data from screen shots. Only use  data(including compartment name) provided in the content section of the lab

- Mac OS Users should use ctrl+C / ctrl+V to copy and paste inside the OCI Console

- Login credentials are provided later in the guide (scroll down). Every User MUST keep these credentials handy.

**Cloud Tenant Name**
**User Name**
**Password**
**Compartment Name (Provided Later)**

**Note:** OCI UI is being updated thus some screenshots in the instructions might be different than actual UI

## Pre-Requisites

1. OCI Training : https://cloud.oracle.com/en_US/iaas/training

2. Familiarity with OCI console: https://docs.us-phoenix-1.oraclecloud.com/Content/GSG/Concepts/console.htm

3. Overview of Networking: https://docs.us-phoenix-1.oraclecloud.com/Content/Network/Concepts/overview.htm

4. Familiarity with Compartment: https://docs.us-phoenix-1.oraclecloud.com/Content/GSG/Concepts/concepts.htm

5. Connecting to a compute instance: https://docs.us-phoenix-1.oraclecloud.com/Content/Compute/Tasks/accessinginstance.htm


## Sign in to OCI Console

* **Tenant Name:** {{Cloud Tenant}}
* **User Name:** {{User Name}}
* **Password:** {{Password}}
* **Compartment:**{{Compartment}}

1. Sign in using your tenant name, user name and password. Use the login option under **Oracle Cloud Infrastructure**

<img src="./img/Grafana_015.PNG" alt="image-alt-text">

### Using the Clipboard ###

1. To copy content from the lab instructions to your OCI instance, select the content and use Ctrl-C to copy the content.

2. Click on the Clipboard icon and select **Paste to remote session**.

<img src="./img/ADW_CLIP.png" alt="Qloudable clipboard icon">

3. Click into the pop up window and press Ctrl-V.

4. Click in the tool or field where you want to paste and press Ctrl-V again.

## Download the Notebook from Object Storage ##

1. Find the data file in Object Storage. Select Object Storage from the menu and select Object Storage.

<img src="./img/ADW_ML_OBJ_000.png" alt="image-alt-text">

2. Select your compartment from Scope and then click on the bucket.

<img src="./img/ADW_ML_OBJ_001.png" alt="image-alt-text">

3. Select the file <code>Pick_A_Good_Wine_for_Less_Than_20_dollars.json</code> and click the elipses to download the file.

<img src="./img/ADW_download.png" alt="image-alt-text">

6. Note the location where the file was downloaded.

## Download and Import the Machine Learning Notebook ##

Next, you'll import a Zeppelin Notebook into the Oracle Machine Learning instance associated with your Autonomous Data Warehouse instance.

1. Select Autonomous Data Warehouse from the menu

<img src="./img/ADW_instance.PNG" alt="image-alt-text">

2. Click the ADW instance name and then click **Service Console**

<img src="./img/ADW_service_console.PNG" alt="image-alt-text">

3. Click **Adminstration** and then click **Manage Oracle ML Users**

<img src="./img/ADW_OPEN_ADMIN.PNG" alt="image-alt-text">

4. Click **Show All Users**, then click your OCITEST user

<img src="./img/ADW_ML_USER_01.PNG" alt="image-alt-text">

5. Enter admin@oracle.com in the E-mail Address field and click Save

<img src="./img/ADW_ML_USER_02.PNG" alt="image-alt-text">

6. Your OCITEST user is now added as an Oracle ML User.

<img src="./img/ADW_ML_USER_03.PNG" alt="image-alt-text">

7. Click **Development** then click **Oracle ML SQL Notebooks**

<img src="./img/ADW_OPEN_ML.PNG" alt="image-alt-text">

8. Sign in with your OCITEST user.

9. Click on Notebooks.

<img src="./img/ADW_ML_NOTEBOOK.PNG" alt="image-alt-text">

5. Click **Import** and locate the file <code>Pick_a_Good_Wine_for_less_than_20_dollars.json</code> that you downloaded earlier.

6. Click the notebook name to run it.

<img src="./img/ADW_OPEN_NOTEBOOK.PNG" alt="image-alt-text">

7. Click the gear icon to open Interpreter Binding.

<img src="./img/ADW_NOTEBOOK_INTER_BIND.PNG" alt="image-alt-text">

8. Run each paragraph of the notebook by clicking on the run icon.

<img src="./img/ADW_NOTEBOOK_RUN.PNG" alt="image-alt-text">

9. Some paragraphs have graphs. If you find the graph is empty or missing, follow the instructions in the comment above the SQL command:

<img src="./img/ADW_NOTEBOOK_RUN2.PNG" alt="image-alt-text">

10. Experiment with the Keys, Groups and Values to change how you graph the data. For example, click **settings**, and remove COUNTRY and POINTS by clicking the **x** in each tag. Then drag POINTS to Keys, drag PRICE to Groups to see the distribution of price over the wine points ratings.

<img src="./img/ADW_NOTEBOOK_RUN3.PNG" alt="image-alt-text">

12. Run the remaining paragraphs to determine what is the right wine to bring to your party!

12. When you have completed the Notebook, you can explore other example Notebooks by clicking **Home** from the menu, and then **Examples**.

## Delete the resources

**Delete Auth Token and Autonomous Data Warehouse**

1. Navigate to User Settings, click **Auth Token** and Click **Delete** for your Auth Token by Hovering your mouse over action icon (Three Dots)

<img src="./img/ADW_017.PNG" alt="image-alt-text">

2. Navigate to Autonomous Data Warehouse menu, hover over the action icon(Three dots) and click **Terminate**

<img src="./img/ADW_018.PNG" alt="image-alt-text">

**Congratulations! You have successfully completed the lab.**

