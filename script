import os
import time

def change_router_password(router_ip, admin_username, admin_password, new_password):
    # Example using `requests` to login to router and change password
    import requests

    # Log in to the router
    login_url = f"http://{router_ip}/login"
    payload = {'username': admin_username, 'password': admin_password}
    
    session = requests.Session()
    response = session.post(login_url, data=payload)
    
    if response.status_code == 200:
        print("[*] Logged in successfully!")
        
        # Navigate to change password page and update password
        password_url = f"http://{router_ip}/change_password"
        new_password_payload = {'new_password': new_password}
        
        change_response = session.post(password_url, data=new_password_payload)
        
        if change_response.status_code == 200:
            print(f"[*] Password successfully changed to: {new_password}")
        else:
            print("[!] Failed to change password.")
    else:
        print("[!] Login failed. Check credentials.")

def enable_wpa_encryption(router_ip, admin_username, admin_password):
    # Example command to enable WPA encryption via SSH (you can adjust based on router)
    print("[*] Enabling WPA2 encryption...")
    os.system(f"ssh {admin_username}@{router_ip} 'set encryption WPA2'")

def disable_wps(router_ip, admin_username, admin_password):
    # Example SSH command to disable WPS (Wi-Fi Protected Setup)
    print("[*] Disabling WPS...")
    os.system(f"ssh {admin_username}@{router_ip} 'disable wps'")

def setup_firewall(router_ip, admin_username, admin_password):
    # Example firewall setup to block unused ports (adjust as needed for your router model)
    print("[*] Setting up router firewall...")
    os.system(f"ssh {admin_username}@{router_ip} 'set firewall block_ports 80,443'")

def main():
    router_ip = "10.0.2.1"  # Replace with your router's IP address
    admin_username = "admin"  # Replace with your router's admin username
    admin_password = "admin"  # Replace with your router's admin password
    new_password = "NewSecurePassword123!"  # New strong password

    # Change the router password
    change_router_password(router_ip, admin_username, admin_password, new_password)

    # Enable WPA2 encryption
    enable_wpa_encryption(router_ip, admin_username, admin_password)

    # Disable WPS to enhance security
    disable_wps(router_ip, admin_username, admin_password)

    # Set up firewall to block unnecessary ports
    setup_firewall(router_ip, admin_username, admin_password)

    print("[*] Router protection settings have been updated.")

if __name__ == "__main__":
    main()
