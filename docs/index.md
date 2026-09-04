---
icon: lucide/keyboard
---

# Ed Plant's CV

## Introduction

I, Ed Plant, am a UK-based Senior Software Architect (IC) for [Expend](https://expend.com), a FinTech software company 
handling millions of pounds of customer card spend per year.

I am a Product Engineer able to reason about our customers' business needs and workflows.
At the same time, I have a strong understanding of how our system *currently* works, 
opinions on how it *should* work, and can design and implement change safely.

Skills:

- Python (Starlette, Pydantic, SQLalchemy)
- AWS (Lambda, ECS, RDS, DynamoDB, SNS, SQS, S3, Cloudwatch, VPC, Route 53, KMS)
- PostgreSQL and PL/pgSQL
- GitHub Actions CI/CD
- [Pulumi](https://www.pulumi.com/) (Infrastructure as Code alternative to Terraform)
- [TDD](https://agilealliance.org/glossary/tdd/)
- Contract/Acceptance Testing
- Microservices and Event Driven Architecture
- Dependency Injection Pattern
- Progressive Rollouts

Contact me on [LinkedIn](https://www.linkedin.com/in/shedplant/).

<div class="print-hide" markdown="1">
## My AI Opinion
*All words in the CV are my own. I solicited advice from both humans and AI and made my own decisions.*

:robot: :technologist:

I have been a cautious adopter of AI Coding Assistants, experiencing both benefits and a new class of problems.

I use Claude Code and have found certain tasks solved impressively competently and quickly.

However, without the steering of an experienced engineer,
it produces false confidence in something plausible-looking but subtly wrong and usually unnecessarily complicated.

I see it as my responsibility to keep my codebase working, clean and coherent for future maintainers (human or AI).
I don't accept AI as an excuse for ignoring best practices, avoiding critical thinking or accepting poor quality solutions.
Used well, it can accelerate individuals/teams.

I haven't used fully agentic SDLC before and am concerned that an AI-only developer will eventually lose the skills that made them capable of doing the job to begin with.


## Strengths and Traits

- [x] structured approach to problem solving
- [x] meticulous attention to detail
- [x] good recall of business and technical knowledge
- [x] clarifies requirements from ambiguity, false assumptions and general confusion
- [x] investigate and resolve production incidents calmly and systematically
- [x] drives change to improve technical foundations
- [x] can coach juniors or manage a small team
- [x] friendly and personable with colleagues
- [x] knowledge sharing using diagrams, tables, documents and presentations
- [x] understand and improve legacy systems, pay down technical debt
- [x] dislikes inter-personal conflict, yet stays professional

## Testimonials

[Matthew Finding](https://www.linkedin.com/in/matthew-finding-95612475/), managed me:

??? info print-collapse "'he would constantly challenge the status quo and any outdated practices, coming up with sensible and considered approaches to move the organisation forward'"

    > Ed was brought to my attention as part of a project where he validated the suitability of a new product for use in real-world customer trading platform environments. His attention to detail, thorough documentation of issues, and pragmatic approach to resolution of problems, quickly led to a fantastic working relationship with my team at the time. This was before he worked for me directly and already had a solid reputation as a technical leader, which was backed up when I looked for references from his managers when recruiting him into my own group.
    >
    > Upon joining my team Ed had to embed himself as the new lead within an existing team, helping to implement new processes and practices as well as assisting with spearheading our latest automation initiative. This was a challenging and no doubt daunting task but he did a fantastic job, not only giving his team a new purpose but ensuring that they were contributing effectively for the benefit of the wider engineering department. To do so, he had quickly get himself and his team up to speed on several new technologies and tools, and gain a deeper, low-level, insight into the inner workings of our product set. He very much rose to the challenge. 
    >
    > Ed is a really great team player, I really enjoyed working with him and was privileged to have him in my group - I knew I could assign work to his his team and be confident he would get it done, or feedback immediately where there were issues.  I always enjoyed our 1-2-1s; he would constantly challenge the status quo and any outdated practices, coming up with sensible and considered approaches to move the organisation forward.
    >
    > I would wholeheartedly recommend Ed to any organisation and am sure he would be a valuable member to any team. 


[Francesca Wise](https://www.linkedin.com/in/francesca-wise-b96143128/), managed by me:

??? info print-collapse "'Since taking over the Platform Deployment team Ed has revolutionised the way the team works, pushing automation initiatives, questioning and refining procedures.'"

    > I have had the pleasure of working for Ed for the past 2 years. 
    >
    > Ed has really pushed me to exceed my own expectations and evolve my skillset. 
    > 
    > He has excelled at pushing his team to succeed and evolve. 
    > 
    > Since taking over the Platform Deployment team Ed has revolutionised the way the team works, pushing automation initiatives, questioning and refining procedures. 
    > 
    > He has an excellent wealth of knowledge and is always looking to apply that knowledge to help the team and company improve.
    > 
    > I have enjoyed working for Ed and would recommend him to any employer.


</div>


## 2021-Present Senior Software Architect @ [Expend](https://expend.com/)

Expend is a UK FinTech expenses software company:

- ~5k users
- ~5k cards
- ~£28m spend made through our platform in ~45k customer transactions in 2025
- fewer than ten developers
- ~200 Lambdas, ~40 microservices
- webservices and event-driven architecture

In the last five years I've improved Expend's developer experience, platform stability, and increased velocity to implement new customer-facing features :rocket:.


???+ success "Integration to a Card Issuer"

    In 2025-26 I led the implementation effort to integrate with a new Card Issuer partner, [Adyen](https://www.adyen.com/).

    I performed a deep analysis of our previous integration, communicated with the partner's consultant to understand their APIs, webhooks and reports, and planned how our use cases could be achieved.

    I pushed for some significant deliberate architectural changes compared to the old system, based on pain points I had experienced:

    - it would not be Expend's responsibility to maintain a 'ledger' of account balances, instead we would trust Adyen to provide reliable account balances for generating account statements
    - for card spending realtime authorisation decisions, the partner's transaction rules would support all our use cases, while being more performant than a call-out system like we had before
    - we would publish a stream of transactions to a downstream unified transaction service, supporting multiple sources to support parallel running with the old system

    I acted as a project manager to raise epics in a clear sequence, where there were blocking dependencies.
    I assigned the required front-end and mobile tasks to the relevant team members, and had brief communication sessions (inspired by '[three amigos](https://agilealliance.org/glossary/three-amigos/)') before starting work, to check shared understanding.

    I collaborated closely with a team-mate on the back-end work, pairing sometimes to make a decision, or work on something tricky, otherwise reviewing each other's PRs.
    We used the [TDD](https://agilealliance.org/glossary/tdd/) approach and had high confidence in the quality and correctness of what we were shipping, which was borne out by later production usage.

    The migration to the new Card provider has gone smoothly with 300+ customers migrated in 6 months,
    with only one day pre-arranged spending downtime per customer.

    The system I architected has stood up well, now that it is being used by real customers in production: the major decisions about trade-offs have not been regretted. The Adyen team said they were impressed with the speed at which Expend integrated with them.


???+ success "Distributed Monolith -> Microservices"

    **Problem**

    I inherited an architecture which looked superficially like microservices but was monolithic in practice
    (shared databases, one folder of shared code, one CICD pipeline), without getting the advantages of either approach.

    **Solution**

    As a pre-requisite to allow safe refactoring for each service, I created more acceptance tests which asserted the API contracts with other services independent of the internal behaviour.

    With [12 factor app](https://www.12factor.net/) principles in mind, I pulled apart the monolith to distinct projects with clear domain boundaries and dependencies. Each project can now be deployed independently, without blocking PRs for other projects in the monorepo.

    I refactored each service to use a dependency injection pattern 
    instead of a singleton 'resource manager' used anywhere and everywhere, 
    so it's more explicit at every level how different pieces fit together, and easier to mock in unit tests.

    I split out chunks from the shared code folder into many discrete libraries published with [semantic versioning](https://semver.org/), and then installed only into the projects which need them.

    **Benefit**

    Publishing a new library no longer risks breaking all services simultaneously. The trade-off is that promoting the new library version across multiple/all projects is more of a chore.

    Introducing clearer boundaries, explicit dependencies and looser coupling has improved confidence, lowered risk and increased deployment frequency. Each developer in the team can easily deploy to production multiple times per day, if required.

    By making deployments small and frequent, a regression is easy to trace back to the breaking change and our mean time to recovery (MTTR) is usually less than 2 hours.

    Unfortunately we still have some shared databases for complex legacy systems where the risk of change was too high to justify a rewrite.
    However, we haven't extended that antipattern for any new work since I joined.
    In some cases we managed to replace direct database access of foreign data with HTTP calls to the owning service,
    even though both services ultimately still use the same database.

??? success print-collapse "Multi Factor Authentication (2FA / MFA)"

    **Problem**

    Expend already has a secure user authentication system,
    but since our product can control cards and spending, our customers now expect additional security.

    **Solution**

    In 2023, I implemented the new multi-factor authentication service for Expend. The most difficult part was the constraint of only having one login endpoint (legacy, hard to change), which needed to support multiple new MFA workflows before the user is fully logged in.

    - new microservice with fairly simple db schema to save user's preferred delivery mechanism in one table, and another table of already-used OTPs to prevent a replay attack
    - [pyotp](https://github.com/pyauth/pyotp) library for the core mechanics
    - an mfa auth workflow with different code paths for first-time setup, confirm delivery mechanism with OTP, log in with OTP, log in with 'remember me on this device' JWT, log in with recovery code

    In the MFA service, I wrote integration tests for the pyotp wrappers, the database utilities, and the various login workflows. The legacy login service's integration with the new MFA service was also tested. Additionally I collaborated with front-end and mobile developers to make sure that all of our contributions worked together end-to-end.

    We then did a staged rollout where customers could opt-in to MFA, before it was made mandatory for all customers.

    **Benefit**

    - positive feedback from a customer who requested the feature: "We love the 2fa feature so thank you for rolling it out!"
    - MFA was a pre-requisite for Card PIN reveal feature with Adyen (when we found this out in 2025-2026 it was simply already done)
    - a step towards ISO 27001 compliance

??? success print-collapse "Introduced Pulumi Infrastructure as Code"

    **Problem**
    Cloud resources were maintained manually only by the CTO. No like-live test environment.

    **Solution**

    I introduced Pulumi as our Infrastructure as Code tool:

    - made libraries to codify our common patterns
    - established guardrails to prevent accidental destruction
    - imported existing cloud resources
    - deployed a new AWS staging environment

    **Benefit**
    Most legacy services have now been migrated to Pulumi and deployed to Staging.

    This has made our environment more robust and scalable. Anyone in the team can make changes to cloud resources with confidence, and it's trivial to deploy new projects.

    In hindsight I should have trained the rest of the team how to import legacy infrastructure, as my time has become a bottleneck to progress on the initiative.

??? success print-collapse "Migrated CICD to GitHub Actions"

    **Problem**

    Our CI/CD was using an expensive software vendor, while being poorly understood and temperamental.

    **Solution**

    I migrated our CI/CD from an expensive software vendor to GitHub Actions.

    **Benefit**

    Cheaper, simpler, better understood. Less responsibility of running our own runner infrastructure.

    To be fair, GitHub's own uptime has got worse in the last year or two.


## Previous Roles

??? success print-collapse "2017-2021 Trading Platform Deployment Team Lead @ [Fidessa](https://iongroup.com/products/markets/fidessa/)"

    Fidessa (now part of ION Group) is a market leader in stock market trading software.

    I led a development automation team (5-10 reports at peak) with a mission to deliver change to SaaS customers more frequently and more automatically.

    I streamlined the software delivery pipeline by a few days per monthly release, by squashing some software layers added by different teams.

    My greatest achievement was deploying the company's first ever multi-tenanted trading platform in a more modern way:

    - Straight from Development group, without hand-over to Delivery group
    - consistent automated deployment technology in all environments
    - Monthly, automated upgrade cycle rather than yearly, semi-manual

    This resulted in the application developers being able to deliver value to market more rapidly than before.
    Overheads of supporting old code branches are minimal.
    Being multi-tenanted, the marginal cost of on-boarding additional customers is much lower than normal practice of purchasing and deploying to new hardware.

??? success print-collapse "2016 Consultant @ [FIS](https://www.fisglobal.com/)"

    I mainly did client-facing 1st and 2nd line Production support, and left to get more hands-on development and automation opportunities.

??? success print-collapse "2014-2016 Trading Platform Delivery Team Lead @ [Fidessa](https://iongroup.com/products/markets/fidessa/)"

    The role was a generalist mix of Implementation Consultancy, Project Management, Development, Testing, Deployment and Application Support.

    I led a team of 3, responsible for several customers’ trading platforms. I managed and helped hands-on deliver SDLC projects across the whole lifecycle for a high-profile customer.

??? success print-collapse "2010-2014 Trading Platform Delivery Engineer @ [Fidessa](https://iongroup.com/products/markets/fidessa/)"

    Configured, customised and upgraded trading platform applications.


## Education

??? success print-collapse "2009-2010 IT Consultancy MSc Distinction @ University of Kent"

??? success print-collapse "2006-2009 Politics BA 2:1 @ the University of Exeter"

