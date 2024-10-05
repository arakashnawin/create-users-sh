---

# User Management Script

## Overview

This bash script automates the process of user management on a Linux system. It allows for creating users, assigning them to groups, generating secure passwords, and logging all actions to a file. The script is ideal for system administrators who need to manage multiple users efficiently.

## Features

- **User Creation**: Automatically creates users based on the input file.
- **Group Management**: Assigns users to specified groups or creates groups if they don't exist.
- **Password Generation**: Generates secure, random passwords using OpenSSL.
- **Logging**: Maintains a log of all actions performed, including user and group creation, in `/var/log/user_management.log`.
- **Password Storage**: Saves the generated usernames and passwords in a secure file at `/var/secure/user_passwords.csv`.

## Prerequisites

- Ensure you have root or `sudo` privileges to execute the script.
- Install OpenSSL for password generation: 
  ```bash
  sudo apt-get install openssl
  ```

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/user-management-script.git
   cd user-management-script
   ```

2. Make the script executable:
   ```bash
   chmod +x user_management.sh
   ```

3. Prepare an input file with the list of users and groups in the following format:
   ```
   username1;group1,group2
   username2;group3
   ```
   - **username**: The user's name.
   - **group**: Groups the user should belong to (separated by commas if multiple).

4. Run the script with the input file:
   ```bash
   sudo ./user_management.sh <input_file>
   ```

## Logs

- The script logs all actions in `/var/log/user_management.log`.
- Generated usernames and passwords are securely saved in `/var/secure/user_passwords.csv`.

## Example

Input file (`users.txt`):
```
john;admins,developers
jane;designers
```

Command:
```bash
sudo ./user_management.sh users.txt
```

## Error Handling

- If the script is not run with root privileges, it will prompt for proper execution.
- The script checks for the existence of the input file and user groups before proceeding.

## Author

**Akash Nawin**  
GitHub: [https://github.com/arakashnawin](https://github.com/arakashnawin)

---
