# AWS Multi-AZ Web Infrastructure (Basic High Availability)

## 🏗 Architecture

This project demonstrates a basic AWS infrastructure setup using a custom VPC and networking components.

- Created a VPC with public subnets across multiple Availability Zones
- Configured an Internet Gateway to allow internet access
- Set up Route Tables for proper traffic routing
- Deployed an EC2 instance inside a public subnet

## ⚠️ Limitations

- The infrastructure currently uses a single EC2 instance, which creates a single point of failure.

## 🔄 Future Improvements

- Add multiple EC2 instances
- Use a Load Balancer
- Implement Auto Scaling

                🌐 Internet
                      │
              ┌────────────────┐
              │ Internet Gateway│
              └────────────────┘
                      │
              ┌────────────────┐
              │   Route Table   │
              └────────────────┘
                      │
        ┌─────────────┴─────────────┐
        │                           │
┌──────────────────┐      ┌──────────────────┐
│ public-subnet-1  │      │ public-subnet-2  │
│      (AZ-a)      │      │      (AZ-b)      │
│                  │      │                  │
│    🖥 EC2-1       │      │      (empty)     │
└──────────────────┘      └──────────────────┘

