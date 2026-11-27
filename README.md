# AWS Cloud Infrastructure Monitoring & Alerting

## Project Overview
This project demonstrates proactive AWS infrastructure monitoring, alerting, troubleshooting, and incident response for an Amazon EC2 workload.

## Architecture
![Monitoring Architecture](architecture/17-monitoring-architecture.png)

## Monitoring Workflow
Detect → Alert → Investigate → Resolve → Validate

## AWS Services Used
- Amazon EC2
- Amazon CloudWatch
- CloudWatch Alarms
- Amazon SNS

## Technologies Used
- Amazon Linux 2023
- Linux
- SSH
- CloudWatch Metrics
- Email Notifications
- GitHub
- draw.io

## Implementation

### EC2 Monitoring
Amazon CloudWatch was configured to monitor CPU utilization for the EC2 workload.

![CPU Metric](screenshots/03-cloudwatch-cpu-metric.jpeg)

### SNS Notifications
Amazon SNS was configured to deliver infrastructure alerts through email.

![SNS Subscription](screenshots/05-sns-subscription.jpeg)

### CloudWatch Alarm
A CloudWatch alarm was configured to trigger when average CPU utilization exceeded 50%.

![Alarm Configuration](screenshots/07-cpu-alarm-condition.jpeg)

### Performance Incident Simulation
A CPU-intensive workload was intentionally generated on the EC2 instance.

![CPU Simulation](screenshots/10-high-cpu-simulation.jpeg)

### Alarm Detection
CloudWatch detected the threshold breach and transitioned the alarm to ALARM.

![Alarm Triggered](screenshots/11-alarm-triggered.jpeg)

### Automated Notification
Amazon SNS delivered an automated email notification.

![Alert Email](screenshots/12-cloudwatch-alert-email.jpeg)

### Incident Investigation
Linux monitoring tools were used to identify the CPU-intensive processes responsible for the issue.

![Investigation](screenshots/13-incident-investigation.jpeg)

### Remediation
The offending processes were stopped and CPU utilization returned to normal.

![Resolution](screenshots/14-incident-resolved.jpeg)

### Recovery Validation
CloudWatch returned the alarm state to OK.

![Recovery](screenshots/15-alarm-recovered.jpeg)

### Operations Dashboard
A CloudWatch dashboard was created to provide centralized infrastructure visibility.

![Dashboard](screenshots/16-cloudwatch-dashboard.jpeg)

## Incident Documentation
[View Incident Report](incident-report.md)

## Key Takeaways
- AWS infrastructure monitoring
- CloudWatch metrics
- CloudWatch alarms
- SNS notifications
- Linux troubleshooting
- Incident investigation
- Remediation
- Recovery validation
- Operational documentation

## Business Value
Proactive monitoring helps teams detect infrastructure issues quickly, automate notifications, reduce response time, and validate recovery after remediation.

## Skills Demonstrated
`AWS` `EC2` `CloudWatch` `SNS` `Linux` `Monitoring` `Alerting` `Troubleshooting` `Incident Response` `Cloud Operations`
