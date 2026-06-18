# AWS Load Balancer Demo

## Project Overview

This project demonstrates how an AWS Application Load Balancer (ALB) distributes incoming traffic across multiple EC2 instances.

Each EC2 instance hosts the same web application with a unique identifier (Instance 1, Instance 2, Instance 3, or Instance 4). When users access the Load Balancer URL and refresh the page, requests are routed to different instances.

## Features

- Application Load Balancer (ALB)
- Multiple EC2 Instances
- Health Checks
- High Availability
- Traffic Distribution
- Apache Web Server

## Technologies Used

- AWS EC2
- AWS Application Load Balancer
- AWS Target Groups
- Amazon Linux 2023
- Apache HTTP Server
- HTML
- CSS

## Architecture

```text
                User
                  |
                  v
    Application Load Balancer
                  |
                  v
    +---------+---------+---------+---------+
    |Instance1|Instance2|Instance3|Instance4|
    +---------+---------+---------+---------+
```
## How It Works

The Application Load Balancer receives incoming requests and forwards them to healthy EC2 instances registered in the target group. Refreshing the page may display a different instance, demonstrating load balancing.

## Learning Outcomes

- AWS EC2 Management
- Apache Web Server Configuration
- Load Balancer Setup
- Target Groups and Health Checks
- High Availability Concepts

## Author

Ayan Ahmed