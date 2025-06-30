To **add an SSH key to your GitHub repo access**, you need to go through **two steps**:

---

## ✅ Step 1: Generate SSH Key (if not done yet)

Open Git Bash or Terminal:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

When prompted:

* **File location**: Press `Enter` to accept the default.
* **Passphrase** (optional): Enter or skip.

Then, run:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

---

## ✅ Step 2: Add SSH Key to GitHub

1. Copy the SSH key to clipboard:

```bash
cat ~/.ssh/id_ed25519.pub
```

> Or use:

```bash
clip < ~/.ssh/id_ed25519.pub     # On Git Bash/Windows
```

2. Go to [GitHub SSH keys page](https://github.com/settings/keys).

3. Click **"New SSH key"**:

   * **Title**: Name your device.
   * **Key**: Paste the public key from above.
   * Click **Add SSH key**.

---

## ✅ Step 3: Use SSH Instead of HTTPS for Git

Make sure your remote is set to SSH:

```bash
git remote set-url origin git@github.com:USERNAME/REPO.git
```

Check with:

```bash
git remote -v
```

---

## ✅ Step 4: Test Your Connection

```bash
ssh -T git@github.com
```

You should see:

```
Hi USERNAME! You've successfully authenticated...
```

---

Let me know if you're using GitLab, Bitbucket, or Azure DevOps instead — steps are slightly different.
