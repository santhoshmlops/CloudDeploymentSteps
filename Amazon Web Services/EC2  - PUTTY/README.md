# Requied Files :
- requirements.txt
- app.py
- templates
- static
- pickle file



# 1. Local Run :
- Once the app.py runs perfectly on the local system, it will be moved to the cloud for Deployment
# 2. Create EC2 Instance :
- EC2 > Launch Instance > Name > choose the AMI > Create new key pair ( it will download the .pem file ) > Network Settings ( Allow HTTPS and HTTP ) > Launch Instance
# 3. Putty Gen :
- Putty Key Gen > Load > choose the .pem file > Save Private Key > .ppk file
- Putty >
# 4. Win SCP - ( Windows and Ubuntu Connection ) :
- WinSCP > Host Name ( Public IPv4 address ) > User Name ( ubuntu ) > Advanced > SSH > Authentication > Load the .ppk file > login
- Drag and Drop the required file to run on the EC2 Instance ( Win SCP )
# 5. Putty :
- Putty > Host Name ( Public IPv4 address ) > Saved Sessions ( any name ) > Save > SSH > Auth > Credentials > add .ppk file > open 
- ubuntu terminal will open > login as > ubuntu

      sudo apt-get update && sudo apt-get install python3-pip
      
# 6. AWS Network & Security :
- Security group > Create security Group > Security group name > Description > Inbound Rules > Add rule > type ( ALL Traffic ) > Create Security group
- Network Interfaces > select the network interface ( Right click ) > Change Security Group > select the created security group > Add the security group > save
# 7.Install all required libraries using putty with this command :
    
    pip3 install -r requirements.txt
Run the Python app with this command :

    python3 app.py
