#aws #development_career #certification 

# Content Delivery Network
Temporary replication of data on locations, ideally, far from the server. Let's say your server is on Japan, and you want people from all around the world to access it without much delay. A CDN can see incoming requests from the USA, generate the code the client will should receive, and then store it in a server near the request source. So whenever someone near the USA wants to access your content, they can simply use the USA copy and avoid all latency innate of long distance communication.

### Origin Shield
When enabled, CloudFront creates an additional caching layer. All edge locations will go first to your Origin Shield cache. That means your origin will not have to process multiple times the same cacheable request just because different edge locations request it.

![[Pasted image 20220224073858.png]]
![[Pasted image 20220224073939.png]]

### S3 Bucket Access
CloudFront allows you to access private S3 files using Origin Access Identity (OAI). That allows you to make those bucket files acessable only via CloudFront. You can further restrict access to those files with [[CDN#Signed URLs|Signed URLs]].

### Signed URLs
You can restrict access to CloudFront files to securely signed requests (URL or cookie). To have signed requests, you need a *signer*. This could be a trusted key group (recommended) or an AWS account.

## How can CDN improve Live Streaming?