## Introduction to AWS 

# Parallel Clusters
https://docs.aws.amazon.com/parallelcluster/


AWS Overview : https://on24static.akamaized.net/event/18/69/53/9/rt/1/documents/resourceList1553280843494/gettingstartedwithamazonwebservices11553280842853.pdf

```
//Install venv
pip3 install --user --upgrade virtualenv
virtualenv %USERPROFILE%\apc-ve
%USERPROFILE%\apc-ve\Scripts\activate

//Install pcluster
pip3 install aws-parallelcluster

(apc-ve) (base) C:\Users\Regular\apc-ve\Scripts>pcluster configure
WARNING: Configuration file C:\Users\Regular\.parallelcluster\config will be ove
rwritten.
Press CTRL-C to interrupt the procedure.


Allowed values for AWS Region ID:
1. ap-northeast-1
2. ap-northeast-2
3. ap-south-1
4. ap-southeast-1
5. ap-southeast-2
6. ca-central-1
7. eu-central-1
8. eu-north-1
9. eu-west-1
10. eu-west-2
11. eu-west-3
12. sa-east-1
13. us-east-1
14. us-east-2
15. us-west-1
16. us-west-2
AWS Region ID [ap-northeast-1]: 3
Allowed values for EC2 Key Pair Name:
1. awsIndia
EC2 Key Pair Name [awsIndia]: 1
Allowed values for Scheduler:
1. sge
2. torque
3. slurm
4. awsbatch
Scheduler [awsbatch]: 3
Allowed values for Operating System:
1. alinux
2. centos6
3. centos7
4. ubuntu1604
5. ubuntu1804
Operating System [alinux]: 5
Minimum cluster size (instances) [0]:
Maximum cluster size (instances) [10]:
Master instance type [t2.micro]:
Compute instance type [optimal]:
ERROR: optimal is not an acceptable value for Compute instance type
Compute instance type [optimal]:
ERROR: optimal is not an acceptable value for Compute instance type
Compute instance type [optimal]:
ERROR: optimal is not an acceptable value for Compute instance type
Compute instance type [optimal]:
ERROR: optimal is not an acceptable value for Compute instance type
Compute instance type [optimal]:
ERROR: optimal is not an acceptable value for Compute instance type
Compute instance type [optimal]: t2.micro
Automate VPC creation? (y/n) [n]:
Allowed values for VPC ID:
1. vpc-2b2d2a43 | 5 subnets inside
VPC ID [vpc-2b2d2a43]: 1
Automate Subnet creation? (y/n) [y]:
Allowed values for Network Configuration:
1. Master in a public subnet and compute fleet in a private subnet
2. Master and compute fleet in the same public subnet
Network Configuration [Master in a public subnet and compute fleet in a private
subnet]: 1
Creating CloudFormation stack...
Do not leave the terminal until the process has finished
Stack Name: parallelclusternetworking-pubpriv-20191116201712
Status: parallelclusternetworking-pubpriv-20191116201712 - CREATE_IN_PROGRESS
Status: DefaultRouteNoDependsOnPublic - CREATE_IN_PROGRESS
Status: DefaultRouteNoDependsOnPublic - CREATE_IN_PROGRESS
Status: DefaultRouteNoDependsOnPublic - CREATE_IN_PROGRESS
Status: RouteAssociationPrivate - CREATE_IN_PROGRESS
Status: RouteAssociationPrivate - CREATE_IN_PROGRESS
Status: RouteAssociationPrivate - CREATE_IN_PROGRESS
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: RouteAssociationPrivate - CREATE_COMPLETE
Status: NatRoutePrivate - CREATE_IN_PROGRESS
Status: NatRoutePrivate - CREATE_IN_PROGRESS
Status: NatRoutePrivate - CREATE_IN_PROGRESS
Status: parallelclusternetworking-pubpriv-20191116201712 - CREATE_COMPLETE

The stack has been created
Configuration file written to C:\Users\Regular\.parallelcluster\config
You can edit your configuration file or simply run 'pcluster create -c C:\Users\
Regular\.parallelcluster\config cluster-name' to create your cluster

(apc-ve) (base) C:\Users\Regular\apc-ve\Scripts>pcluster create capability-demo
Beginning cluster creation for cluster: capability-demo
Creating stack named: parallelcluster-capability-demo
Status: parallelcluster-capability-demo - CREATE_IN_PROGRESS
Status: parallelcluster-capability-demo - CREATE_IN_PROGRESS
Status: parallelcluster-capability-demo - CREATE_IN_PROGRESS
Status: parallelcluster-capability-demo - CREATE_IN_PROGRESS
Status: parallelcluster-capability-demo - CREATE_IN_PROGRESS
Status: SQS - CREATE_COMPLETE
Status: MasterSecurityGroup - CREATE_COMPLETE
Status: ComputeSecurityGroup - CREATE_IN_PROGRESS
Status: SQSPolicy - CREATE_IN_PROGRESS
Status: EBSCfnStack - CREATE_COMPLETE
Status: MasterENI - CREATE_COMPLETE
Status: DynamoDBTable - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_IN_PROGRESS
Status: ParallelClusterPolicies - CREATE_IN_PROGRESS
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: ParallelClusterPolicies - CREATE_COMPLETE
Status: RootInstanceProfile - CREATE_COMPLETE
Status: MasterServerLaunchTemplate - CREATE_IN_PROGRESS
Status: MasterServer - CREATE_IN_PROGRESS
Status: MasterServer - CREATE_IN_PROGRESS
Status: MasterServer - CREATE_IN_PROGRESS
Status: MasterServer - CREATE_COMPLETE
Status: ComputeServerLaunchTemplate - CREATE_COMPLETE
Status: ComputeFleet - CREATE_IN_PROGRESS
Status: ComputeFleet - CREATE_IN_PROGRESS
Status: ComputeFleet - CREATE_IN_PROGRESS
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: ComputeFleet - CREATE_COMPLETE
Status: MasterServerWaitCondition - CREATE_COMPLETE
Status: parallelcluster-capability-demo - CREATE_COMPLETE

ClusterUser: ubuntu
MasterPrivateIP: *


//ASSUME ROLE
1. Create Policy
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}

2. Create Role with that policy
3. Create Inline policy in group
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": "sts:AssumeRole",
    "Resource": "*"
  }
}
4. Login to CLI
aws sts assume-role --role-arn






```
