#  Step-by-Step Guide to Hosting a Static Website with AWS S3 and CloudFront

## Step one: Create the bucket
### I used the us-east-1 region and gave a unique name to my S3 bucket (traffic-light-app-bucket).
<img width="1440" alt="Screenshot 2024-05-09 at 13 12 56" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/35f9b61d-5778-4e69-8f70-d4a7fff160c3">

### I also disabled all forms of public access to my bucket and then created it.
<img width="1435" alt="Screenshot 2024-05-09 at 13 13 36" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/9273ecf3-6451-46bb-b91f-af2d72dc9054">

## Step Two: Upload Website Files
### I accessed the newly created bucket (traffic-light-app-bucket) and uploaded my website files.
<img width="1440" alt="Screenshot 2024-05-09 at 13 18 39" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/0ab7fb0d-652f-42fc-b59b-7e88cc576c47">
<img width="1440" alt="Screenshot 2024-05-09 at 13 20 25" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/0cd11719-fe13-4e34-9a72-0ef0d828e488">
<img width="1440" alt="Screenshot 2024-05-09 at 16 30 56" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/feb4507a-f43e-4508-82b3-6baa12d01163">

## Step Three: Enable Static Website Hosting
### Within my S3 bucket, I accessed properties, scrolled downwards to "Static Website Hosting" and enabled it. I also attached the root document "index.html"
<img width="1440" alt="Screenshot 2024-05-09 at 16 46 28" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/f2467624-78d7-4ec3-b62e-23c34f6be921">

## Step Four: Setup CloudFront for the S3 Bucket
### I selected the traffic light bucket
### Enabled orgin access control, that way the bucket would restrict access to only cloudfront.
### I also created a new OAC for this CloudFront distribution
<img width="1405" alt="Screenshot 2024-05-09 at 16 37 13" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/f3b1df19-6aa2-4fac-95d7-734922bb01ef">\

### Also enabled WAF(Web Application Firewall), added my default root object and created the CloudFront distribution
<img width="1431" alt="Screenshot 2024-05-09 at 16 39 48" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/fa20b8b9-0777-4eef-9e2e-6255b42afdad">

## Step Five: Update Bucket policy with to allow CloudFront Access and Public Read Access as well
### After my CloudFront distribution was created, I copied it's policy statement
<img width="1438" alt="Screenshot 2024-05-09 at 16 42 19" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/4fa4737d-56de-4533-a944-34c525b8b81a">

### Pasted the policy statement in bucket policy.
<img width="1440" alt="Screenshot 2024-05-09 at 16 45 04" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/dbb1835c-2240-4c32-97e3-84a5f345484e">

### Added the json statemnt, allowing public read and saved the edited bucket policy.
<img width="1440" alt="Screenshot 2024-05-09 at 16 59 44" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/f9a18f1f-74ef-4854-89c7-47d21fb95fd2">

## Step Six: Load the webpage
### I copied the CloudFront domain name (https://d1p0z85k2uifgc.cloudfront.net/), pasted it on my web browser and loaded a working static website.
<img width="1438" alt="Screenshot 2024-05-09 at 17 21 01" src="https://github.com/busybrainx99/S3_CF_Hosting/assets/105159710/eba57dbc-fc7c-40b7-a9a7-34a1874bb90b">






