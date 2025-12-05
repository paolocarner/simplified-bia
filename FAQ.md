# Frequently Asked Questions

## General Questions

### Who should use this template?

This template is designed for small and medium-sized businesses (typically 10-500 employees) who need to understand their business continuity risks but don't have enterprise-level resources. If you're dependent on cloud services, vendors, and technology but don't have a dedicated risk management team, this is for you.

### How is this different from enterprise BIA frameworks?

Enterprise frameworks assume you have dedicated teams, months of time, and the ability to demand detailed security assessments from vendors. This template can be completed in 2-3 hours, uses plain language, and focuses on "good enough" decision-making rather than comprehensive documentation.

### Do I need technical expertise to complete this?

No, but you need the right people in the room. Bring someone who understands your technology (IT person/team) and people who run your key business processes. The template asks business questions first, technical questions second.

### How long does it take to complete?

Plan for 2-3 hours with the right people. If you're spending significantly more time than that, you're probably overthinking it or trying to achieve enterprise-level precision that isn't necessary.

## About the Analysis

### How accurate do my time estimates need to be?

Rough categories are fine. The difference between "4 hours" and "6 hours" doesn't change your priorities or decisions. The difference between "4 hours" and "3 days" does. Don't waste time pursuing false precision.

### What if I don't know how long we can tolerate downtime?

Talk to the people who run those processes daily. They know what happens when things break. If you still don't know, start conservative (shorter tolerance) and adjust based on actual incidents.

### Should I include every system we use?

No. Focus on the 5-10 systems that, if they failed, would prevent you from serving customers or generating revenue. Your accounting software might be important, but if it's down for a day, you probably won't lose customers. Your payment processor or primary application? Different story.

### What if we depend entirely on vendors we can't control?

That's reality for most SMBs. Document the dependency honestly, understand your contractual protections (or lack thereof), and consider whether contingent business interruption insurance makes sense for critical vendor relationships.

## Using the Results

### What do I do with the completed BIA?

Use it to:
1. **Prioritize recovery efforts** during actual incidents
2. **Make insurance decisions** about business interruption coverage
3. **Focus vendor management** on critical dependencies
4. **Support compliance requirements** (ISO 27001, NIS2, DORA, etc.)
5. **Justify security spending** by connecting it to business impact

### How often should I update this?

Review annually at minimum, or whenever you:
- Add critical new systems or vendors
- Change business models (new products/services)
- Experience an actual outage that reveals gaps
- Make major architectural changes

### Should I share this document?

The completed BIA contains information about your critical dependencies and tolerances. Share it with people who need it for incident response or business continuity planning. Don't post it publicly or share it with vendors unless you have a good reason.

### How does this relate to incident response planning?

Your BIA tells you WHAT to prioritize during recovery. Your incident response plan tells you HOW to actually do the recovery. They're complementary documents. The BIA informs the priorities in your IR plan.

## Compliance and Insurance

### Does this satisfy ISO 27001 requirements?

This template addresses the business impact analysis requirements in ISO 27001 (specifically Annex A 5.29 through 5.31 in the 2022 version). You'll still need other business continuity documentation, but this is a solid foundation.

### Will this help with NIS2 or DORA compliance?

Yes. Both frameworks require understanding critical functions and supply chain dependencies. This BIA addresses those requirements in a practical way. You may need additional documentation for full compliance, but this is a strong start.

### How does this relate to cyber insurance?

A completed BIA helps you:
- Understand your exposure to vendor failures (contingent business interruption)
- Quantify potential business interruption losses
- Document risk management practices that insurers ask about
- Make informed decisions about coverage limits

### Can I use this for other compliance frameworks?

Probably. Most compliance frameworks that include business continuity requirements need some form of BIA. This template is deliberately generic enough to support multiple frameworks.

## Common Challenges

### We can't agree on downtime tolerances.

This usually happens when you're trying to be too precise. Use rough categories (hours, days, weeks) instead of exact numbers. If people still disagree, document both perspectives and circle back after you've seen real incidents.

### Our entire business depends on one vendor.

Document it honestly. That's your reality. Focus on:
- What contractual protections you have
- Whether contingent business interruption insurance makes sense
- What workarounds exist, even if imperfect
- What your customer communication plan is if that vendor fails

### We've never tested our recovery procedures.

That's common. Document your ESTIMATED recovery times, clearly mark them as untested, and build in significant buffer. Testing reveals reality, and reality is usually slower than estimates.

### Everything feels critical.

Focus on direct revenue generation and customer-facing functions first. If stopping a process would cause you to lose customers or fail to deliver your core value proposition within days, it's critical. If it would be annoying but you could work around it for a week, it's important but not critical.

## Getting Help

### I'm still confused. Can you help?

If you're stuck or want feedback on your completed BIA, consider reaching out to a cybersecurity consultant who specializes in SMBs. Look for consultants who:
- Focus on practical risk management, not fear-mongering
- Have experience with businesses your size
- Understand your compliance requirements
- Speak plain language instead of jargon

### Can I pay someone to complete this for me?

Yes, but you need to be involved in the process. External consultants can facilitate the discussion and document results, but only you and your team know your business processes and dependencies well enough to provide accurate information.

### Where can I learn more?

- Read the [related blog post](https://paolocarner.com/blog/understanding-third-party-cyber-risk-for-smbs) on third-party cyber risk
- Review the [example completed BIA](EXAMPLE_COMPLETED_BIA.md) to see what good looks like
- Check out business continuity resources from NIST, ISO, or your local cybersecurity authority

## Technical Questions

### What format should I use for the completed BIA?

Markdown works well if you're comfortable with it. But honestly, a Word doc or Google Doc is fine. The format matters less than having accurate, accessible information.

### Should I keep this in version control?

If your team already uses Git, sure. But it's not critical. Just make sure you:
- Keep the current version accessible to people who need it
- Track when reviews happen
- Maintain some history of major changes

### Can I automate any of this?

Some tools claim to automate BIA, but they often miss the business context that makes a BIA useful. The value comes from the discussion and thinking, not from auto-generated outputs. Save your money.

---

**Still have questions?** [Open an issue](../../issues) on GitHub or reach out through the contact information in the README.
