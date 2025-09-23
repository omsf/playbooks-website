---
layout: section
title: Project Management
weight: 3
sidebar:
  order: 3
---
Translating projects’ vision and mission is never easy, and execution paths will depend on many things, including available resources, environment, and even personalities of people involved in the execution. At OMSF, we came to rely on Project Managers to assist with the project execution. The PM takes the vision laid out by project leadership and enacts it. While it may seem that a PM does not need to be an expert in either the scientific field or in software engineering, we found that  having knowledge and skill in the area is immensely helpful. The most important skills for a PM are prioritization and delegation, but putting these skills into practice requires a deep intuition for the nature of the problem being solved. This intuition comes from domain context, as do awareness of the skills and limitations of the other members of the team. The PM must be able to hold onto the vision of the project and keep it in sight of the rest of the team, helping them resist distraction and prevent scope creep. For projects that have to manage lots of ideas and potential solutions, this strict focus is an uphill battle. The PM should also be comfortable thinking in possibilities, to make strategic decisions that consider both the present reality of the project and multiple potential futures.

## Following the roadmap

The [annual roadmap](../roadmapping/#tactics) serves as the definitive guide to the desires of the governing body and the tactical plan for the project. Following the roadmap means delivering the approved objectives, but in practice it usually means *not* delivering non-approved features. It also means assigning a sequence, or order of completion, to the objectives on the roadmap.

### Delivering subprojects

The annual roadmap should be divided into a set of distinct features or deliverables that can be planned separately and worked on independently. We sometimes call these discrete efforts "subprojects." Dividing the project into subprojects provides a framework for planning work, managing scope, setting priorities, estimating effort, and assigning work. 

#### Tips for success

* Map out dependencies between subprojects to adjust priority and set sequence. Subprojects that must be completed before other subprojects are called "bottlenecks" or "blockers."
* Set a delivery date for each project based on priority (higher priority things first), dependencies (bottlenecks first), and effort estimate (larger things first).
* Assign a [Driver](../governance/#consortium-governance-example-the-advisory-board--governing-board-model) to each subproject based on the skills required, interests and preferences, and balance of workload. 
* Also identify which other team members will contribute
* Estimate the length of calendar time required to complete the subproject, considering all other work assigned to the responsible team members
* Schedule work on a Quarterly basis

### Preventing scope creep

In software development, the temptation to add *just one more feature* before the next release is called "scope creep." Scientific software projects are especially vulnerable to scope creep as engineering advances enable scientific discoveries that enable further engineering advances. One of the most important functions of project management is to manage this process and prevent it from grinding progress to a halt. Preventing scope creep requires recognizing it, and recognizing it means defining your scope in advance and evaluating all development decisions against the agreed-upon scope. 

The Driver assigned to a particular subproject is usually tasked with proposing ("scoping") the list of features to be included in the subproject. The project leadership considers the proposed scope in the context of the entire roadmap and the estimated effort required, and approves it with any necessary changes. Any changes to the scope, once the subproject is underway, must also be approved by leadership.

### Defining scope

There are a few different frameworks for defining scope, from simplest to must complex:
* Minimum Viable Product (MVP): An important concept in Agile software development, the MVP is the smallest set of features or capabilities that can be given to users. In this framework, no additional features are included until required based on user feedback.
* Must-have, nice-to-have, not-in-scope: This is the framework OMSF projects use most commonly to discuss scope. The must-have scope corresponds closely to the MVP, but nice-to-have items are identified in advance and are only included if they don't slow down progress toward the must-have items. In our experience, defining not-in-scope is crucial both to developers, to keep them focused, and to stakeholders, to give them a chance to argue for why their own feature should be included.
* MoSCoW: The MoSCoW framework defines Must have, Should have, Could have, and Won't have. It adds one more level of scope. Some of our projects have attempted to use this scope framework, but have found it less helpful than the three-tier definition.

### Estimating effort

To follow the roadmap, the project manager must make some estimate of the amount of effort required to deliver each subproject. All effort estimates are wrong, but some are more useful than others. The two useful techniques that we have used in OMSF projects are
* T-shirt sizes: Most work tasks are defined as Small, Medium, or Large, where the amount of work that these sizes map onto are completely context-dependent (as with T-shirts). If necessary, work items can also be estimated as X-Small or X-Large (as with T-shirts).
* Story points: An arbitrary unit of developer time used to measure how complex a task is. We usually approximate one story point as 30 minutes of developer effort, but it is important not to overestimate the precision of story points. Assigning powers of 2 or Fibbonacci numbers can give a reasonable approximation of the precision of story points.

## Product management

Where Project Management is concerned with advancing the state of the project as the voice of the project, adding new frameworks and products, Product Management is concerned as the voice of the product; with maintaining stability of existing software products, fixing bugs, and delivering new features and user experiences. These two processes are complementary and share some strategies, but require a different mindset. In our projects, Product Management responsibilities are mostly devolved to individual [Drivers](../governance/#consortium-governance-example-the-advisory-board--governing-board-model).

Product Management includes the following concerns:
* *Feature development:* Adding new features to an existing software product to meet new needs of existing users or appeal to a broader user base
* *Maintenance:* Bug fixing, dependency updates, performance improvements
* *Testing:* 
  * Continuous integration testing to identify when a change to the code introduce bugs into existing features or when dependency updates introduce bugs
  * *Benchmarking* (See [Benchmarking Playbook](/benchmarking/))
* *Documentation* (See [Documentation Playbook], coming soon!)
* User support: Collect support requests in a central location and assign them to team members for response. Our projects use automation to connect an email inbox to other productivity tools, like Slack or [GitHub](https://github.com/omsf-eco-infra/ticgithub). 

## Project management software platforms

Effective project management requires several software tools to record, organize and coordinate knowledge and work. 

When choosing a tool or platform, ask these questions:
* Is it easy to use?
* Does it meet your specific need?
* Does it integrate with tools you already use?
* How much extra work will it take to implement and adopt this new tool?

Here are some of the functions that our projects have found critical, along with our experiences using different platforms.

### Code and data repositories

Data and code must be publicly accessible. All current OMSF projects host their code on GitHub. Though are alternative code repositories, they have very little uptake in scientific software development, so our projects are where our community can be found.

OMSF projects make use of Zenodo for data storage. Zenodo provides a flexible system for storing and accessing virtually unlimited amounts of data, including assigning a DOI to every record. Each project should create a [community on Zenodo](https://zenodo.org/communities). A Community provides tools for collecting and curating items produced as part of the same project. You can the publish datasets, talk slides, and even [software releases]( https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content) to Zenodo.

### Knowledge base

Your project will generate lots of knowledge, plans and decisions, which should be written down in a place readily accessible to everyone involved in the project. Projects thrive on comprehensive communication, especially in remote organizations like OMSF. Additionally, knowledge must be stored to maintain a level of sustainability as projects scale - new members need a place to discover, and old members need a place to reference. This knowledge base should be able to store and catalogue: 
* Meeting notes
* Project plans
* Organizational decisions

There are a number of proprietary solutions that allow for storage and organization of knowledge. OMSF projects have experience with 
* *Google Drive:* Useful for a wide range of file types, sharing with external collaborators. Difficult to organize or search, if used as the primary knowledge base it requires a lot of work to make documents discoverable (e.g. making Tabler of Contents files)
* *Confluence:* A powerful knowledge base with many built-in templates and automations. Very customizable, but requires a lot of commitment to use well.
* *Notion:* A lighter-weight knowledge base platform than Confluence, with similar use cases.
 In addition, open source alternatives exist, ranging from wikis to full-featured knowledge base systems, but currently no OMSF project has experience with such a platform.
 
### Tracker

Many of the responsibilities of project management described above require the team, and especially the PM, to have a comprehensive overview of the work being done. Projects thrive on comprehensive communication. While a knowledge base provides a long term, general understanding of a project, Trackers provide real-time information to members of a project team, giving context and clarity to day-to-day project tasks. A useful tracker should fit your individual projects needs, but all trackers should:
* Manage priorities
* Coordinate interdependent development efforts
* Give PM insight into the work to provide support to the team

Sometimes, a spreadsheet is not enough. There are a number of platforms that balance functionality and complexity -- the more things the platform can do, the steeper the learning curve and the more friction it can introduce into the team's workflow. OMSF projects have tried
* *Native GitHub features:* useful for small projects. Github has recently added features for coordinating work between different repositories or subprojects, but they don't scale well to the complexity of our larger projects that involve several team members working across many repos.
* *Trello:* Useful for small teams. Limited functionality.
* *Jira:* Useful for comprehensive management of large projects. Doesn't integrate well with GitHub.
* *Zenhub:* Project management layer on top of GitHub, for reduced friction between development and project management. Scales to complex projects better than native GitHub features, but is still pushed to the limits by our larger projects.

### Communications

Projects need a platform for internal communications between team members, as well as range of different channels for communicating with different stakeholders (see [Project Community](../project_community/#community-engagement/)). Remember, projects thrive on comprehensive communication. It is vital that projects not only have the ability to reach out to peers and close stakeholders, but that team members feel comfortable enough with the tools to do so. Whatever platform you choose, it should
* Facilitate asynchronous communication
* Keep written records of staff communication
* Organize communication records for easier recovery

Communication platforms are usually chosen based on cultural norms -- again, it's important that team members feel comfortable communicating on the platform. OMSF project primarily use Slack, with some common norms:
* Public channels for engaging with stakeholders
* Private channels for high-volume staff communication
* One Channel for each subproject / deliverable
* One Channel for each group of stakeholders
* One Channel for each software product
* Use group DMs sparingly - named channels allow more flexibility

OMSF projects also use Gmail for private, formal correspondence, including some engagement with industry partners.

## Evaluation and metrics

Simply put, metrics are measurable changes over time. More often than not, these are quantitative measurements that represent the state of a project. Metrics are almost never useful as individual points - they require a baseline and some time to determine health. Measuring Open Source Software is a hard problem, and OMSF projects have not settled on any specific set of metrics to track. We have considered
* *GitHub statistics:* These primarily reflect the actions of the developer team, except in very widely used, mature projects.
* *Package downloads:* Difficult to distinguish users from automated downloads in Continuous Integration pipelines.
* *Citations:* Nonexistent for young projects. Difficult to normalize for mature projects, as software tools may be described in a number of publications, making it unclear which papers' citations should be included.

## Publishing scientific papers

If your software project is successful, it will lead to new, publication-worthy science. Publishing a scientific paper is a much different kind of task than software development, and requires different expertise and considerations. The following is adapted from [Open Force Field's writing process and stages](https://docs.google.com/document/d/1tvkGiP5N_T2v7iH_Y1R69V-pXJUnTS8RqEnwf_TG-wM/edit?usp=sharing).

### Prepare a manuscript

Assign a *lead author* and a *lead PI*. The *lead author* is responsible for:
* providing drafts,
* coordinating feedback (give deadlines!)
* ensuring editing is done in a manner which does not result in irreconcilable editing clashes (e.g. multiple authors editing simultaneously in a way where they are making opposite edits simultaneously)

The *lead PI* is responsible for 
* supporting the lead author 
* ensuring that papers progress through stages in a timely manner. 

If an author does not provide feedback when required, the *lead PI* (or their delegate) should take responsibility to give that author appropriate options, such as (a) drop off of the paper, or (b) agree to let it proceed without providing review at that stage. 
The choice of option (b) affects later stages – for example, a collaborator who declines to provide feedback on a rough draft should not then request major restructuring at a later stage.

The lead author and PI will set the timeline for feedback for each stage of the process. 
* Usually 1-2 weeks is reasonable for comments, but extensions may be granted for individuals on a case-by-case basis, such as (for example) if someone is traveling. 
* However, if the work is funded by Consortium, a draft must be provided to the partners for comment for 30 days (or up to 45 days if they need and request more time) before preprinting and submission. This review (per the CRA) is to ensure appropriate credit is given, and can serve to strengthen the work, but does not give partners veto power. 
* The lead PI should request the review from partners. 
* Partners will check the box associated with their name in the provided spreadsheet for each manuscript. 
* Partners should also be informed that a failure to provide comments will be assumed to mean they approve.
#### Resources 

* [Manuscript review tracker](https://docs.google.com/spreadsheets/d/12UgwPGjWFXqsBm5FTW59SKUUw4PzSHvvA79aSItOog8/edit?usp=sharing)
* [Ten simple rules for collaboratively writing a multi-authored paper](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006508)

### Attribute authorship

We recommend using the [Contributor Role Taxonomy (CRediT)](https://credit.niso.org/) framework for attributing authorship. For each publication, prepare a chart where individuals will be able to put their or someone else’s name next to the appropriate CRediT category (see [example](https://docs.google.com/spreadsheets/d/12UgwPGjWFXqsBm5FTW59SKUUw4PzSHvvA79aSItOog8/edit?gid=0#gid=0)). The list of contributors with short contribution descriptions should be published on the website and on Zenodo record for the given record.

### Publish!

OMSF projects usually publish manuscripts to a preprint server, such as 
* [Arxiv](https://arxiv.org/)
* [Chemrxiv](https://chemrxiv.org/)
* [Biorxiv](https://www.biorxiv.org/)

Once a manuscript is available as a preprint, be sure to [share it on social media!](../project_community/#community-engagement/) Figures should be published on Zenodo under a CC-BY license.

The [Journal of Open Source Software](https://joss.theoj.org/) is often an appropriate venue for a relatively brief software publication, which can serve as a reference for subsequent data-driven papers in discipline-specific journals.
