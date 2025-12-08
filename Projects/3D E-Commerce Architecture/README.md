3D E-Commerce Platform Architecture on AWS

This project showcases a full cloud architecture design for a 3D e-commerce web application.
The platform allows users to view and interact with 3D product models (like furniture, gadgets, and fashion items) before buying.

The main goal of this project is to design an architecture that is:
1. Highly Available
2. Scalable
3. Fast and responsive
4. Secure
5. Cost-efficient

The Team:
 Kwanele
 Neo
 Madimetja
 Leah
 Keketso

This is part of my learning journey through the AWS Cloud Practitioner path.


---

🖼 Project Files Included

This folder contains:
Word Document (Full project explanation)
README (You’re reading it now!)


---

📄 Project Files

📘 View the PDF (Recommended – Opens directly on GitHub)

👉 Click here to open the PDF

📝 Download the Word Document (Editable version)

👉 Click here to download the Word file

🖼 Architecture Diagrams

Option 4 Architecture Diagram


---

🏗 What This Architecture Includes

This design uses several managed AWS services:

Amazon S3 → Stores 3D models, textures, and static assets

Amazon CloudFront → Speeds up delivery for global users

Route 53 → Domain and traffic routing

Elastic Load Balancer (ELB) → Distributes traffic to backend servers

EC2 / AWS Lambda → Runs the backend logic

Amazon RDS (Aurora) → Stores customer accounts & orders

Amazon DynamoDB → Stores fast product catalog lookups

CloudWatch → Monitoring & logging

Trusted Advisor → Helps with cost, performance, and security optimization


---

📝 Project Summary

This architecture is designed to handle millions of users globally, with:

 -Smooth 3D rendering
 -Low latency
 -High availability
 -Automatic scaling up and down
 -Strong security best practices
 -Optimized costs