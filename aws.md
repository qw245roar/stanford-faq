Below steps will guide you on getting your bot development and deployment started on Amazon Web Services.

## Create your AWS account ##
1. If you do not already have an account, please sign up at https://aws.amazon.com. 
    - Note that **AWS Free tier will not be enough** to request powerful enough VM to build and host Docker container. Hence paid account must be opened
1. Navigate to [AWS Management Console](https://console.aws.amazon.com) and log in with your n account

## Create a VM instance
1. Click "Launch a virtual machine" with EC2
1. On the right, click the "Select" corresponding to "Ubuntu Server 18.04 LTS"
1. Choose "t3a.medium" instance
1. At the top click "6. Configure Security Group"
1. Add the following rules:
    - "SSH" with "Source" `0.0.0.0/0`
    - "Custom TCP Rule" with "Port Range" `8888`
1. Click "Review and Launch".
1. Create a .pem file
    - In the dialog box with the title "Select an existing key pair or create a new key pair", click "Create a new key pair"
    - Give it the name "roartest"
    - Click "Download Key Pair".  This will open a window with text in it. Save it as `roartest.pem`
        - Some platforms add `.txt` to the downloaded file name. Rename it to `roartest.pem` in such case
    - If case you use non-Windows OS, open a terminal window and go to the directory where you saved the .pem file and change its permissions by running: `chmod 400 roartest.pem`
1. Click "Launch Instances" -> "View Instances" and wait for the Instance State to become `running`

## Deploy the bot

1. Upload the SDK to the VM instance
    - Click "Connect" button at the top of the AWS Console page and follow the instructions to connect through standalone SSH client. Note the remote server address as it will be needed in the `scp` command below.
    - Use `scp` tool to copy the SDK .zip file to the VM by running: `scp -i roartest.pem Tutorial.zip <VM URL>:`
    Above command assumes the PEM file created in the previous sections and the Tutorial.zip file downloaded 
    from the ROAR web site are located in the current directory. *Note* the semicolons after the URL which indicate that the file must be copied in the home directory of the remote user.
4. Unzip the SDK and run it
    - Go to the SSH window and type: `sudo apt install unzip`
    - To expand the contents type: `unzip Tutorial.zip`
    - Update Ubuntu package registry: `sudo apt update`
    - To install Docker in the VM run: `sudo apt install docker.io`

## Run the bot
1. Now follow the steps from [Build and Run Docker Container](docker.md#docker-install) section.
   - Note that in the JupyterLab URL shown after the container starts you must substitute the localhost IP with your remote VM IP address, which is visible in "IPv4 Public IP" column of your instance in the AWS Console.
   
