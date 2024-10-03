# Networking in GCP and Azure - IPs and Domain Management

## Overview 

This project explores the networking features in Google Cloud Platform (GCP) and Azure, focusing on setting up a Virtual Private Cloud (VPC), mapping a custom domain to the IP, deploying a Flask web application, and configuring firewall settings to allow public access.

## Steps Performed

###  Networking in GCP - IPs and Domain Management

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


###  Networking in Azure - IPs and Domain Management

### 1. Set up Azure VM:
-A new VM was created in Azure with the required configurations to host the Flask web application.
-SSH access was configured, and I successfully connected to the VM.
![Screenshot 2024-10-03 161412](https://github.com/user-attachments/assets/996b8e11-154f-46cc-bff6-bbf8ff104ced)

### 2. DNS Configuration
- Acquired a domain via GitHub Student Pack (Namecheap).
- Configured DNS settings to map the static IP to the custom domain `shvsharma.me` and a subdomain `app.shvsharma.me`.
  - Added **A Record** for the root domain (`shvsharma.me`) pointing to the reserved static IP.
  - Added **A Record** for the subdomain (`app.shvsharma.me`) pointing to the same IP.

![Screenshot 2024-10-03 165817](https://github.com/user-attachments/assets/a5c3ee74-24fa-4da1-b359-eedf369b4110)

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
![Screenshot 2024-10-03 163633](https://github.com/user-attachments/assets/648b5b2f-3741-4ce4-97b7-7eb53328c53d)

![Screenshot 2024-10-03 163841](https://github.com/user-attachments/assets/d3afafe5-c1c1-4487-ba10-9540f637a345)

![Screenshot 2024-10-03 164458](https://github.com/user-attachments/assets/15d5eba2-6b7a-47d2-8e0c-62542529dfaa)

### 4. Configured Firewall Rules
-Configured GCP firewall rules to allow inbound traffic on port 5007 for the Flask application.

![Screenshot 2024-10-03 164706](https://github.com/user-attachments/assets/b8a7d5c1-e1f5-4244-aaad-238d720445bc)


### 5. Accessing the Application
-Accessed the running Flask application via the custom domain: http://flask.Shvsharma.me:5007

![Screenshot 2024-10-03 165024](https://github.com/user-attachments/assets/6e113089-3036-442c-bc3b-c452fdfbd367)


### Conclusion
In this project, I successfully:

-Set up a VPC and reserved a static IP in GCP and Azure.

-Mapped a custom domain to the static IP.

-Deployed a Flask web application accessible via the custom domain.

-Configured firewall settings to allow public traffic on the required port.
