---
marp: true
class: invert
paginate: true
---

<!-- _paginate: false -->

# Confoo 2026 <!--fit-->

Conferences: https://confoo.ca/en/2026/schedule

Slides: https://github.com/confoo-ca/ConFoo-2026

---

# The Director to CTO path: following it, or mentoring it (Kevin Goldsmith)

> A systematic approach to the Director-to-CTO growth path for aspiring CTOs and their mentors. Covers essential skill development (technical depth, strategic planning, leadership), mentorship strategies for identifying and nurturing potential, plus real-world examples of successful transitions and everyday challenges.

---

## Takeaways

<!-- _header: The Director to CTO path: following it, or mentoring it (Kevin Goldsmith) -->

> Understand your broader organization's goals. Work to make sure that your teams are informed and aligned.

> Suggest and/or volunteer for organizational improvement efforts.

> Work to understand the strategy of your organization and company.
> How does your team's work support that strategy? How could it better support the strategy?

> Track industry trends and discuss how they may impact your company or product with your manager.

---

## Takeaways (continued)

<!-- _header: The Director to CTO path: following it, or mentoring it (Kevin Goldsmith) -->

> Identify potential.

> Delegate.

> Explain.

> Overshare.

> Give opportunity.

> Give feedback.

---

# From Vulnerability to Victory: Java Security Essentials

Anthony Dahanne

<!-- > This session demystifies the vulnerability lifecycle for Java developers: how flaws are found, scored (CVSS), and disclosed. Learn the key databases (NVD, GitHub Advisory, OSS Index), the tools that use them, automated remediation tools, and dependency management strategies to transform Java application security from burden to advantage. -->

---

## Takeaways

<!-- _header: From Vulnerability to Victory: Java Security Essentials (Anthony Dahanne) -->

- Use SAST to catch classic OWASP vulnerabilities early
- Use CycloneDX SBOMs to vulernabilities in _all_ dependencies:
  - Container images
  - Language runtime
  - Libraries and sub-dependencies
- Monitor vulnerabilities continuously
- Exclude accepted CVEs with a VEX file

---

# Beyond the chatbot, beyond the IDE: AI in my CI/CD

Justine Gehring

<!-- > AI's potential in software development extends far beyond code generation or chatbot-style assistants in the IDE. This talk explores how five families of AI capabilities (Learning & Onboarding, Coding Assistants, Automation & Agents, Planning, and Data Exploration & Synthesis) can transform the entire CI/CD lifecycle. -->

---

## Takeaways

<!-- _header: Beyond the chatbot, beyond the IDE: AI in my CI/CD (Justine Gehring) -->

- ML and AI can help everywhere in the SDLC, not just in coding:
  - Error logs analysis
  - Checking for outdated documentation in merge requests
  - Triaging tickets
  - ...

---

