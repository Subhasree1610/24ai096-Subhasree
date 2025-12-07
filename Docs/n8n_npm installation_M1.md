n8n: npm Installation Method

1. Open the terminal on your server.

This is where you will type all commands.
Make sure you have permission to install software.

2. Update your system first.

Type: apt update
This makes sure your system has the latest package info.

3. Install curl (a simple tool we need).

Type: apt install curl
This helps us download the Node installer.

4. Install nvm (tool used to install Node & npm).

Type the nvm install command given earlier.
This will add nvm to your system automatically.

5. Reload your terminal settings.

Type: source ~/.bashrc
This makes the nvm command start working instantly.

6. Install Node (this will also install npm).

Type: nvm install --lts
This installs the stable version of Node + npm.

7. Check if Node and npm installed correctly.

Type: node -v and npm -v
You should see version numbers on the screen.

8. Create a folder for n8n.

Type: mkdir n8n && cd n8n
We do this to keep all files in one place.

9. Install n8n globally on your system.

Type: npm install -g n8n
Wait for it to finish — this may take some time.

10. Start n8n to test everything.

Type: n8n
If it opens in browser, npm is installed and working.
