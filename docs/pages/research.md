---
layout: page
title: Research
---

# Budget
Don't edit this - the RPPR generator populates this section

# Research Design
The goal of this project is to establish a network/ecosystem of terminological resoures that, in aggregate, can serve as
a virtual integrated source of semantic content, workflow and tooling for the CTSA network.  We will assemble and evaluate 
representative instances of terminological servers, tools, editing and mapping workflow and content and will use this 
evaluation to determine the strengths and gaps within the various tools.  We will then use the nascent FHIR Terminology
specification as foundation for a federated "ecosystem" of terminological resources that can serve as a single, virtual source
of semantic content for the various communities and use cases across the CTSA network.

 
# Methodology
* Create an inventory of existing terminology tools that are in active use by CTSA and related communities.  The purpose
of this exercise is to expose and evaluate the capabilities and limitations of each of these resources within the context
of a larger federation.
* Evaluate the assembled resources to determine the requirements and use cases that they are intended to address and their strong
points and limitations
* Use the existing resources and their evaluation to flesh out CTSA community requirements -- what exists today and what is
or will be needed in the near future
* Design an architecture based on a FHIR Terminology foundation that allows the requirements and use cases to be addressed
in a de-centralized, federated fashion and that takes advantage of, to the extent possible, existing technology, community 
involvement and workflow.
* Select a set of representative use cases, requirements and content will be used for:
   * testing and hardening the architectural base
   * delivering immediate value to the larger community
   
# Expected Outcomes
* A functioning collection of terminology servers, tools and development enviroments drawn from resources that exist today
* A model and architecture that allows this collection to co-exist as elements in a unified, virtual federation
* An implementation of key portions of this model and architecture that validates and demonstrates the key elements of the
model and architecture
* A proposal for a set of extensions and enhancements to the FHIR terminology service model that will document and 
standardize the model and underlying elements of the architecture
* An open source set of tools, services and connectors that enable content discovery, mapping, editing and extensions of
semantic content from a unified semantic perspective.

# Deliverables
1) [Inventory of existing terminology models, tools, servers and content](https://github.com/hot-fhir/server/milestone/6)
2) [Baseline requirements document](https://github.com/hot-fhir/server/milestone/7)
3) [Community portal for evaluation, requirements gathering, discussion, etc.]((https://github.com/HOT-FHIR/server/milestone/3))
4) [Resource architecture and gap analysis](https://github.com/hot-fhir/server/milestone/8)
5) [Implementation of selected high-priority extensions to support community needs](https://github.com/HOT-FHIR/server/milestone/4)
6) [Demonstration scripts and API services integrated into applications such as REDCap](https://github.com/HOT-FHIR/server/milestone/5)

# Timeline (monthly)
* 2019
  * 6/15 - Selection of and deployment of baseline FHIR terminology server
  * 7/1/ - Deployment of other selected services and resources
  * 7/15 - Evaluation environment in place
  * 7/15 – Identifying key semantic resources (e.g. terminologies, classifications, an ontologies) that are required for translational research
  * 8/1  - Preliminary requirements and use case documentation
  * 8/1  - Demonstration of FHIR terminology server and extensions that support a representative sample of semantic content needed for translational research
  * 8/15 - Deploy community portal and initiate advertisement and gathering of requirements and use cases
  * 10/1 - Preliminary architectural proposal ready for review
  * 12/1 - First draft of FHIR based extensions to implement architectural proposal
* 2020
    * 2/1 - Baseline extensions implemented on top of existing services
    * 4/1 - Existing services and content integrated into FHIR Terminology Federation model
    * 4/1 – Broaden network of FHIR terminology resources to increase content
    * 6/1 -  Increase amount of CTSA FHIR data model having canonical semantic binding
    # Potential Pitfalls and Alternative Strategies
The overall timeline and cost of this approach depends, in no small part on:
1) How much of the CTSA community requirements are already implemented and available in existing services and tooling
2) How amenable existing services and tooling are to federation and integration within a larger infrastructure

Until we've completed the initial evaluation and moved into the requirements gathering phase, we will not know how much we can
reuse as is, how much we can modify, what we need to rewrite or re-create and how much bespoke work we will need to do.  In addition,
the extent that we can depend on the assistance and/or collaboration from existing communities will make a big difference in the
cost and timeline for the final product.

Another major issue that we will face is that most of our needs and requirements are not unique to the CTSA community.  We are 
aware of similar efforts that are "on the drawing board" in related communities and that there is a real potential for competing
or conflicting solutions.  For this reason we believe that ongoing education, outreach and collaborative efforts will need to
be a core, funded component for this project from its inception, and we will need to establish an open, welcoming community that
fosters collaboration and sharing.
