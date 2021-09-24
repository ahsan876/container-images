# CyberArk Conjur IAM Authenticator

CyberArk Conjur is an open-source solution for controlling non-human access to tools, applications, and cloud environments. Conjur IAM client that enables an AWS resource to use its AWS IAM role to authenticate with Conjur.

## Challenges

The business challenges that led to evaluate and ultimately select CyberArk:

Resolved the following challenges after using CyberArk:

* Securing credentials used by applications
* Unaudited third-party/remote vendor access
* Auditing the use of privileged access in production systems
* Too many endpoints with local administrator privileges 


## Use Case

A typical DevOps pipeline contains GitHub, Jenkins, Nexus or JFrog, Docker, Kubernetes, and other 10 different tools. Every tool has its administrator account, user accounts, some form of RBAC (Role-Based Access Control), and amount drive or KeyStore database to store them locally.

The environment has a number of secrets and some of them are below.
* Application passwords
* Container Credentials
* SSH Keys
* Database username/passwords
* TLS Certificates
* LDAP passwords
* Machine Identities
* Third-party vendor accounts

DevOps environment becomes vulnerable to hackers unless you have a Secrets Management Strategy, Implementation and Practice.

Security should be built into every phase of the DevOps pipeline.
For example, Jenkins stores its password locally at its home and in some XML configuration files. There are software utilities to crack the password from the shell prompt or accessing its URL from another device. People who have knowledge about these URLs can easily come into your DevOps pipeline and push a malware into the production.

An organization needs a centralized DevOps secrets management tool that is invisible.

## Key Feature
The key features and functionalities of CyberArk Conjur:

* Securing privileged credentials in a vault
* Rotating credentials based on policies
* Securing and rotating shared service accounts
* Monitoring and recording privileged sessions


## Results

Achieved the following results with CyberArk Conjur:

* With CyberArk Conjur privileged accounts and credentials, they are now much more secure.
* secure their privileged accounts and credentials, the time and cost of audit reporting have reduced a lot.


## Installation

Install the libraries with the following command:

```bash
pip install requirements.txt
```

## Configuration
1. Create IAM user with prgrammatic access enabled.
2. Create IAM role with policy of sts service enabled.
3. Configure the aws cli with the following command:

```bash
aws configure
```

You have to enter the following information when prompted:
```bash
AWS Access Key ID [****************YTM6]:
AWS Secret Access Key [****************GOM6]:
Default region name [None]:
Default output format [None]:
```
## Parameters

| Name            | Description  |
| :-------------: | :-------------: |
| appliance_url   | appliance_url is the URL of your conjur application. e.g 'https://conjur.yourorg.com'|

| account         | Conjur account of your conjur application i.e  account being created after the conjur application is deployed. e.g "dev", "prod", "demo" etc| 

| service_id      | IAM Authenticator service ID to identify each service. e.g 'dev', 'prod', 'sysadmins' etc |

| host_id         | The host ID needs to match the AWS ARN of the role we wish to authenticate e.g 'host/cust-portal/<aws-account-id>/<iam-role-name>'|

| cert_file       | cert_file is associated with account which is creadted in conjur application along witht the API key e.g 'conjur-cert.pem'. |

| iam_role_name   | IAM role name of AWS Authenticator |

| ssl_verify      | binary value True or False for untrusted ssl certificate |

## Output
Client instance which have some expiry time, using that instance access the AWS resource depending on the IAM role provided.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
