Automation Basics for AIOps & SRE
1. What is Automation in IT Operations?

Automation in IT operations refers to using scripts, tools, or AI to perform repetitive tasks without manual intervention.

Goals:

Reduce toil (repetitive, manual work)

Improve reliability and consistency

Enable faster response to incidents

Free engineers to focus on higher-value work

2. Why Automation Matters

Human operators cannot handle the scale and complexity of modern cloud-native systems.

Automation improves:

Consistency: Eliminates human error

Speed: Respond to issues faster than humans

Scalability: Handle large environments

Predictability: Repeatable processes

3. Types of Automation
Type	Description	Example
Scripting	Small tasks automated with shell or Python scripts	Restart a service when CPU > 80%
Configuration Management	Declarative infrastructure setup	Terraform, Ansible, Puppet
Event-Driven Automation	Triggered by events or alerts	Auto-scale pods in Kubernetes on high load
AI/ML-Driven Automation	Predictive or autonomous remediation	AIOps detects anomaly → triggers fix
4. Common Automation Tools

Shell scripting / Bash

Python / Go scripts

Terraform / Pulumi (Infrastructure as Code)

Ansible / Chef / Puppet (Configuration automation)

Kubernetes Operators (Event-driven automation)

AIOps platforms (Moogsoft, Dynatrace, Splunk ITSI)

5. Basic Hands-On Examples
a) Bash Script to Monitor CPU
#!/bin/bash
CPU=$(top -bn1 | grep "Cpu(s)" | awk '{print $2 + $4}')
THRESHOLD=80

if (( $(echo "$CPU > $THRESHOLD" | bc -l) )); then
  echo "Warning: High CPU usage: $CPU%"
fi

b) Cron Job to Run Script Every Minute
* * * * * /path/to/cpu-monitor.sh >> /var/log/cpu-monitor.log 2>&1

c) Event-Driven Automation Concept

Monitor HTTP 5xx errors

Trigger automatic restart of failing microservice

6. Best Practices for Automation

Start small: Automate one task at a time.

Test thoroughly: Avoid unintended outages.

Idempotency: Scripts should be repeatable with same results.

Logging: Keep logs for audit and troubleshooting.

Combine with Observability: Only automate based on reliable metrics.

7. Automation & AIOps

Automation is the action layer of AIOps.

AIOps platforms use AI/ML to detect anomalies → automation executes fixes.

Example:

Anomaly detected: high memory usage → auto-scale pods → notify team