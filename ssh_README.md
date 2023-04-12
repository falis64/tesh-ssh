# Creating and using SSH with github

# 1 : Setting up SSH folder and creating private/public keys


- In order to save our keys, we make a folder called.ssh. We are able to construct this directory, which we will call .ssh, using the mkdir function. The current directory is explored using ls, and the desired directory is reached by using cd and the directory name. Here, we use cd.ssh.
- Now run the command ssh-keygen -t - rsa -b 4096 -C "your email address". This will generate a new SSH key pair both public and private on your computer.
- You will be prompted to enter a file name for your SSH key where you can enter a custom name, we used firstname-github-key and then pressing enter.
- Next, you will be asked to enter a passphrase for your SSH key. This passphrase will be used to encrypt your private key, so make sure it's a strong and secure one. You can also leave it blank if you prefer like we did.
- Once your SSH key pair is generated, you can view your public key by running the command cat firstname-github-key.pub. We use .pub because 2 keys are generated sice the las step.
- Copy the contents of the public key to your clipboard.

Step 2: Adding your public SSH key to your GitHub account

Log in to your GitHub account and go to the "Settings" page.
![img_3.png](img_3.png)
Click on "SSH and GPG keys" in the sidebar.
![img_2.png](img_2.png)
Click on the "New SSH key" button.
![img_4.png](img_4.png)
Give your key a descriptive title and paste your public key into the "Key" field.
![img_5.png](img_5.png)
Click the "Add SSH key" button to save your key to your GitHub account
![img_6.png](img_6.png)

# Step 3: Adding your private key to github
We need to store our key in a way that isn't accessible without our permission. To do this:
- Type eval 'ssh-add name-github-key'
To check if this was successfull; use ssh -T github@githu.com and you should see a messaging ending with:
```
Hi 'name'! You've successfully authenticated, but GitHub does not provide shell access."
```

Step 4: Pushing files to GitHub using SSH
Go to GitHub and make a new repository or rename an old one
Don't forget to select SSH
