
# VWSID XML Schema definition Version 2.0 

## Reference: Details of the Asset Administration Shell
Part 1 - The exchange of information between partners in the value chain of Industrie 4.0 (Version 2.0)
https://www.plattform-i40.de/PI40/Redaktion/DE/Downloads/Publikation/Details-of-the-Asset-Administration-Shell-Part1.html 

### General
In the following clauses an overview of the main concepts of the AssetAdministration Shell XML serialization is presented. For import and export scenarios the metamodel of an AssetAdministration Shell needs to be serialized. A serialization format is XML. The information is divided in three parts. The first part discusses the rules, in the second part are examples for some specific rules and in the third part the schema and a complete example is shown in the annex.

### Introduction
eXtensible Markup Language (XML ) is very well suited to deriving information from an IT system, perhaps to process it manually, and then to feed it into another IT system. It therefore meets the needs of the information sharing scenario defined in Section 0. XML provides for the possibilities of scheme definitions which can be used to syntactically validate the represented information in each step. For this reason, this document provides basic scheme definitions to permit a validation of information which is shared.
The XML definitions are divided into two different files:
•	IEC61360 datatype definition: iec61360.xsd
•	Core definitions for the AssetAdministration Shell and its export container: aas.xsd
Subsequently, an example in XML is provided.

### Rules
The main concepts of the XML schema and the resulting XML serialization are explained by the following rules. Rules 1 through 6 are general rules, while rules 7 through 11 are specific to References.

1.	XSD global Types are used for modeling
For reusability XSD global types will be used for modeling. There will be a naming convention <informationModelName>+’_t’
2. If present, names are taken from the information model. 
For comprehensibility reasons the XML key names should be the same as the representing Element in the metamodel. 
3. All identifiables have an aggregation on root level.
The identifiables are AssetAdministrationShells, Assets, Submodels, ConceptDescriptions. To reduce redundancy instances, they are located exclusively in the top-level aggregation. 
4. Repeating elements and their types will get the same names of their instances in plural.
If the element has a cardinality of n>1 a parent element will be used with the name of the name of the element in plural. For example, each element in the aggregation assets needs to be an asset. 
5.	Identifiables which are not in the top-level aggregations are only references to the corresponding instances in one of the top-level aggregations.
This rule completes the concept of rule 3. There should be no redundant identifiable in the serialized metamodel. 
6.	For elements with type LangStringSet an aggregation element called langStrings_t is added. For the single element a language tag “lang” is added. 
For internationalization purposes this rule is necessary.
7. The attributes of a key in a reference except for the value itself are realized as XML attributes.
8.	Data Specification Templates are directly added to the Concept Description because up to now only property descriptions are supported. 

Additionally, a new element EmbeddedDataSpecification is introduced that has two attributes: one for the global reference to the data specification identifier and one for the content of the data specification.
