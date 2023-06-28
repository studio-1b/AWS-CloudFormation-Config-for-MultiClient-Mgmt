# AWS-CloudFormation-Config-for-MultiClient-Mgmt
AWS CloudFormation Configurations to Create Multiple VPC as different companies, and access to them via peering from your own VPC, accessed by VPN.  Hub-and-spokes topology

    +----------------------+
    | Your VPC             |
    | (use BastionVPC.yml) |
    |   subnet1            |
    |     openvpn          |
    |   subnet2            |
    |     splunk           |
    +----------------------+
      |                       |
    peering connection      peering connection
      |                       |
      V                       V
    +---------------------+ +---------------------+
    | Other VPC           | | Other VPC           |
    | (use CompanyA.yml)  | | (use CompanyA.yml)  |
    |   subnet1           | |   subnet1           |
    |     apache2         | |     apache2         |
    |   subnet2           | |   subnet2           |
    |     mysql           | |     mysql           |
    +---------------------+ +---------------------+
