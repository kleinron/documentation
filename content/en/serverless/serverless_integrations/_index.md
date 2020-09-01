---
title: Serverless Integrations
kind: documentation
further_reading:
- link: "/serverless/serverless_integrations/plugin/"
  tag: "Datadog Serverless Plugin"
  text: "Datadog Serverless Plugin"
- link: "/serverless/serverless_integrations/macro/"
  tag: "Datadog Serverless Macro"
  text: "Datadog Serverless Macro"
- link: "/serverless/serverless_integrations/cli/"
  tag: "Datadog Serverless CLI"
  text: "Datadog Serverless CLI"
---

## Datadog Serverless Plugin

The Datadog serverless framework plugin automatically installs the Datadog Lambda library to your Python and Node.js serverless applications, and enables the collection of enhanced Lambda metrics, custom metrics, traces, and logs from your Lambda functions. See [more details][1].

## Datadog Serverless Macro

The Datadog Serverless macro for AWS CloudFormation automatically installs the Datadog Lambda library to your Python and Node.js serverless applications that are deployed using AWS CloudFormation, SAM or CDK, and enables the collection of enhanced Lambda metrics, custom metrics, traces, and logs from your Lambda functions. See [more details][2].

## Datadog Serverless CLI

The Datadog serverless CLI allows you to set up the instrumentation of your serverless applications from the command line or a CI/CD pipeline. The CLI automatically installs the Datadog Lambda library to your Python and Node.js serverless applications, and enables the collection of enhanced Lambda metrics, custom metrics, traces, and logs from your Lambda functions. See [more details][3].

## AWS Step Functions

Enable the [AWS Step Functions integration][4] to automatically get additional tags on your Lambda metrics to identify which state machines a particular function belongs to. Use these tags to get an aggregated view of your Lambda metrics and logs per Step Function on the [Serverless view][5].

1. Install the [AWS Step Functions integration][4].
2. Add the following permissions to your [Datadog IAM policy][6] to add additional tags to your Lambda metrics.

    | AWS Permission     | Description                                  |
    | ------------------ | -------------------------------------------- |
    | `states:ListStateMachines`     | List active Step Functions.   |
    | `states:DescribeStateMachine` | Get Step Function metadata, and tags.  |

## Amazon EFS for Lambda

Enable [Amazon EFS for Lambda][7] to automatically get additional tags on your Lambda metrics to identify which EFS a particular function belongs to. Use these tags to get an aggregated view of your Lambda metrics and logs per EFS on the [Serverless view][1].

1. Install the [Amazon EFS integration][8].
2. Add the following permissions to your [Datadog IAM policy][6] to collect EFS metrics from Lambda.

    | AWS Permission     | Description                                  |
    | ------------------ | -------------------------------------------- |
    | `elasticfilesystem:DescribeAccessPoints`     | Lists active EFS connected to Lambda functions. |

3. Once done, go to the [Serverless view][5] to use the new `filesystemid` tag on your Lambda functions.

{{< img src="integrations/amazon_lambda/efs_for_lambda.gif" alt="Amazon EFS for Lambda" >}}

## Lambda@Edge

Use the `at_edge`, `edge_master_name`, and `edge_master_arn` tags to get an aggregated view of your Lambda function metrics and logs as they run in Edge locations.

## Further Reading

{{< partial name="whats-next/whats-next.html" >}}


[1]: /serverless/serverless_integrations/plugin/
[2]: /serverless/serverless_integrations/macro/
[3]: /serverless/serverless_integrations/cli/
[4]: /integrations/amazon_step_functions/
[5]: https://app.datadoghq.com/functions
[6]: /integrations/amazon_web_services/#installation
[7]: /integrations/amazon_efs/#amazon-efs-for-lambda
[8]: /integrations/amazon_efs/