# Business Impact Analysis Template

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

**Examples might include:**
- Taking customer orders
- Delivering your product or service
- Processing payments
- Providing customer support
- Manufacturing or production
- Managing inventory

For each process, ask: "If this stopped working tomorrow, how bad would it be?"

| BUSINESS PROCESS | WHAT THIS PROCESS DOES |
|------------------|------------------------|
| [Process Name] | [Describe what happens and why customers care] |
| [Process Name] | [Describe what happens and why customers care] |
| [Process Name] | [Describe what happens and why customers care] |
| [Process Name] | [Describe what happens and why customers care] |
| [Process Name] | [Describe what happens and why customers care] |

## Step 2: Determine How Long Things Can Be Down

For each critical process, figure out how long it can be unavailable before you start losing serious money or customers. You don't need precision here—use rough categories like "a few hours," "1-2 days," or "a week."

Also think about data loss. If you lost a day's worth of customer orders or financial records, could you recreate them? Would customers accept that?

**Talk to the people who run these processes.** They know what happens when things break.

| BUSINESS PROCESS | HOW LONG CAN IT BE DOWN? (MTD) | HOW MUCH DATA CAN WE LOSE? (RPO) |
|------------------|--------------------------------|----------------------------------|
| [Process Name] | [e.g., 4 hours, 2 days, 1 week] | [e.g., 1 hour, 1 day] |
| [Process Name] | [e.g., 4 hours, 2 days, 1 week] | [e.g., 1 hour, 1 day] |
| [Process Name] | [e.g., 4 hours, 2 days, 1 week] | [e.g., 1 hour, 1 day] |
| [Process Name] | [e.g., 4 hours, 2 days, 1 week] | [e.g., 1 hour, 1 day] |
| [Process Name] | [e.g., 4 hours, 2 days, 1 week] | [e.g., 1 hour, 1 day] |

## Step 3: Map Your Dependencies

Now connect the dots. For each critical business process, list what systems, software, or vendors you depend on to keep it running. Be specific—this is where you'll discover single points of failure.

**Think about:**
- Cloud services (hosting, email, file storage)
- Payment processors
- Internet connectivity
- Specific software applications
- Hardware (servers, laptops, phones)
- Key suppliers or service providers

For each dependency, estimate how quickly it needs to be back online. Some systems you can live without for days. Others cause immediate problems.

| SYSTEM OR SERVICE | WHY YOU NEED IT | HOW FAST MUST IT RECOVER? (RTO) |
|-------------------|-----------------|--------------------------------|
| [Name] | [What breaks if this fails?] | [e.g., 1 hour, 4 hours, 2 days] |
| [Name] | [What breaks if this fails?] | [e.g., 1 hour, 4 hours, 2 days] |
| [Name] | [What breaks if this fails?] | [e.g., 1 hour, 4 hours, 2 days] |
| [Name] | [What breaks if this fails?] | [e.g., 1 hour, 4 hours, 2 days] |
| [Name] | [What breaks if this fails?] | [e.g., 1 hour, 4 hours, 2 days] |
| [Name] | [What breaks if this fails?] | [e.g., 1 hour, 4 hours, 2 days] |

**Pro tip:** If you find yourself writing "N/A" or "not critical" for the RTO, ask yourself if that system really belongs on this list.

## Your Most Critical Systems

From the list above, identify the systems that are absolutely essential—the ones where an outage would immediately prevent you from serving customers or would risk data loss. These are your "drop everything and fix this now" systems.

**Typically includes:**
- Core application or product infrastructure
- Primary database
- Payment processing systems
- Authentication/login systems
- Critical third-party services

List them here (usually 3-6 systems):

- [System Name]
- [System Name]
- [System Name]
- [System Name]
- [System Name]

## Recovery Order: What Comes Back First?

When disaster strikes, you can't fix everything at once. This section helps you prioritize recovery efforts. Think about dependencies—some systems need to be running before others can start.

**Example:** Your application needs the database first. Your payment processing needs your application running. Your customer support team needs internet and laptops before they can help customers.

List your critical systems in the order they should be restored. Include realistic recovery times assuming worst-case scenarios (complete failure, need to rebuild or switch to backup).

| PRIORITY | SYSTEM NAME | WORST-CASE RECOVERY TIME |
|----------|-------------|-------------------------|
| 1 | [System/Service] | [e.g., 1 hour, 4 hours] |
| 2 | [System/Service] | [e.g., 1 hour, 4 hours] |
| 3 | [System/Service] | [e.g., 1 hour, 4 hours] |
| 4 | [System/Service] | [e.g., 1 hour, 4 hours] |
| 5 | [System/Service] | [e.g., 1 hour, 4 hours] |
| 6 | [System/Service] | [e.g., 1 hour, 4 hours] |

**Reality check:** These recovery times should be based on actual capabilities, not wishes. If you don't have backups or failover systems in place, rebuilding from scratch might take days, not hours.

---

## How to Actually Use This Template

**Time needed:** 2-3 hours with the right people in the room

**Who should be involved:** Your IT person/team, someone who understands operations, and whoever manages key business processes (sales, production, customer service, etc.)

**The process:**

1. **Start with business processes, not technology.** Forget about servers and software for now. Talk about what your business actually does for customers. What are the 5-7 things that generate revenue or fulfill your core value proposition?

2. **Get real about downtime tolerance.** For each process, honestly discuss how long it could be down before you're in trouble. "Trouble" means lost revenue, angry customers, contract penalties, or regulatory issues. Don't aim for perfection—rough categories like "hours," "1-2 days," or "a week" are fine.

3. **Map technology to business processes.** Now connect each critical process to the systems, software, and vendors it depends on. This is where you'll probably discover some uncomfortable single points of failure.

4. **Determine recovery priorities.** If everything broke tomorrow, what order would you fix things? What can wait and what can't? This should be driven by business impact, not technical preference.

5. **Be honest about your capabilities.** If you're estimating a 1-hour recovery time but you don't actually have backups or a tested recovery process, you're lying to yourself. Worst-case recovery times should reflect reality, not aspirations.

6. **Review and update regularly.** Your business changes, vendors change, dependencies change. Review this document at least once a year, or whenever you add a critical new system or vendor.

## What This Document Gets You

- **Better incident response:** When something breaks, you know what to fix first and why
- **Smarter insurance decisions:** You can have informed conversations about coverage for vendor failures and business interruption
- **Compliance alignment:** This work supports ISO 27001, NIS2, DORA, and other frameworks that require business impact analysis
- **Vendor management priorities:** You know which vendor relationships need the most attention and strongest contracts
- **Resource allocation:** You can justify spending on redundancy, backups, or failover systems based on actual business impact

## Common Pitfalls to Avoid

**Perfectionism paralysis.** You don't need precise calculations down to the minute or exact financial models. You need good enough information to make better decisions than you're making now.

**Technology-first thinking.** Starting with "we have these systems" instead of "we do these things for customers" leads to missing important dependencies and misunderstanding actual business impact.

**Optimistic recovery estimates.** If you've never tested your backup and recovery process, your actual recovery time will be much longer than you think. Factor in fumbling, troubleshooting, and unexpected complications.

**Static documentation.** A BIA that sits in a drawer and never gets updated is worse than no BIA at all because it creates false confidence. Set a calendar reminder to review this at least annually.

**Ignoring vendor dependencies.** Your payment processor going down is just as problematic as your own server failing, but many BIAs only look at systems you directly control.

---

**Questions or need help completing this?** The hardest part is often getting honest answers about downtime tolerance and realistic recovery capabilities. If you'd like help facilitating this exercise or reviewing your results, reach out.
