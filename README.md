# CSN-AWS-WEEK8-TASK
Managing static and dynamic content delivery with amazon S3 and cloud front integration##

## 🌐 Personal Static Website Deployment
### Project Description
This project involved deploying a personal static website (such as a resume, portfolio, or "About Me" page) using Amazon S3 and CloudFront. The core steps included:
-Uploading HTML files to an S3 bucket.
-Enabling static website hosting on the S3 bucket.
-Configuring the S3 bucket policy to allow public access.
-Setting up a CloudFront distribution that uses the S3 bucket as its origin to securely deliver content with improved performance.

### 💻 Technologies Used
- Amazon S3 (Simple Storage Service): Used for storing the static website files and serving them with static website hosting.
- Amazon CloudFront: Utilized as a Content Delivery Network (CDN) to securely deliver the website content, providing low latency and high transfer speeds to users globally.
- HTML: The foundational technologies for the static website content itself.

## ✅ Deliverables & Proof of Work
As part of this task, the following deliverables were prepared.
- Screenshots of Key Configurations
- S3 Bucket Configuration Screenshot
- Proof that static website hosting was enabled on the S3 bucket.

###### S3 bucket SCREENSHOT
 <img width="950" height="290" alt="Screenshot 2025-08-11 121610" src="https://github.com/user-attachments/assets/2bf36d9a-a2f4-4b82-bbc6-ef454658c2c7" />
 <img width="957" height="224" alt="Screenshot 2025-08-11 120846" src="https://github.com/user-attachments/assets/159a1ba0-c105-4d2c-aeb3-5f94319448db" />
 <img width="959" height="359" alt="Screenshot 2025-08-11 115430" src="https://github.com/user-attachments/assets/98e64b85-cb2a-4746-902c-3e83587388bf" />

##### Bucket Policy Screenshot:
Demonstrating the bucket policy configured to allow public access.
<img width="960" height="398" alt="Screenshot 2025-08-11 120137" src="https://github.com/user-attachments/assets/a4a731da-57ba-496e-9b02-ff0315b27330" />

##### CloudFront Distribution Screenshot:
Showing the CloudFront distribution settings and its deployment status.
<img width="949" height="159" alt="Screenshot 2025-08-11 121248" src="https://github.com/user-attachments/assets/de34f014-a954-4e7f-a6d9-b081b4fbee74" />
<img width="959" height="359" alt="Screenshot 2025-08-11 115430" src="https://github.com/user-attachments/assets/093bafd2-383e-4f79-ac63-a1de947c8a3a" />
<img width="960" height="401" alt="distribution cloudfront" src="https://github.com/user-attachments/assets/ccf05f78-9c25-483f-b686-30491227ebfd" />

##### Live Website Screenshot via cloudfront:
A visual confirmation of the deployed website, accessible through the CloudFront domain.
<img width="958" height="497" alt="live page" src="https://github.com/user-attachments/assets/1b18b01c-6e38-4dae-b67c-e45e9d942d37" />
<img width="950" height="417" alt="Screenshot 2025-08-11 114127" src="https://github.com/user-attachments/assets/11b6d380-cb70-4e72-bf9a-52b34572cc6f" />


## Here's a step-by-step breakdown of how I accomplished this Static website deployment
### Step 1: Prepare Your Website Files 📁
Organize Your Files: Make sure all your website files (HTML, CSS, JavaScript, images, etc.) are neatly organized in a single folder on your computer. Your main page should usually be named index.html.
Keep it Static: Remember, S3 is for static websites. This means your website shouldn't need a database or complex server-side code.

