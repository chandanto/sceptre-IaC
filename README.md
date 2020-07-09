# sceptre-IaC
IaC - Sceptre build Infrastructure on AWS Public Cloud provider

# Procedure to build IaC on AWS 

# List of Variables used :
  vpc_stack_name=MYVPC01
  env=ST1
  vpcIP=10.100.0.0/16
  tagname=MYVPC01
  exvpc=vnet1
  
# Sceptre provides two modes before execute - launch > cd C:\sceptre-code\aws\infra\aws-vpc 
Generate - sceptre.exe --var vpc_stack_name=MYVPC01 --var env=ST1 --var vpcIP=10.100.0.0/16 --var tagname=MYVPC01 --var exvpc=vnet1 --output json generate vpcconfig
Validate - sceptre.exe --var vpc_stack_name=MYVPC01 --var env=ST1 --var vpcIP=10.100.0.0/16 --var tagname=MYVPC01 --var exvpc=vnet1 --output json validate vpcconfig 

# Create Stack : Using sceptre
sceptre.exe --var vpc_stack_name=MYVPC01 --var env=ST1 --var vpcIP=10.100.0.0/16 --var tagname=MYVPC01 --var exvpc=vnet1 --output json launch -y vpcconfig 

# Deleting Stack : using sceptre
sceptre.exe --var vpc_stack_name=MYVPC01 --var env=ST1 --var vpcIP=10.100.0.0/16 --var tagname=MYVPC01 --var exvpc=vnet1 --output json delete -y vpcconfig
