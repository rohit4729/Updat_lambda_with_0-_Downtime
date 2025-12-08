# 🚀 Zero Downtime Lambda Function-Update

This project demonstrates how to **update an AWS Lambda function with zero downtime** using **Lambda versions, aliases, API Gateway stage variables, and weighted traffic shifting**.  

With this structured approach, users experience a seamless transition while you roll out new versions of your Lambda function in production.

---

## 📖 Project Overview
- **Goal:** Deploy new Lambda versions without disrupting live traffic.  
- **Key Features:**  
  - Lambda **versions** for controlled releases  
  - Lambda **aliases** for environment separation (`dev`, `test`, `prod`)  
  - API Gateway **stage variables** for dynamic routing  
  - Weighted aliasing for **gradual traffic shifting**  

---

## ⚙️ Step-by-Step Implementation

### **Step 1: Lambda Function Setup**
- Created a simple Lambda function returning:  
  ```text
  Hello V1



- Published two versions:

    Version 1 → Testing

    Version 2 → Production

- Created three aliases:

    dev → Latest version

    test → Testing version

    prod → Production version

---


### **Step 2: API Gateway Integration**


- Created a REST API with a GET method pointing to the Lambda function.

- Configured integration request with:
 
    stageVariables.lambdaAlias


- Added resource-based policy statements for all aliases via shell script.

- Deployed the API into three stages:

    dev

    test

    prod

  ---

  ### **Step 3: Stage Variables**

- Configured API Gateway stage variables:

    lambdaAlias = dev for Dev stage

    lambdaAlias = test for Test stage

    lambdaAlias = prod for Prod stage

  ---


 ### **Step 4: Weighted Traffic Shifting**

- Updated the prod alias in Lambda:

    Assigned Version 1 with 10% traffic

    Assigned Version 2 with 90% traffic

- Gradually shifted traffic from 10% → 100% until fully moved to the new version.

✅ Result: Users experienced zero downtime while new Lambda code rolled out.

---

### **🌍 Real-World Use Cases**

   🔄 Rolling out new Lambda versions without breaking production.

   🧪 A/B testing Lambda functions with different versions.

   🏢 Enterprise-grade continuous deployment pipelines.

   ☁️ Improving API reliability with seamless transitions.

   ---

### **🛠️ Tech Stack**

  - AWS Lambda – Serverless compute

  - AWS API Gateway – API management

  - IAM Policies – Secure alias permissions

  - Stage Variables & Aliases – Environment control

✨ This project ensures safe, gradual, and reliable Lambda updates with no downtime. Perfect for production workloads requiring high availability.

---

### **🖼️ Screenshots:**
<img width="1920" height="1080" alt="Screenshot (36)" src="https://github.com/user-attachments/assets/fbd63335-c3de-4e39-a98c-7bc67e3a68e5" />
<img width="1920" height="1080" alt="Screenshot (37)" src="https://github.com/user-attachments/assets/235429d3-47ba-4fda-b9ab-bc6c26745b5d" />
<img width="1920" height="1080" alt="Screenshot (38)" src="https://github.com/user-attachments/assets/f9c72d81-5334-4ed5-96c7-eb85de42f8a5" />
<img width="1920" height="1080" alt="Screenshot (43)" src="https://github.com/user-attachments/assets/d8f02130-562b-404c-8baa-3e9acb0d3d1e" />
<img width="1920" height="1080" alt="Screenshot (40)" src="https://github.com/user-attachments/assets/034acc6c-56f6-4b98-b16a-8fcac7a24caf" />
<img width="1920" height="1080" alt="Screenshot (41)" src="https://github.com/user-attachments/assets/f08c2245-ced3-4d31-96b2-ea6e1db5750e" />
<img width="1920" height="1080" alt="Screenshot (42)" src="https://github.com/user-attachments/assets/c99b3776-a367-43a9-a46f-641bf7109a80" />
<img width="1920" height="1080" alt="Screenshot (44)" src="https://github.com/user-attachments/assets/98424829-1a4f-46b6-bb5e-c5b6ca908ade" />
<img width="1920" height="1080" alt="Screenshot (45)" src="https://github.com/user-attachments/assets/c40fea83-44c1-4f53-b92d-2b44af42b4bd" />