![bg](https://beyond.addy.ie/1.svg)

<!-- _footer: https://beyond.addy.ie -->

---

# Securing the SDLC: From Code to Production

Mohamed Wali

<!-- > Modern applications face security challenges across the full software lifecycle, from development to production. This session explores strategies to integrate vulnerability scanning early in the IDE, enforce secure practices in CI/CD, and monitor running systems. Learn how to identify, remediate, and prevent security risks throughout the SDLC. -->

---

## Takeaways

<!-- _header: Securing the SDLC: From Code to Production (Mohamed Wali) -->

- Run SCA (Software Composition Analysis) scans
  - to identify vulnerabilities in dependencies
- Run SAST (Static Application Security Testing) scans
  - to catch security issues in code
- Run IaC (Infrastructure as Code) vulnerability scans
  - to identify misconfigurations in cloud infrastructure

---

# From Dev to Lead: Guiding Without Managing

Erik Beaulieu

<!-- > Stepping into leadership as a developer is tricky: you're expected to guide peers without becoming a manager. This talk shares strategies to influence without authority, avoid micromanagement, and balance coding with people skills. -->

---

## Takeaways

<!-- _header: From Dev to Lead: Guiding Without Managing (Erik Beaulieu) -->

> Leadership is a direction, not a promotion.

> Broader human impact vs. deeper technical mastery

> | Leadership might be for you if...      | Leadership might not be for you if...   |
> | -------------------------------------- | --------------------------------------- |
> | You care how decisions are made        | You prefer depth over breadth           |
> | Brokering collaboration frustrates you | Interpersonal complexity drains you     |
> | You want impact beyond your own work   | You value technical solitude            |
> | You enjoy helping others grow          | You want ownership of code, not culture |

---

# Managing the human side of a large-scale platform upgrade

Joyce Peralta

<!-- > McGill University is leading a multi-year migration to a new major version of their content management system (Drupal), impacting several hundred websites and numerous stakeholders. This session explores the change management strategy behind the project, including stakeholder engagement, communication planning, and user outreach. -->

---

## Takeaways

<!-- _header: Managing the human side of a large-scale platform upgrade (Joyce Peralta) -->

- Communication is key:
  - Develop a communication plan and channels
  - Engage users early and often
- Change management is a continuous process:
  - Measure and communicate progress
  - Provide training and support to users

---

# Ghosts in the Machine: Tampering with the JS Supply Chain

Chris DeMars

<!-- > What if the code you're shipping isn't yours anymore? The scariest JavaScript bugs don't always come from your team—they come from open-source packages that have been possessed. This talk digs deep into the dark world of supply chain tampering: what it looks like, how it happens, and what modern devs can do to protect themselves. Covers tamper detection, package provenance, lockfile integrity, and GitHub Actions setup. -->

---

## Takeaways

<!-- _header: Ghosts in the Machine: Tampering with the JS Supply Chain (Chris DeMars) -->

- For most security breaches related to supply chain attacks,
  > a patch was available but was not applied.
- Pin versions and commit lockfiles...
  - ...but continuously monitor vulnerabilities and patch dependencies.

---

# Ditch Flaky Tests: Node + Testcontainers = Reliable Testing

Scott Stroz

<!-- > Testing code that talks to your database doesn't have to be stressful. With Testcontainers, you can eliminate database testing headaches and boost your workflow by ensuring reliable, containerized test environments. -->

---

## Takeaways

<!-- _header: Ditch Flaky Tests: Node + Testcontainers = Reliable Testing (Scott Stroz) -->

- Testcontainers allow spinning up a customized Docker container in code
- Testcontainers are prebuilt for many popular databases and services
- Testcontainers allow running service tests against a real database

<style scoped>
  pre {
    zoom: 0.8;
  }
</style>

```ts
const container = await new MySqlContainer("mysql:9.6")
  .withExposedPorts(3306)
  .start();

// connect to a real database using:
container.getUsername();
container.getUserPassword();
container.getHost();
container.getMappedPort(3306);
container.getDatabase();

await container.stop();
```

---

# GITOPS with fluxCD, kubernetes and kubeseal

Benoit des Ligneris

<!-- > An introduction to GitOps and how it works in practice. This session covers implementing GitOps workflows using FluxCD, Kubernetes, and Kubeseal (Bitnami Sealed Secrets) to manage infrastructure and application deployments declaratively and securely. -->

---

## Takeaways

<!-- _header: GITOPS with fluxCD, kubernetes and kubeseal (Benoit des Ligneris) -->

> Git as the single source of truth for declarative infrastructure and applications.

- Declarative: the entire system is described in code
- Versioned: all changes are tracked in Git
- Automated: changes are automatically applied once committed
- Observable: correctness/drift of the live system state is monitored

Tools:

- OpenTofu: infrastructure as code
- FluxCD: syncs Git state to Kubernetes
- Kubeseal: encrypts secrets for safe storage in Git

---

# AI Assemble! Build your own private Development Team

Heath Kesler

<!-- > This presentation examines how AI automation through MCP servers can help you build your own private development team, exploring patterns for AI-assisted development workflows. -->

---

## Takeaways

<!-- _header: AI Assemble! Build your own private Development Team (Heath Kesler) -->

- Spec-driven development: use AI to generate code based on specifications
  - SpecKit: a tool to generate specifications in AI-friendly format
- Agent roles: PO, architect, developer, tester, etc.
- Integrate with existing tools via MCP: JIRA, GitHub, etc.

---

# Rising After the Fall: Engineering Your Career Comeback

Kevin Goldsmith

<!-- > Everyone faces career inflection points: some by choice, others thrust upon us. When your career gets disrupted, recover faster with proven frameworks. Learn systematic methods for self-assessment, market positioning, and opportunity evaluation to engineer your career comeback. -->

---

## Takeaways

<!-- _header: Rising After the Fall: Engineering Your Career Comeback (Kevin Goldsmith) -->

- Tech is cyclical: periods of growth and disruption are expected
- Don't get caught off guard, prepare for disruption
  - Figure out your "why" and your "what"
  - Understand the market and your value proposition
  - Address gaps while you're employed
  - Build your network, quality over quantity
- If something happens:
  - Activate your network to find opportunities, this is how most hires happen
  - Don't be afraid to take a temporary step back to move forward
  - Don't waste your time in between jobs: learn, contribute, build, etc.

---

# How we failed at Event Sourcing

Louis Beaudoin-Allaire

<!-- > Event Sourcing is a powerful but tricky pattern. When the need for a new product arose, the team began adopting the practice—and soon enough, issues in the implementation started surfacing. This session shares the hard-learned lessons from a failed Event Sourcing implementation. -->

---

## Takeaways

<!-- _header: How we failed at Event Sourcing (Louis Beaudoin-Allaire) -->

<small>_ES (Event Sourcing) is basically the Redux pattern, but for the backend: events are persisted, and reducers compute the state of the system at runtime based on the events._</small>

<small>_CQRS (Command Query Responsibility Segregation) is a related pattern where the read queries and write commands are handled separately, often with different data stores with a processing step in between, giving eventual consistency._</small>

<small>_DDD (Domain-Driven Design) is a methodology for designing complex software systems by modeling the business domain, often implemented using aggregates, entities, and value objects._</small>

- Combining ES + CQRS + DDD is powerful but comes with a lot of overhead

---

# Messaging Patterns to Transform Your Cloud Architecture

Chad Green

<!-- > Messaging patterns are the backbone of resilient, high-performance cloud systems. This session explores paradigms from Point-to-Point to the Saga Pattern, showing how they enable scalable, dynamic designs. Through hands-on demos and real-world case studies, gain practical skills to integrate effective, future-proof messaging into your cloud solutions. -->

---

## Takeaways

<!-- _header: Messaging Patterns to Transform Your Cloud Architecture (Chad Green) -->

Nothing new, but a good summary of key concepts and messaging patterns:

- Message Queue: decouples producers and consumers, allows for asynchronous processing and load leveling
- Publish-Subscribe: allows multiple consumers to subscribe to messages from a producer, enabling event-driven architectures
- Message Broker: intermediates between producers and consumers, providing routing, transformation, and delivery guarantees
- Idempotency: ensures that processing the same message multiple times has the same effect as processing it once

---

## Takeaways (continued)

- Dead Letter Queue: holds messages that cannot be processed successfully
- Saga Pattern: manages distributed transactions and ensures data consistency across microservices
  - A coordinator service tracks the state of the saga and orchestrates the execution of the steps, handling compensation in case of failures

---

# How I automated my life with MCP Servers

Cedric Clyburn

<!-- > Being a developer these days means you're not only writing code, but also a Linux admin, a DevOps engineer, and more. This session demonstrates how to use MCP (Model Context Protocol) servers to automate daily workflows and simplify your development life. -->

---

## Takeaways

<!-- _header: How I automated my life with MCP Servers (Cedric Clyburn) -->

- MCP servers allow AI agents to interact with tools and APIs
- There are more and more MCP servers available, beyond code-related ones
- Local AI agent orchestators like [Goose](https://block.github.io/goose/) enable easy MCP server configuration

---

# Mental Models and Heuristics

Marc-Antoine Aubé

<!-- > Thinking tools to solve thorny problems. Software engineering isn't just about production—it's about learning in complex, uncertain situations. This talk explores how useful (if imperfect) models and practical heuristics can help you reframe problems, cut through complexity, and make better technical decisions. -->

---

## Takeaways

<!-- _header: Mental Models and Heuristics (Marc-Antoine Aubé) -->

- Type 1 vs type 2 decisions:
  - One-way door: irreversible
    - Analyze carefully
    - Document the thought process
  - Two-way door: reversible
    - Don't spend time analyzing, just do it and learn from it
    - Pick an industry-standard solution and change later if needed
- Software development is a learning process, not a production process
  - Take notes of why decisions were made to not lose the learnings

---

# 3 Illusions in Software Delivery

Joel Tosi

<!-- > Software Delivery is full of illusions. This session examines three of them: the Illusion of Progress, the Illusion of Predictability, and the Illusion of Control. Understand why all those meetings aren't helping, why all that planning may be misguided, and what to do about it. -->

---

## Takeaways

<!-- _header: 3 Illusions in Software Delivery (Joel Tosi) -->

- The Illusion of Progress, created by processes
  - Signs: "It's done but...", PowerPoint "demos"
  - Focus on business outcomes and customer value, not on process artifacts
- The Illusion of Predictability, created by estimations
  - Focus on adaptability and learning
- The Illusion of Control, created by meetings
  - Signs: review boards, freezes
  - Focus on trust, autonomy, and continuous improvement

> Act where pain is caused, not where it is observed.

---

# Screen Reader 101

Ashleigh Lodge

<!-- > What is a screen reader? How do they work? Screen readers are essential tools to navigate websites for a wide variety of disabled users, and navigating via a screen reader is a very different experience from navigating visually. This beginner-friendly session introduces accessibility testing with screen readers. -->

---

## Takeaways

<!-- _header: Screen Reader 101 (Ashleigh Lodge) -->

- Only 75% of screen reader users are blind
- Focus on:
  - Desktop: JAWS on Chrome, NVDA on Firefox, and VoiceOver on Safari
  - Mobile: TalkBack on Android, and VoiceOver on iOS
- Use semantic HTML unless absolutely impossible
- Use ARIA attributes when semantic HTML is not enough

> Test! You're not an expert, but neither are most users.

---

# How the browser is breaking your web app

Anthony Vallee-Dubois

<!-- > Browsers can be more opinionated than expected when building for the web. Whether it's to provide features to users, manage device resources, or make performance tradeoffs, the browser takes actions that subtly break web apps. This talk explores these cases and how to make your applications more resilient. -->

---

## Takeaways

<!-- _header: How the browser is breaking your web app (Anthony Vallee-Dubois) -->

- Background tabs can be frozen, throttled, or discarded
- Timers can be throttled in background tabs
  - Don't assume timers will be precise
  - Aligned to 1 second, 1 minute, or frozen
- `requestAnimationFrame` is not called in background tabs
  - Don't use it for non-animation purposes

---

# Seven Habits of a (Mostly) Successful Team

Sander Hoogendoorn

<!-- > After five years of building our team, we’ve distilled seven practical habits—no Scrum, no dogma—that fuel delivery, motivation, and continuous improvement. -->

---

## Takeaways

<!-- _header: Seven Habits of a (Mostly) Successful Team (Sander Hoogendoorn) -->

- Business vision: a "dot on the horizon"
  - a clear, compelling, and shared vision of the future
- Kill complexity
  - Decisions: have a clear business vision, prioritize ruthlessly
  - Tech: simplify your stack, automate everything
  - Process: deliver continuously, remove handoffs
  - Organizational: get rid of bureaucracy, communicate relentlessly
- Microteams (autonomous and cross-functional) collaborate better and move faster

---

## Takeaways (continued)

<!-- _header: Seven Habits of a (Mostly) Successful Team (Sander Hoogendoorn) -->

### Simplify to amplify

> Simple, clear purpose and principles give rise to complex and intelligent behavior. Complex rules and regulations give rise to simple and stupid behavior.

### Deliver continuously

> If it hurts, do it more frequently, and bring the pain forward.

### Build quality in

> Cease dependence on inspection to achieve quality.

---

That was Confoo 2026!
