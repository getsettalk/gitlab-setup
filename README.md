# Setting Up SSH for GitLab on Your PC

## Prerequisites
- Git installed on your system
- A GitLab account
- Terminal or Command Prompt access

---

## Step 1: Check for an Existing SSH Key
Before generating a new SSH key, check if you already have one:

```sh
ls ~/.ssh/id_rsa.pub
```

If the file exists, you can use it. If not, proceed to generate a new key.

---

## Step 2: Generate a New SSH Key
If you don’t have an SSH key, generate one using the following command:

```sh
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
```

- When prompted to "Enter a file in which to save the key," press **Enter** to use the default location (`~/.ssh/id_rsa`).
- Optionally, set a **passphrase** for added security.

---

## Step 3: Add the SSH Key to the SSH Agent
Start the SSH agent and add your key:

```sh
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

---

## Step 4: Copy the SSH Key
Copy the generated SSH key to your clipboard:

```sh
cat ~/.ssh/id_rsa.pub
```

For Windows users:
```sh
clip < ~/.ssh/id_rsa.pub
```

---

## Step 5: Add the SSH Key to GitLab
1. Log in to **GitLab**.
2. Go to **Preferences** (Click on your profile picture > **Edit Profile**).
3. Navigate to **SSH Keys**.
4. Paste your **SSH public key** into the "Key" field.
5. Add a **title** (e.g., "My PC SSH Key").
6. Click **Add key**.

---

## Step 6: Test the SSH Connection
Run the following command to test if the connection is successful:

```sh
ssh -T git@gitlab.com
```

If everything is set up correctly, you should see:

```

### Conclusion
Setting up SSH for GitLab makes working with repositories more efficient and secure. Follow these steps, and you'll never have to type your password for Git operations again!

Happy coding! 🚀

