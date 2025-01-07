# HyperSpace-Node-setup

---

### ➡️ Method 1. Browser Node

Run using a browser if you have an idle PC or during the times you're working on your computer.  
You might obtain uptime for multipliers, and I'm running it 24/7.  
You can run it on a Windows server (if you have a VPS with Windows installed for other extension nodes).

1. Visit: [https://node.hyper.space/](https://node.hyper.space/)
2. Switch the red button to green.

   ![image](https://github.com/user-attachments/assets/7ed1c492-5027-449f-b8b8-ca6945b63271)

3. Check your points.

   ![image](https://github.com/user-attachments/assets/3d965e34-e9be-472c-89d7-e501f17dc529)

---

You will receive points based on your node's uptime, liveness multiplier, and your system's specification tier.  
You initially start with **Tier-5**, but your tier and multiplier will increase over time as your node stays online with good performance.

4. **Save your PrivateKey**  
   You can import it later.

   ![image](https://github.com/user-attachments/assets/fb77da17-f566-4681-b310-6b9cb5dda17f)

❗️*Make sure to keep the red switch turned on because it can sometimes disconnect, possibly due to network issues.*

---

### ➡️ Method 2. Download App (Windows, Linux, Mac)

1. Visit: [https://hyper.space/downloads](https://hyper.space/downloads)  
   Choose either the **GPU** or **CPU** versions.

   ![image](https://github.com/user-attachments/assets/aa4e128b-da2b-4430-a93e-7cb3469114d8)

2. Download a model and toggle on the red button.

   ![image](https://github.com/user-attachments/assets/162014a3-b359-4774-b4f0-e1721aa4005b)

You can find your PrivateKey file (`key.pmf`) in this directory:  
`C:\Users\XXX\AppData\Roaming\hyperspace`

---

### ➡️ Method 3. Linux CLI Node (VPS)

I'm receiving points on my VPS by going through the following guide. I will update the repo if needed to enhance it.  
You can also check out the [Official Repo](https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file) for more commands and info.

#### Install

```bash
curl https://download.hyper.space/api/install | bash
source /root/.bashrc
Start your node
Create a screen to run it in the background for later:

bash
Copy code
screen -S hyperspace
Run the node:

bash
Copy code
aios-cli start
To continue, minimize your screen using CTRL+A+D or open a second terminal.

Turn back to the screen:

bash
Copy code
screen -r hyperspace
Config Node
Download a required model:

bash
Copy code
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
Import your private key
Create a my.pem file using nano .pem and input your private key (You can get a private key from the browser version):

bash
Copy code
aios-cli hive import-keys ./my.pem
Set those keys as the preferred keys for this session:

bash
Copy code
aios-cli hive login
Make sure the model is registered:

bash
Copy code
aios-cli hive connect
aios-cli hive select-tier 5
You can Upgrade to Tier-3 to receive 2x points:

bash
Copy code
aios-cli hive select-tier 3
Check Points
To check your current multiplier and points:

bash
Copy code
aios-cli hive points

Useful Commands
Shortcut for Start, Login, and Connect to Hive commands (if you've stopped your node):

bash
Copy code
aios-cli start --connect
Update node:

bash
Copy code
aios-cli version
Stop node:

bash
Copy code
aios-cli kill
