# DevOps Task 1: Install Nginx using Jenkins FreeStyle Job

## Prerequisites
Ensure the following requirements are met before proceeding:

1. **Jenkins Installed**: Jenkins should be installed and running on your system.
2. **Jenkins Slave/Agent**: If you're using an Ubuntu VM as a Jenkins agent, make sure Jenkins can communicate with it.

## Procedure

### Step 1: Create a New Jenkins FreeStyle Project
1. Open **Jenkins** in your browser.
2. Click on **New Item**.
3. Enter a name for your project (e.g., `Install Nginx on Ubuntu`).
4. Select **Freestyle project**.
5. Click **OK**.

### Step 2: Configure the Project
- In the **General** tab, you can leave most of the defaults, but you can set a description if needed.

### Step 3: Add Build Steps
1. Scroll down to the **Build** section.
2. Click on **Add build step**.
3. Select **Execute shell**.

### Step 4: Write the Script for Nginx Installation
- In the **Command** text area, add the following script to install Nginx:
  
  ```sh
  sudo apt update
  sudo apt install -y nginx
  sudo systemctl enable nginx
  sudo systemctl start nginx
  ```

### Step 5: Verify Installation
After running the commands, check if Nginx is running using:
  
```sh
systemctl status nginx
```

- If it's **active and running**, then the installation was successful.

### Step 6: Check in Browser
1. Open your browser.
2. Go to `http://your-server-ip`.
3. You should see the **default Nginx welcome page**.

---
This confirms that Nginx has been successfully installed and is running on your Ubuntu server via Jenkins.
