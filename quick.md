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

## [AWS Certificate Manager(ACM)](https://aws.amazon.com/certificate-manager/)
To manage and deploy SSL/TLS certificates. It automatically handles renewal.

**Note**
* You cannot download a SSL certificate from ACM. And c.an use them on specific AWS services
*

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
