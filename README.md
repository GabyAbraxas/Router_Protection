
instructions for using the router protection script:

Steps:
Install Dependencies:

Install the requests library:
bash
Copy code
pip install requests
Save the Script:

Open a text editor and save the script as router_protection.py.
Modify the Script:

Update the script with your router’s IP, admin username, admin password, and a new secure password.
Example:

python
Copy code
router_ip = "10.0.2.1"  # Your router IP
admin_username = "admin"   # Your router admin username
admin_password = "admin"   # Your router admin password
new_password = "NewPassword123!"  # Your new strong password
Run the Script:

Execute the script:
bash
Copy code
python3 router_protection.py
Verify Changes:

Log into your router’s web interface to ensure the new password is set, WPA encryption is enabled, and WPS is disabled.

Important: This script is for educational purposes and should only be used on networks you own or have permission to access!


