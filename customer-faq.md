---
audience: Microsoft
---

# Customer FAQ for HVE Conversations

> **Internal Use Only:** This FAQ is designed for Microsoft engineers to reference when speaking with customers about HVE. It is not intended to be shared directly with customers.

## What is an HVE Conversation?

An HVE Conversation is any discussion with a customer—whether a workshop, advisory call, or informal check-in—where Microsoft engineers help explore how Hypervelocity Engineering practices could accelerate their software delivery while maintaining or improving quality.

Frequently asked questions and answers that customers may ask when starting Hypervelocity Engineering (HVE) conversations. Use this reference to respond consistently and confidently during engagements.

---

## Using Customer Responses to Guide Recommendations

| If a customer says... | Consider recommending... |
|----------------------|-------------------------|
| "Our biggest bottleneck is unclear requirements" | M365 Copilot for transcript → backlog, design thinking workshop |
| "We have no ADRs, everything is tribal knowledge" | Copilot-assisted ADR generation, markdown context in repo |
| "AI-generated code goes straight to PR with no special review" | Comprehension debt conversation, expert validation process |
| "Our cycle time is 6+ weeks" | Value stream mapping to identify where cycle time is lost |
| "Only one person understands the legacy system" | Copilot for codebase onboarding, documentation generation |

---

## Quick Reference: Top 10 Questions

| Question | Short Answer |
|----------|--------------|
| What is HVE? | Expert multidisciplinary teams applying AI, proven accelerators, and design thinking across the SDLC to maximize quality and accelerate value |
| Is HVE just GitHub Copilot? | No—HVE addresses the entire engineering system, not just code generation |
| What problems does HVE solve? | Long lead times, documentation overhead, slow CI/CD, testing gaps, process friction |
| Who should attend workshops? | Mix of engineering leadership, hands-on engineers, and DevOps/platform owners |
| Does HVE replace Agile/DevOps? | No—teams evolve processes to maximize value in an AI-assisted environment, not just add tools |
| Can HVE work in regulated environments? | Yes—HVE works anywhere you can bring the four pillars: multidisciplinary teams, AI tooling, accelerators, and design thinking |
| What does HVE require from customers? | Leadership sponsorship, willingness to rethink processes, active engineer participation |
| How long to see value? | Weeks, not months—when scope is small and teams are empowered |
| How is success measured? | Quality, speed, productivity, confidence, and sustainability metrics |
| What is the biggest mistake customers make? | Assuming AI will instantly accelerate everything, instead of first identifying where the engineering system actually slows down |

---

## What HVE is NOT

Before diving into questions, here's a quick myth-busting reference:

- ❌ **Not a product** you purchase or install
- ❌ **Not just AI code generation** or GitHub Copilot adoption
- ❌ **Not a replacement** for Agile, DevOps, or existing processes
- ❌ **Not a one-time workshop** with no follow-up
- ❌ **Not vibe coding** — AI outputs require expert validation to ensure quality, security, and maintainability
- ❌ **Not only for greenfield** projects—often most valuable in brownfield scenarios

---

## 1. Foundational / Framing Questions

### What is Hypervelocity Engineering (HVE)?

HVE is built on **four pillars** that work together:

1. **Tight, Multidisciplinary Teams** — Expert teams bringing together diverse disciplines—engineering, design, data science, product, and domain expertise—to shorten feedback loops and validate decisions together
2. **AI Tooling** — AI assistants and agents embedded across the entire SDLC: research, ideation, prototyping, design, development, testing, and debugging
3. **Proven Accelerators** — Production-ready starting points (templates, reference architectures, validated prompts) that shave weeks to months off development cycles
4. **Design Thinking** — Customer-focused discovery that ensures teams solve the highest-impact problems the right way

HVE is not a product, framework, or single tool. It's a way of working where these pillars combine to help teams maintain or improve quality while dramatically accelerating time-to-value. This is not vibe coding—it's disciplined, expert-led engineering.

**In short:** HVE focuses on improving how software is built, not just making code faster to write.

### Is HVE the same thing as using Copilot or AI to write code faster? / Is HVE just about using GitHub Copilot or AI code generation?

No. That's a common misconception. While AI tools (e.g., GitHub Copilot, M365 Copilot, agents) are important, HVE addresses the entire engineering system, including:

- Research and discovery
- Requirements and backlog creation
- Documentation and context management
- Testing and quality automation
- CI/CD and deployment pipelines
- Security, compliance, and governance

AI amplifies strong engineering fundamentals; it does not replace them.

### What are ISE Accelerators?

ISE Accelerators are production-ready, open-source starting points developed by Microsoft's Industry Solutions Engineering (ISE) team. They cover common patterns for cloud, edge, AI, and data workloads—infrastructure and code that has already been validated with Microsoft's top customers. By starting from accelerators instead of from scratch, teams can focus on the hard, differentiated problems rather than rebuilding foundational components.

