# hot-fhir-projects
Overarching repo for hot-fhir projects.

# Healthcare Open Terminology FHIR (HOT-FHIR) ecosystem
**Federated terminology environment / ecosystem for healthcare** 

Virtually all clinical and translational science data must be bound to controlled terminologies or ontologies to be 
interoperable, interpretable, and computable. The integration of data from different, potentially disparate domains requires
a federated, shared suite of terminology resources based on a common set of API's, representational formats and underpinning
semantics.  The goal of the HOT-FHIR ecosystem project is to establish a unifying framework and scaffolding that allows 
terminological resources to be integrated, merged and extended to meet the requirements of the translational community


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
We will begin by creating an inventory of the terminology models, tools and content that are being utilized by our 
community members today. Our goal is to reuse and integrate as much as possible of these existing tools, with the goal 
being that the majority of our efforts be focused in (a) integration and (b) creation of missing bits and pieces that 
don't already exist elsewhere. This inventory will include, but will not be limited to:

### Models
* [Open Biomedical Ontololgies (OBO)](http://obofoundry.org/) - a model, semantics, community and infrastructure used to develop and
support a large collection of ontologies for biomedical data integration
* [Resource Description Format(RDF)](https://www.w3.org/2001/sw/wiki/RDF) - a basic model and fundamental set of semantics for the representation
of "triples" -- atomic assertions consisting of a *subject*, a *predicate* and an *object*.
* [The Web Ontology Language (OWL)](https://www.w3.org/OWL/) - a model and semantics for the representation of formal set-theoretical
ontology definitions
* [Simple Knowledge Organization System (SKOS)](https://www.w3.org/2004/02/skos/) - a model for representating thesauri based models developed by the library science
and translation communities
* [FHIR Terminology resources](http://hl7.org/fhir/terminology-module.html) - models and semantics for representing a core set of terminological resources from the FHIR perspective
* Tabular structures including:
    * [NLM Rich Release Format (RRF)](https://www.ncbi.nlm.nih.gov/books/NBK9685/) -- distribution format for the National Library of Medicine (NLM) Metathesaurus -- an integrated collection 
    of terminologies from the clinical space
    * [SNOMED Release Form 2 (RF2)](https://confluence.ihtsdotools.org/display/DOCRELFMT/SNOMED+CT+Release+File+Specifications) -- the model and format used to represent and
    distribute SNOMED CT content
    * [LOINC Distribution format](https://loinc.org/) -- a tabular format for distributing the Logical Observation Identifiers Names and Codes (LOINC) content 
* [HL7/OMG Common Terminology Services 2 (CTS2)](https://www.omg.org/spec/CTS2/About-CTS2/) -- a standard model for the REST based representation of terminological content.
 
### Tools and services
* FHIR Terminology Services - a specification for a set of terminology services designed to support Fast Healthcare Interoperability Resources (FHIR) specific use cases.  There
are multiple FHIR service implementations available that support the FHIR Terminology Service specification. For our purposes, we will do a short evaluation and select one of 
these that appears to most nearly support our reliability, performance and extensibility/usibility requirements. 
* [NCI Enterprise Vocabulary Services (EVS)](https://evs.nci.nih.gov/) - A rich, well established collection of REST based terminology services based on the HL7 Common Terminology Services 2 model
* NCI Development Enviroment - tools and workflow for maintaining the NCI Thesaurus
* [Protégé](https://protege.stanford.edu/) - An ontology editor and tooling ecosystem for working with OWL, SKOS and RDF terminology systems.  Protégé also supports a frame based model that may play some useful roles
* [SNOMED CT Terminology Services](https://github.com/ihtsdo) - a collection of RESTful and web services that support terminologies represented in the SNOMED RF2 model
* [OntoServer](https://ontoserver.csiro.au/) - a set of tools, workflow and extensions to the FHIR Terminology Service API for supporting SNOMED, OWL and OBO based ontologies
* [VocBench3](http://vocbench.uniroma2.it/) - a web-based, multilingual, collaborative development platform for managing OWL ontologies, SKOS(/XL) thesauri, Ontolex-lemon lexicons and generic RDF datasets.
* [Solor](http://solor.io) - a common model and accompanying set of tools for integrating SNOMED CT, LOINC, RxNORM and other terminologies developed by the Veterans Administration
* [BioPortal](http://bioportal.bioontology.org/) - a repository of biomedical ontologies and tools for integration and mapping.

### Content  
We will start with a baseline set of terminological resources that (a) are needed by many different communities within our
user base and (b) are representative of the different types of terminological resources that we expect to encounter as the ecosystem
expands.  This will include:
* RDF/RDFS
* SKOS
* ICD-10-CM
* LOINC
* RxNorm
* MONDO
* NCI Thesaurus
* SNOMED CT
* NCI MetaThesaurus / UMLS


### Requirements
We will assemble and prioritize community requirements.  We will start with the requirements that underly the set of models, tools and content assembled above and
will proceed to enhance and extend these requirements to support new needs that derive from the translation and integration process.  Requirements will include discovery, mapping, 
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
1) [Inventory of existing terminology models, tools, servers and content](https://github.com/hot-fhir/server/milestone/6)
2) [Baseline requirements document](https://github.com/hot-fhir/server/milestone/7)
3) [Community portal for evaluation, requirements gathering, discussion, etc.]((https://github.com/HOT-FHIR/server/milestone/3))
4) [Resource architecture and gap analysis](https://github.com/hot-fhir/server/milestone/8)
5) [Implementation of selected high-priority extensions to support community needs](https://github.com/HOT-FHIR/server/milestone/4)
6) [Demonstration scripts and API services integrated into applications such as REDCap](https://github.com/HOT-FHIR/server/milestone/5)




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
