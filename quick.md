Here is the list of services provided by AWS in summary with pricing for rough idea. The information presents on this page will give you roguh idea. There can be multiple reasons in price difference. For example, date and time when the information was captured, or region specific pricing etc.

## [Pinpoint](https://aws.amazon.com/pinpoint)
Communicate your customers using Email, SMS, Push Notifications, and Voice. And collect events for analysis.

> **First 12 months (Free Tier)** Target 5,000 endpoints, send 1 million push notifications, and track 100 million events for free each month with Amazon Pinpoint.

### Pricing

| Service | Transactional | Campaign-based |
| --------- | --------- | --------- |
| **Email** | $1.00 per 10,000 emails |  1) $1 per 10,000 emails. 2) $0 for the first 5,000 endpoints in your MTA, and $1.20 per 1,000 endpoints after that. (up tp 1 million) |
| **SMS** | Each SMS is chargable and based on country |  |
| **Push Notifications** | $0 for the first million notifications, and $1.00 / million after that | 1) $0 for the first million notifications, and $1.00 /million after that. 2) $0 for the first 5,000 endpoints in your MTA, and $1.20 per 1,000 endpoints after that (up tp 1 million). |
| **Voice** | | |

* **endpoint**: **receipint**. An endpoint is a messaging destination for an individual customer, such as an email address, mobile phone number, or device identifier.
* **MTA**: (Monthly Targeted Audience) The total number of endpoints that you contact in a 30-day period

#### Events
$0 for the first 100,000,000 events that you collect each month, and $0.000001 per event you collect after that.



## [Amazon Cognito](https://aws.amazon.com/cognito/)
For Sign-Up, Sign-In, and Access Control. You can let user to signin through username & password, federated identites (social identity providers like Google, FB, twitter etc), and through enterprise identity providers.

### Direct or social signin

|Pricing Tier (MAUs)|Price per MAU|
|-----------------|-----------------|
|First 50,000 |	Free|
|Next 50,000 |	$0.00550|
|Next 900,000 |	$0.00460|
|Next 9,000,000 |	$0.00325|
|Greater than 10,000,000 |	$0.00250|

Note
* You can't export user's account information to move out from AWS.
* Monthly Active Users (MAUs): A user is counted as a MAU if, within a calendar month, there is an identity operation related to that user, such as sign-up, sign-in, token refresh or password change. You are not charged for subsequent sessions or for inactive users within that calendar month.
* Enabling advanced security features cost more.

Example
If you don't enable advanced security features, 5k users are joining you every month, and you're refreshing the token every week then it'll cost $28 on 3rd month, $138 on 4th month, $248 on 4th month and so on. 

## [API Gateway](https://aws.amazon.com/api-gateway)
API Gateway is the front door for applications to access data, business logic, or functionality from your backend services. It can be used for traffic management, authorization and access control, monitoring, and API version management.

### Price

| Number of Requests (per month) | 	Price (per million) |
|-----------|---------------|
| First 333 million |	$3.50 |
| Next 667 million |	$2.80 |

### Price for cahcing

| Cache Memory Size (GB) |	Price per Hour |
| --------------- | ----------- |
| 0.5 | 	$0.020 |
| 1.6 | 	$0.038 |
| 6.1 | 	$0.20 |


Note
* Every API may respond with some data that will be charged according to EC2 instance.

Example:
5 million calls sending 3kb data in each call where data transfer charges are $0.09/GB. (no caching)
```
( 5 million * $3.50/million ) x ( 3 KB * 5 million * $0.09) = $18.79
```

## [AWS Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/)
 Provision a logically isolated section of the Amazon Web Services (AWS) Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways. You can use both IPv4 and IPv6 in your VPC for secure and easy access to resources and applications. A VPC can be connected to Internet, to a data center, or other VPCs.
 
User is not charged to setup VPC but for private links.

## [CloudFront]()
Consider it as CDN. The static contents are served from the edge location at the lowest latency. CloudFront retrieves the content from the S3 bucket. 


Free: 50 GB of data transfer out and 2,000,000 HTTP or HTTPS Requests each month for one year

There are 5 factors affect the price

* **Data Transfer Out (Internet/Origin)**
 * Out to Internet (per GB): For first 10TB $0.085 for all the regions in United States & Canada and $0.170 for India.
 * Out to Origin (per GB): For all data transfer $0.02 for all the regions in United States & Canada and $0.160 for India.

* **HTTP/HTTPS Requests**
 * HTTP: $0.0075 for United States & Canada and $0.0090 for India.
 * HTTPs: $0.01 for United States & Canada and $0.012 for India.
