# Let's Build: FHIR from Jupyter

In this lab, we import the following Jupyter notebooks into IBM Watson Studio within the IBM Cloud Pak for Data:
1. The FHIR API
2. FHIR in Spark
3. Predictive Modeling

Notebook 1 is configured to use an instance of the [IBM FHIR Server](https://github.com/IBM/FHIR) (running on IBM Cloud) which has been loaded with sample data generated from the Synthea™️ Patient Generator.

Notebook 2 requires access to a Cloud Object Store with FHIR R4 resources from [SyntheticMass](https://synthea.mitre.org/downloads).

Notebook 3 builds a predictive model from Parquet files that are built in notebook 2 from features extracted from the FHIR resources.

Notebook 1 should work from almost any Jupyter notebook environment, but notebooks 2 and 3 use Apache Spark to process bulk FHIR resources into a dataframe and therefor must run in a Jupyter environment with access to Spark.

## Getting started

### Download the notebooks

Clone or download the notebooks from this repo to your local system.
![download the notebooks](images/0.download.png?raw=true)

### Register / log in to IBM Cloud

1. Navigate to https://dataplatform.cloud.ibm.com/registration/stepone
2. Choose `Dallas` to be nearest to the data for this lab
    ![register for IBM Cloud](images/1.register.png?raw=true)

If you already have an IBMid, enter it on the right.
If not, enter a valid email address on the left, agree to the terms, click *Next*, and check your email to complete the registration process.

Once registered and logged in, continue to the Watson Studio dashboard.
![the watson studio dashboard](images/3.dashboard.png?raw=true)

### Create a project

1. From the IBM Cloud Pak for Data dashboard, click `New project +`
    ![new project dialog](images/4.create-project-1.png?raw=true)
2. Select `Create an empty project`
    ![create a project](images/5.create-project-2.png?raw=true)
3. Give the project a name (e.g. *FHIR from Jupyter*) and click `Add` to define a storage service
    ![create cloud object storage](images/6.create-storage.png?raw=true)
4. Select a plan (the free `Lite` plan should be fine) and click `Create`
5. Click `Refresh` to see your Cloud Object Storage instance appear and then click `Create`

![project dashboard](images/7.project-dashboard.png)

### Create a notebook

From the Project dashboard, click `Add to project +` and choose the `Notebook` asset type.
![create a notebook](images/8.new-notebook.png?raw=true)

Select the `From file` tab and select the `Default Spark 2.4 & Python 3.7` environment.
Then, upload one of the notebook files that was downloaded in the [Download the notebooks section](#Download-the-notebooks) and click `Create`.

Repeat this process for the other notebooks that you desire to load.
