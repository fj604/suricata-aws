# suricata-aws
CloudFormation template to deploy Suricata IDS on AWS 

This template will create the following resources:
- CloudWatch Log Group where Suricata instances will stream their eve.json logs;
- Network Load Balancer listening on UDP port 4789 for VXLAN encapsulated packets;
- Auto Scaling Group for Suricata instances;
- Amazon Linux 2 instances bootstrapped with Suricata and CloudWatch Agent streaming eve.json logs;
