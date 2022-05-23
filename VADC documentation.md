# **VA Data Commons**
bla The VA Data Commons supports the management, and analysis of veteran oncologic data for the research community. The data commons aims to accelerate discovery and development of therapies, diagnostic tests, and other technologies for precision oncology. The data commons supports cross-project analyses by harmonizing data from different projects through the collaborative development of a data dictionary, providing an API for data queries, and providing a cloud-based analysis with rich tools and resources.
<br>  

# Getting Started
## **Login Page**
Users will login with their VA PIV credentials.  Start by visiting the login page (https://va.data-commons.org/login). After successfully logging in, your username will appear in the upper right-hand corner of the page. 

Once logged in, the user will see there are several options in the upper right hand corner of the screen. In the blue bar at the top of the page, there is a link to VA Data Commons Documentation (the page you are currently reading), Email Support, your username and a log out button.  Below these options, there are tabs for the Workspace, the Apps, and the Profile pages.

### **VA Data Commons Documentation**
The button for VA Data Commons Documentation takes you to this page.

### **Email Support**
If you need help, the Email Support button allows you to send a message to our help desk at support@datacommons.io 

## **Profile Page**
The Profile page contains two sections: API keys and Project access.

[Note - Insert image of profile page here]: #

### **API key(s)**
To download large amounts of data, an API key will be required as a part of the <a href="https://gen3.org/resources/user/gen3-client/" target="blank">gen3-client</a> . To create a key on your local machine, click Create API key, which will activate a pop-up window. 

[Note - Insert image of create API Key here]: #

Click Download json to save the credential file to your local machine. After completion, a new entry will appear in the API key(s) section of the Profile page. It will display the API key key_id and the expiration date (one month after the key creation). The user should delete the key after it has expired and create a new key. If for any reason a user feels that their API key has been compromised, the key should be deleted before subsequently creating a new one.

### **Project Access**
This section of the Profile page lists the projects and the methods of access for the data within in the Gen3 VA Data Commons system. If you do not see access to a specific study, check that you have been granted access. 

# Data Access and Analysis
## **Workspace**
Workspaces are secure data analysis environments in the cloud that can access data from one or more data resources. By default, Workspaces include Jupyter notebooks, Python and RStudio, but can be configured to host virtually any application, including analysis workflows, data processing pipelines, or data visualization apps. 

New to Jupyter? Learn more about the popular tool for data scientists on <a href="https://jupyter.org/" target="blank">Jupyter.org</a> (disclaimer: CTDS is not responsible for the content).

[Note - Insert image of workspace page here]: #

There are six workspace options available. The options include four versions of Jupyter Notebook Bio Python and two versions of R Studio. Click "Launch" to spin up a copy of that VM.  Launching may take several minutes depending on the size and complexity of the workspace.  

Once the VM is ready, the initial screen for the workspace will appear. After launching, the home folders are displayed, one of which is the user's persistent drive ("pd"). For scripts and output that need to be saved when the workspace is terminated, store those files in the pd/ directory. Only files saved in the /pd directory will remain available after termination of a workspace session. 

Start a new notebook by clicking “New” in the top right corner and choose between Python 3 or R Studio as the base programmatic language. 
Code blocks are entered in cells, which can be executed individually or all at once. Code documentation and comments can also be entered in cells, and the cell type can be set to support Markdown.

Results, including plots, tables, and graphics, can be generated in the workspace and downloaded as files. Only files saved in the /pd directory will remain available after termination of a workspace session. 

Do not forget to terminate your workspace once your work is finished to be mindful of the cost-intensive computational effort. Note, that Workspaces automatically shut down after 90 minutes of idle time.

For more information about the Gen3 Workspace, refer to <a href="https://gen3.org/resources/user/analyze-data/" target="blank">Data Analysis in a Gen3 Data Commons</a>.


## **Apps**
The Apps page displays the option of two apps, OHDSI Atlas and Gen3 GWAS.

### **OHDSI Atlas**
ATLAS is an open source application developed as a part of <a href="https://www.ohdsi.org/" target="blank" >OHDSI</a> intended to provide a unified interface to patient level data and analytics.
The ATLAS user guide can be found <a href="https://www.ohdsi.org/web/wiki/doku.php?id=documentation:software:atlas" target="blank" >here</a>. (disclaimer: CTDS is not responsible for the content).

### **Gen3 GWAS**
Use this app to perform a high throughput GWAS on MVP data using the University of Washington Genesis pipeline.

There are five steps to performing a Gen3 GWAS.  Click the Next or Previous box in the lower corners of the screen to navigate between them.

**Step 1**

Select the cohort you would like to use for GWAS from the coices in the box on the screen, Diabetes Demo or T1D-cases. (**Note: Need a description of these studies**) Click Next.

**Step 2**

Select harmonized variables for phenotypes and covariates from the table of variables.  The selected variables will be used for both the covariates and the phenotype. Click Next.

**Step 3**

Select which variable is your phenotype from previous choices. Click Next.

**Step 4**

Set workflow parameters and remove unwanted covariates. Click Next.

**Step 5**

Submit GWAS job. Click the Sumit button.