### What do teams need to succeed with HVE?

Teams that get the most from HVE typically have or are ready to develop:

- Clear understanding of where time is lost in their current workflow
- Willingness to evolve processes, not just adopt new tools
- CI/CD pipelines they can iterate on and improve
- Testing strategies that can scale with AI-assisted development
- Leadership support for experimentation and measured risk-taking
- Engineers empowered to focus on building value, not just following process

### Is HVE meant for experimentation only, or production systems?

Both. HVE applies across the full spectrum—from rapid prototyping to production-grade systems. The four pillars (multidisciplinary teams, AI tooling, accelerators, design thinking) are designed to maintain quality and governance at any stage. Teams often start with experimentation to build confidence, then apply the same disciplined approach to production workloads where security, compliance, and reliability requirements are non-negotiable.

---

## 2. Engagement & Workshop Expectations

### What should we realistically expect at the end of an HVE workshop?

Customers typically leave with shared understanding, clearer problem framing, identification of high-leverage bottlenecks, and one or more focused pilot directions—not a finished solution or fully hardened system. Depending on the engagement, workshops may also produce low-fidelity to high-fidelity prototypes that validate whether proposed solutions will deliver real value.

### Who should attend the workshop for it to be effective?

Effective workshops include a mix of engineering leadership, hands-on engineers, and DevOps or platform owners. Without this mix, momentum stalls: leadership-only sessions produce strategies no one implements, while IC-only sessions lack the authority to change processes or allocate resources. The right blend ensures decisions made in the room can actually be executed afterward.

### How much prep is required before an HVE kickoff?

Customers spend less time on formal pre-reads and more time clarifying where time is actually lost today (handoffs, testing delays, deployment friction). Rough clarity beats polished documentation.

### How do we avoid the workshop becoming a one-time event?

Customers that sustain momentum establish a follow-up cadence (often lightweight advisory touchpoints) where teams bring artifacts, decisions, and tradeoffs—not status updates.

---

## 3. Organizational Readiness & Change

### What makes an organization ready (or not ready) for HVE?

**Readiness strengths observed:**

- Leadership willing to rethink existing workflows
- Engineers open to pilot new practices
- Clear business problems tied to engineering bottlenecks
- Willingness to separate POC speed from production rigor
- Access to AI tooling (or a clear path to procurement)

**Readiness gaps that slowed impact:**

- Treating AI as a side tool rather than changing processes
- Large PRs without review discipline
- Inconsistent CI/CD pipelines
- Governance and security discussions postponed until "later"
- Lack of experienced engineers to validate AI-generated outputs

### How do we know if our organization is ready for HVE?

Readiness shows up in willingness to question existing workflows, not in tool maturity. Resistance often comes from process ownership, not technical capability.

### Can different teams adopt HVE at different speeds?

Yes. Customers often start with a small group and allow practices to spread organically rather than enforcing consistency upfront.

### What does HVE require from the customer?

Successful HVE engagements typically require:

- Leadership sponsorship
- Willingness to rethink existing processes
- Engineers actively participating (not observing)
- Openness to pilot and iterate
- Acceptance that not all legacy steps are sacred

Tool access alone is not sufficient.

### What cultural shifts are usually required?

Teams shift from optimizing individual tasks to optimizing flow, and from measuring effort to measuring time-to-decision and learning velocity.

### How does HVE change team size or composition?

HVE enables smaller, more focused teams to accomplish what previously required larger groups. Where engagements might have needed 10-12 people, teams applying HVE practices often achieve the same outcomes with half that number—without sacrificing quality. The key is having the right mix of expertise (multidisciplinary), not more headcount. AI tooling and accelerators multiply what each team member can accomplish.

---

## 4. SDLC & Engineering Practice Questions

### Does HVE replace our existing Agile or DevOps processes?

Customers do not replace processes wholesale. Instead, they reassess which steps still create value in an AI-assisted environment and remove or reshape those that no longer do.

### Can HVE work with complex brownfield systems?

Yes, many customers find the most value in brownfield scenarios because existing complexity makes bottlenecks visible. HVE often surfaces systemic friction that greenfield projects hide.

### How does HVE help with requirements and backlog creation?

Customers commonly use HVE to turn vision documents, meeting transcripts, and informal knowledge into actionable, testable work items—reducing ambiguity before development begins.

### Does HVE change how documentation is created?

Customers shift from documentation as a reporting artifact toward documentation as execution context: concise, updated continuously, and usable by both humans and AI tools.

---

## 5. AI Tooling & Developer Experience

### Do we need specific AI tools enabled to do HVE?

HVE benefits from AI tooling in two key environments:

- **Developer environment** — AI coding assistants (e.g., GitHub Copilot) embedded in the IDE for code generation, testing, debugging, and documentation
- **Non-developer environment** — AI assistants (e.g., M365 Copilot) for research, requirements gathering, meeting summaries, backlog creation, and stakeholder communication

