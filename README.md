# HyperSpace-Node-setup

➡️ Method 1. Browser Node
Run using browser if you have an idle PC or during the times you're working on your computer
You might obtain uptime for multipliers, I'm running it 24/7
You can run it on a windows server (if you have a VPS with windows installed on for other extension nodes)
1. Visit: https://node.hyper.space/
2. Switch the red button to green
image
![image](https://github.com/user-attachments/assets/7ed1c492-5027-449f-b8b8-ca6945b63271)


4. Check your points
   ![image](https://github.com/user-attachments/assets/3d965e34-e9be-472c-89d7-e501f17dc529)




You receive points based on your node's uptime, liveness multiplier, and your system specification's tier
You initially get Tier-5 but your tier and multiplier will increase over time as your node stays online with good performance
4. Save your PrivateKey
You can import it later

![image](https://github.com/user-attachments/assets/fb77da17-f566-4681-b310-6b9cb5dda17f)


❗️* Make sure to keep the red switch turned on because it can sometimes disconnect, possibly because of network issues.

➡️ Method 2. Download App (Windows, Linux, Mac)
1. Visit: https://hyper.space/downloads
You can choose GPU or CPU versions

![image](https://github.com/user-attachments/assets/aa4e128b-da2b-4430-a93e-7cb3469114d8)


2.Download a model and toggle on the red button
![image](https://github.com/user-attachments/assets/162014a3-b359-4774-b4f0-e1721aa4005b)


You can find your PrivateKey file key.pmf in this directory C:\Users\XXX\AppData\Roaming\hyperspace
➡️ Method 3. Linux CLI Node (VPS)
I'm receiving points on my VPS by going through the following guide but I will update the repo if it was needed to enhance it
You can also check out [Officil Repo](https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file) for more commands and info
Install
curl https://download.hyper.space/api/install | bash

source /root/.bashrc
Start your node
# Create a screen ro run it in background for later
screen -S hyperspace

# Run node
aios-cli start
To continue, minimize your screen using CTRL+A+D or Open second terminal
Turn back to screen: screen -r hyperspace
Config Node
# Download a required model
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
# Import your private key - Create a my.pem file using nano .pem and input a privatekey (You can get a privatekey from browser version)
aios-cli hive import-keys ./my.pem
# Set those keys as the preferred keys for this session
aios-cli hive login
# Make sure the model is registered
aios-cli hive connect
aios-cli hive select-tier 5
You can Upgrade to Tier-3 to receive 2x points

aios-cli hive select-tier 3
Check Points
# To check your current multiplier and points
aios-cli hive points
![image](https://github.com/user-attachments/assets/88282203-a3d5-48ca-89e6-485623c7ad9d)


Usefull commands
# Shortcut for Start, Login and Connect to Hive commands, if you've stopped you node
aios-cli start --connect
# Update node
aios-cli version
# Stop node
aios-cli kill


