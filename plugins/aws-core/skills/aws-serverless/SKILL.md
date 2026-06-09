---
name: aws-serverless
description: 'AWS serverless internals: Lambda cold-start (SnapStart/provisioned-concurrency), VPC-timeout, concurrency, layers-vs-EFS, Powertools; API Gateway CORS/502-504, REST-vs-HTTP; Step Functions express-vs-standard; event source mappings (SQS/Kinesis/DDB-stream, partial-batch); EventBridge Scheduler; Durable Functions checkpoint-replay; SAM/CDK deploy errors. Skip EC2, ECS/Fargate, Amplify.'
version: 1
---

# AWS Serverless
## Overview

Domain expertise for building serverless applications on AWS. Covers Lambda configuration, API Gateway debugging, Step Functions orchestration, EventBridge patterns, event source mappings, concurrency tuning, cold start optimization, deployment with SAM/CDK, production readiness, and troubleshooting across all serverless services.

**Works best with** the [AWS MCP server](https://docs.aws.amazon.com/aws-mcp/) — enables running CLI commands, querying CloudWatch, and validating configurations directly. All guidance also works with standard AWS CLI access.

**Note:** Reference files contain specific runtime versions, quota values, and feature matrices that may change. When precision matters (e.g., deploying to production, choosing a runtime, or checking a quota), confirm values against current AWS documentation rather than relying solely on the values in these files.

## Routing

| User need | Action |
|-----------|--------|
| Building a new serverless app | Read [architecture.md](references/architecture.md) for pattern selection, then [deployment.md](references/deployment.md) for SAM/CDK templates |
| Debugging an error | Read [troubleshooting.md](references/troubleshooting.md) — starts with the 5 most common fixes |
| Optimizing performance or cost | Read [lambda.md](references/lambda.md) for cold starts and memory tuning, [production.md](references/production.md) for readiness checklist |
| Configuring event sources (SQS, DDB Streams, SNS) | Read [event-sources.md](references/event-sources.md) |
| Step Functions, EventBridge, or orchestration | Read [orchestration.md](references/orchestration.md) |
| Concurrency configuration | Read [concurrency.md](references/concurrency.md) |
| API Gateway setup | Read [api-gateway.md](references/api-gateway.md) |
| Common anti-patterns | Read the anti-patterns section in [production.md](references/production.md) |
| Starting with Powertools | Use [powertools-handler.py](assets/powertools-handler.py) as a template |
| Spans multiple areas | Read the most specific reference first, then consult others as needed |

## Files

| File | Content |
|------|---------|
| [lambda.md](references/lambda.md) | Runtime, memory/CPU, cold starts, SnapStart, layers, containers |
| [api-gateway.md](references/api-gateway.md) | REST vs HTTP API, stages, auth, throttling, mapping |
| [event-sources.md](references/event-sources.md) | SQS, DDB Streams, SNS, S3, Kinesis triggers |
| [orchestration.md](references/orchestration.md) | Step Functions, EventBridge rules/pipes/scheduler |
| [concurrency.md](references/concurrency.md) | Reserved vs provisioned, scaling, ESM concurrency |
| [architecture.md](references/architecture.md) | Patterns, reference architectures, service selection |
| [deployment.md](references/deployment.md) | SAM/CDK resource types, globals, fast iteration |
| [production.md](references/production.md) | Readiness checklist, observability, anti-patterns |
| [troubleshooting.md](references/troubleshooting.md) | Error → cause → fix for all serverless services |
