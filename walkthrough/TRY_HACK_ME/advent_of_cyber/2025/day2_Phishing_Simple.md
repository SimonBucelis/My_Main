# URL
https://tryhackme.com/room/phishing-aoc2025-h2tkye9fzU

# Concept
- Phishing

# Solving Solution
- First, find the server on the AttackBox:
  - cd ~/Rooms/AoC2025/Day02
- Then start the server:
  - ./server.py

# Using the Phishing Toolkit
- In a new terminal, run:
  - setoolkit
- Press 1 for Social Engineering Attacks
- Press 5 for the Mass Mailer Attack
- Press 1 for E-Mail Attack Single Email Address (spear phishing)
- Send email to: factory@wareville.thm
- Choose 2 to use your own server or open relay
- From address: updates@flyingdeer.thm
- From name: Flying Deer
- Leave Username for open-relay blank
- Leave Password for open-relay blank
- SMTP email server address: <YOUR_VICTIM_MACHINE_IP>
- Port: 25
- Flag this message as high priority: no
- Do you want to attach a file: n
- Do you want to attach an inline file: n
- Email subject: Shipping Schedule Changes
- Send the message as HTML or plain: p (plain)
- Write a convincing message and include the URL:
  - http://<YOUR_ATTACKBOX_IP>:8000
- End the body with:
  - END

# Q1 - What is the password used to access the TBFC portal?
- On the terminal running server.py you should see captured credentials similar to:
  - Captured -> username: admin    password: unranked-wisdom-anthem    from: IP
- Answer: unranked-wisdom-anthem

# Q2 - What is the total number of toys expected for delivery?
- Browse to:
  - http://<IP_ADDRESS_NOTED_FROM_Q1_ANSWER>
- Log in with:
  - username: factory
  - password: unranked-wisdom-anthem
- Check the mailbox to find the email showing the total number of toys expected for delivery.