* [**Invalidation Requests**](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html): Static files are cached by CloudFront edges. When the file is updated, their cache is needed to be invalidated. First 1,000 paths requests for invalidation are free each month. Thereafter, $0.005 per path request. A path can have wildcard to invalidate all or multiple file requests. (:bulb: Though 1000 free requests are sufficient. But this cost can be saved by versioning the files)
* **Field Level Encryption Requests**: Encrypting particular field(s) in a post request. So they're not accidently logged as plaint text on the server logs. $0.02 for every 10,000 requests.
* **Dedicated IP Custom SSL certificates associated with a CloudFront distribution**: 
* Date transfer in POST/PUT requests will be charged
* **Lambda@Edge**: Check the relevant section for more detail.

Classes can help to reduce the cost.

## [S3](https://aws.amazon.com/s3)
To store the static files. User can request to replicate the data in cross regions.

### Price
5 GB free in first 12 months. Different charges after that on monthly basis,

| Class | Price |
| ---- | ------|
| S3 Standard Storage | $0.023/GB up to 50TB |
| S3 Intelligent-Tiering Storage, Frequent Access Tier| $0.023/GB up to 50TB|
| S3 Intelligent-Tiering Storage, Infrequent Access Tier| $0.0125/GB up to 50TB|
| S3 Standard-Infrequent Access (S3 Standard-IA) Storage | $0.0125/GB for all storage |
| S3 One Zone-Infrequent Access (S3 Standard-IA) Storage | $0.01/GB for all storage |
| Monitoring and Automation | $0.0025 per 1,000 objects  for all storage  | 

**Note** 
* User needs to pay extra when he performs any opration on data like retieves, scan, or copy paste from/to/in S3 bucket. The charges are different for each class. Operations charges increases when you go from top to bottom in above table.
* User will also be charged for storage management and data transfer (out) to other AWS services, regions, or to Internet.
* Data transfer out is free upto 1GB/month to Internet, and all to CloudFront.
* User will be charged extra if we want to speed up data upload.


#### Class
A class can be applied on a folder, file, or whole bucket. You can also specify rules to apply particular class automatically.

* **Infrequent Access Storage**: accessed infrequently but still needs an immediate access.
* **Glacier**: For archieve.
* **Intelligent-Tiering**: a storage object is monitored for 30 days and automatically move to appropriate class as per the access pattern. No extra fees when it moves to particular tier.


|S3 Standard |S3 Intelligent-Tiering*|S3 Standard-IA|S3 One Zone-IA†|S3 Glacier|S3 GlacierDeep Archive**|
|-----|-----|-----|-----|-----|-----|
|Designed for durability|99.999999999% (11 9’s) |99.999999999% (11 9’s) |99.999999999% (11 9’s) |99.999999999% (11 9’s) |99.999999999% (11 9’s) |99.999999999% (11 9’s)
|Designed for availability |99.99% |99.9% |99.9% |99.5% |N/A |N/A|
|Availability SLA |99.9% |99% |99% |99% |N/A |N/A|
|Availability Zones |≥3 |≥3 |≥3 |1 |≥3 |≥3|
|Minimum capacity charge per object |N/A |N/A |128KB |128KB |40KB |40KB|
|Minimum storage duration charge |N/A |30 days |30 days |30 days |90 days |180 days|
|Retrieval fee |N/A |N/A |per GB retrieved |per GB retrieved |per GB retrieved |per GB retrieved|
|First byte latency |milliseconds |millseconds |milliseconds |milliseconds |select minutes or hours |select hours|
|Storage type |Object |Object |Object |Object |Object |Object|
|Lifecycle transitions |Yes |Yes |Yes |Yes |Yes |Yes|

† Because S3 One Zone-IA stores data in a single AWS Availability Zone, data stored in this storage class will be lost in the event of Availability Zone destruction.
* S3 Intelligent-Tiering charges a small tiering fee and has a minimum eligible object size of 128KB for auto-tiering. Smaller objects may be stored but will always be charged at the Frequent Access tier rates. 

Change CloudFront pricing to know how the pricing for accessing static contents can be affected.

## [Lambda@Edge](https://aws.amazon.com/lambda/edge/)
Run code closer to users.

Use cases
* Add security headers
* Reject requests when mandatory headers are missing.
* Redirect a user to waiting queue if he is not premium
* Inject particular headers based on the user type. So the application need not to check user's type and work
* Monitoring & Analytics

### Pricing
* Monthly compute charges: $0.00000625125 per 128MB-second
* Monthly request charges: $0.60 per 1 million requests

If your Lambda@Edge function executed 10 million times in one month, and it ran for 50ms each time;
```
Total compute (seconds) = 10M * (0.05sec) = 500,000 seconds
Monthly compute charges = 500,000 * $0.00000625125 = $3.13
Monthly request charges = 10M * $0.6/M = $6.00
Total charges = Compute charges + Request charges = $3.13 + $6.00 = $9.13 per month
```