### Step 2: Create an S3 Bucket and Upload Files 📦
Log in to AWS Management Console: Go to the AWS website and log in to your account.
* Create a New Bucket:
* Click the "Create bucket" button.
* Give your bucket a unique name. This name needs to be globally unique across all of AWS, so it's often a good idea to use your domain name if you have one (e.g., my-personal-portfolio.com).
* Choose an AWS Region close to where you (or your primary audience) are located. This helps with speed.
* Disable "Block all public access." This is a crucial step for a public website. You'll get a warning, which is expected since you want the website to be public.
* Keep other settings as default for now, then click "Create bucket."
* Once the bucket is created, click on its name to enter the bucket.
* Click the "Upload" button.
* Drag and drop all your website files and folders from your computer into the upload area. Click Upload.

### Step 3: Enable Static Website Hosting on S3 
* Go to Bucket Properties: Inside your S3 bucket, click on the "Properties" tab.
* Find Static Website Hosting: Scroll down until you find the "Static website hosting" section and Enable Hosting:
* Click "Edit" next to Static website hosting and select "Enable."
* For "Index document," type index.html (or whatever your main HTML file is called).
* For "Error document" (optional but recommended), you can type error.html if you have a custom error page, or index.html to redirect to the home page for errors.
* Click "Save changes."

### Step 4: Configure S3 Bucket Policy for Public Access 
* Go to Bucket Permissions: Inside your S3 bucket, click on the "Permissions" tab.
* Edit Bucket Policy: Scroll down to the "Bucket policy" section and click "Edit."
* IMPORTANT: Remember to replace your-bucket-name in the Resource line with the actual name of your S3 bucket.
* Save Policy: Click "Save changes."

### Step 5: Set Up CloudFront Distribution for Speed and Security 🔒
* Navigate to CloudFront: Search for "CloudFront" in the AWS services search bar and click on "CloudFront."
* Create a Distribution: Click the "Create distribution" button.
* Choose Your S3 Bucket as Origin:
* In the "Origin domain" field, click to select your S3 bucket from the dropdown list. It should show your bucket's website endpoint (e.g., your-bucket-name.s3-website-us-east-1.amazonaws.com).
* For "Viewer protocol policy," select "Redirect HTTP to HTTPS". This forces all visitors to use the secure HTTPS version of your site.
* Leave other caching settings as default for now, or adjust them based on your needs.
* Distribution Settings :Alternate Domain Names (CNAMEs): If you have your own custom domain name (like www.yourwebsite.com), you'd add it here.
* Create Distribution: Click "Create distribution."
* Wait for Deployment: CloudFront distributions take some time to deploy (10-20 minutes or more). You'll see the status change from "Deploying" to "Deployed."

### Step 6: Test Your Live Website! 
* Get the CloudFront Domain Name: Once your CloudFront distribution is "Deployed," go back to the CloudFront dashboard. Find your distribution and copy its "Domain name" (it will look something like d1234abcd.cloudfront.net).
* Open in Browser: Paste this domain name into your web browser.
* Verify Content: Your static website should now load, delivered securely and quickly via CloudFront, This is the final proof that your entire setup works.


## Key Concepts & Implementation Highlights
This project provided hands on experience with fundamental cloud deployment concepts:

- Static Website Hosting: Understanding how S3 can directly serve web content without requiring traditional web servers.

- Bucket Policies: Learning to define granular access controls for S3 buckets, specifically to allow public read access for website content.

- Grasping the role of CloudFront in caching content closer to users, reducing load on the origin (S3), and improving website performance and security (e.g., via HTTPS).

## This task is a valuable  because it demonstrates practical skills in:

* Proficiency in deploying web applications on AWS, a leading cloud platform.
* Expertise in configuring and managing static websites.
* Understanding and utilizing CDNs for performance optimization and secure content delivery.
* Hands-on experience with core AWS services like S3 and CloudFront, which are widely used in modern web development.
* The process involved understanding how different cloud services interact and configuring them correctly, showcasing problem-solving abilities in a real-world scenario.
* This task Demonstrates an understanding of how static sites served via S3 and CloudFront are highly scalable and cost-effective solutions for web presence.
* This task highlights my ability to take a web project from local development to a globally accessible, high-performance, and secure online presence.
