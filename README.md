# suricata-aws
CloudFormation template to deploy Suricata IDS on AWS 

This template will create the following resources:
- CloudWatch Log Group where Suricata instances will stream their eve.json logs;
- Network Load Balancer listening on UDP port 4789 for VXLAN encapsulated packets;
- Auto Scaling Group for Suricata instances;
- Amazon Linux 2 instances bootstrapped with Suricata and CloudWatch Agent streaming eve.json logs;

The solution has to be deployed in an existing VPC with subnets that have outbound Internet access; it will create all other required resources, including an IAM role. 

To send traffic to Suricata you have to create a VPC Mirror Target and point it to the Network Load Balancer; then create Mirror Filters and Mirror Sessions.
CloudWatch logs can then be streamed to ElasticSearch and analysed in Kibana.