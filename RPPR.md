# Budget
Don't edit this - the RPPR generator populates this section

# Research Design
Aggregating, mapping, binding, and serving semantic content is best done through a terminology server.  The key goal of this project is to establish a network of compatible terminology servers that in aggregate can serve the source for semantic content for the CTSA network.
# Methodology
We will explore FHIR compatible terminology servers
* That are capable of responding to FHIR API terminology queries
* create or point to instances that contain conventional US Core FHIR specification ontology
* can support RDF/OWL dependent terminologies such as Human Phenotype Ontology or MONDO
* can be configured are addressed as a networked resource across many sites
* can contain or point to content in related federal terminology resource such as the NCI Thesaurus
* can support cloning or replication for local terminology service response optimization
* can be extended to support the OMG Common Terminology Services V2 specification functionality relevant to the translational research use case
# Expected Outcomes
The primary outcomes for this project are:
* an integrated network of terminology services that in aggregate address the semantic needs of the CTSA program and translational research
* Identifying FHIR services that contain critical and important sematic resources 
* extending or adopting extensions to FHIR terminology services where necessary
# Timeline (monthly)
* 6/15 – A FHIR terminology server that can demonstrate some semantic content needed for translational research
* 6/15 – Identifying key semantic resources (e.g. terminologies, classifications, an ontologies) that are required for translational research
* 8/1 – Exploring the CRISO terminology server for RDF/OWL functionality extensions
* 9/1 – Prototype cross-server functionality and services in a proto-network of severs
* 9/20 – Demonstrate proto-network of terminology services and preliminary binding to FHIR data model for translational science
* 1/1 – Broaden network of FHIR terminology servers to increase content
* 1/1 – Support downloads of semantic maps
* 1/1 -  Increase amount of CTSA FHIR data model having canonical semantic binding
# Potential Pitfalls and Alternative Strategies
The biggest challenge for CTSA data aggregation is that the source data simply will not have sufficient information to identify canonical semantic tagging or binding.  The major alternatives include:
* identifying what coding exists and exploiting semantic mapping into canonical form
* using NLP methods to capture information not in coded form, and transform into canonical terms
