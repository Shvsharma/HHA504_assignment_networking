# Networking in GCP - IPs and Domain Management

## Overview 

This project explores the networking features in Google Cloud Platform (GCP), focusing on setting up a Virtual Private Cloud (VPC), mapping a custom domain to the IP, deploying a Flask web application, and configuring firewall settings to allow public access.

## Steps Performed

### 1. VPC Creation in GCP

![Screenshot 2024-09-30 110903](https://github.com/user-attachments/assets/883e6bff-a303-43d5-8298-d150e0c04bd7)


### 2. DNS Configuration
- Acquired a domain via GitHub Student Pack (Namecheap).
- Configured DNS settings to map the static IP to the custom domain `shvsharma.me` and a subdomain `app.shvsharma.me`.
  - Added **A Record** for the root domain (`shvsharma.me`) pointing to the reserved static IP.
  - Added **A Record** for the subdomain (`app.shvsharma.me`) pointing to the same IP.

![Screenshot 2024-09-30 135844](https://github.com/user-attachments/assets/485e29fa-e851-498a-90d9-137b0ba50d4b)


### 3. Created and Deployed Flask Application
- Deployed a Flask application on the GCP VM and ran it on port 5007.
- Flask code example:
  ```python
  from flask import Flask
  app = Flask(__name__)

  @app.route('/')
  def home():
      return "Hello from Flask app on GCP!"

  if __name__ == '__main__':
      app.run(host='0.0.0.0', port=5007)

### 4. Configured Firewall Rules
-Configured GCP firewall rules to allow inbound traffic on port 5007 for the Flask application.

![Screenshot 2024-09-30 115351](https://github.com/user-attachments/assets/c3958a3c-e925-40fe-bd70-0de5857fe671)


### 5. SSH into the VM
-Used SSH to connect to the VM and deploy the Flask application.

### 6. Accessing the Application
-Accessed the running Flask application via the custom domain: http://app.shvsharma.me:5007.

![Screenshot 2024-09-30 135900](https://github.com/user-attachments/assets/617859f2-280a-49d1-b4a4-a0b469b0ef1c)


### Conclusion
In this project, we successfully:

-Set up a VPC and reserved a static IP in GCP.
-Mapped a custom domain to the static IP.
-Deployed a Flask web application accessible via the custom domain.
-Configured firewall settings to allow public traffic on the required port.



### Networking in Azure - IPs and Domain Management
Set up Azure VM:
-A new VM was created in Azure with the required configurations to host the Flask web application.
-SSH access was configured, and I successfully connected to the VM.
![Screenshot 2024-09-30 161728](https://github.com/user-attachments/assets/0df78159-8905-426f-88d3-ed0a3131affb)
![Screenshot 2024-09-30 161851](https://github.com/user-attachments/assets/43bc9119-4838-4ba8-8709-32a16e2ddb7d)


### Issues Encountered:
Sudo Restrictions:
-When attempting to run commands with sudo, I encountered the following error:
-The "no new privileges" flag is set, which prevents sudo from running as root.

Attempting to install Python packages using pip3 without sudo resulted in warnings such as:
error: externally-managed-environment
WARNING: Package(s) not found: Flask

Tried to Install Flask with --break-system-packages Flag

I attempted to force the installation of Flask by using the --break-system-packages flag as recommended in the error message: pip3 install Flask --break-system-packages
However, this did not resolve the issue, and I was still unable to install Flask on the Azure VM.

### Possible Cause of Issues:
The most likely cause of these issues is that I was working within a restricted containerized environment.

![Screenshot 2024-09-30 161646](https://github.com/user-attachments/assets/0d3dc06d-8445-475c-9470-d266ebe78108)
