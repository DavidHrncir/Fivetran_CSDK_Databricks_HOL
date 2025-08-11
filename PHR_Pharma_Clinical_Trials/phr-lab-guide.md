# Fivetran Connector SDK Hands on Lab with Databricks 2025: Pharmaceutical Clinical Trial Design and Optimization

## Overview
In this hands on lab, you'll build a **custom Fivetran connector** using the **Fivetran Connector SDK** and the **LLM service of your choice** to integrate data from a custom REST API into Databricks. You'll then create a **Streamlit (in Databricks)** application with various tools and dashboards powering key metrics as well as a **Databricks Mosaic AI Model Serving** feature to drive even deeper analytics, descriptive, and prescriptive insights.

The Pharmaceutical PHR custom connector should fetch clinical trial and patient records from a REST API and load them into a single table called `phr_records` in your Databricks database. The connector should deliver detailed information about clinical trial protocols and patient enrollment details, including properties like enrollment date, trial status, patient demographics, disease area, enrollment rate, dropout rate, and regulatory approval status. It should handle authentication, pagination, error handling, and maintain state between sync runs using a cursor-based approach.

## Lab Steps - Quick Access

- [Step 1: Set up the Development Environment](#step-1-set-up-the-development-environment)
- [Step 2: Create a Custom Fivetran Connector](#step-2-create-a-custom-fivetran-connector)
- [Step 3: Start Data Sync in Fivetran](#step-3-start-data-sync-in-fivetran)
- [Step 4: Create a Streamlit Application in Databricks](#step-4-create-a-streamlit-application-in-databricks)

## Web Locations
- Browser tabs (leave them open throughout the lab):
  - Tab 1: GitHub Lab Repo: This Lab Guide (stays on lab guide)
  - Tab 2: GitHub Lab Repo: This Lab Guide (expands folders and opens files) 
  - Tab 3: [Fivetran: Automated Data Movement Platform](https://www.fivetran.com/login)
  - Tab 4: [Databricks: Data and AI Platform](https://accounts.cloud.databricks.com/login?account_id=c7e4e80f-925e-4a24-8fb4-34d7b876c698)
  - Tab 5: [Fivetran Connector SDK Docs](https://fivetran.com/docs/connector-sdk)ß

***PAUSE: Let's quickly walk through the GitHub interface.***

## Step 1: Set up the Development Environment
1. Create the project directory. On a Windows or Mac, create the **phr** folder in a folder that does not reside under a system folder such as "My Documents".

2. Download the project files from the git repo (easiest way):
   - **phr_manual.env**: Environment variables loading file
   - **configuration.json**: Configure your API credentials and settings
   - **connector.py**: Our connector code for this vertical
   - **requirements.txt**: Python requirements file
3. Once the above files are downloaded copy/move them to the newly created **phr** folder
4. Open this folder in your development IDE or in a terminal window
5. **Activate your Python virtual environment in your terminal window**

6. Set up our environment variables.
   - Edit the **phr_manual.env** file.  These values will become environment variables in your current terminal session (meaning if you close the terminal by accident, you will need to re-apply these environment variables). NOTE: If these environment variables are not present, you will be prompted to enter them manually during debugging and deployment (added complexity).  Note that the **FIVETRAN_CONFIGURATION** and **FIVETRAN_PYTHON_VERSION** values are already set.  We need to update the first 3 values now.
      - **FIVETRAN_API_KEY**: We need to be in our Fivetran UI, then click your name in the lower left nav panel, then click API Key, and click Generate New API Key.  Copy the ***base64 encoded key***, remove the default text including the brackets and paste that value. If you make a mistake, you can generate a new key as it will overwrite the previous one.
      - **FIVETRAN_DESTINATION_NAME**:  The instructor will place the value in the webinar chat area.  Copy and paste from there.
      - **FIVETRAN_CONNECTION_NAME**: This must be all lower case letters, numbers, and underscores.  Since we are sharing a common environment, the <ins>connection names must be unique</ins>.  An option that works well here is, your initials followed by your birth month and day followed by phr.  Example: **dh0816phr** This value will be the connector name in Fivetran as well as the schema name in Databricks.  Ensure you save the **phr_manual.env** file.
7. Copy all 5 values from the phr_manual.env file and paste them into your terminal and press enter/return.
   - To view/verify the values are applied in Windows:
   ```bash
   set
   ```
   - To view/verify the values are applied in Mac:
   ```bash
   env
   ```

## Step 2: Create a Custom Fivetran Connector

### 2.1 Install the Fivetran Connector SDK Package
Let's install the Fivetran Connector SDK package. We will directly use version 1.7.0. In your terminal with your Python environment already activated, run the following command:
```bash
pip install fivetran-connector-sdk==1.7.0
```

### 2.2 Debug the Custom Connector Locally
1. Let's debug our code in the terminal by running the following commands. **fivetran reset** tells your local SDK system that all files and temporary databases should be reset for a brand new run. **fivetran debug** tells your local SDK system that it should mimic locally what Fivetran would be doing in Fivetran's environment.  You will notice that you must pass in the **--configuration configuration.json** parameter for the debug command since you could be testing multiple types of configurations during a development/testing cycle.
```bash
fivetran reset
```
```bash
fivetran debug --configuration configuration.json
```

2. (Optional-Instructor will demo) Once debug completes, you are able to open a tool like dBeaver and open the DuckDB in the projects **files** folder and inspect the contents.  **Ensure you disconnect** the tool from the database when done since most tools will lock the database while open.

3. If you let the code run to the end, you should see a statement that 600 rows were replicated/upserted.

***PAUSE: Let's analyze what is happening behind the scenes.***

### 2.3 Deploy the Custom Connector to Fivetran
Let's deploy this code into Fivetran. This is the portion where all of the environment variables will be utilized.  Let's run the following command.  This command will prompt you for parameters, but you will notice that the command takes our environment variables and presents them as defaults.  You can just press enter/return through those.  **Note that only a portion of the Fivetran API key will be shown.**
```bash
fivetran deploy --configuration configuration.json
```

You should receive a message stating the connection was deployed successfully along with the Python version and the Connection ID value. At this point, we are done with developing our connection.  Let's move some data!

## Step 3: Start Data Sync in Fivetran

1. Switch to the Fivetran tab in your browser.
2. Ensure you are in the **Connections** page and refresh the page to find your newly created connection.  If you enter your initials in the search, it should filter directly to your connection.
3. Click on the connection to open the **Status** page.
4. Click the **Start Initial Sync** button.
5. You should see a status message indicating that the sync is **Active** and that it is the first time syncing data for this connection.
6. Once your sync completes, you will see a message "Next sync will run in x hours" and if you click on the **1 HOUR** selection on the right side, you will see some sync metrics.  <ins>You may need to refresh the UI to see updated sync progress and logs in the UI. </ins>
7. Once your sync completes, you will see a message "Next sync will run in x hours" and if you click on the **1 HOUR** selection on the right side, you will see some sync metrics.

***PAUSE: Recap.***

## Step 4: Create a Streamlit Application in Databricks

### 4.1 Create the Application Compute
Databricks offers a variety of application types: Dash, Flask, Gradio, Shiny, Streamlit, and Node.js. Today we will use the Streamlit version. We need to create a compute instance to run our Streamlit application.
1. In the Databricks UI, left navigation panel, click on **Compute**.
2. Click on the **Apps** tab.
3. Click the **Create app** button on the right side of the screen.
4. Click the **Create a custom app** option at the top of the list.
5. For the **App name** field, enter an app name that is unique such as [initials][birth month][birthday][phr]-app. ex. **dh0816phr-app** The **Description** can be left blank.
6. <ins>VERY IMPORTANT</ins>, click the **Next: Configure** button and <ins>NOT</ins> the **Create app** button.
7. Under **App resources** click **+Add resource**, choose **Secret**, and fill in the fields as follows:
   - For **Secret**, choose **databricks-app-secrets**.
   - For **Select secret key**, choose **databricks-token**.
   - **Permission** should stay as **can read**.
   - **Resource key** should stay as **secret**.
8. Now click **Create app**.  You will see a screen stating that the compute is starting. This process will take 2-3 minutes to create the compute to run our Streamlit application. While the compute is being created, we will set up our application code.

### 4.2 Create the Vertical-Based Folder in Your Databricks Workspace
1. While still in the Databricks tab, click the **Workspace** item in the left navigation panel (top-left); this will open a middle navigation panel.
2. In the middle navigation panel, expand **Workspace**, then expand **Users**.
3. Your login name is at the top of the list by default in the user list panel; click on your login name.
4. In the upper right portion of your screen, click **Create** and choose **Folder** (Note: You may also right-click in the whitespace and choose Create Folder as well.)
5. Enter this vertical's abbreviation, **phr**, as the name of the folder and click **Create**.
6. This folder will automatically become the current folder as you will see at the top of the screen now states **phr**.

### 4.3 Create Empty File Placeholders In Your Workspace Folder
In the **phr** folder you just created, create 3 empty files by either right-clicking or using the **Create** button in the upper right for the first file. <ins>Once the first file is created, you can simply click the **+** sign in the tabbed view to create new files.</ins>
   - **app.py**
   - **app.yaml**
   - **requirements.txt**

### 4.4 Copy File Text from Git Repo to Workspace Files
1. In the vertical project GitHub tab, expand the **Streamlit App** folder
2. Click the **app.py** file.
3. Click the **copy** icon in the upper right corner of the text window.
4. In the Databricks workspace, click the **app.py** file and paste the contents into that file.
5. The file will auto-save.
6. Do the same steps 2-5 above for the **app.yaml** and **requirements.txt** files pasting the contents into their respected files.

### 4.5 Update the app.yaml with Schema
The **app.yaml** file is mostly set up and ready to use.  The only property we need to update is the **UC_SCHEMA value** which is set as the first property in the **env** section. This is done because each one of us created our own schema in the catalog.
1. Find the name of your Fivetran connection. That is your schema name.  If you do not recall the name of your connection, you can either use the Fivetran Connections UI to locate your connection name, or use the catalog explorer in the middle navigation panel.
2. Fill in the **UC_SCHEMA value** with your schema/connection name between the two single quotes. An example is below.
```bash
  - name: UC_SCHEMA
    value: 'dh0816phr'
```

With that our application is ready to be built in Databricks Apps.

### 4.6 Deploy the Streamlit App using Our Code Folder
1. Click **Compute** in the left navigation panel.
2. Click the **Apps** tab.
3. Find the app you created using your initials and click on the app.
4. The **Deploy** button in the upper right should now be available; click the **Deploy** button.
5. You will be prompted to enter your source code path. Click the icon. You should be directly at the **phr** folder. Click the **phr** folder. If by chance this is not the default, simply choose **Workspace, Users, [your login], phr**. <ins>Note that you should see the 3 files we created earlier.</ins>
6. Click the **Select** button.
7. Click the **Deploy** button.
8. The deployment process will start and usually takes about 30-180 seconds to install, create the app, and make the URL available for use.
9. When ready, you will see a green dot stating **Running** at the top of the screen.  Click the URL in that location to launch your application in a new browser tab.

### 4.7 Explore the Streamlit in Databricks Gen AI Data App
The TrialGenius data app should now be running with the following sections:
- **Metrics**: View key performance metrics, patient age distribution, enrollment rates by disease area, trial status distribution, dropout rate trends, site performance analysis, and comprehensive clinical trial statistics
- **AI Insights**: Generate AI-powered analysis of the clinical trial and patient enrollment data across four focus areas with advanced agent workflows providing transparent, step-by-step pharmaceutical analysis
- **Insights History**: Access previously generated AI insights
- **Data Explorer**: Browse the underlying data

## Done!
You've successfully:
1. Created a custom Fivetran connector using the Fivetran Connector SDK
2. Deployed the connector to sync pharmaceutical clinical trial data into Databricks
3. Built a Streamlit application in Databricks Apps to visualize and analyze the data using Databricks Mosaic AI Model Serving

## Next Steps
Consider how you might adapt this solution for your own use:
- Integration with clinical trial management systems like Veeva Vault CTMS, Oracle Clinical One, or Medidata Rave for comprehensive trial protocol management
- Adding real-time patient enrollment monitoring from electronic data capture systems like Medidata Rave EDC, Oracle Clinical One Data Collection, or Veeva Vault EDC
- Implementing machine learning models for more sophisticated trial failure prediction and adaptive protocol optimization
- Customizing the Streamlit app for specific therapeutic areas, patient populations, or pharmaceutical development goals

## Resources
- Fivetran Connector SDK Documentation: [https://fivetran.com/docs/connectors/connector-sdk](https://fivetran.com/docs/connectors/connector-sdk)  
- Fivetran Connector SDK Examples: [https://fivetran.com/docs/connector-sdk/examples](https://fivetran.com/docs/connector-sdk/examples)
- API Connector Reference: [https://sdk-demo-api-dot-internal-sales.uc.r.appspot.com/hed_api_spec](https://sdk-demo-api-dot-internal-sales.uc.r.appspot.com/hed_api_spec)
- Databricks Mosaic AI Model Serving Documentation: [https://docs.databricks.com/aws/en/machine-learning/model-serving/](https://docs.databricks.com/aws/en/machine-learning/model-serving/)
- Databricks Apps Documentation: [https://docs.databricks.com/aws/en/dev-tools/databricks-apps/](https://docs.databricks.com/aws/en/dev-tools/databricks-apps/)
