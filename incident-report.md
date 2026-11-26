# EC2 High CPU Incident Report

## Incident Summary

A high CPU utilization event was intentionally generated on an Amazon EC2 instance to test the infrastructure monitoring and alerting solution.

Amazon CloudWatch detected the performance threshold breach and triggered an automated notification through Amazon SNS.

## Detection

Amazon CloudWatch monitored the EC2 instance CPUUtilization metric.

The CloudWatch alarm was configured to trigger when average CPU utilization exceeded 50%.

## Alerting

When the CPU threshold was exceeded, the CloudWatch alarm changed from OK to ALARM.

Amazon SNS then delivered an email notification.

## Investigation

I connected to the EC2 instance using SSH and used Linux monitoring tools to investigate the issue.

The `top` command identified multiple `yes` processes consuming CPU resources.

## Root Cause

The elevated CPU utilization was caused by CPU-intensive `yes` processes that were intentionally started to simulate a performance incident.

## Resolution

The CPU-intensive processes were stopped using:

`pkill yes`

## Validation

After remediation:

- CPU utilization returned to normal.
- CloudWatch detected the lower CPU utilization.
- The alarm transitioned from ALARM back to OK.
- The monitoring and alerting workflow operated successfully.

## Incident Response Workflow

Detect → Alert → Investigate → Resolve → Validate

## Lessons Learned

This project demonstrated how CloudWatch and SNS can provide proactive infrastructure monitoring and automated alerting.

It also demonstrated the importance of investigating the root cause, resolving the issue, and validating recovery after remediation.
