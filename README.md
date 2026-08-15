# Linux-System-Administration-User-Management-Lab

For this project, I created and configured a Linux environment using Ubuntu in Oracle VirtualBox. The lab focused on creating and managing users, groups, directories, and files while configuring file ownership and permissions. The purpose of this project was to practice basic Linux system administration, command-line operations, package management, and system information commands.

**Devices/Tools Used**
- Oracle VirtualBox — Used to create and run the virtual machine where the Linux lab was completed.
- Ubuntu Linux — Used as the operating system for practicing Linux administration and command-line tasks.
- Windows PC — Used as the host computer to run Oracle VirtualBox and access the Ubuntu virtual machine.
- Ubuntu Terminal — Used to create users, groups, directories, and files and to configure permissions and manage packages.

**Step-by-Step Lab Instructions**

**Step 1: Set Up the Ubuntu Virtual Machine**
- Open Oracle VirtualBox on the Windows PC.
- Start the Ubuntu Linux virtual machine.
- Log in to Ubuntu.
- Open the Terminal application.

**Step 2: Create the Lab Directory**

I created a directory to store the files used for the Linux administration lab.

cd ~
mkdir linux-admin-lab
cd linux-admin-lab

**Step 3: Create the Company Directories**

I created directories to represent different departments within a company.

sudo mkdir -p company/{IT,HR,Finance}

I verified that the directories were created:
ls -l company

**Step 4: Create Linux Groups**

I created a separate Linux group for each department.

sudo groupadd itteam
sudo groupadd hrteam
sudo groupadd financeteam

I verified the groups:

getent group itteam hrteam financeteam

**Step 5: Create Linux Users**

I created three users to represent employees in the different departments.

sudo useradd -m -s /bin/bash ituser
sudo useradd -m -s /bin/bash hruser
sudo useradd -m -s /bin/bash financeuser

I created passwords for each user:

sudo passwd ituser
sudo passwd hruser
sudo passwd financeuser

**Step 6: Add Users to Their Groups**

I assigned each user to the appropriate department group.

sudo usermod -aG itteam ituser
sudo usermod -aG hrteam hruser
sudo usermod -aG financeteam financeuser

I verified the group memberships:

id ituser
id hruser
id financeuser

**Step 7: Create Department Files**

I created files for each department.

sudo touch company/IT/network.txt
sudo touch company/HR/employees.txt
sudo touch company/Finance/budget.txt

I added basic information to each file:

echo "Network configuration and IT notes" | sudo tee company/IT/network.txt
echo "Employee information" | sudo tee company/HR/employees.txt
echo "Company budget information" | sudo tee company/Finance/budget.txt

I verified the files:

find company -type f

**Step 8: Configure File Ownership**

I assigned each file to the appropriate user and group.

sudo chown ituser:itteam company/IT/network.txt
sudo chown hruser:hrteam company/HR/employees.txt
sudo chown financeuser:financeteam company/Finance/budget.txt

I verified the ownership:

ls -l company/IT
ls -l company/HR
ls -l company/Finance

**Step 9: Configure File Permissions**

I configured the files so the owner could read and write, the group could read, and other users would have no access.

sudo chmod 640 company/IT/network.txt
sudo chmod 640 company/HR/employees.txt
sudo chmod 640 company/Finance/budget.txt

I verified the permissions:

ls -l company/*/*

**Step 10: Practice Package Management**

I updated the Ubuntu package list:

sudo apt update

I installed the **tree** package:

sudo apt install tree

I used **tree** to display the project directory structure:

tree company

**Step 11: Practice System Administration Commands**

I used several Linux commands to view system information:

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

**Skills Demonstrated**
- Linux system administration
- Ubuntu Linux command-line operations
- User and group management
- File and directory management
- File ownership and permissions
- chmod and chown commands
- Package management using apt
- System information and monitoring
- Virtual machine management using Oracle VirtualBox
- Basic Linux troubleshooting
- Technical documentation and project organization
- GitHub project documentation

Created By: Zakhena K. Shorter | Linux-System_Administration-User-Management
