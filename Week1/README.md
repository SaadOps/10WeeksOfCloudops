![S3](https://github.com/SaadOps/10WeeksOfCloudops/assets/94478736/8eaddf64-dbc7-47c2-8184-ed49dd522b68)

1) Create an S3 bucket.

2) Select the created bucket.

3) Scroll down to the last and edit static website hosting:
   - Click on "Enable".
   - Enter "index.html" for the index document.
   - Enter "error.html" for the error document.
   - Click "Save changes".

4) Go to the "Objects" tab and upload your files.

5) Go to CloudFront and create a distribution:
   - Choose the origin domain.
   - Select "Legacy Access Identities".
   - Create a new Origin Access Identity (OAI).
   - Update the bucket policy by selecting "Yes".

6) Configure the CloudFront distribution settings:
   - Enable "Viewer Protocol Policy" to redirect HTTP to HTTPS.
   - Allow HTTP methods: GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE.
   - Add an alternate domain name.
   - Request a public certificate.
   - Click "Request".

7) Go to the certificate settings:
   - Go to Namecheap and access the advanced DNS settings of your domain.
   - Add a new record with the type "CNAME".
   - Paste the CNAME name in the "Host" field (copy until before the dot).
   - Paste the CNAME value in the "Target" field (without the last dot).

8) Select the custom SSL certificate in CloudFront.

9) Enter "index.html" as the default root object.

10) Create the CloudFront distribution.

11) Copy the distributed domain name from CloudFront.

12) Create a new CNAME record in Namecheap:
   - Type "www" in the "Host" field.
   - Enter the distributed domain name in the "Target" field.

13) Create another CNAME record in Namecheap:
   - Add your domain name to the "Host" field.
   - Enter the distributed domain name in the "Target" field.

14) Visit your domain link, and your website is live!

15) To create a pipeline:
   - Provide the source provider (GitHub, in this case).
   - Configure the build stage (skip it, if not needed).
   - Provide the deploy provider.
   - Create the pipeline.
