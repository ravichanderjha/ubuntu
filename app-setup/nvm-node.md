To install **NVM (Node Version Manager)** and then install **Node.js 18** on Ubuntu, follow these steps:

### Step 1: Install NVM

1. **Install NVM** using the command below:
   Open your terminal and run this command to download and install NVM:

   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
   ```

   > This will install the latest version of NVM. At the time of writing, `v0.39.3` is the latest version, but you can check for updates in the [official NVM repository](https://github.com/nvm-sh/nvm).

2. **Activate NVM** by either closing and reopening your terminal or running this command:

   ```bash
   source ~/.bashrc
   ```

   If you're using a different shell (like `zsh`), the profile file might be `~/.zshrc` instead.

3. **Verify that NVM was installed correctly**:

   ```bash
   command -v nvm
   ```

   This should output `nvm`, confirming that it's installed.

### Step 2: Install Node.js 18 using NVM

1. **Install Node.js 18**:

   Now that you have NVM installed, you can install **Node.js 18** with the following command:

   ```bash
   nvm install 18
   ```

   This will download and install the latest **Node.js 18** version. NVM will automatically set it as the default version.

2. **Verify Node.js and npm installation**:

   Once Node.js 18 is installed, verify that both **Node.js** and **npm** (Node package manager) were installed correctly:

   ```bash
   node -v
   npm -v
   ```

   This should show the installed versions of Node.js and npm. You should see something like:

   ```bash
   v18.x.x   # Node.js version
   8.x.x     # npm version
   ```

### Step 3: Set Node.js 18 as the default version (if needed)

If you have multiple versions of Node.js installed via NVM and want to set Node.js 18 as the default version, run:

```bash
nvm use 18
nvm alias default 18
```

This will ensure that Node.js 18 is used as the default version every time you open a terminal.

---

Now you're all set up with **Node.js 18** using **NVM**! Let me know if you need further help.