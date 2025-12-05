# Business Impact Analysis - Example Company

**Company:** TechFlow Analytics (fictional SaaS company)  
**Industry:** B2B Data Analytics Platform  
**Size:** 35 employees  
**Date Completed:** December 2024  
**Next Review:** December 2025

---

## What This Document Is For

This Business Impact Analysis (BIA) helps you understand which parts of your business are most critical and what happens when they stop working. Think of it as a roadmap for answering these questions: "If this system or process goes down, how long before we're in serious trouble?" and "What needs to come back first when we're recovering from an outage?"

This document has three main parts:

1. **Identify your critical business processes.** What does your business actually do that generates revenue or keeps customers happy? If a system goes down, which business activities would stop?

2. **List what you need to run those processes.** What software, hardware, internet services, or vendors do you depend on? If any of these fail, what's the real impact?

3. **Figure out the recovery order.** When things go wrong, what needs to come back online first, second, third? This helps you focus your recovery efforts where they matter most.

## Key Terms Explained

These three terms describe how long things can be down and how much data you can afford to lose:

- **Maximum Tolerable Downtime (MTD):** How long can a business process be down before the damage becomes unacceptable? This includes everything—lost revenue, angry customers, contract penalties, and reputational harm.

- **Recovery Point Objective (RPO):** How much data can you afford to lose? If your backup runs every night, and your system crashes at 4 PM, you might lose up to 16 hours of work. Can your business tolerate that?

- **Recovery Time Objective (RTO):** How quickly must a specific system be back online before it causes real problems for your business? This is about the system's availability, not the business process as a whole.

## Step 1: Identify Your Critical Business Processes

List the 5-7 core things your business does that directly generate revenue or fulfill your promises to customers. Don't overthink this—focus on what would cause serious pain if it stopped working.

| BUSINESS PROCESS | WHAT THIS PROCESS DOES |
|------------------|------------------------|
| Product Delivery | Customers access our analytics platform 24/7 to view dashboards and reports. This is our core value proposition. |
| Customer Support | Technical support via chat and email. Critical for customer retention and resolving login/access issues. |
| Data Processing | Nightly ETL jobs that process customer data and update dashboards. Without this, customer data goes stale. |
| Sales & Demo | Sales team conducts product demos and manages the sales pipeline. Extended downtime means lost deals. |
| Billing & Invoicing | Monthly automated billing for subscriptions and usage-based charges. Downtime delays cash flow. |

## Step 2: Determine How Long Things Can Be Down

For each critical process, figure out how long it can be unavailable before you start losing serious money or customers. You don't need precision here—use rough categories like "a few hours," "1-2 days," or "a week."

Also think about data loss. If you lost a day's worth of customer orders or financial records, could you recreate them? Would customers accept that?

| BUSINESS PROCESS | HOW LONG CAN IT BE DOWN? (MTD) | HOW MUCH DATA CAN WE LOSE? (RPO) |
|------------------|--------------------------------|----------------------------------|
| Product Delivery | 4 hours | 1 hour - Customers expect near real-time data |
| Customer Support | 1 day | 4 hours - Can tolerate some ticket data loss |
| Data Processing | 8 hours | 2 hours - Nightly jobs must complete by morning |
| Sales & Demo | 1 day | 1 day - Sales can work from notes short-term |
| Billing & Invoicing | 3 days | 8 hours - Can manually process if needed |

**Notes from discussion:**
- Product delivery is most time-sensitive because customers have SLAs requiring 99.5% uptime
- Extended outages (>4 hours) trigger SLA credits and customer churn risk
- Sales can function manually for a day but loses efficiency and deal velocity
- Billing can be delayed a few days before impacting cash flow significantly

## Step 3: Map Your Dependencies

Now connect the dots. For each critical business process, list what systems, software, or vendors you depend on to keep it running. Be specific—this is where you'll discover single points of failure.

