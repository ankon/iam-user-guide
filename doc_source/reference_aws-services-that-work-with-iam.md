# AWS Services That Work with IAM<a name="reference_aws-services-that-work-with-iam"></a>

The AWS services listed below are grouped by their [AWS product categories](https://aws.amazon.com/products/) and include information about what IAM features they support:
+ **Service** – You can choose the name of a service to view the AWS documentation about IAM authorization and access for that service\.
+ **Actions** – You can specify individual actions in a policy\. If the service does not support this feature, then **All actions** is selected in the [visual editor](access_policies_create.md#access_policies_create-visual-editor)\. In a JSON policy document, you must use `*` in the `Action` element\. For a list of actions in each service, see [Actions, Resources, and Condition Keys for AWS Services](reference_policies_actions-resources-contextkeys.md)\.
+ **Resource\-level permissions** – You can use [ARNs](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html) to specify individual resources in the policy\. If the service does not support this feature, then **All resources** is chosen in the [policy visual editor](access_policies_create.md#access_policies_create-visual-editor)\. In a JSON policy document, you must use `*` in the `Resource` element\. Some actions, such as `List*` actions, do not support specifying an ARN because they are designed to return multiple resources\. If a service supports this feature for some resources but not others, it is indicated by yellow cells in the table\. See the documentation for that service for more information\.
+ **Resource\-based policies** – You can attach resource\-based policies to a resource within the service\. Resource\-based policies include a `Principal` element to specify which IAM identities can access that resource\. For more information, see [Identity\-Based Policies and Resource\-Based Policies](access_policies_identity-vs-resource.md)\.
+ **Authorization based on tags** – You can use [resource tags](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/tag-editor.html) in the condition of a policy to control access to a resource in the service\. You do this using the [`aws:ResourceTag`](reference_policies_condition-keys.md#condition-keys-resourcetag) global condition key or service\-specific tags, such as [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ExamplePolicies_EC2.html#iam-example-taggingresources](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ExamplePolicies_EC2.html#iam-example-taggingresources)\. For more information about defining permissions based on attributes such as tags, see [What Is ABAC for AWS?](introduction_attribute-based-access-control.md)\.
+ **Temporary credentials** – Users signed in with federation, a cross\-account role, or a [service role](id_roles_terms-and-concepts.md#iam-term-service-role) can access the service\. Temporary security credentials are obtained by calling AWS STS API operations like [AssumeRole](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html) or [GetFederationToken](https://docs.aws.amazon.com/STS/latest/APIReference/API_GetFederationToken.html)\. For more information, see [Temporary Security Credentials](id_credentials_temp.md)\. 
+ **Service\-linked roles** – A [service\-linked role](id_roles_terms-and-concepts.md#iam-term-service-linked-role) gives the service permission to access resources in other services to complete an action on your behalf\. Choose the `Yes` link to see the documentation for services that support these roles\. For more information, see [Using Service\-Linked Roles](using-service-linked-roles.md)\.
+ **More information** – If a service doesn't fully support a feature, you can review the footnotes for an entry to view the limitations and links to related information\.

## Compute Services<a name="compute_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS Batch](https://docs.aws.amazon.com/batch/latest/userguide/IAM_policies.html)  | Yes | [Yes](https://docs.aws.amazon.com/batch/latest/userguide/batch-supported-iam-actions-resources.html) | No | No | Yes | No | 
|  [Compute Optimizer](https://docs.aws.amazon.com/compute-optimizer/latest/ug/security-iam.html)  | Yes | No | No | No | Yes | No | 
|  [Amazon Elastic Compute Cloud \(Amazon EC2\)](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UsingIAM.html)  | Yes | Yes | No | [Yes](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html#tag-resources) | Yes | Yes¹ | 
|  [Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/latest/userguide/control-access-using-iam.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/autoscaling/ec2/userguide/autoscaling-service-linked-role.html) | 
|  [Amazon EC2 Image Builder](https://docs.aws.amazon.com/imagebuilder/latest/userguide/security-iam.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/AWSHowTo.iam.html)  | Yes | Yes | No | [Yes](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/AWSHowTo.iam.policies.access-tags.html) | Yes | [Yes](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-service-linked-roles.html) | 
|  [Amazon Elastic Container Registry \(Amazon ECR\)](https://docs.aws.amazon.com/AmazonECR/latest/userguide/ECR_IAM_policies.html)  | Yes | Yes | Yes | Yes | Yes | No | 
|  [Amazon Elastic Container Service \(Amazon ECS\)](https://docs.aws.amazon.com/AmazonECS/latest/developerguide//IAM_policies.html)  | Yes | Yes² | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/using-service-linked-roles.html) | 
|  [Amazon Elastic Kubernetes Service \(Amazon EKS\)](https://docs.aws.amazon.com/eks/latest/userguide/IAM_policies.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Elastic Inference](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-inference.html)  | Yes | Yes | Yes | No | No | No | 
|  [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/index.html?UsingIAM.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/elb-service-linked-roles.html) | 
|  [AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-auth-and-access-control.html)  | Yes | Yes | [Yes](https://docs.aws.amazon.com/lambda/latest/dg/access-control-resource-based.html) | No | Yes | [Yes³](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-edge-permissions.html#using-service-linked-roles) | 
|  [Amazon Lightsail](https://lightsail.aws.amazon.com/ls/docs/all) | Yes | Yes | No | Yes | Yes | No | 

¹ Amazon EC2 service\-linked roles cannot be created using the AWS Management Console, and can be used only for the following features: [Scheduled Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-scheduled-instances.html#service-linked-roles-scheduled-instances), [Spot Instance Requests](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#service-linked-roles-spot-instance-requests), [Spot Fleet Requests](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-fleet-requests.html#service-linked-roles-spot-fleet-requests) 

² Only some Amazon EC2 actions [support resource\-level permissions](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-supported-iam-actions-resources.html)\.

³ AWS Lambda doesn't have service\-linked roles, but Lambda@Edge does\. For more information, see [Service\-Linked Roles for Lambda@Edge](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-edge-permissions.html#using-service-linked-roles) in the Amazon CloudFront Developer Guide\.

## Storage Services<a name="storage_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/security-considerations.html)  | Yes | Yes | Yes | No | Yes | No | 
|  [Amazon Elastic Block Store \(Amazon EBS\)](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using                 .html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Elastic File System \(Amazon EFS\)](https://docs.aws.amazon.com/efs/latest/ug/auth-and-access-control.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/efs/latest/ug/auth-and-access-control.html) | 
|  [Amazon FSx](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/access-control-overview.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/using-service-linked-roles.html) | 
|  [Amazon S3 Glacier](https://docs.aws.amazon.com/amazonglacier/latest/dev/auth-and-access-control.html)  | Yes | Yes | Yes | Yes | Yes | No | 
|  [AWS Import/Export](https://docs.aws.amazon.com/AWSImportExport/latest/DG/using-iam.html)  | Yes | No | No | No | Yes | No | 
|  [AWS Migration Hub](https://docs.aws.amazon.com/server-migration-service/latest/userguide/auth-and-access-control.html)  | Yes | Yes | No | No | Yes | No | 
|  [Amazon Simple Storage Service \(Amazon S3\)](https://docs.aws.amazon.com/AmazonS3/latest/dev/s3-access-control.html)  | Yes | Yes | Yes | [Yes¹](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-tagging.html) | Yes | No | 
| [AWS Snowball](https://docs.aws.amazon.com/snowball/latest/ug/auth-access-control.html) | Yes | No | No | No | Yes | No | 
| [AWS Snowball Edge](https://docs.aws.amazon.com/snowball/latest/developer-guide/authentication-and-access-control.html) | Yes | No | No | No | No | No | 
|  [AWS Storage Gateway](https://docs.aws.amazon.com/storagegateway/latest/userguide/UsingIAMWithStorageGateway.html)  | Yes | Yes | No | Yes | Yes | No | 

¹ Amazon S3 supports tag\-based authorization for only object resources\. 

## Database Services<a name="database_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/UsingIAMWithDDB.html)  | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/using-service-linked-roles.html) | 
|  [Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/IAM.html)  | Yes | No¹ | No | No | Yes | [Yes](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/using-service-linked-roles.html) | 
|  [AWS Managed Apache Cassandra Service \(MCS\)](https://docs.aws.amazon.com/mcs/latest/developerguide/assets.html)  | Yes | Yes | No | No | Yes | No | 
|  [Amazon Quantum Ledger Database \(Amazon QLDB\)](https://docs.aws.amazon.com/qldb/latest/developerguide/security-iam.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Redshift](https://docs.aws.amazon.com/redshift/latest/mgmt/redshift-iam-authentication-access-control.html)  | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/redshift/latest/mgmt/using-service-linked-roles.html) | 
|  [Amazon Relational Database Service \(Amazon RDS\)](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAM.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAM.ServiceLinkedRoles.html) | 
|  [Amazon RDS Data API](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAM.html)  | Yes | No | No | No | Yes | No | 
|  [Amazon SimpleDB](https://docs.aws.amazon.com/AmazonSimpleDB/latest/DeveloperGuide/UsingIAMWithSDB.html)  | Yes | Yes | No | No | Yes | No | 

¹ You cannot specify ElastiCache resource ARNs in a policy, but when seeding a cluster or replication, you can specify an Amazon S3 ARN with ElastiCache actions\. group\.

## Developer Tools Services<a name="deploy_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS Cloud9](https://docs.aws.amazon.com/cloud9/latest/user-guide/auth-and-access-control.html)  | Yes | Yes | Yes | Yes | Yes | [Yes](https://docs.aws.amazon.com/cloud9/latest/user-guide/using-service-linked-roles.html) | 
|  [CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/auth-and-access-control.html)  | Yes | Yes | Yes¹ | Yes² | Yes | No | 
|  [CodeCommit](https://docs.aws.amazon.com/codecommit/latest/userguide/auth-and-access-control.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS CodeDeploy](https://docs.aws.amazon.com/codedeploy/latest/userguide/access-permissions.html)  | Yes | Yes | No | No | Yes | No | 
|  [CodePipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/access-permissions.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS CodeStar](https://docs.aws.amazon.com/codestar/latest/userguide/access-permissions.html)  | Yes | Yes¹ | No | Yes | Yes | No | 
|  [AWS CodeStar Notifications](https://docs.aws.amazon.com/codestar-notifications/latest/userguide/security.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/codestar-notifications/latest/userguide/using-service-linked-roles.html) | 
| [AWS X\-Ray](https://docs.aws.amazon.com/xray/latest/devguide/xray-permissions.html) | Yes | No | No | No | Yes | No | 

¹ CodeBuild supports cross\-account resource sharing via AWS RAM\.

² CodeBuild supports authorization based on tags for project\-based actions\.

## Security, Identity, and Compliance Services<a name="admin_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS Certificate Manager Private Certificate Authority \(ACM\)](https://docs.aws.amazon.com/acm-pca/latest/userguide/auth-toplevel.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS Artifact](https://docs.aws.amazon.com/artifact/latest/ug/getting-started.html)  | Yes | Yes | No | No | Yes | No | 
|  [AWS Certificate Manager \(ACM\)](https://docs.aws.amazon.com/acm/latest/userguide/authen-toplevel.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS CloudHSM](https://docs.aws.amazon.com/cloudhsm/latest/userguide/prerequisites.html#permissions-for-cloudhsm)  | Yes | No | No | No | Yes | Yes | 
|  [AWS CloudHSM Classic](https://docs.aws.amazon.com/cloudhsm/classic/userguide/iam-policy.html)  | Yes | No | No | No | No | No | 
|  [Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/resource-permissions.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Detective](https://docs.aws.amazon.com/detective/latest/adminguide/security-iam.html)  | Yes | Yes | No | No | Yes | No | 
|  [AWS Directory Service](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/iam_policy.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html)  | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/guardduty/latest/ug/using-service-linked-roles.html) | 
|  [AWS Identity and Access Management \(IAM\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_permissions-required.html)  | Yes | Yes | Yes¹ | [Yes²](access_iam-tags.md) | Yes³ | No | 
|  [IAM Access Analyzer](https://docs.aws.amazon.com/IAM/latest/UserGuide/access-analyzer-access.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/IAM/latest/UserGuide/access-analyzer-using-service-linked-roles.html) | 
|  [Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/userguide/inspector_introduction.html)  | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/inspector/latest/userguide/inspector_slr.html) | 
|  [AWS Key Management Service \(AWS KMS\)](https://docs.aws.amazon.com/kms/latest/developerguide/control-access.html)  | Yes | Yes | Yes | No | Yes | [Yes](https://docs.aws.amazon.com/kms/latest/developerguide/using-service-linked-roles.html) | 
|  [Amazon Macie ](https://docs.aws.amazon.com/macie/latest/userguide/macie-access-control.html)  | Yes | No | No | No | Yes | Yes | 
|  [AWS Resource Access Manager \(AWS RAM\)](https://docs.aws.amazon.com/ram/latest/userguide/control-access.html)  | Yes | Yes | No | Yes | Yes | No | 
| [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/auth-and-access.html) | Yes | Yes | [Yes](https://docs.aws.amazon.com/secretsmanager/latest/userguide/auth-and-access_resource-based-policies.html) | Yes | Yes | No | 
| [AWS Security Hub](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-settingup.html) | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/securityhub/latest/userguide/using-service-linked-roles.html) | 
|  [AWS Single Sign\-On \(AWS SSO\)](https://docs.aws.amazon.com/singlesignon/latest/userguide/iam-auth-access.html)  | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/singlesignon/latest/userguide/using-service-linked-roles.html) | 
|  [AWS SSO Directory](https://docs.aws.amazon.com/singlesignon/latest/userguide/iam-auth-access.html)  | Yes | No | No | No | Yes | No | 
|  [AWS Security Token Service \(AWS STS\)](https://docs.aws.amazon.com/STS/latest/UsingSTS/TokenPermissions.html)  | Yes | Yes⁴ | No | Yes | Yes⁵ | No | 
|  [AWS Shield Advanced](https://docs.aws.amazon.com/waf/latest/developerguide/shield-chapter.html)  | Yes | No | No | No | Yes | No | 
|  [AWS WAF](https://docs.aws.amazon.com/waf/latest/developerguide/waf-auth-and-access-control.html)  | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/waf/latest/developerguide/using-service-linked-roles.html) | 

¹ IAM supports only one type of resource\-based policy called a role *trust policy*, which is attached to an IAM role\. For more information, see [Granting a User Permissions to Switch Roles](id_roles_use_permissions-to-switch.md)\.

² IAM supports tag\-based access control for only user and role resources\.

³ Only some of the API actions for IAM can be called with temporary credentials\. For more information, see [Comparing your API options](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html)

⁴ AWS STS does not have "resources," but does allow restricting access in a similar way to users\. For more information, see [Denying Access to Temporary Security Credentials by Name](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_disable-perms.html#denying-access-to-credentials-by-name)\. 

⁵ Only some of the API operations for AWS STS support calling with temporary credentials\. For more information, see [Comparing your API options](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html)\.

## Machine Learning Services<a name="machine_learning"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
| [Amazon Comprehend](https://docs.aws.amazon.com/comprehend/latest/dg/auth-and-access-control.html) | Yes | No | No | Yes | Yes | No | 
| [AWS DeepRacer](https://docs.aws.amazon.com/deepracer/latest/developerguide/deepracer-security.html) | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/deepracer/latest/developerguide/deepracer-understand-required-permissions-and-iam-roles.html) | 
|  [Forecast](https://docs.aws.amazon.com/forecast/latest/dg/authentication-and-access-control.html)  | Yes | Yes | No | No | Yes | No | 
|  [Amazon Fraud Detector](https://docs.aws.amazon.com/frauddetector/latest/ug/set-up.html#set-up-iam-admin)  | Yes | No | No | No | Yes | No | 
|  [Amazon Kendra](https://docs.aws.amazon.com/kendra/latest/dg/security-iam.html)  | Yes | Yes | No | No | Yes | No | 
| [Amazon Lex](https://docs.aws.amazon.com/lex/latest/dg/auth-and-access-control.html) | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/lex/latest/dg/howitworks-service-permissions.html) | 
|  [Amazon Machine Learning](https://docs.aws.amazon.com/machine-learning/latest/dg/reference.html#controlling-access-to-amazon-ml-resources-by-using-iam)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Personalize](https://docs.aws.amazon.com/personalize/latest/dg/authentication-and-access-control.html)  | Yes | Yes | No | No | Yes | No | 
|  [Amazon Polly](https://docs.aws.amazon.com/polly/latest/dg/authentication-and-access-control.html)  | Yes | Yes | No | No | Yes | No | 
|  [Amazon Rekognition](https://docs.aws.amazon.com/rekognition/latest/dg/authentication-and-access-control.html)  | Yes | Yes | No | No | Yes | No | 
|  [Amazon SageMaker](https://docs.aws.amazon.com/sagemaker/latest/dg/authentication-and-access-control.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Textract](https://docs.aws.amazon.com/textract/latest/dg/authentication-and-access-control.html)  | Yes | Yes | No | No | No | No | 
| [Amazon Transcribe](https://docs.aws.amazon.com/transcribe/latest/dg/auth-and-access-control.html) | Yes | No | No | No | Yes | No | 
| [Amazon Translate](https://docs.aws.amazon.com/translate/latest/dg/auth-and-access-control.html)  | Yes | No | No | No | Yes | No | 

## Management and Governance Services<a name="management_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Application Auto Scaling](https://docs.aws.amazon.com/autoscaling/application/userguide/auth-and-access-control.html)  | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/autoscaling/application/userguide/application-auto-scaling-service-linked-roles.html) | 
|  [AWS Auto Scaling](https://docs.aws.amazon.com/autoscaling/plans/userguide/auth-and-access-control.html)  | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/autoscaling/plans/userguide/aws-auto-scaling-service-linked-roles.html) | 
|  [AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-access-control.html)  | Yes | Yes | No | No | Yes | No | 
|  [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/UsingIAM.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/using-service-linked-roles.html)¹ | 
|  [Amazon CloudWatch Events](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/EventsPoliciesRolesAccessControl.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon CloudWatch Logs ](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/auth-and-access-control-cwl.html)  | Yes | Yes | Yes | Yes | Yes | No | 
|  [Amazon CloudWatch Synthetics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Synthetics_Canaries.html)  | Yes | Yes | No | No | Yes | No | 
|  [AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/recommended-iam-permissions-using-aws-config-console-cli.html)  | Yes | Yes² | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/config/latest/developerguide/using-service-linked-roles.html) | 
|  [Amazon Data Lifecycle Manager](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/snapshot-lifecycle.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS Health](https://docs.aws.amazon.com/health/latest/ug/controlling-access.html)  | Yes | No | No | No | Yes | No | 
|  [AWS OpsWorks](https://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html)  | Yes | Yes | No | No | Yes | No | 
|  [AWS OpsWorks for Chef Automate](https://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html)  | Yes | Yes | No | No | Yes | No | 
| [AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions_overview.html) | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html#orgs_integrate_services-using_slrs) | 
|  [AWS Resource Groups](https://docs.aws.amazon.com/ARG/latest/userguide/gettingstarted-prereqs.html#rg-permissions)  | Yes | Yes | No | Yes | Yes³ | No | 
|  [Resource Groups Tagging API](https://docs.aws.amazon.com/resourcegroupstagging/latest/APIReference/Welcome.html)  | Yes | No | No | No | Yes | No | 
|  [AWS Service Catalog](https://docs.aws.amazon.com/servicecatalog/latest/adminguide/permissions.html)  | Yes | No | No | Yes⁴ | Yes | No | 
|  [AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/auth-and-access-control.html)  | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/systems-manager/latest/userguide/using-service-linked-roles.html) | 
| [AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/ta-iam/) | Yes⁵ | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/awssupport/latest/user/using-service-linked-roles-ta.html) | 

¹ Amazon CloudWatch service\-linked roles cannot be created using the AWS Management Console, and support only the [ Alarm Actions](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/UsingAlarmActions.html) feature\.

² AWS Config supports resource\-level permissions for multi\-account multi\-Region data aggregation and AWS Config Rules\. For a list of supported resources, see the **Multi\-Account Multi\-Region Data Aggregation** section and **AWS Config Rules** section of [AWS Config API Guide](https://docs.aws.amazon.com/config/latest/APIReference/Welcome.html)\.

³ Users can assume a role with a policy that allows AWS Resource Groups operations\.

⁴ AWS Service Catalog supports tag\-based access control for only actions that match API operations with one resource in the input\.

⁵ API access to Trusted Advisor is through the AWS Support API and is controlled by AWS Support IAM policies\.

## Migration and Transfer Services<a name="migration_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS Application Discovery Service](https://docs.aws.amazon.com/application-discovery/latest/userguide/setting-up.html)  | Yes | No | No | No | No | [Yes](https://docs.aws.amazon.com/application-discovery/latest/userguide/setting-up.html#using-service-linked-roles) | 
|  [AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Security.IAMPermissions.html)  | Yes | Yes | Yes¹ | Yes | Yes | No | 
|  [AWS Migration Hub](https://docs.aws.amazon.com/server-migration-service/latest/userguide/auth-and-access-control.html)  | Yes | Yes | No | No | Yes | No | 
|  [AWS Server Migration Service](https://docs.aws.amazon.com/server-migration-service/latest/userguide/permissions-roles.html)  | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/server-migration-service/latest/userguide/using-service-linked-roles.html) | 

¹ You can create and modify policies that are attached to AWS KMS encryption keys you create to encrypt data migrated to supported target endpoints\. The supported target endpoints include Amazon Redshift and Amazon S3\. For more information, see [Creating and Using AWS KMS Keys to Encrypt Amazon Redshift Target Data](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Target.Redshift.html#CHAP_Target.Redshift.KMSKeys) and [Creating AWS KMS Keys to Encrypt Amazon S3 Target Objects](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Target.S3.html#CHAP_Target.S3.KMSKeys) in the *AWS Database Migration Service User Guide*\.

## Mobile Services<a name="mobile_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS Amplify](https://docs.aws.amazon.com/amplify/latest/userguide/welcome.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS Device Farm](https://docs.aws.amazon.com/devicefarm/latest/developerguide/permissions.html)  | Yes | Yes | No | Yes | Yes | No | 

## Networking and Content Delivery Services<a name="networking_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/permissions.html)  | Yes | Yes | Yes | Yes | Yes | Yes | 
|   [AWS App Mesh](https://docs.aws.amazon.com//app-mesh/latest/userguide/IAM_policies.html)   | Yes | Yes | No | Yes | Yes | [Yes](https://docs.aws.amazon.com//app-mesh/latest/userguide/using-service-linked-roles.html) | 
|   [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/auth-and-access-control.html)   | Yes¹ | Yes | No | Yes | Yes | [Yes⁴](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-edge-permissions.html#using-service-linked-roles) | 
|   [AWS Cloud Map](https://docs.aws.amazon.com/cloud-map/latest/dg/auth-and-access-control.html)   | Yes | Yes | No | No | Yes | No | 
|  [AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/using_iam.html)  | Yes | Yes | No | [Yes](https://docs.aws.amazon.com/directconnect/latest/UserGuide/using_tags.html) | Yes | No | 
|  [AWS Global Accelerator](https://docs.aws.amazon.com/global-accelerator/latest/dg/auth-and-access-control.html)  | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/global-accelerator/latest/dg/using-service-linked-roles.html) | 
|  [Network Manager](https://docs.aws.amazon.com/vpc/latest/tgw/nm-security-iam.html)  | Yes | Yes | Yes | Yes | Yes | [Yes](https://docs.aws.amazon.com/vpc/latest/tgw/nm-service-linked-roles.html) | 
|  [Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide//auth-and-access-control.html)  | Yes | Yes | No | No | Yes | No | 
|  [Amazon Route 53 Resolver](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide//auth-and-access-control.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Virtual Private Cloud \(Amazon VPC\)](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_IAM.html)  | Yes | Yes² | Yes³ | No | Yes | No | 

¹ CloudFront does not support action\-level permissions for creating CloudFront key pairs\. You must use an AWS account root user to create a CloudFront key pair\. For more information, see [Creating CloudFront Key Pairs for Your Trusted Signers](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-trusted-signers.html#private-content-creating-cloudfront-key-pairs) in the *Amazon CloudFront Developer Guide*\. 

² In an IAM user policy, you cannot restrict permissions to a specific Amazon VPC endpoint\. Any `Action` element that includes the `ec2:*VpcEndpoint*` or `ec2:DescribePrefixLists` API actions must specify "`"Resource": "*"`"\. For more information, see [Controlling the Use of Endpoints](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints.html#vpc-endpoints-iam-access) in the *Amazon VPC User Guide*\. 

³ Amazon VPC supports attaching a single resource policy to a VPC endpoint to restrict what can be accessed through that endpoint\. For more information about using resource\-based policies to control access to resources from specific Amazon VPC endpoints, see [Using Endpoint Policies](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints.html#vpc-endpoint-policies) in the *Amazon VPC User Guide*\.

⁴ Amazon CloudFront doesn't have service\-linked roles, but Lambda@Edge does\. For more information, see [Service\-Linked Roles for Lambda@Edge](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-edge-permissions.html#using-service-linked-roles) in the Amazon CloudFront Developer Guide\.

## Media Services<a name="media_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon Elastic Transcoder](https://docs.aws.amazon.com/elastictranscoder/latest/developerguide/security.html)  | Yes | Yes | No | No | Yes | No | 
| [AWS Elemental MediaConnect](https://docs.aws.amazon.com/mediaconnect/latest/ug/auth-and-access-control.html) | Yes | Yes | No | No | Yes | No | 
| [AWS Elemental MediaConvert](https://docs.aws.amazon.com/mediaconvert/latest/ug/auth-and-access-control.html) | Yes | Yes | No | [Yes](https://docs.aws.amazon.com/mediaconvert/latest/ug/example-policies.html#example-policy-tag-based-access-control-using-resource-tags) | Yes | No | 
| [AWS Elemental MediaLive](https://docs.aws.amazon.com/medialive/latest/ug/setting-up-for-production.html) | Yes | Yes | Yes | Yes | Yes | No | 
| [AWS Elemental MediaPackage](https://docs.aws.amazon.com/mediapackage/latest/ug/setting-up.html) | Yes | Yes | No | Yes | Yes | No | 
| [AWS Elemental MediaStore](https://docs.aws.amazon.com/mediastore/latest/ug/setting-up.html) | Yes | Yes | Yes | No | Yes | No | 
| [AWS Elemental MediaTailor](https://docs.aws.amazon.com/mediatailor/latest/ug/setting-up.html) | Yes | Yes | No | Yes | Yes | No | 
| [Kinesis Video Streams](https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/how-iam.html) | Yes | Yes | No | Yes | Yes | No | 

## Analytics Services<a name="analytics_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon Athena](https://docs.aws.amazon.com/athena/latest/ug/access.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon CloudSearch](https://docs.aws.amazon.com/cloudsearch/latest/developerguide/configureaccess.html)  | Yes | Yes | No | No | Yes | No | 
|  [AWS Data Exchange](https://docs.aws.amazon.com/data-exchange/latest/userguide/auth-access.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS Data Pipeline](https://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-concepts-roles.html)  | Yes | No | No | Yes | Yes | No | 
|  [Amazon Elasticsearch Service](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-access-policies)  | Yes | Yes | Yes | No | Yes | [Yes](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/slr-es.html) | 
|  [Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-access-iam.html)  | Yes | No | No | Yes | Yes | [Yes](https://docs.aws.amazon.com/emr/latest/ManagementGuide/using-service-linked-roles.html) | 
|  [AWS Glue](https://docs.aws.amazon.com/glue/latest/dg/authentication-and-access-control.html)  | Yes | Yes | Yes | [Yes](https://docs.aws.amazon.com/glue/latest/dg/monitor-tags.html) | Yes | No | 
|  [Amazon Kinesis Data Analytics](https://docs.aws.amazon.com/kinesisanalytics/latest/dev/authentication-and-access-control.html)  | Yes | Yes | No | Yes | Yes | No | 
| [Amazon Kinesis Data Firehose](https://docs.aws.amazon.com/firehose/latest/dev/controlling-access.html) | Yes | Yes | No | Yes | Yes | No | 
| [Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/controlling-access.html) | Yes | Yes | No | No | Yes | No | 
| [Amazon Managed Streaming for Apache Kafka \(MSK\)](https://docs.aws.amazon.com/msk/latest/developerguide/security_iam_service-with-iam.html) | Yes | Yes | No | Yes | Yes | No | 
| [Amazon QuickSight](https://docs.aws.amazon.com/quicksight/latest/user/managing-access.html) | Yes | Yes | No | No | Yes | No | 

## Application Integration Services<a name="app_integration_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/auth-and-access-control-eventbridge.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon EventBridge Schemas](https://docs.aws.amazon.com/eventbridge/latest/userguide/auth-and-access-control-eventbridge.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon MQ](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/amazon-mq-security.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Simple Notification Service \(Amazon SNS\)](https://docs.aws.amazon.com/sns/latest/dg/UsingIAMwithSNS.html)  | Yes | Yes | Yes | No | Yes | No | 
|  [Amazon Simple Queue Service \(Amazon SQS\)](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/UsingIAM.html)  | Yes | Yes | Yes | No | Yes | No | 
|  [AWS Step Functions](https://docs.aws.amazon.com/step-functions/latest/dg/security.html)  | Yes | Yes | No | [Yes](https://docs.aws.amazon.com/step-functions/latest/dg/tag-based-policies.html) | Yes | No | 
|  [Amazon Simple Workflow Service \(Amazon SWF\)](https://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html)  | Yes | Yes | No | Yes | Yes | No | 

## Business Applications Services<a name="enterprise_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
| Alexa for Business  | Yes | Yes | No | No | Yes | No | 
| [Amazon Chime](https://docs.aws.amazon.com/chime/latest/ag/control-access.html) | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/chime/latest/ag/using-service-linked-roles.html) | 
|  [Amazon WorkMail](https://docs.aws.amazon.com/workmail/latest/adminguide/iam_users_groups.html)  | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/workmail/latest/adminguide/using-service-linked-roles.html) | 

## Satellite Services<a name="satellite_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS Ground Station](https://docs.aws.amazon.com/ground-station/latest/ug/auth-and-access-control.html)  | Yes | Yes | No | Yes | Yes | No | 

## Internet of Things Services<a name="iot_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS IoT](https://docs.aws.amazon.com/iot/latest/developerguide/iot-security-identity.html)  | [Yes](https://docs.aws.amazon.com/iot/latest/developerguide/policy-actions.html) | [Yes](https://docs.aws.amazon.com/iot/latest/developerguide/action-resources.html) | Yes¹ | [Yes](https://docs.aws.amazon.com/iot/latest/developerguide/tagging-iot-iam.html) | Yes | No | 
|  [AWS IoT Analytics](https://docs.aws.amazon.com/iotanalytics/latest/userguide/security.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS IoT Events](https://docs.aws.amazon.com/iotevents/latest/developerguide/security-iam.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS IoT Greengrass](https://docs.aws.amazon.com/greengrass/latest/userguide/gg-ug.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [AWS IoT Things Graph](https://docs.aws.amazon.com/thingsgraph/latest/ug/iot-tg-security.html)  | Yes | No | No | No | Yes | No | 
|  [AWS IoT SiteWise](https://docs.aws.amazon.com/iot-sitewise/latest/userguide/set-up-aws-account.html)  | Yes | Yes | No | No | Yes | No | 

¹ Devices connected to AWS IoT are authenticated by using X\.509 certificates or using Amazon Cognito Identities\. You can attach AWS IoT policies to an X\.509 certificate or Amazon Cognito Identity to control what the device is authorized to do\. For more information, see [Security and Identity for AWS IoT](https://docs.aws.amazon.com/iot/latest/developerguide/iot-security-identity.html) in the *AWS IoT Developer Guide*\. 

## Robotics Services<a name="robotics_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [RoboMaker](https://docs.aws.amazon.com/robomaker/latest/dg/what-is-robomaker.html)  | Yes | Yes | No | [Yes](https://docs.aws.amazon.com/robomaker/latest/dg/auth-and-access-control.html) | No | [Yes](https://docs.aws.amazon.com/robomaker/latest/dg/using-service-linked-roles.html) | 

## Blockchain Services<a name="blockchain_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon Managed Blockchain](https://docs.aws.amazon.com/managed-blockchain/latest/managementguide/managed-blockchain-auth-and-access-control.html)  | Yes | Yes | No | No | Yes | No | 

## Game Development Services<a name="game_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon GameLift](https://docs.aws.amazon.com/gamelift/latest/developerguide/gamelift-iam-policy-intro.html)  | Yes | No | No | No | Yes | No | 

## AR & VR Services<a name="arvr_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon Sumerian](https://docs.aws.amazon.com/sumerian/latest/userguide/sumerian-permissions.html)  | Yes | Yes | No | No | Yes | No | 

## Customer Engagement Services<a name="engagement_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon Connect](https://docs.aws.amazon.com/connect/latest/adminguide/what-is-amazon-connect.html)  | Yes | Yes | No | No | Yes | [Yes](https://docs.aws.amazon.com/connect/latest/adminguide/connect-slr.html) | 
|  [Amazon Pinpoint](https://docs.aws.amazon.com/pinpoint/latest/developerguide/permissions-actions.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon Simple Email Service \(Amazon SES\)](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/UsingWithIAM.html)  | Yes | Yes¹ | Yes | Yes | Yes² | No | 

¹ You can only use resource\-level permissions in policy statements that refer to actions related to sending email, such as `ses:SendEmail` or `ses:SendRawEmail`\. For policy statements that refer to any other actions, the Resource element can only contain `*`\.

² Only the Amazon SES API supports temporary security credentials\. The Amazon SES SMTP interface does not support SMTP credentials that are derived from temporary security credentials\. 

## End User Computing Services<a name="end-user-computing_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [Amazon AppStream](https://docs.aws.amazon.com/appstream/latest/developerguide/appstream-security.html)  | Yes | No | No | No | Yes | No | 
|  [Amazon AppStream 2\.0](https://docs.aws.amazon.com/appstream2/latest/developerguide/controlling-access.html)  | Yes | Yes | No | Yes | Yes | No | 
|  [Amazon WAM](http://docs.aws.amazon.com/wam/latest/adminguide/iam.html)  | Yes | No | No | No | Yes | No | 
|  [Amazon WorkDocs](https://docs.aws.amazon.com/workdocs/latest/adminguide/setting_up.html#iam_policies)  | Yes | No | No | No | Yes | No | 
|  [Amazon WorkLink](https://docs.aws.amazon.com/worklink/latest/ag/what-is.html) | Yes | Yes | Yes | No | Yes | [Yes](https://docs.aws.amazon.com/worklink/latest/ag/using-service-linked-roles.html) | 
|  [Amazon WorkSpaces](https://docs.aws.amazon.com/workspaces/latest/adminguide/wsp_iam.html)  | Yes | Yes | No | Yes | Yes | No | 

## Additional Resources<a name="resources_svcs"></a>


|  |  |  |  |  |  |  | 
| --- |--- |--- |--- |--- |--- |--- |
|  Service  |  Actions  |  Resource\-level permissions  | Resource\-based policies |  Authorization based on tags  |  Temporary credentials  |  Service\-linked roles  | 
|  [AWS Billing and Cost Management](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ControllingAccessWebsite.html)  | Yes | No | No | No | Yes | No | 
|  [AWS Marketplace](http://docs.aws.amazon.com/marketplace/latest/controlling-access/ControllingAccessToAWSMarketplaceSubscriptions.html)  | Yes | No | No | No | Yes | No | 
|  [AWS Private Marketplace](https://docs.aws.amazon.com/marketplace/latest/buyerguideprivate-marketplace.html)  | Yes | No | No | No | No | No | 
|  [AWS Support](https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html#accessing-support)  | Yes | No | No | No | Yes | [Yes](https://docs.aws.amazon.com/awssupport/latest/user/using-service-linked-roles-sup.html) | 