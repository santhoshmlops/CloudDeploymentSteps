# Requied Files :
- .github / workflows / main.yml ( It will automatically created by Azure during development )
-  Dockerfile
-  app.py
-  templates / static
-  source file ( src )

# 1. GitHub :
- Commit all the code inth Github Repository

# 2. Azure ( Container Registry ) :
- Create container registry > Resource group > Create new > Registry name > Review + Create 
- Once Your deployment is complete > Go to resource > Settings > Access Keys > Admin User ( Enabled ) 
- Copy the Login Server and Password keep it safe for the later use 
- Login Server : testdockersan.azurecr.io
- user name : testdockersan
- Password : LbSc9KWS7/En8BRmMx2RBeAAewOIas1sXEFqWHqCEx+ACRDurPtv

# 3. Azure ( Web App ) :
- Create Web App > Resource group (same Resource group) > Instance Details ( Name ) > Publish ( Docker Container ) > Operating System ( Linux ) > Region > 
- Next : Docker > Options ( Single Container ) > image Source ( Azure Container Registry ) > Registry > ( But there will be no image we have to build the docker image )

## Go to Root folder Command Promt and paste the following commands
> docker build -t (Container Registry Login server)/(image name):latest .

Example >>  docker build -t testdockersan.azurecr.io/student:latest .

-After Docker image has been build next we have to login to azure, to login follow the code

> docker login (Container Registry Login server)

Example >> docker login testdockersan.azurecr.io
- user name : testdockersan
- password : LbSc9KWS7/En8BRmMx2RBeAAewOIas1sXEFqWHqCEx+ACRDurPtv ( to paste password right click and press enter )
- After login succeded we have to push the docker image 
> docker push (Container Registry Login server)/(image name):latest

Example >> docker push testdockersan.azurecr.io/student:latest

## Once the image is pushed refesh the azure web app image will be shown as created
- Create Web App > Resource group (same Resource group) > Instance Details ( Name ) > Publish ( Docker Container ) > Operating System ( Linux ) > Region > 
- Next : Docker > Options ( Single Container ) > image Source ( Azure Container Registry ) > Registry > Image > tag > Review + Create > Create
- Open the Created Web App > Deployment ( Deploymeny Center ) > Continous Deployment ( ON ) >Source ( Github actions ) > ( Sign in As ) Organization > Repository > Branch > ( Registry settings ) > Registry > Image > Tag > Save 
- Once it saved in the Github new file will added ( github / workflows / main.yml ) and Github Actions will starts running after completion web link is available to launch 