| SYSTEM OR SERVICE | WHY YOU NEED IT | HOW FAST MUST IT RECOVER? (RTO) |
|-------------------|-----------------|--------------------------------|
| AWS (EC2, RDS) | Hosts our entire application stack and database | 1 hour - Complete application outage |
| Auth0 | User authentication - customers can't login without it | 1 hour - Login failures = support tickets |
| Stripe | Payment processing for subscriptions | 4 hours - Billing can wait briefly |
| Intercom | Customer support chat and ticketing | 2 hours - Support team can't respond to customers |
| GitHub | Code repository and deployment pipeline | 4 hours - Blocks hotfixes and deployments |
| Datadog | Monitoring and alerting | 2 hours - Can't detect issues without it |
| Office Internet (Primary) | Remote team needs connectivity | 30 minutes - Team uses home internet as backup |
| Google Workspace | Email, Drive, Meet for internal collaboration | 4 hours - Can use alternatives temporarily |
| Snowflake | Data warehouse for customer analytics | 2 hours - Customer dashboards go stale |

**Single points of failure identified:**
- AWS hosts everything - no multi-cloud redundancy currently
- Auth0 authentication - no fallback login method
- Stripe for all payment processing - no alternative processor configured
- Single internet provider for office (but most team is remote)

**Pro tip:** If you find yourself writing "N/A" or "not critical" for the RTO, ask yourself if that system really belongs on this list.

## Your Most Critical Systems

From the list above, identify the systems that are absolutely essential—the ones where an outage would immediately prevent you from serving customers or would risk data loss. These are your "drop everything and fix this now" systems.

**Our most critical systems:**

1. **AWS (EC2, RDS)** - Complete application outage, affects all customer access
2. **Auth0** - Customers can't login, creates immediate support burden  
3. **Snowflake** - Customer data becomes stale, affects core product value
4. **Datadog** - Blinds us to other issues, prevents proactive response
5. **Intercom** - Support team can't respond to outage-related tickets

**Why these five:**
- They directly impact customer-facing functionality
- Outages cascade to multiple business processes
- We have no immediate workaround or alternative
- Recovery requires vendor response (outside our control)

## Recovery Order: What Comes Back First?

When disaster strikes, you can't fix everything at once. This section helps you prioritize recovery efforts. Think about dependencies—some systems need to be running before others can start.

| PRIORITY | SYSTEM NAME | WORST-CASE RECOVERY TIME |
|----------|-------------|-------------------------|
| 1 | AWS (EC2) | 2 hours - Restore from AMI snapshots |
| 2 | AWS (RDS) | 1 hour - Database has automated backups |
| 3 | Auth0 | N/A - Vendor dependency, no control |
| 4 | Snowflake | N/A - Vendor dependency, 99.9% SLA |
| 5 | Intercom | N/A - Vendor dependency, can use email temporarily |
| 6 | Datadog | 30 minutes - Redeploy monitoring agents |

**Reality check on vendor dependencies:**
- Auth0, Snowflake, and Intercom are completely outside our control
- Our contingent business interruption insurance covers vendor outages >4 hours
- We have emergency communication plan for customer notifications during vendor outages
- Recovery times assume our AWS expertise; without our lead DevOps engineer, times would double

**Dependency notes:**
- Application (EC2) needs database (RDS) to function
- Monitoring (Datadog) should come up early to verify recovery
- Auth0 is a black box - if it's down, we wait
- We tested RDS recovery last quarter and hit the 1-hour target

---

## Implementation Notes

**Completed by:** CTO, Head of Support, VP Sales  
**Time invested:** 2.5 hours including follow-up research  
**Key decisions made:**
- Purchased contingent business interruption insurance to cover AWS and Auth0 failures
- Started project to implement backup authentication method (target: Q2 2025)
- Documented customer communication procedures for vendor-caused outages
- Scheduled quarterly disaster recovery testing

**Action items from this BIA:**
1. Negotiate better SLA terms with Auth0 (include in next renewal)
2. Document manual billing procedures for Stripe outages
3. Create runbook for AWS recovery procedures
4. Test RDS recovery process quarterly
5. Evaluate multi-cloud strategy for critical components (long-term)

**Next review scheduled:** December 2025 or when major vendor changes occur

---

## Notes on Using This Example

This is a fictional company created to demonstrate what a completed BIA looks like. Your BIA will look different based on your industry, size, and dependencies. 

**What to notice:**
- Specific, concrete descriptions rather than generic statements
- Honest acknowledgment of vendor dependencies and lack of control
- Realistic recovery times based on actual capabilities
- Action items that came out of the analysis
- Notes explaining reasoning behind decisions

**What not to copy:**
- The specific MTD/RPO/RTO values - yours will be different
- The vendor choices - use your actual dependencies
- The recovery times - test yours, don't guess

Use this as a reference for tone and level of detail, not as a template to fill in with your own names.
