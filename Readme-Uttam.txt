https://uttamduta.github.io/my-react-app

1.0 	npm install gh-pages --save-dev

2.0	https://github.com/uttamduta

3.0 	new repository name /uttamduta/my-react-app

4.0   	Reposity Access URL : git@github.com:uttamduta/my-react-app.git


---------------------------------------
Creage a repository on command line
echo "# my-react-app" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:uttamduta/my-react-app.git
git push -u origin main
----------------------------------------
…or push an existing repository from the command line

git remote add origin git@github.com:uttamduta/my-react-app.git
git branch -M main
git push -u origin main


SSH Key for Github created

Phrase  : Radha Krishna



You tube links to deploy a react applcation : 

https://www.youtube.com/watch?v=7wzuievFjrk

https://www.youtube.com/watch?v=hn1IkJk24ow

DeepSeek Information on creating SSH and sharing with Github :

The error `git@github.com: Permission denied (publickey)` indicates that Git is unable to authenticate with GitHub using your SSH key. This typically happens when:

1. **You don't have an SSH key configured**.
2. **Your SSH key is not added to your GitHub account**.
3. **The SSH key is not being used by Git**.

Here’s how to resolve this issue step by step:

---

### **Step 1: Check for Existing SSH Keys**

1. Open a terminal (or Git Bash on Windows).
2. Run the following command to check if you already have an SSH key:
   ```bash
   ls -al ~/.ssh
   ```
   Look for files named `id_rsa` and `id_rsa.pub` (or `id_ed25519` and `id_ed25519.pub`). These are your private and public SSH keys.

---

### **Step 2: Generate a New SSH Key (If You Don’t Have One)**

If you don’t have an SSH key, generate one:

1. Run the following command (replace `your_email@example.com` with your GitHub email):
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```
   - If your system doesn’t support `ed25519`, use:
     ```bash
     ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
     ```

2. When prompted to "Enter a file in which to save the key," press `Enter` to accept the default location.

3. When prompted to "Enter a passphrase," you can either:
   - Press `Enter` to leave it empty (not recommended for security reasons).
   - Enter a secure passphrase (recommended).   /*  Radha Krishna is the  Phrase */


4. The key will be generated and saved in `~/.ssh/id_ed25519` (or `~/.ssh/id_rsa`).

---

### **Step 3: Add the SSH Key to the SSH Agent**

1. Start the SSH agent in the background:
   ```bash
   eval "$(ssh-agent -s)"
   ```

2. Add your SSH private key to the SSH agent:
   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```
   If you used an RSA key, replace `id_ed25519` with `id_rsa`.

---

### **Step 4: Add the SSH Key to Your GitHub Account**

1. Copy the contents of your public key to the clipboard:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
   Or, for RSA:
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```

2. Go to your GitHub account:
   - Log in to GitHub.
   - Go to **Settings** > **SSH and GPG keys** > **New SSH key**.

3. Add the SSH key:
   - Give the key a title (e.g., "My Laptop").
   - Paste the copied public key into the "Key" field.
   - Click **Add SSH key**.

---

### **Step 5: Test the SSH Connection**

1. Test the connection to GitHub:
   ```bash
   ssh -T git@github.com
   ```

2. If successful, you’ll see a message like:
   ```
   Hi <your-username>! You've successfully authenticated, but GitHub does not provide shell access.
   ```

---

### **Step 6: Configure Git to Use SSH**

Ensure Git is using the SSH URL for GitHub repositories:

1. Clone the repository using the SSH URL:
   ```bash
   git clone git@github.com:username/repository.git
   ```

2. If you already cloned the repository using HTTPS, update the remote URL:
   ```bash
   git remote set-url origin git@github.com:username/repository.git
   ```

---

### **Step 7: Retry the Git Operation**

Now, try the Git operation again (e.g., `git pull`, `git push`, or `git clone`). It should work without the `Permission denied` error.

---

### **Troubleshooting**

1. **Check SSH Key Permissions**:
   - Ensure the `.ssh` directory and key files have the correct permissions:
     ```bash
     chmod 700 ~/.ssh
     chmod 600 ~/.ssh/id_ed25519
     chmod 644 ~/.ssh/id_ed25519.pub
     ```

2. **Verify SSH Key is Added to GitHub**:
   - Double-check that the public key is correctly added to your GitHub account.

3. **Restart the SSH Agent**:
   - If the SSH agent isn’t working, restart it:
     ```bash
     eval "$(ssh-agent -s)"
     ssh-add ~/.ssh/id_ed25519
     ```

4. **Check for Multiple SSH Keys**:
   - If you have multiple SSH keys, ensure the correct one is being used. You can specify the key in your SSH config:
     ```bash
     nano ~/.ssh/config
     ```
     Add the following:
     ```
     Host github.com
       IdentityFile ~/.ssh/id_ed25519
     ```

---

If you still encounter issues, let me know, and I can help you debug further!