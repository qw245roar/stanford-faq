Below steps will guide you on getting your bot development and deployment started on Google Cloud Platform.

## Create a `Google Cloud` account:

1. If you do not already have an account, please sign up for a free account at [https://cloud.google.com/free/](https://cloud.google.com/free/)
1. Navigate to [cloud.google.com](cloud.google.com) and log in with your new account

## Create a VM instance

1. On [cloud.google.com](cloud.google.com), go to the upper left and click the main menu (the horizontal bars) then "Compute Engine" -> "VM Instances"
1. At the top, click "Create Instance"
1. In "Boot disk" section choose the "Ubuntu 18.04LTS" image
1. Click "Create" to create the instance. This may take some time - wait for it to complete
1. We need to add a firewall rule which will allow accessing the Jupyter server running in the VM from your local computer browser:
   - Go to the upper left and click the main menu -> "VPC Network" -> "Firewall Rules"
   - At the top click "Create New Firewall Rule"
   - Give it the Name "jupyter"
   - Give it the Target Tag "jupyter'
   - Give it source IP range of "0.0.0.0/0"
   - In Protocols and Ports, allow TCP port 8888
   - Click "Create"
1. Associate the VM with the firewall rule:
   - Go to the upper left and click the main menu -> "Compute Engine" -> "VM Instances"
   - Click on your instance name to bring up its current settings.
   - At the top click "Edit"
   - In Network Tags type "jupyter"
   - At the bottom click "Save"
   
## Deploy the bot

1. Copy the Tutorial.zip to the remote machine and expand it:
   - Go to the upper left and click the main menu -> "Compute Engine" -> "VM Instances"
   - On the right, there is a small button labelled "SSH".  Click it to open an SSH terminal.
   - In the top right of the SSH terminal is a Gear icon.  Click it, then click "Upload File" and select the Tutorial.zip file.
   - Go to the SSH window and type: `sudo apt install unzip`
   - To expand the contents type: `unzip Tutorial.zip`
   - Update Ubuntu package registry: `sudo apt update`
   - To install Docker in the VM run: `sudo apt install docker.io`
   
## Run the bot

1. Now follow the steps from [Build and Run Docker Container](docker.md#docker-install) section.
   - Note that in the JupyterLab URL shown after the container starts you must substitute 127.0.0.1 (localhost IP) with your remote VM IP address. To get that IP from the Cloud Console, navigate to "Compute Engine" -> "VM Instances", and look at "External IP" for your instance.
   

