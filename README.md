
# 🚀 AWS Static Website with CI/CD

This project is a fully automated **static website** deployed to AWS using:

- **S3** → static site hosting  
- **CloudFront** → global CDN with HTTPS  
- **CodePipeline** → CI/CD automation  
- **CodeBuild** → build + deploy steps  
- **GitHub** → source control + trigger pipeline

Whenever you push a change to the GitHub repository, AWS CodePipeline automatically:
1. Pulls the code
2. Runs CodeBuild to deploy to S3
3. Invalidates the CloudFront cache so changes appear instantly

---

## 🌟 Technologies Used

- **AWS S3** → static website hosting  
- **AWS CloudFront** → CDN + HTTPS + caching  
- **AWS CodePipeline** → continuous delivery  
- **AWS CodeBuild** → deployment automation  
- **GitHub** → version control + CI trigger  
- **buildspec.yml** → defines build + deploy steps  
- **HTML/CSS** → simple, modern landing page

---

## 📸 Screenshot

![Screenshot](Screenshot%202025-05-08%20195931.png)

---

## 📦 Project Structure

```
.
├── index.html         → Main landing page
├── error.html         → Custom 404 page
├── buildspec.yml      → AWS CodeBuild script
└── README.md          → Project documentation
```

---

## 🚀 How to Set Up

1. **Clone the repository**
   ```bash
   git clone https://github.com/ssfawad/aws-static-site-repo.git
   cd aws-static-site-repo
   ```

2. **Set up AWS resources**
   - Create an S3 bucket with static website hosting.
   - Add a bucket policy to allow public read access.
   - Create a CloudFront distribution pointing to the S3 bucket.
   - Set up CodeBuild with permissions to deploy to S3 + invalidate CloudFront.
   - Set up CodePipeline to connect GitHub → CodeBuild.

3. **Connect GitHub**
   - Use a GitHub personal access token (PAT) to allow CodePipeline access.
   - Authorize the AWS connection to your GitHub repo.

4. **Push changes**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

5. **Verify deployment**
   - Visit the **CloudFront URL** to view the live site.
   - Verify CloudFront invalidation runs after each push.

---

## ⚙️ Pipeline Workflow

```
GitHub → CodePipeline → CodeBuild → S3 → CloudFront → Users
```

- Any push to `main`:
  - Triggers CodePipeline
  - Runs CodeBuild (`buildspec.yml` handles S3 deploy + CloudFront invalidation)
  - Instantly updates the live site

---

## ✨ Features

- Modern, animated landing page
- Responsive design
- Automatic deployment on push
- Cache busting with CloudFront invalidations
- GitHub integration with CodePipeline

---

Built with ☕ on AWS