# Required File :
- app.yaml ( python38 )
- main.py  ( For GCP app.py must be renamed as main.py )

# 1. Create GCP Project :
- IAM & Admin > Create a project > Project Name > Create 

# 2. Download and install Google Cloud SDK app :

# 3. App Engine :
- App Engine > Create Application > Select a Region > Resources ( Python ) 
- Open Command Prompt in the Root folder 

      gcloud init

- Pick Configuration to use  > Choose the Account  > pick the cloud project ( it will initialize your project )

      gcloud app deploy app.yaml --project ( PROJECT NAME )
