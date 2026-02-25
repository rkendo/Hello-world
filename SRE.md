🔹 Scenario 1 — Users suddenly report 502 errors from your Load Balancer. What do you do first?

Question: How would you troubleshoot this in production?

Answer:
I’d validate the flow layer by layer:

• Check target health — are instances/pods failing health checks?
• Validate backend app logs for crashes/timeouts
• Confirm security groups/NACL allow LB → backend traffic
• Inspect listener & target group configuration
• Verify backend port mapping & readiness probes

Most 502 issues come from unhealthy targets, timeout misconfiguration, or backend app failures — not the load balancer itself.

🔹 Scenario 2 — You must choose between ALB and NLB for a production system. How do you decide?

Question: When would you choose each?

Answer:
I decide based on traffic behavior:

Application-style routing → use ALB
• Path/host routing
• HTTP/HTTPS awareness
• Microservices ingress

High-performance TCP/UDP workloads → use NLB
• Ultra low latency
• Static IP requirement
• Millions of connections

Choice is workload-driven, not preference-driven.

🔹 Scenario 3 — A client requires static IP whitelisting but your app needs path-based routing. What’s your solution?

Answer:
Yes — common in advanced production architectures:

Example pattern:
Internet → NLB (static IP + performance) → ALB (smart routing)
Useful when:
• Clients require static IP whitelisting
• Need Layer-4 performance + Layer-7 routing
• Hybrid or legacy integrations exist

This pattern balances networking control with application intelligence.

🔹 Scenario 4 — Your organization has 40 VPCs that must communicate securely. What architecture would you design?

Question: What scales best?

Answer:
Manual peering becomes operational chaos.

Production solution:

• Central transit architecture
• Route segmentation
• Security isolation
• Policy-driven connectivity

This provides scalable routing, centralized control, and cleaner governance.

🔹 Scenario 5 — How do you securely connect App Servers to a Database in production?

Answer:
Never expose databases publicly.

Best practice:

• Private subnets for DB
• Strict security group referencing (app → DB only)
• No internet route for DB
• Encryption in transit
• IAM/secret management for credentials

Principle: least privilege + network isolation.
