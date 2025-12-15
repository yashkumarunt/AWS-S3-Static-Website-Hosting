**🌐 AWS S3 Static Website Hosting**
**Overview**

This project demonstrates how to host a static website on Amazon S3 using native AWS services.
The goal was to understand public access control, bucket policies, and static website configuration—core fundamentals for Cloud and DevOps roles.

This setup is commonly used for:
* Portfolio websites
* Landing pages
* Documentation sites

**Problem Statement**
Hosting a static website traditionally requires servers, maintenance, and cost overhead.
For simple websites, this is unnecessary.
Amazon S3 provides a serverless, scalable, and low-cost solution for static content hosting.

**Solution**
Used Amazon S3 to host HTML and image files
Configured static website hosting
Managed public access securely via bucket policy
Verified accessibility using AWS website endpoint

**Architecture**

Simple flow:

* User accesses S3 website endpoint
* S3 serves static HTML and image files
* Access is controlled via bucket policy (read-only)
(Architecture is intentionally simple for clarity and cost efficiency)

**Tech Stack**

Cloud Provider: AWS
Service: Amazon S3
Region: us-east-1 (N. Virginia)\
Website Type: Static (HTML, Images)
Access Control: Bucket Policy (Public Read)

## 🚀 Steps Performed

**Implementation Steps**
**1️⃣ Create S3 Bucket**

* Created an S3 bucket:
* yash-portfolio-hostingstaticwebsite
* Region: us-east-1

![01 – Bucket created](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/01-bucket-created.png)

---

**2️⃣ Upload Website Files**

Uploaded:
final.html
profile_face.jpg

![02 – Uploaded files](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/02-uploaded-files.png)

---

**3️⃣ Configure Public Access**

Disabled Block all public access
Allowed public object reads (required for website hosting)

![03 – Block public access](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/03-block-public-access.png)

---
**4️⃣ Enable Static Website Hosting**

* Enabled static website hosting under bucket properties
* Set index document to: final.html

![04 – Static hosting enabled](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/04-static-hosting-enabled.png)

---

**5️⃣ Apply Bucket Policy**

Applied a bucket policy to allow public read-only access to objects:

![05 – Bucket policy](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/05%20Bucket%20Policy.png)

**6️⃣ Retrieve Website Endpoint**

Retrieved website endpoint URL from S3 properties

![06 – Website endpoint URL](https://raw.githubusercontent.com/yashkumarunt/AWS-S3-Static-Website-Hosting/main/06-website-url.png)

**7️⃣ Test Website**

Accessed endpoint via browser

Verified HTML and image rendering

![07 – Website open](https://raw.githubusercontent.com/yashkumarunt/AWS-S3-Static-Website-Hosting/main/07-website-open.png)

**Security Considerations**

No credentials or secrets stored in repository
Bucket policy restricted to read-only
No write or delete permissions exposed
Suitable only for static, non-sensitive content

**Cost & Cleanup**

This project fits within AWS Free Tier
To avoid any future charges:
Deleted the S3 bucket after testing

**Skills Demonstrated**

Amazon S3 bucket provisioning
Static website hosting configuration
Public access management (Block Public Access & Bucket Policy)
AWS cost awareness and cleanup practices
Clear technical documentation with screenshots

**Key Learnings**

Difference between Block Public Access and Bucket Policies
How S3 serves content via website endpoints
Why S3 static hosting is ideal for serverless frontends
Importance of cleanup in AWS projects
Future Improvements
Add CloudFront CDN for HTTPS and caching
Add custom domain using Route 53\
Add CI/CD pipeline to auto-deploy static files
Convert setup into Terraform (IaC)

**bucket-policy.json:**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadForStaticWebsite",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::yash-portfolio-hostingstaticwebsite/*"
    }
  ]
}

