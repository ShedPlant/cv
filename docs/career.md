---
icon: lucide/keyboard
---

# Career

## Introduction

I, Ed Plant, am a Senior Software Backend Developer / Architect for [Expend](https://expend.com), a UK FinTech software company.
Previously at [Fidessa](https://iongroup.com/products/markets/fidessa/) working on stock market trading platforms.

I combine the strongest understanding in the team of how things *currently* work, with idealistic opinions of how they *should* work, and work on continuous improvement.

Technology Stack:

- Python (Starlette, Pydantic, SQLalchemy)
- AWS (Lambda, ECS, RDS, DynamoDB, SNS, SQS, S3, Cloudwatch, VPC, Route 53, KMS)
- PostgreSQL and PL/pgSQL
- GitHub Actions CI/CD
- Pulumi

## AI Statement
I have been a cautious adopter of AI Coding Assistants, experiencing both benefits and a new class of problems.

I use Claude Code and have found certain tasks solved impressively competently and quickly.

However, without the steering of an experienced operator,
it produces false confidence in something plausible-looking but subtly wrong and usually overengineered.

I see it as my responsibility to keep my codebase working, clean and coherent for future maintainers (human or AI).
I don't accept AI as an excuse for ignoring best practices, avoiding critical thinking or accepting poor quality solutions.
Used well, it can accelerate individuals/teams.

Adding more AI elsewhere in SDLC (e.g. to review AI-generated code) may help a bit but is not the whole solution.

*This website text was not written with any AI assistance.*


## Strengths and Self-Knowledge

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
- [ ] less experienced with JS UI/mobile development
- [ ] less comfortable communicating directly with customers

## Testimonials

[Matthew Finding](https://www.linkedin.com/in/matthew-finding-95612475/), managed me:

> Ed was brought to my attention as part of a project where he validated the suitability of a new product for use in real-world customer trading platform environments.  His attention to detail, thorough documentation of issues, and pragmatic approach to resolution of problems, quickly led to a fantastic working relationship with my team at the time.  This was before he worked for me directly and already had a solid reputation as a technical leader, which was backed up when I looked for references from his managers when recruiting him into my own group.
>
> Upon joining my team Ed had to embed himself as the new lead within an existing team, helping to implement new processes and practices as well as assisting with spearheading our latest automation initiative.  This was a challenging and no doubt daunting task but he did a fantastic job, not only giving his team a new purpose but ensuring that they were contributing effectively for the benefit of the wider engineering department.  To do so, he had quickly get himself and his team up to speed on several new technologies and tools, and gain a deeper, low-level, insight into the inner workings of our product set.  He very much rose to the challenge. 
>
> Ed is a really great team player, I really enjoyed working with him and was privileged to have him in my group - I knew I could assign work to his his team and be confident he would get it done, or feedback immediately where there were issues.  I always enjoyed our 1-2-1s; he would constantly challenge the status quo and any outdated practices, coming up with sensible and considered approaches to move the organisation forward.
>
> I would wholeheartedly recommend Ed to any organisation and am sure he would be a valuable member to any team. 

[Francesca Wise](https://www.linkedin.com/in/francesca-wise-b96143128/), managed by me:

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




## Senior Software Architect @ Expend

???+ success "Senior Software Architect @ Expend"

    *5+ years July 2021 - present*

    ### Summary

    Expend is a UK FinTech expenses software company with hundreds of customers, thousands of users and cards, fewer than ten developers.

    In the last five years I've improved Expend's developer experience, platform stability, and increased velocity to implement new customer-facing features.


    ### Architecture

    #### Problem

    I inherited a hybrid architecture which looked superficially like microservices but was monolithic in practice, without getting the advantages of either approach.

    #### Solution

    With [12 factor app](https://www.12factor.net/) principles in mind, I pulled apart the monolith to distinct projects with clear domain boundaries, and dependencies,
    and better tests to cover the API contracts with other services.

    #### Benefit
    This has improved the developer experience, reduced time between code change and deployment (including mean time to recovery), improved confidence that making a change is safe.

    ### Infrastructure as Code

    #### Problem
    Cloud resources were maintained manually only by the CTO. No like-live test environment.

    #### Solution

    I introduced Pulumi as our Infrastructure as Code tool:

    - made libraries to codify our common patterns
    - established guardrails to prevent accidental destruction
    - imported existing cloud resources
    - deployed a new AWS staging environment

    #### Benefit
    This has made our environment more robust and scalable. Anyone in the team can make changes to cloud resources with confidence, and it's trivial to deploy new projects.

    ### CICD

    #### Problem

    Our CI/CD was using an expensive software vendor, while being poorly understood and temperamental.

    #### Solution

    I migrated our CI/CD from an expensive software vendor to GitHub Actions.

    #### Benefit
    Cheaper, simpler, better understood. Less responsibility of running our own runner infrastructure.

    To be fair, GitHub's own uptime has got worse in the last year or two.

    ### Feature Development

    I am also a big contributor to new feature development.
    For example, in 2025-26 I led the effort to integrate with a new Card Issuer partner.

    Using my deep understanding of our previous integration, I took on temporary project manager responsibilities to break up the work into many sequenced epics. 
    I communicated with the partner's consultant to analyse how our use cases could be achieved with their APIs and reports.
    Then implemented most of the back-end work and working closely with the team's front-end developers.

    The migration to the new Card provider has gone smoothly with only minor bugs found in the back-end implementation.

## Previous Roles

??? success "Trading Platform Deployment Team Lead @ Fidessa"

    *4 years January 2017 - May 2021*

    I led a development automation team with a mission to deliver change to SaaS customers more frequently and more automatically.

    I first focussed on making CIB/QA more automatically configured, more 'cattle' than 'pets'.

    I wanted development teams to take responsibility and pride in their applications' health and stability in CIB and QA.

    We improved visualisation of system health:

    - new health webpages on office TVs
    - deployment status notifications by email and MS Teams

    I streamlined the software delivery pipeline by back-porting legacy customisation layers
    that were historically added post-release by other siloed development teams.
    This shortened the release turnaround time by a few days per monthly release.

    I led the development of a new automated configuration and deployment tool based on Rundeck, Ansible & Tcl.
    We accumulated a userbase community of development system owners.
    This reduced manual toil to deploy or upgrade the Fidessa trading stack compared to previous disparate manual practices.

    My greatest achievement was a company-first of deploying a new green-field Internet-facing multi-tenanted trading platform:

    - Using consistent automated deployment technology in all environments (Continuous Integration, Quality Assurance, User Acceptance Testing, Production)
    - Straight from Development group, without hand-over to Delivery group
    - Monthly, automated upgrade cycle rather than yearly, semi-manual

    This resulted in the application developers being able to deliver value to market more rapidly than before.
    Overheads of supporting old code branches are minimal.
    Being multi-tenanted, the marginal cost of on-boarding additional customers is much lower than normal practice of purchasing and deploying to new hardware.

??? question "Consultant @ FIS"

    *3 months October 2016 - December 2016*

    It was a hard decision to leave so soon but the role was not a good fit.

    I mainly did client-facing 1st and 2nd line Production support but wanted more hands-on development and automation opportunities.

??? success "Trading Platform Delivery Team Lead @ Fidessa"

    *2 years July 2014 - September 2016*

    The role was a generalist mix of Implementation Consultancy, Project Management, Development, Testing, Deployment and Application Support.

    I led a team of 3, responsible for several customers’ trading platforms. I managed 6-week back-to-back sprints for a high-profile customer.

    - Liaised with customer-facing delivery managers and business analysts, to understand customer requirements
    - Analysed requirements to produce solution design
    - Software development / implementation
    - Writing and executing manual test plans in User Acceptance Testing (UAT) environment
    - Re-factoring or re-testing customisations following a major underlying software upgrade
    - Coordinating patches/upgrades e.g. reacting to mandatory 3rd party upgrades, or for regulatory compliance
    - Deployment to Production with mix of manual action and automation
    - issue triage and support, remaining calm in a high-pressure environment
    - Coached and managed junior team members including SMART objective setting and one-to-ones.
    - Gate-kept and code reviewed my team's work
    - Proactively drove change to improve the department's procedures, documentation and tools.

??? success "Trading Platform Delivery Engineer @ Fidessa"

    *4 years September 2010 - July 2014*

    Configured, customised and upgraded trading platform applications.


## Education

??? success "IT Consultancy MSc Distinction @ University of Kent"

    *2009 - 2010*

??? success "Politics BA 2:1 @ the University of Exeter"

    *2006 - 2009*