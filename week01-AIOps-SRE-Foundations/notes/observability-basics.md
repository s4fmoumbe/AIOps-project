Observability Basics
1. What is Observability?

Observability is the ability to understand the internal state of a system based on its outputs.
It allows engineers to detect, debug, and optimize complex systems, especially in distributed and cloud-native environments.

Key idea: You can’t fix what you can’t see. Observability provides visibility into system behavior.

2. Observability vs Monitoring
Aspect	Monitoring	Observability
Focus	Checks if system is up/down	Understands system internals
Method	Alerts on metrics thresholds	Correlates metrics, logs, and traces
Output	“Service is failing”	“Service failed due to high DB latency”
Goal	Detect known problems	Diagnose unknown problems
3. The Three Pillars of Observability

Metrics

Numerical measurements over time

Examples: CPU usage, request rate, error rate

Tools: Prometheus, Datadog

Logs

Timestamped records of events

Examples: HTTP request logs, system errors

Tools: ELK Stack (Elasticsearch, Logstash, Kibana), Loki

Traces

Tracks request flow across services

Detects latency and bottlenecks in distributed systems

Tools: OpenTelemetry, Jaeger, Zipkin

Metrics = “What is happening?”
Logs = “What happened?”
Traces = “Why did it happen?”

4. Observability vs AIOps

Observability is data-driven visibility, while AIOps is AI-driven action.

Observability provides the inputs (metrics, logs, traces).

AIOps applies ML and automation on top to predict issues and trigger remediations.

5. Key Observability Concepts

High Cardinality Metrics

Metrics with many unique values (e.g., per-user metrics)

Must be used carefully to avoid overload

Tagging / Labeling

Add metadata to metrics and logs for correlation

Example: service=payments, region=us-east-1

Distributed Tracing

Follow request path across microservices

Identify slow services or bottlenecks

Alerting

Alerts should be actionable, not noisy

Use SLOs to define thresholds

6. Hands-On Observability

Install Prometheus & Grafana

Collect basic metrics:

CPU, memory, HTTP request rate, errors

Create a simple Grafana dashboard:

Graph CPU usage over time

Graph request latency

Configure a threshold alert for high CPU or error rate

7. Benefits of Observability

Faster incident detection and root cause analysis

Better understanding of system behavior under load

Reduced MTTR (Mean Time to Resolve)

Provides data foundation for AIOps automation