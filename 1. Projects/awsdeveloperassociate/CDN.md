#aws #development_career #certification 

# Content Delivery Network
Temporary replication of data on locations, ideally, far from the server. Let's say your server is on Japan, and you want people from all around the world to access it without much delay. A CDN can see incoming requests from the USA, generate the code the client will should receive, and then store it in a server near the request source. So whenever someone near the USA wants to access your content, they can simply use the USA copy and avoid all latency innate of long distance communication.

## Origin Settings

### Origin Shield
When enabled, CloudFront creates an additional caching layer. All edge locations will go first to your Origin Shield cache. That means your origin will not have to process multiple times the same cacheable request just because different edge locations request it.

![[Pasted image 20220224073858.png]]
![[Pasted image 20220224073939.png]]

## Default Cache Behavior
### S3 Bucket Access
CloudFront allows you to access private S3 files using Origin Access Identity (OAI). That allows you to make those bucket files acessable only via CloudFront. You can further restrict access to those files with [[CDN#Signed URLs|Signed URLs]].

### Signed URLs
You can restrict access to CloudFront files to securely signed requests (URL or cookie). To have signed requests, you need a *signer*. This could be a trusted key group (recommended) or an AWS account (this is not recommended because it means you would have to use your root AWS account to sign requests).

### Cache, Origin Requests and Response Headers Policies
For Cache and Origin Requests, the current recommendation is to use specific policies for each one. But you can opt to use the legacy cache settings, which are a poorer version of the recommended approach. 

In Cache Policies, you can define cache TTL, how the key is formed (the more fields included, the more restricted will your cache be) and which compressions should be used. 
![[Pasted image 20220225065627.png]]

With Origin Requests Policies you'll be able to manipulate the incomming request's headers, query strings and cookies.
![[Pasted image 20220225065559.png]]

The last one Response Headers Policies allows you to manipulate headers returned to the client. 
![[Pasted image 20220225065532.png]]

### Additional Settings
- Smooth Streaming: this enables usage of Microsoft's IIS Live Smooth Streaming, if your origin has that enabled.
- Field-level Encription: when your CDN supports POST methods and accepts only HTTPS, this feature can be enabled to encript data that your end-users send into those POST (and PUT) methods.
- Real-time Logs: it delivers a stream of your logs to AWS Kinses. This can be configured to send only a percentage of the interactions of end-users, select extra fields you wish to send, the CDN Distribution to source from and some other configurations.

## Function Associations
Pick lambda or CloudFront functions to run at specific events.
![[Pasted image 20220225072548.png]]

## How can CDN improve Live Streaming?
Without a CDN each end-user has to request all the way to the origin. If there is a CDN, the user can communicate only with the edge location. Since the edge location won't have the content the user expects, it will then fetch it from the origin. This simply transfers the latency from end-user -> origin to end-user -> edge location -> origin. What is the benefit of that? Consider that you have a 300Mbps internet bandwidth. With a CDN, that will take effect only until the edge location, which should be a lot closer to you than the origin. Between edge location and  origin, the bandwidth and latency will be AWS responsability. That means 10 Gbps is a common thing. 

```ad-info
In this scenario, you can image the CDN not as the storage of your content, but as a highway to it
```
