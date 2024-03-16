# Funding

We are not seeking donations/contributions at this time.

# If you are interested in contributing and/or the licensing for my projects

Please refer to the contributing-to-my-projects and the licensing directories for the general terms and what not.

Contributions and licensing info is available here: https://github.com/idle-interactive/.github

# Public Project Status

https://www.CityConflicts.com - Early Alpha - Planned to be open sourced but exact date is tbd since I need to make some build/deploy tooling and get it usable

There is a variety of tooling I need to build that is dev-ops/sideproject-ops type stuff as well as just lifestyle-ops. :P Everything is "ops" these days!

But that is future me stuff, nothing ready for the public yet.

# We are coding lifestyle tools, browser games, AI tools, & dev-ops stuff as a hobby @ [IdleInteractive](https://www.IdleInteractive.com)

This account is for related open sourced projects.

Do not expect quality code, code reviews to be regular, or revisions to pull requests to be timely.

As this is intended to be a chill, relaxing hobby account, I simply do not have the time to perform to my usual professional standard. 

I just want to relax and code things.

Projects are going to be opinionated and based on my needs/interests/opinions. 

* If they work your use case, great. 

* If you can adapt them with some features you add via pull requests that don't increase my personal infrastructure costs, great.

* If you expect me to provide customer support, fix non-critical/security issues, or add features you request. These are not the projects for you.
    * The fact that I've considered commercial licensing is more "future proofing" these projects for later in life.

* If you expect any of my projects to have an interest in feature parity with commercially viable projects...
    * Yeah, just don't. 
    * I probably spend 20 hours a month on this stuff. 
    * There is 0 chance any of this is going to reach the level of a business with multiple employees.

* Do not add complications to the stability, infrastructure/devops, and maintainability.
    * This is gonna be an automatic No.
    * Project languages are restricted to Python, PHP, and Javascript. Plus the occassional bash/zsh script.
    * Data storage is MySQL + Redis + local files. No exceptions.
        * HA setup will be MySQL InnoDB Cluster + Redis w/ Failover
        * Redis is to be used as a cache where data loss is a minor annoyance (i.e. forcing users to login due to session loss)
        * MySQL is the store of truth
        * Local files are for configuration and/or static "baked" deployments that can be copied between environments as they rarely change.
            * The assumption here is anything in this category is either part of the deployment process or can afford the delay of a rsync b/t nodes.
    * Deployment and testing is via Docker containers behind Traefik.
    * Deployment processes are to be done via Ansible and/or bash scripts.
    * Testing processes fall in the above categories of operation.
    * The only real exceptions is existing open source projects I utilize in my infrastructure that might get referenced as projects you install/download.

* Deployment Infrastructure
    * We are looking at standard virtual machines and/or bare metal + docker.
        * This helps with potential vendor lock-in since there are plenty of these providers at various price/quality points.
    * Supported CDNs are Cloudflare and BunnyCDN.
        * This is not for failover between them but just avoiding vendor lock-in.
    * I may add some API support for a couple of vendors but right now all my infrastructure is on "low end" providers that are cheap, no frills service.
        * This being the case, availability issues can be expected even with some redudancy in my setup for projects that are active enough to warrant the expense.
        * Basically, for writes, I'm going to have 1 datacenter availability.
        * For reads, I plan to have redudancy eventually but it'll be read-only in the event of failover.