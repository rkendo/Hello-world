. What is the difference between monitoring and observability?
 Monitoring tells you something is wrong.
 Observability helps you understand why it is wrong by correlating metrics, logs, and traces.

2. What do you monitor first in production?
 You start with user-impacting signals — latency, traffic, error rates, and saturation — not just infrastructure metrics.

3. How do you define SLIs and SLOs?
 You define measurable reliability indicators (like availability or latency) and align SLO targets with business expectations.

4. How do you design monitoring for high-availability systems?
 You monitor failover events, redundancy health, replication lag, and regional availability to ensure resilience.

5. How do you monitor distributed systems?
 You combine metrics for performance trends, centralized logging for visibility, and distributed tracing to detect cross-service bottlenecks.

6. How do you monitor Kubernetes workloads?
 You track pod restarts, node pressure, autoscaling behavior, service latency, and error patterns — not just cluster uptime.

7. How do you monitor application-level issues?
 You focus on response time, throughput, error codes, and dependency health such as databases and third-party APIs.

8. How do you prevent alert fatigue?
 You alert only on actionable, sustained symptoms — not temporary spikes or non-impacting noise.

9. What do you do when an alert fires?
 You validate the alert, check dashboards, correlate logs and traces, implement the fix, and confirm system recovery.

10. How do you know your monitoring strategy is effective?
 When incidents are detected and resolved before users report them.

What interviewers are really evaluating:

• Can you think in signals instead of tools?
• Can you reduce noise and detect real incidents?
• Can you explain technical failures in business terms?
• Can you stay calm during on-call pressure?
• Can you design monitoring with a true production mindset?
