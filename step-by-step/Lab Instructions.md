**Step-by-Step Lab Instructions**

**Step 1: Set Up the Ubuntu Virtual Machine**
- Open Oracle VirtualBox on the Windows PC.
- Start the Ubuntu Linux virtual machine.
- Log in to Ubuntu.
- Open the Terminal application.

**Step 2: Create the Lab Directory**

Created a directory to store the files used for the Linux administration lab.

cd ~
mkdir linux-admin-lab
cd linux-admin-lab

**Step 3: Create the Company Directories**

Made directories to represent different departments within a company.

sudo mkdir -p company/{IT,HR,Finance}

Verified that the directories were created:

ls -l company

**Step 4: Create Linux Groups**

Made a separate Linux group for each department.

sudo groupadd itteam
sudo groupadd hrteam
sudo groupadd financeteam

Confirmed the groups:

getent group itteam hrteam financeteam

**Step 5: Create Linux Users**

Made three users to represent employees in the different departments.

sudo useradd -m -s /bin/bash ituser
sudo useradd -m -s /bin/bash hruser
sudo useradd -m -s /bin/bash financeuser

Created passwords for each user:

sudo passwd ituser
sudo passwd hruser
sudo passwd financeuser

**Step 6: Add Users to Their Groups**

Assigned each user to the appropriate department group.

sudo usermod -aG itteam ituser
sudo usermod -aG hrteam hruser
sudo usermod -aG financeteam financeuser

Confirmed the group memberships:

id ituser
id hruser
id financeuser

**Step 7: Create Department Files**

Created files for each department.

sudo touch company/IT/network.txt
sudo touch company/HR/employees.txt
sudo touch company/Finance/budget.txt

Added basic information to each file:

echo "Network configuration and IT notes" | sudo tee company/IT/network.txt
echo "Employee information" | sudo tee company/HR/employees.txt
echo "Company budget information" | sudo tee company/Finance/budget.txt

Verified the files:

find company -type f

**Step 8: Configure File Ownership**

Assigned each file to the appropriate user and group.

sudo chown ituser:itteam company/IT/network.txt
sudo chown hruser:hrteam company/HR/employees.txt
sudo chown financeuser:financeteam company/Finance/budget.txt

Verified the ownership:

ls -l company/IT
ls -l company/HR
ls -l company/Finance

**Step 9: Configure File Permissions**

Configured the files so the owner could read and write, the group could read, and other users would have no access.

sudo chmod 640 company/IT/network.txt
sudo chmod 640 company/HR/employees.txt
sudo chmod 640 company/Finance/budget.txt

Verified the permissions:

ls -l company/*/*

**Step 10: Practice Package Management**

Updated the Ubuntu package list:

sudo apt update

Installed the **tree** package:

sudo apt install tree

Used **tree** to display the project directory structure:

tree company

**Step 11: Practice System Administration Commands**

Used several Linux commands to view system information:

whoami
hostname
df -h
free -h
ip addr

**Step 12: Document the Lab**

I captured screenshots of the completed tasks, including:
- Directory structure
- Linux users and groups
- Group memberships
- File ownership
- File permissions
- Package installation
- System information
