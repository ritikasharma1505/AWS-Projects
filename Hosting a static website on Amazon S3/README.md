## Host a static website on Amazon S3
"A static website has static content created in HTML, CSS, and JavaScript"

Step 1: Create a bucket

- Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/
- Choose "Create bucket".
- Enter the Bucket name (for example, example.com).
- Choose the Region where you want to create the bucket.
- Choose "Create".


Step 2: Enable static website hosting
- In the Buckets list, choose the name of the bucket that you want to enable static website hosting for.
- Choose Properties.
- Under Static website hosting, choose Edit.
- Under Static website hosting, choose "Enable".
- In Index document, enter the file name of the index document, typically "index.html".
- Choose Save changes.
- Under Static website hosting, note the Endpoint.

**NOTE** The Endpoint is the Amazon S3 website endpoint for your bucket. After you finish configuring your bucket as a static website, you can use this endpoint to test your website.


Step 3: Edit Block Public Access settings (Tis is not a secure way, but for this demo usecase performing this action)
- Choose the name of the bucket that you have configured as a static website.
- Choose Permissions.
- Under Block public access (bucket settings), choose Edit.
- Un-tick Block all public access, and choose Save changes.


Step 4: Add a bucket policy that makes your bucket content publicly available

- Under Buckets, choose the name of your bucket.
- Choose Permissions.
- Under Bucket Policy, choose Edit.
- To grant public read access for your website, copy the following bucket policy, and paste it in the Bucket policy editor.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::Bucket-Name/*"
            ]
        }
    ]
}
```
- Update the Resource to your bucket name.
- Choose Save changes.


Step 5: Configure an index document
- Create an index.html file or other necessary files and upload on the created S3 bucket.
- If you don't have an index.html file, you can use the following HTML to create one:
```
<html xmlns="http://www.w3.org/1999/xhtml" >
<head>
    <title>My Website Home Page</title>
</head>
<body>
  <h1>Welcome to my website</h1>
  <p>Now hosted on Amazon S3!</p>
</body>
</html>
```

Step 6: Configure an error document(if any)


Step 7: Test your website endpoint
- Under Buckets, choose the name of your bucket.
- Choose Properties.
- At the bottom of the page, under Static website hosting, choose your Bucket website endpoint.
- Your index document opens in a separate browser window.


Step 8: Clean up
- Delete the AWS resources that you allocated so that you no longer accrue charges. After you delete your AWS resources, your website is no longer available.

**Extra Note: Amazon S3 static websites support only HTTP endpoints.
If you want to use HTTPS, you can use Amazon CloudFront to serve a static website hosted on Amazon S3
To use HTTPS with a custom domain, see Configuring a static website using a custom domain registered with Route 53.**

Why Hosting static website on Amazon S3?

+ Highly Available: Because AWS S3 allows for unlimited object storage and replicates each object across multiple availability zones, high availability, and durability are guaranteed even in the event of an AZ failure.
+ Security: AWS S3, which is managed and maintained by AWS, is a highly secure service that can be made even more secure by turning on bucket encryption.

+ Easy to manage and maintain: When necessary, AWS S3 offers a simple console interface for managing and maintaining bucket objects. It also offers API support using the AWS SDKs that are available.

+ Easy integration with other AWS services: Other AWS services like CloudFront, Route53, CloudWatch, Lambda, etc. can be used with AWS S3 with ease.