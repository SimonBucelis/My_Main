# URL

https://tryhackme.com/room/linuxcli-aoc2025-o1fpqkvxti
Concept
```
Linux Basic comands
```
# Method of solve
After finishing the basics inside 

```
mcskidy@tbfc-web01:~$ cd /home
mcskidy@tbfc-web01:/home$ cd mcskidy
mcskidy@tbfc-web01:~$ cd Documents
mcskidy@tbfc-web01:~/Documents$ cat read-me-please.txt


```

There is txt file whic i cated to open new task for advanced users

username: 
```
eddi_knapp
```

password: 
```
S0mething1Sc0ming
```
There are three hidden easter eggs.
They combine to form the passcode to open my encrypted vault.

# Clues (one for each egg):
```
1)
I ride with your session, not with your chest of files.
Open the little bag your shell carries when you arrive.
Talking about 
3)
The tree shows today; the rings remember yesterday.
Read the ledger’s older pages.
4)
When pixels sleep, their tails sometimes whisper plain words.
Listen to the tail.
```

# Login into eddi_kanpp 

Change to root
```
sudo su
```
Login into eddi_kanpp

```
login <username>

```
# 1. The first Clue
* First clue was found in `env`  inside user session in linux 
* type in `env` you will see frist password fragmaant PASSFRAG1=3ast3r
# 2. Second Clue
*  The second clue is found in hidden git directory
*  Firstly run `ls -a` to check hidden files
*  Secondly clue was given to to search git so `cd` indside .secret_git directory
*  Lasty with command `git show` show the private coments in wich you get -PASSFRAG2: -1s-
# 3. Last clue
* Last clue was hidden inside Pictures directory
* So firstly I `cd` inside Pictures
* Then again searched for hiddent suspictios files wich I found .easter_egg file
* and finally i `cat` the hidden file to find last clue PASSFRAG3: c0M1nG

# Decoding the password

New password for decryption is:
```
3ast3r-1s-c0M1nG
```
Decryption
* Inside the `cd` Documents directory find file mcskidy_note.txt.gpg
* Decrypt with this command
  ```
  gpg -d mcskidy_note.txt.gpg
  ```
* The `gpg` is used to unformat the file and the `-d` stands for --decryption
* After puttin in password  it gives the UNLOCK_KEY: 91J6X7R4FQ9TQPM9JX2Q9X2Z
* The command i past with output file had code url from website 
```
openssl enc -d -aes-256-cbc -pbkdf2 -iter 200000 -salt -base64 -in /tmp/website_output.txt -out /tmp/decoded_message.txt -pass pass:'91J6X7R4FQ9TQPM9JX2Q9X2Z'
cat /tmp/decoded_message.txt
```
Code from website 
```
U2FsdGVkX1/7xkS74RBSFMhpR9Pv0PZrzOVsIzd38sUGzGsDJOB9FbybAWod5HMsa+WIr5HDprvK6aFNYuOGoZ60qI7axX5Qnn1E6D+BPknRgktrZTbMqfJ7wnwCExyU8ek1RxohYBehaDyUWxSNAkARJtjVJEAOA1kEOUOah11iaPGKxrKRV0kVQKpEVnuZMbf0gv1ih421QvmGucErFhnuX+xv63drOTkYy15s9BVCUfKmjMLniusI0tqs236zv4LGbgrcOfgir+P+gWHc2TVW4CYszVXlAZUg07JlLLx1jkF85TIMjQ3B91MQS+btaH2WGWFyakmqYltz6jB5DOSCA6AMQYsqLlx53ORLxy3FfJhZTl9iwlrgEZjJZjDoXBBMdlMCOjKUZfTbt3pnlHWEaGJD7NoTgywFsIw5cz7hkmAMxAIkNn/5hGd/S7mwVp9h6GmBUYDsgHWpRxvnjh0s5kVD8TYjLzVnvaNFS4FXrQCiVIcp1ETqicXRjE4T0MYdnFD8h7og3ZlAFixM3nYpUYgKnqi2o2zJg7fEZ8c=
```
Answer
```
THM{w3lcome_2_A0c_2025}
```
Unziping the Spicy file extra content
```
root@tbfc-web01:/home/eddi_knapp/.secret$ gpg --out dir.tar.gz -d dir.tar.gz.gpg
gpg: AES256.CFB encrypted data
gpg: encrypted with 1 passphrase
root@tbfc-web01:/home/eddi_knapp/.secret$ ls
dir.tar.gz  dir.tar.gz.gpg
root@tbfc-web01:/home/eddi_knapp/.secret$ gunzip dir.tar.gz
root@tbfc-web01:/home/eddi_knapp/.secret$ ls
dir.tar  dir.tar.gz.gpg
root@tbfc-web01:/home/eddi_knapp/.secret$ tar -xf dir.tar
root@tbfc-web01:/home/eddi_knapp/.secret$ ls
dir  dir.tar  dir.tar.gz.gpg
root@tbfc-web01:/home/eddi_knapp/.secret$ cd dir
root@tbfc-web01:/home/eddi_knapp/.secret/dir$ ls
sq1.png
root@tbfc-web01:/home/eddi_knapp/.secret/dir$ sq1.png$
sq1.png$: command not found
root@tbfc-web01:/home/eddi_knapp/.secret/dir$ open sq1.png
root@tbfc-web01:/home/eddi_knapp/.secret/dir$ 
```
the image shows text `now_you_see_me`
