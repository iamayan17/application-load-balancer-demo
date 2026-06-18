# Deployment Steps

## Step 1: Launch EC2 Instances

Launch 4 Amazon Linux 2023 EC2 instances.

Security Group:
- SSH (22)
- HTTP (80)

---

## Step 2: Install Apache

Connect to each EC2 instance and run:

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl enable httpd
sudo systemctl start httpd
```

---

## Step 3: Deploy Website

Create the webpage:

```bash
sudo nano /var/www/html/index.html
```

Paste the HTML code.

Change the instance label:

- Server 1 → INSTANCE 1
- Server 2 → INSTANCE 2
- Server 3 → INSTANCE 3
- Server 4 → INSTANCE 4

Save the file.

---

## Step 4: Verify Website

Open:

```bash
http://<EC2-Public-IP>
```

Confirm the page loads correctly.

---

## Step 5: Create Target Group

AWS Console → EC2 → Target Groups

- Create Target Group
- Target Type: Instances
- Protocol: HTTP
- Port: 80

Register all 4 EC2 instances.

---

## Step 6: Create Application Load Balancer

AWS Console → EC2 → Load Balancers

- Create Application Load Balancer
- Internet-facing
- HTTP Listener (Port 80)
- Select public subnets
- Attach the Target Group

---

## Step 7: Verify Health Checks

Go to:

Target Groups → Targets

Ensure all instances show:

Healthy

---

## Step 8: Test Load Balancer

Open:

```bash
http://<Load-Balancer-DNS>
```

Refresh multiple times.

Expected Output:

- INSTANCE 1
- INSTANCE 2
- INSTANCE 3
- INSTANCE 4

The displayed instance changes as requests are distributed across servers.

---

## Step 9: Cleanup

To avoid AWS charges:

- Delete Load Balancer
- Delete Target Group
- Release Elastic IPs (if used)
- Terminate EC2 Instances