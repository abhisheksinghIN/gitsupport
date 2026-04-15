## Introduction

Action	                 Command

Check Status	           git status

Stage Changes	           git add .

Commit	                 git commit -m "Your message"

Push to GitHub	         git push

Pull latest updates	     git pull


# Generate the SSH Key

- To connect your Linux machine to GitHub securely, you need to generate an SSH Key, add it to your local agent, and then paste the public part into your GitHub settings.

1. ssh-keygen -t ed25519 -C "your-email@example.com"

- When it says "Enter file in which to save the key," just press Enter (it will save to the default location).
  
- When it asks for a passphrase, you can either type a password for extra security or just press Enter twice for no password.



# Add the Key to the SSH Agent

This ensures Linux "remembers" your key so you don't have to re-enter your password constantly.

eval "$(ssh-agent -s)"

ssh-add ~/.ssh/id_ed25519

# Copy the Public Key

You need to copy the text of your key so you can give it to GitHub:

cat ~/.ssh/id_ed25519.pub

# Add the Key to GitHub

1. Go to GitHub.com and log in.

2. Click your profile photo (top right) > Settings > SSH and GPG keys.

3. Click the green New SSH key button.

4. Give it a Title (e.g., "Linux VM") and paste your key into the Key box.

5. Click Add SSH key.

# Test the Connection

Run this command to make sure it works:

ssh -T git@github.com


git --version

e.g.

git add Readme.md

git commit -m "Updated README"

git push
