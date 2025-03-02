# DeadLetterConfig<a name="sam-property-statemachine-statemachinescheduledeadletterconfig"></a>

The object used to specify the Amazon Simple Queue Service \(Amazon SQS\) queue where EventBridge sends events after a failed target invocation\. Invocation can fail, for example, when sending an event to a state machine that doesn’t exist, or insufficient permissions to invoke the state machine\. For more information, see [Event retry policy and using dead\-letter queues](https://docs.aws.amazon.com/eventbridge/latest/userguide/rule-dlq.html) in the *Amazon EventBridge User Guide*\.

## Syntax<a name="sam-property-statemachine-statemachinescheduledeadletterconfig-syntax"></a>

To declare this entity in your AWS Serverless Application Model \(AWS SAM\) template, use the following syntax\.

### YAML<a name="sam-property-statemachine-statemachinescheduledeadletterconfig-syntax.yaml"></a>

```
  [Arn](#sam-statemachine-statemachinescheduledeadletterconfig-arn): String
  [QueueLogicalId](#sam-statemachine-statemachinescheduledeadletterconfig-queuelogicalid): String
  [Type](#sam-statemachine-statemachinescheduledeadletterconfig-type): String
```

## Properties<a name="sam-property-statemachine-statemachinescheduledeadletterconfig-properties"></a>

 `Arn`   <a name="sam-statemachine-statemachinescheduledeadletterconfig-arn"></a>
The Amazon Resource Name \(ARN\) of the Amazon SQS queue specified as the target for the dead\-letter queue\.  
Specify either the `Type` property or `Arn` property, but not both\.
*Type*: String  
*Required*: No  
*AWS CloudFormation compatibility*: This property is passed directly to the `[Arn](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-events-rule-deadletterconfig.html#cfn-events-rule-deadletterconfig-arn)` property of the `AWS::Events::Rule` `DeadLetterConfig` data type\.

 `QueueLogicalId`   <a name="sam-statemachine-statemachinescheduledeadletterconfig-queuelogicalid"></a>
The custom name of the dead letter queue that AWS SAM creates if `Type` is specified\.  
If the `Type` property is not set, this property is ignored\.
*Type*: String  
*Required*: No  
*AWS CloudFormation compatibility*: This property is unique to AWS SAM and doesn't have an AWS CloudFormation equivalent\.

 `Type`   <a name="sam-statemachine-statemachinescheduledeadletterconfig-type"></a>
The type of the queue\. When this property is set, AWS SAM automatically creates a dead\-letter queue and attaches necessary [resource\-based policy](https://docs.aws.amazon.com/eventbridge/latest/userguide/rule-dlq.html#dlq-perms) to grant permission to rule resource to send events to the queue\.  
Specify either the `Type` property or `Arn` property, but not both\.
*Valid values*: `SQS`  
*Type*: String  
*Required*: No  
*AWS CloudFormation compatibility*: This property is unique to AWS SAM and doesn't have an AWS CloudFormation equivalent\.

## Examples<a name="sam-property-statemachine-statemachinescheduledeadletterconfig--examples"></a>

### DeadLetterConfig<a name="sam-property-statemachine-statemachinescheduledeadletterconfig--examples--deadletterconfig"></a>

DeadLetterConfig

#### YAML<a name="sam-property-statemachine-statemachinescheduledeadletterconfig--examples--deadletterconfig--yaml"></a>

```
DeadLetterConfig:
  Type: SQS
  QueueLogicalId: MyDLQ
```