# Assignment 4 Submission

<!--
How to use this template:

1. Copy this file to submissions/assignment-4/group-<number>/submission.md
2. Replace every <answer> with your group's answer. Delete the angle brackets too.
3. Write GitHub usernames, not full names or student numbers.
-->

## About us

- Group number: 07
- Section: IV-BCSAD

## Estimate 1: the Lab 4 endpoint

Asia Pacific (Singapore), 1 million requests a month: 800,000 GET and 200,000 POST.

| Service | Settings | Monthly cost (USD) |
| --- | --- | --- |
| Amazon API Gateway | HTTP API, 1 million requests, 1 KB each | 1.25 |
| AWS Lambda | Without Free Tier, x86, 1,000,000 requests, 100 ms, 128 MB | 0.41 |
| Amazon DynamoDB | On-demand, Standard, 1 GB, 1 KB items, 0.2 million writes, 0.8 million eventually consistent reads | 0.48 |
| **Total** | | 2.14 |

## Estimate 2: the Lab 2 setup

| Service | Settings | Monthly cost (USD) |
| --- | --- | --- |
| Amazon EC2 | 1 `t3.micro`, Linux, On-Demand, 100% utilization, 8 GB gp3, detailed monitoring on | 12.51 |

Share link of our estimate: https://calculator.aws/#/estimate?id=1a60f4c4dccc2832186355dc9826266b2b118b8e

## Question

In a month with no requests at all, which costs remain in each setup, and why?

- In the serverless setup, API Gateway and AWS Lambda have no request-processing charges because there are no incoming requests or executions. However, Amazon DynamoDB still charges for data storage because the 1 GB of stored data remains even when it is not being accessed. There will be no on-demand read and write charges because no database operations are performed.
- In the EC2 setup, the instance continues to incur charges because it runs continuously throughout the month, even when there are no visitors or requests. The 8 GB gp3 EBS storage and detailed monitoring also continue to incur charges. This means that the EC2 setup still costs money even when it is idle.

## Recommendation

Five sentences. Which setup fits the Lab 4 message API at 1 million requests a month, and why? Use our two totals, our answer to the question, and the work that each setup needs from our group.

- For our Lab 4 message API, we recommend the serverless setup because it is more cost-effective for handling 1 million requests per month.
- Based on our estimates, the serverless setup costs only $2.14 per month, compared to $12.51 per month for the EC2 setup, saving $10.37 monthly.
- In a month with no requests, the serverless setup only keeps a small DynamoDB storage charge, while the EC2 instance continues to incur costs for running the server, storage, and monitoring.
- The EC2 setup would also require our group to patch the operating system and size the server for traffic, while API Gateway, Lambda, and DynamoDB are managed by AWS, which removes that server maintenance work.
- The serverless setup is also more suitable for sudden increases in traffic because it can automatically scale based on incoming requests without requiring our group to manually manage server capacity.

## Contribution

| GitHub username | What this groupmate did |
| --- | --- |
| abijeyn | Configured the Amazon API Gateway estimate and calculated the monthly request costs. |
| Dan-Ike | Configured the AWS Lambda estimate and reviewed the serverless setup's total monthly cost. |
| StarMirai | Configured the Amazon DynamoDB estimate and checked the read, write, and storage costs. |
| o4o29 | Configured the Amazon EC2 estimate and helped compare the costs and prepare the final recommendation. |
