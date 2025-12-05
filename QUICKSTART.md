# Quick Start Guide

**Time needed:** 2-3 hours  
**Goal:** Understand what's critical, how long it can be down, and what to fix first

## Before You Start

**Gather these people:**
- Someone who understands your technology (IT lead)
- Someone who runs operations
- Key business process owners (sales, support, production, etc.)

**Block time:**
- 2-3 hours without interruptions
- Not your first meeting of the day (people need to be sharp)

## The Process

### Step 1: List 5-7 Critical Business Processes (30 minutes)

**Question:** "What do we do that directly generates revenue or delivers our core value to customers?"

**Not this:** Every process you have  
**This:** The ones that, if stopped, would cause serious customer or revenue problems within days

**Examples:**
- Taking and fulfilling orders
- Delivering your product/service
- Processing payments
- Providing customer support
- Manufacturing/production

Write them down with a one-sentence description of what each does.

### Step 2: Determine Downtime Tolerance (45 minutes)

**For each process, ask:** "How long could this be down before we're in real trouble?"

**Real trouble means:**
- Lost revenue
- Customers leaving
- Contract penalties
- Regulatory problems
- Reputation damage

**Use rough categories:**
- Hours
- 1-2 days  
- 3-5 days
- A week or more

Also ask: "How much data could we lose without serious problems?"

**Example:**
- Process: "Payment processing"
- Downtime tolerance: "4-6 hours"
- Data loss tolerance: "2 hours"
- Why: "Longer outages mean customers can't pay us; lost transactions require manual recovery"

### Step 3: Map Dependencies (45 minutes)

**For each critical process, ask:** "What systems, software, or vendors does this depend on?"

Be specific:
- Cloud hosting (AWS, Azure, GCP)
- SaaS applications (specific names)
- Payment processors
- Your own application infrastructure
- Internet connectivity
- Critical suppliers

For each dependency, estimate: "How fast must this recover?"

**Look for:**
- Single points of failure (one thing that breaks everything)
- Vendors you can't control
- Things you haven't tested recovering from

### Step 4: Set Recovery Priorities (30 minutes)

**Question:** "If everything broke right now, what order would we fix things?"

Think about dependencies:
- Database before application
- Authentication before application
- Core systems before nice-to-haves

List your top 5-8 systems in priority order with realistic recovery times.

**Be honest:** If you've never tested recovery, it will take longer than you think.

## What You Should Have Now

✅ List of critical business processes  
✅ Understanding of how long each can be down  
✅ Map of system dependencies  
✅ Priority order for recovery  
✅ Honest assessment of single points of failure

## Next Steps

1. **Document this** in the [BIA Template](BIA_Template.md)
2. **Share with stakeholders** who need it for incident response
3. **Use it to inform:**
   - Insurance coverage decisions
   - Vendor management priorities
   - Security spending justification
   - Compliance documentation
4. **Schedule annual review** (set a calendar reminder now)

## Red Flags You Uncovered

If you discovered any of these, take action:

**🚩 Critical process depends entirely on one vendor you can't control**
→ Consider contingent business interruption insurance  
→ Document customer communication plan for vendor outages

**🚩 You have no idea how long recovery would actually take**
→ Your estimates are probably optimistic by 2-3x  
→ Schedule recovery testing

**🚩 Everything seems equally critical**
→ You're not being honest about prioritization  
→ Force rank: "If I could only restore one thing, what would it be?"

**🚩 Your IT person is the only one who can recover systems**
→ Major key-person risk  
→ Document procedures, cross-train backup

**🚩 You have no backups or they're untested**
→ Stop. Fix this immediately.  
→ You're one incident away from business-ending data loss

## Common Mistakes to Avoid

❌ **Trying to be too precise** - "Can we tolerate 4.5 hours or 5.2 hours?" → Doesn't matter, move on  
❌ **Starting with technology** - "We have these systems..." → Wrong. Start with business processes  
❌ **Optimistic recovery estimates** - "We can restore from backup in 30 minutes" → Have you tested it?  
❌ **Including everything** - Focus on the 20% of systems that create 80% of business risk  
❌ **One person filling this out alone** - You need multiple perspectives

## Still Stuck?

- Look at the [example completed BIA](EXAMPLE_COMPLETED_BIA.md)
- Read the [FAQ](FAQ.md) for specific questions
- Check the full [BIA Template](BIA_Template.md) for more guidance
- [Open an issue](../../issues) if something's confusing

---

**Remember:** Good enough beats perfect. You need information to make better decisions, not a PhD thesis on business continuity.

Get started: [BIA_Template.md](BIA_Template.md)
