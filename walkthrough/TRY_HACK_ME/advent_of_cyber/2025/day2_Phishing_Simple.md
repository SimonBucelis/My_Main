# URL
[https://tryhackme.com/room/phishing-aoc2025-h2tkye9fzU](https://tryhackme.com/room/phishing-aoc2025-h2tkye9fzU)

# Concept
* Phishing

# Solving Solution
* Firstly find the server on the AttackBox

cd ~/Rooms/AoC2025/Day02

text
* Then start the server

./server.py

text

# Trying to use Phishing Toolkit 
* In a new terminal open

setoolkit

text
* Firstly press `1` for Social Engineering Attack
* Then press `5` for the Mass Email Attack
* After that press `1` for choosing Spear Phishing Attack
* Write the address of a victim `factory@wareville.thm`
* Then press `2` to rely on your own server
* From address `updates@flyingdeer.thm`
* From username: `Flying Deer`
* Input nothing for the Username for open-relay
* Input nothing for the Password for open-relay
* Input `<YOUR_VICTIM_MACHINE_IP>` for SMTP email server address
* Select `25` port
* Choose not to flag mail
* Select `n` for "Do you want to attach an inline file"
* Input `Shipping Schedule Changes` for Email subject
* Select `p` for "Send the message as HTML or plain"
* Write some convincing message and add your AttackBox IP where you can get info
* Make sure to end on `END`

# What is the password used to access the TBFC portal?
* We should receive something similar to the following on our `server.py` program:

Captured -> username: admin password: unranked-wisdom-anthem from: IP

text

# What is the total number of toys expected for delivery?

http://<IP_ADDRESS_NOTED_FROM_Q1_ANSWER>

text
* We're not logging in as the admin user, but rather the factory user

username: factory
password: unranked-wisdom-anthem

* After logged in, click on the Urgent: Production & Shipping Request - 1984000 Units (Next 2 Weeks) email


