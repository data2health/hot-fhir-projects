# hot-fhir-projects
Overarching repo for hot-fhir projects.

# Healthcare Open Terminology FHIR (HOT-FHIR) server
**Baseline terminology server image for Healthcare Open Terminology FHIR Server**

Virtually all clinical and translational science data must be bound to controlled terminologies or ontologies to be 
interoperable, interpretable, and computable. To facilitate and simplify this process, establishing a common, shared 
suite of services to provide reliable API and download access to a family of terminologies, rendered in a common and 
predictable manner, is required. The domain of terminology services describes how this can be done.

Terminological resources (e.g. lexicons, dictionaries, classification systems, thesauri, classification systems, 
ontologies, etc.) come in a variety of shapes, sizes and representational forms.  While there have been a call
for a common API and shared model to unify terminological resources, to date communities have been able to get by with
ad-hoc models.  


## Problem statement
Translational data science bridges multiple communities and domains.   Today, different communities have different approaches
to incorporating terminological resources.  The clinical community still depends, in a large part, on customized tooling 
baked into vendor software, augmented by localized extensions supported by proprietary tools and workflows.
The biomedical domain, on the other hand, supports a large collection or terminological resources that fall under the 
umbrell term of "ontologies".  While many of individual resources share a common (RDF/SKOS or OWL) model, connections
and relationships between these resources often do not exist.

Integrating biomedical knowledge requires integration of the underlying model *semantics*.  One needs to be able to see
the big picture -- how the semantic elements in different models are related.  Doing this, in turn, requires a common
model and semantics to *represent* model semantics. 

The model and semantics of terminological resources need to be integrated across three orthogonol axes:
1) **Representational integration**-- terminological resources need to conform to a common, well-understood, extensible model.
2) **Software integration** -- terminological resources need to be fully accessible (read, query, update, extend) through a 
common Resource Oriented Architecture (ROA) API.
3) **Semantic integration** -- terminological resource *content* needs to be integrated, "mapped" and cross-linked to form
a semantic continuum. 

While there have been many attempts to address the integrational issues described above <sup><a name="footnote1">1</a></sup>, but until
very recently there hasn't been a compelling business case to actually adopt terminology services standards in a 
production environment.  The [FHIR community](http://hl7.org/fhir/), however, has defined a limited set of 
[terminological services](https://www.hl7.org/fhir/terminology-service.html
to support FHIR-specific use cases.  The success of the FHIR standard as a whole has resulted in widespread 
implementation and adoption of these limited cases.

To be useful, terminology services need to be both:
* **Distributed** -- a given terminology server image may need to be deployed on a variety of different platforms with
different security, performance and implementation requirements. The content of multiple of the same server need
to remain synchronized, either under manual or automatic control.
* **Federated** -- not all terminology service instances will carry the same content. There is a need to connect 
multiple server images in such a way that it represents a single, cohesive terminology space to an outside user.  

We will address the CTSA needs described above by:
1) Creating a deployable image of a representative FHIR Terminology service as it exists today.
2) Adding loaders that will allow the content of these servers to be expanded.
3) Extend the service capabilities guided by user requirements and, where appropriate, the HL7 CTS2 specification.


## Project description
We will start with an off-the-shelf FHIR Terminology server, [(HAPI)](http://hapi.fhir.org/) and will equip it with loaders
that will support (a) [Resource Description Format(RDF)](https://www.w3.org/2001/sw/wiki/RDF) and 
[Simple Knowledge Organization System (SKOS)](https://www.w3.org/2004/02/skos/),
(b) [the Web Ontology Language (OWL)](https://www.w3.org/OWL/), 
(c) the [Unified Medical Language System (UMLS)](https://www.nlm.nih.gov/research/umls/) [Rich Release Format (RRF)](https://www.ncbi.nlm.nih.gov/books/NBK9685/,
(d) [SNOMED CT](http://www.snomed.org/snomed-ct/) [RF2](https://confluence.ihtsdotools.org/display/DOCRELFMT/SNOMED+CT+Release+File+Specifications) format and
others as needed.

We will then assemble and prioritize community requirements for enhancements and extensions that support the representation
of the loaded information in the translational informatics settings.  Requirements will include discovery, mapping, 
(support for) authoring and enhancement and others.  We will extend and enhance the terminology services to support these
use cases.  These extensions and enhancements will be based on the existing [HL7/OMG Common Terminology Services 2](https://www.omg.org/spec/CTS2/About-CTS2/)
to the extent possible.


## Contact person

Point person (github handle) | Site | Program Director
----------|--------------|---------------
Harold Solbrig (@hsolbrig) | JHU | Chris Chute (@cgchute)

## Leads 

Lead(s) (github handle) | Site
----------|--------------|
Harold Solbrig (@hsolbrig) | JHU 


## Team members 

No action required here, a list of team members will be imported and linked below.

See https://github.com/data2health/project-repo-template/tree/master/team.md

## Repositories

- https://github.com/HOT-FHIR/server

## Deliverables
1) [Portable, deployable HAPI FHIR based terminology with baseline FHIR content](https://github.com/HOT-FHIR/server/milestone/1)
2) [Loaders for RDF/SKOS, OWL, RRF and RF2](https://github.com/HOT-FHIR/server/milestone/2)
3) [Community portal for evaluation, requirements gathering, discussion, etc.](https://github.com/HOT-FHIR/server/milestone/3)
4) [Implementation of selected high-priority extensions to support community needs](https://github.com/HOT-FHIR/server/milestone/4)
5) [Demonstration scripts and API services integrated into applications such as REDCap](https://github.com/HOT-FHIR/server/milestone/5)



## [Evaluation](evaluation.md)

## [Education](education.md)

## [Get involved](engagement.md)


## Working documents
* [Wiki](https://github.com/HOT-FHIR/server/wiki)

* [Project folder on Google Drive](https://drive.google.com/drive/u/0/folders/1bWaY2zC1MgAenKk-KcTm7q2DNx1rznqY)


## Slack channel
[The #hot-fhir slack channel](https://cd2h.slack.com/messages/CGCAPAANA) is accessible to onboarded participants. 


<sup>[1](#footnote1)</sup> Examples of terminology integration and representation projects include (but not limited to):
* [Unified Medical Language System (UMLS)](https://www.nlm.nih.gov/research/umls/)
* [Object Management Group's Lexicon Query Services](https://www.omg.org/spec/LQS/About-LQS/)
* [HL7 Common Terminology Services](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=10)
* [HL7 Common Terminology Services 2](http://wiki.hl7.org/index.php?title=Common_Terminology_Services_-_Release_2_(Normative))
* [NCI LexEVS](https://evs.nci.nih.gov/)
* [BioPortal](https://bioportal.bioontology.org/)
* [Simple Knowledge Organization System (SKOS)](https://www.w3.org/2004/02/skos/)
