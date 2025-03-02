To install Docker on **Ubuntu**, follow these steps:

---

### **Step 1: Update Packages**
```bash
sudo apt update
sudo apt install -y ca-certificates curl gnupg
```

---

### **Step 2: Add Docker Repository**
```bash
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo tee /etc/apt/keyrings/docker.asc > /dev/null
sudo chmod a+r /etc/apt/keyrings/docker.asc
```
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

### **Step 3: Install Docker**
```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---

### **Step 4: Verify Installation**
Check if Docker is installed and running:
```bash
docker --version
sudo systemctl status docker
```

---

### **Step 5: Run Docker Without `sudo` (Optional)**
To use Docker without `sudo`, add your user to the Docker group:
```bash
sudo usermod -aG docker $USER
newgrp docker
```

---

### **Step 6: Test Docker**
Run a test container:
```bash
docker run hello-world
```

---

It looks like the Docker repository might not be properly added or recognized. Let's troubleshoot and fix this step-by-step.  

---

### **🔹 Step 1: Remove Old Docker Packages (if any)**
Run the following to remove any existing Docker installation:
```bash
sudo apt remove docker docker-engine docker.io containerd runc
```

---

### **🔹 Step 2: Update Package List**
Ensure your package list is updated:
```bash
sudo apt update && sudo apt upgrade -y
```

---

### **🔹 Step 3: Verify Repository Setup**
Check if the Docker repository is correctly added:
```bash
cat /etc/apt/sources.list.d/docker.list
```
Expected output:
```
deb [arch=amd64 signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable
```
If the file is missing, re-run the repository setup commands:
```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo tee /etc/apt/keyrings/docker.asc > /dev/null
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

### **🔹 Step 4: Update & Install Docker**
Now, update and install Docker again:
```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---

### **🔹 Step 5: Check if Docker Installed Correctly**
```bash
docker --version
sudo systemctl status docker
```

---

#### **✅ Alternative Fix (If Still Not Working)**
If you're using an **older Ubuntu version**, replace `$(lsb_release -cs)` with a supported release like `jammy` (22.04) or `focal` (20.04):
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu jammy stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
Then, retry:
```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---

Let me know if you still face issues! 🚀