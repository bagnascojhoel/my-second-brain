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
You can restrict access to CloudFront files to securely signed requests (URL or cookie). To have signed requests, you need a *signer*. This could be a trusted key group (recommended) or an AWS account (this is not recommended because it means you would have to use your root AWS account to sign requests).

### Cache, Origin Requests and Response Headers Policies
For Cache and Origin Requests, the current recommendation is to use specific policies for each one. But you can opt to use the legacy cache settings, which are a poorer version of the recommended approach. 
In Cache Policies, you can define cache TTL, how the key is formed (the more fields included, the more restricted will your cache be) and which compressions should be used. 
With Origin Requests Policies you'll be able to manipulate the incomming request's headers, query strings and cookies.


The last one Response Headers Policies allows you to manipulate headers returned to the client. 
![[Pasted image 20220225065532.png]]

## How can CDN improve Live Streaming?