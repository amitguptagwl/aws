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

## [S3](https://aws.amazon.com/s3)
To store the static files.

### Price
5 GB free in first 12 months. Different charges after that,

| S3 Standard Storage | $0.023/GB up to 50TB |
| S3 Standard-Infrequent Access (S3 Standard-IA) Storage | $0.0125/GB for all storage |
| S3 One Zone-Infrequent Access (S3 Standard-IA) Storage | $0.01/GB for all storage |

#### Class
A class can be applied on a folder, file, or whole bucket. You can also specify rules to apply particular class automatically.

* **Infrequent Access Storage**: accessed infrequently but still needs an immediate access.
* **Glacier**: For archieve.
* **Intelligent-Tiering**: a storage object is monitored for 30 days and automatically move to appropriate class as per the access pattern. No extra fees when it moves to particular tier.

|S3 Standard |S3 Intelligent-Tiering*|S3 Standard-IA|S3 One Zone-IA†|S3 Glacier|S3 GlacierDeep Archive**|
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