Tool access alone is not sufficient. Teams see value only once usage is paired with guidance, shared patterns, and review discipline—rather than ad-hoc experimentation.

### How do teams handle large AI-generated pull requests?

Teams that manage large AI-generated PRs effectively use strategies like:

- **Narrowly-scoped prompts** — Focus prompts on specific, discrete tasks rather than generating entire features at once
- **Clear scope boundaries** — Define what the AI should and should not change before prompting
- **Incremental PRs** — Submit smaller, focused pull requests rather than batching many changes into one large PR
- **Structured review practices** — Focus human review on logic, security, and edge cases rather than line-by-line syntax

The goal is to keep PRs reviewable and avoid accumulating "comprehension debt" where no one fully understands the generated code.

### How much prompting expertise is expected from engineers?

Clear thinking and domain knowledge matter far more than prompt syntax. Prompt quality improves naturally as teams refine how they frame work and experiment with the context they provide. The best results come from an iterative approach—trying different prompts, evaluating outputs, and learning what works for specific tasks.

Tools like prompt-builder can also help generate effective, well-structured prompts rather than requiring engineers to craft every prompt manually from scratch.

---

## 6. Governance, Security & Quality

### Can HVE work in regulated or high-risk environments?

Yes. HVE works in any environment where the four pillars come together—multidisciplinary teams, AI tooling, accelerators, and design thinking. Governance and security are foundational everywhere; in regulated settings, those requirements simply become more explicit and formalized. The disciplined, expert-led approach ensures human validation at every step, strengthening both quality and compliance.

### Do we need governance defined before starting HVE?

Customers usually start with lightweight guardrails and mature governance iteratively. Waiting for perfect policies before starting tends to delay learning without reducing risk.

### How is human review handled with AI-generated outputs?

Human review remains non-negotiable. AI-generated code is treated like any other contribution—reviewed, tested, and owned by the team. The goal is meaningful validation by someone with the expertise to catch issues the AI might miss.

---

## 7. DevOps, Deployment & Operations

### Does HVE help with deployment pipelines or only development?

Customers consistently find that deployment and environment promotion consume far more time than development. HVE surfaces these constraints early and reframes them as first-class problems.

### Can HVE reduce the number of environments or handoffs?

Rather than prescribing a model, HVE helps teams examine why environments exist and where feedback is delayed. Customers often simplify flows once those tradeoffs are visible.

### How does HVE relate to monitoring and evaluation?

Customers treat evaluation and observability as part of delivery, not post-deployment tasks. Early alignment on what "good" looks like prevents late rework.

---

## 8. Data, Evaluation & Architecture

### How does HVE help when evaluation data is incomplete or evolving?

Customers iterate evaluation alongside development instead of waiting for perfect datasets. HVE favors learning loops over upfront completeness.

### Do we need a finalized architecture before starting?

Customers use HVE to establish directional architectures and reusable blueprints, refining details once key constraints are validated.

### How do we avoid over-engineering early evaluation frameworks?

Customers focus first on decisions the evaluation must support, not comprehensive metric coverage. Scope expands only when decisions demand it.

---

## 9. Measuring Progress

### How do customers know HVE is working?

Early indicators are qualitative: fewer handoffs, clearer backlog items, faster feedback. Quantitative metrics tend to stabilize later once behaviors settle. Teams often draw on established frameworks like Accelerate, Scalable Agile Framework, SPACE, and GitHub's Engineering System Success Playbook to structure measurement.

### Which metrics matter early on?

Customers pay attention to cycle time, deployment friction, rework, and confidence in decisions—rather than raw output counts.

### How should success be measured?

Success is typically measured across multiple dimensions:

- **Quality:** test coverage, defect rates, security posture
- **Speed:** cycle time, deployment frequency
- **Productivity:** onboarding time, backlog readiness
- **Confidence:** engineer comfort with AI tools
- **Sustainability:** maintainability, governance clarity

### How long does it take to see value from HVE?

Customers often see value in weeks, not months, when:

- Scope is intentionally small
- Teams are empowered to change ways of working
- AI is applied first to engineering bottlenecks (e.g., testing, deployments)

Value is incremental and compounding rather than a "big bang."

---

## 10. Common Reality-Check Questions

### What if AI tooling improves but delivery speed doesn't?

Customers often discover that organizational and pipeline constraints dominate. HVE explicitly helps make those constraints visible.

### What happens if we stop reinforcing HVE after the kickoff?

Momentum typically declines without reinforcement. Teams that sustain change build lightweight rhythms to reflect, adjust, and reinforce behaviors.

### What's the biggest mistake customers make with AI-assisted engineering?

Assuming AI will instantly accelerate everything. The teams that struggle expect speed gains without examining their current processes. The teams that succeed first identify where their engineering system actually slows down, then apply AI to remove that friction.

HVE works best when it's paired with a willingness to evolve how teams work—not just add AI to existing workflows.
