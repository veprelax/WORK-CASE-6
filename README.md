### Виконала самостійно Слобожан Софія РПЗ-23А

# WORK-CASE-6

# Task 1: Installing Additional Shells

![image](https://github.com/user-attachments/assets/0f11fe56-71ce-4cee-ba7b-c2c811160bb5)


#  Description of Shells:
### Bash (Bourne Again Shell):

Default shell in most Linux distributions.

Supports scripting, job control, command history, and command-line editing.

### Zsh (Z Shell):

Highly customizable with plugins (e.g., Oh My Zsh).

Offers advanced features like improved globbing, spelling correction, and theming.

Fish (Friendly Interactive Shell):

User-friendly with autosuggestions and syntax highlighting out of the box.

Does not use bash-compatible scripting syntax but is very intuitive for new users.
To begin, we installed two additional command-line interpreters besides the default Bash shell. We chose Zsh (Z Shell) and Fish (Friendly Interactive Shell). These shells were installed through the package manager available in the Linux system. After installation, we verified that both shells were working properly by checking their versions and launching them.

###  To allow users to use different shells based on their role or preference, and to demonstrate the flexibility of the Linux shell environment.

# Task 2: Creating Users and Groups
### Commands Used:
# Create groups
for group in techsupport developers financiers founders guests; do
    sudo groupadd $group
done

# Add users with group and shell
sudo useradd -m -s /bin/bash -G techsupport tech1
sudo useradd -m -s /bin/bash -G techsupport tech2

sudo useradd -m -s /usr/bin/zsh -G developers dev1
sudo useradd -m -s /usr/bin/zsh -G developers dev2

sudo useradd -m -s /usr/sbin/nologin -G financiers fin1
sudo useradd -m -s /usr/sbin/nologin -G financiers fin2

sudo useradd -m -s /usr/bin/fish -G founders ceo1
sudo useradd -m -s /usr/bin/fish -G founders ceo2

sudo useradd -m -s /usr/sbin/nologin -G guests guest1
sudo useradd -m -s /usr/sbin/nologin -G guests guest2
 
![image](https://github.com/user-attachments/assets/0f8bede4-cff8-4324-b313-e6cd9425870e)

### To manage permissions and shell access per role by organizing users into logical groups

Next, we created five user groups to reflect different roles within an organization: technical support, developers, financiers, founders, and guests. A total of ten new user accounts were created and assigned to these groups. Each group represents a type of user with specific responsibilities and access needs.

# Task 3: Assigning Default Shells
User Group	Default Shell
Tech Support	/bin/bash
Developers	/usr/bin/zsh
Financiers	/usr/sbin/nologin (Access Denied)
Founders	/usr/bin/fish
Guests	/usr/sbin/nologin (Access Denied)

![image](https://github.com/user-attachments/assets/bd60c555-4b8a-4b4a-964d-01ad12312223)

# Explanation:
nologin shell prevents users from logging into the system interactively.

Each user was created with a specific shell to meet the role requirements.

### To define which command interpreter (shell) is used by default for each user depending on their group/role.

### Shell assignments:

techsupport → /bin/bash (default Bash shell)

developers → /usr/bin/zsh (Zsh shell)

financiers → /usr/sbin/nologin (access denied — shell disabled)

founders → /usr/bin/fish (Fish shell)

guests → /usr/sbin/nologin (access denied — shell disabled)

### To enforce security and usability policies. For example:

Prevent shell access to finance and guest users.

Provide powerful developer-oriented shells to programmers.

### Based on each group’s purpose, we assigned appropriate default shells to users:

Technical support users were assigned the Bash shell.

Developers were assigned the Zsh shell.

Founders were given access to the Fish shell.

Financiers and guests were restricted from accessing any shell by setting their accounts to use a non-interactive shell that blocks login access.

This setup ensured that only technical roles had access to interactive shell environments, while non-technical roles were restricted for security.

# Task 4: Demonstration of User Capabilities
Example Commands Executed by Group Members:
### Tech Support (tech1, tech2) using bash:

uname -a            # Display system info
df -h               # Disk space usage
whoami              # Current user
pwd                 # Print working directory

###  Developers (dev1, dev2) using zsh:
neofetch            # Display system information (if installed)
ls -la              # List files
echo "Dev user active"

### Founders (ceo1, ceo2) using fish:

date                # Show system date
hostname            # Show machine hostname
pwd                 # Current directory

### Financiers & Guests (nologin):
These users are restricted from logging in. Any login attempt will result in:
This account is currently not available.

![image](https://github.com/user-attachments/assets/25afb0f2-847a-426b-8971-9cfa5fe604a6)

Finally, we tested the setup by logging into the accounts of users with shell access. We performed basic system operations such as checking the current user, viewing the working directory, displaying the system date, and checking system uptime. These actions verified that each user’s shell and permissions worked as intended. For users with restricted shells, login attempts were blocked as expected.
# Conclusion 
### In this lab, multiple command-line interpreters (Zsh and Fish) were installed, user groups were created to simulate organizational roles, and users were assigned default shells based on their roles. Appropriate shell access was configured to enhance usability and security, and basic system commands were successfully executed by authorized users, confirming correct setup.
