# Metadata, metadata model and management

## 1. What is metadata?

### ISO definition

In ISO/IEC 11179, the metadata (information objects) are data about Data Elements, Value Domains, and other reusable 
semantic and representational information objects that describe the meaning and technical details of a data item

### My definition 

**Metadata** is `structured information` that describes one or more aspects of a data entity. 
In general, Metadata is used to summarize basic information about data which can make `finding, tracking, using,
and managing` data easier. 

The aspects varie a lot based on the data entity properties and business requirements, below are some examples:

1. Means of creation of the data 
2. Data location, format, size, schema, and used standard
3. Purpose of the data
4. Time and date of creation 
5. Creator or author of the data
6. Process used to create the data 
7. Data quality
8. Data access rules
9. Data modification history


### 1.1 Objectives of the metadata

In general, the metadata can help us to achieve following objectives:

1. Semantic enrichment (SE): also called semantic annotation or semantic profiling, 
            consists in generating a description of the context of data, e.g., with tags, to make 
            them more interpretable and understandable. It is done using knowledge bases such as ontologies. 
            Semantic annotation plays a key role in data exploitation, by summarizing the datasets contained 
            in the lake so that they are more understandable to the user. It can also be used as a basis 
            for identifying data links. For instance, data associated with the same tags can be considered linked.

2. Data indexing (DI): consists in setting up a data structure to retrieve datasets based on specific 
                  characteristics (keywords or patterns). This requires the construction of forward or 
                   inverted indexes. Indexing makes it possible to optimize data querying in the lake through 
                   keyword filtering. It is particularly useful for textual data management, but can also be used 
                   in a semi-structured or structured data context.
3. Link generation and conservation (LG): is the process of detecting similarity relationships or integrating 
                preexisting links between datasets. The integration of data links can be used to expand the 
                range of possible analyses from the lake by recommending data related to those of interest to the 
                user. Data links can also be used to identify data clusters, i.e., groups where data are strongly
                linked to each other and significantly different from other data.
4. We define data polymorphism (DP): as storing multiple representations of the same data. Each representation 
                corresponds to the initial data, modified or reformatted for a specific need. For example, 
                a textual document can be represented without stopwords or as a bag of words. It is essential in 
                the context of data lakes to at least partially structure unstructured data to allow their
                automated analysis. Simultaneously storing several representations of the same data notably 
                avoids repeating preprocessings and thus speeds up analyses.
5. Data versioning (DV): refers to the ability of the metadata system to support data changes while conserving 
               previous states. This ability is essential in data lakes, as it ensures the reproducibility of 
               analyses and supports the detection and correction of possible errors or inconsistencies. 
               Versioning also allows to support a branched evolution of data, especially in their schema.
6. Usage tracking (UT): records the interactions between users and the data lake. Interactions are generally 
               operations of data creation, update and access. The integration of this information into the 
               metadata system makes it possible to understand and explain possible inconsistencies in the data. 
               It can also be used to manage sensitive data, by detecting intrusions.


It should answer the following questions:
- What is the data asset about? 
    - Descriptions (tables, columns)
    - Keywords or tags
    - Themes or categories
- Why does the data asset exist?
    - Data source
    - Lineage
    - Impact analysis
- Where is the data asset from?
    - Spatial coverage
    - Language
    - Business domains
- Who is responsible for the data asset?
    - Creator or owner
    - Contributors or experts
    - Point of contact
- When was the data asset created and updated?
    - Creation date
    - Last updated or modified date
    - Update frequency
- How can the data asset be used?
    - License
    - Classification
    - Use cases
## 2. Metadata classification/model

They are many ways to classify metadata, Here I only highlight two popular classification that I think more suitable
for a data management platform.

For more information, you can read the [UNDERSTANDING METADATA WHAT IS METADATA, AND WHAT IS IT FOR? By Jenn Riley](https://www.niso.org/publications/understanding-metadata-2017)

### 2.1 NISO (National Information Standards Organization of the USA)

NISO distinguishes 3 types of metadata:
- descriptive: Descriptive metadata is typically used for discovery and identification, as information to 
               search and locate an object, such as title, authors, subjects, keywords, and publisher.
- structural: Structural metadata describes how the components of an object are organized. An example of structural 
              metadata would be how a database organize tables inside it (e.g. schema of each table and relation between
              tables).
- administrative: Administrative metadata gives information to help manage the source. Administrative metadata refers 
                   to the technical information, such as file type, or when and how the file was created. 
                   Two sub-types of administrative metadata are `rights management metadata` and `preservation metadata`. 
                   Rights management metadata explains intellectual property rights, while preservation metadata 
                   contains information to preserve and save a resource.

### 2.2 MEDAL (University of lyon 2)

MEDAL distinguishes 3 types of metadata:
- Intra-object Metadata: are metadata that describes all properties of a data entity, in the form of key-value pairs. Including
           not only basic file descriptions (e.g. file title, size, location, etc.), but also advance metadata such as 
           access rights, semantic tags, content summery.
- Inter-object Metadata: are metadata that describes all relationships between data entities. The inter-object relation can be any 
                    relation, for example, it can be a
                     - grouping relation: for example, all data from the same survey should be in the same group   
                     - parenthood relation: if data entity A and B produce C and D, then A and B is the parent of C and D
                     - similarity relation: if two reports of a topic give the same conclusion, we can use a similarity 
                                            relation to link the two reports.
- Global Metadata: are metadata designed to provide a contextual layer to the data entities, which can facilitate data
                  discovery, interoperability. Unlike intra and inter metadata focus on concret data entities, 
                  global metadata are defined by the knowledge bases of entire organization or beyond. For example, 
                  the semantic resources such as ontologies, taxonomies, thesauri, dictionaries, etc.) are often used 
                  to classify data entity.

### 2.3 NISO more detailed classification

NISO also propose a more detailed classification which divide administrative metadata into three subclasses:

- Technical metadata
- Preservation metadata
- Rights metadata

Below shows some example and their primary uses.

| Metadata Type                     | Example Properties                                | Primary Uses                                             |
|-----------------------------------|---------------------------------------------------|----------------------------------------------------------|
| Descriptive metadata              | Title, Author, Subject, Genre, Publication date   | Discovery, Display, Interoperability                     |
| Technical metadata File type (ad) | File size, Creation date/time, Compression scheme | Interoperability, Digital object management,Preservation |
| Preservation metadata (ad)        | Checksum, Preservation event                      | Interoperability,Digital object management, Preservation |
| Rights metadata  (ad)             | Copyright status, License terms, Rights holder    | Interoperability, Digital object management              |
| Structural metadata               | Sequence, Place in hierarchy                      | Navigation                                               |
| Markup languages                  | Paragraph, Heading, List, Name, Date              | Navigation, Interoperability                             |


Note, the markup languages mix metadata and content (actual data) together, a practice only sometimes used with 
other forms of metadata. Flags inserted in the content denote notable features. For example, HTML is a markup, it
contains structural flags such as paragraphs; flagging words with semantic information—that the word is a place 
name or a certain part of speech; or providing formatting information, such as italics.


## 3. Standardizing Metadata

**Metadata is only useful if it is understandable to the software applications and people that use it**. We also 
mentioned before, metadata are structured data. To make metadata understandable, organizations frequently predefine 
metadata schemas(standard) to meet certain requirements, and publish these schemas for all data professionals 
(and sometimes end users) to consult.

I divide the metadata standardisation into two categories:
- the international standard
- the organization standard

### 3.1 The international standard

#### 3.1.1 Metadata (ISO/IEC 11179)
Much work is being accomplished in the national and international standards communities, especially ANSI 
(American National Standards Institute) and ISO (International Organization for Standardization) to reach a consensus 
on standardizing metadata and registries, which is **ISO/IEC 11179**.

This standard specifies a schema for recording both the meaning and technical structure of the data for unambiguous 
usage by humans and computers. 

#### 3.1.2 Geospatial metadata (ISO 19115)

**Geospatial metadata** (also geographic metadata) is a type of metadata applicable to geographic data and information. 

ISO 19115 is a standard to provide a clear procedure for the description of digital geographic data-sets so that 
users will be able to determine whether the data in a holding will be of use to them and how to access the data. 
By establishing a common set of metadata terminology, definitions and extension procedures, this standard promotes 
the proper use and effective retrieval of geographic data.

For more information, please read this [page](https://en.wikipedia.org/wiki/Geospatial_metadata)

#### 3.1.3 Dublin Core metadata terms ( ISO 15836)
The Dublin Core metadata terms are a set of vocabulary terms that can be used to describe resources for the purposes 
of discovery.

The original DCMES Version 1.1 consists of 15 metadata elements, defined this way in the original specification:

1. Contributor – "An entity responsible for making contributions to the resource". 
2. Coverage – "The spatial or temporal topic of the resource, the spatial applicability of the resource, or the jurisdiction under which the resource is relevant". 
3. Creator – "An entity primarily responsible for making the resource". 
4. Date – "A point or period of time associated with an event in the lifecycle of the resource". 
5. Description – "An account of the resource". 
6. Format – "The file format, physical medium, or dimensions of the resource". 
7. Identifier – "An unambiguous reference to the resource within a given context". 
8. Language – "A language of the resource". 
9. Publisher – "An entity responsible for making the resource available". 
10. Relation – "A related resource". 
11. Rights – "Information about rights held in and over the resource". 
12. Source – "A related resource from which the described resource is derived". 
13. Subject – "The topic of the resource". 
14. Title – "A name given to the resource". 
15. Type – "The nature or genre of the resource".

#### 3.1.4 W3C Data Catalog Vocabulary (DCAT)

The W3C Data Catalog Vocabulary (DCAT) is an RDF vocabulary that supplements Dublin Core with classes for Dataset, 
Data Service, Catalog, and Catalog Record.

For more information, please read this [page](https://www.w3.org/TR/vocab-dcat/)

### 3.2 The organization standard

As you can see, the metadata schema depends on the properties of data entities and the requirements of the organization. That's why geospatial data have their
own metadata standard. 

The advantage of using an international metadata standard is that your metadata have international interoperability.
The disadvantage is that it's not flexible enough to meet the requirements or data properties of the organization. So
mang organization have their own standard.

## 4. Metadata creation, 

### 4.1 Metadata created by Human

In traditions, metadata has primarily been created by human. Because there is no other way to create metadata. 
For example, in cultural sector, to assist users with finding printed books, journals, or manuscripts, A human must 
transcribe descriptive metadata such as title, author, and publication date by examining a physical item. 

For advance metadata such as book summaries, book category, or author background, we may even need an expert of the domain
who would do targeted research and then record the results. 

Even though with the digitization, you can use a purpose-built metadata entry systems (e.g. web app) to enter this 
metadata, but we still need a human to key in these data.

### 4.2 Metadata created by software

Technological advances have also demonstrated reliable methods for creating metadata through 
automated processes. `Technical metadata` in particular is an example of this. 

Most file formats(e.g. pdf, excel, etc.) include at least some embedded technical information designed to assist software with 
interpreting the content. File system can also provide some system-level information to add extra administrative 
information to files, such as date created or the ID of the user logged into the system at the time the file 
was generated.

Some machine learning technic are also used to classify text files, but it's still far from the human level accuracy.

## 5. Metadata storage, and sharing

Once we created the metadata, we need to store them and share them, so other user and software can use this metadata.
In general, we need to create a **metadata repository** which centralize all metadata and their related definition
(e.g. glossary, schema, etc.).

This metadata repository often provides Application Programming Interfaces (APIs) and specification documents that 
allows external software and users to `retrieve, create, modify, and delete` metadata.

### 5.1 Metadata repository implementation

There are two major categories of metadata repository implementation:
- database (e.g. relational, graph, key-value)
- file based (e.g. xml,csv,parquet,etc)


#### Database 

As we explained before, the metadata is `structured data`, so it's natual to use relational database to implement the
metadata repository. Each metadata attribute can be stored as `fields/columns` in relational database tables. 

Some implementation uses graph based database to maximize query performance for data lineage.

Maturity and flexibility of databases makes it as number one choice for intra-organization metadata repository.

Even though, implement a metadata repository with a database has many advantage, but it's hard to maintain, and you will
face security issues if you need to expose the repository for public access. 

#### File-based

In a file-based metadata repository, you just store all metadata inside a file, the file format can be structured, 
semi-structured, or even non-structured. 

The advantage is that it's easy to maintain, and no security issues for public access. Because people only download
a copy of the file.

The disadvantage is that it's hard to exploit for other software (for semi-structured, or even non-structured file).

## 6. Metadata management platform

Metadata management platform implements the metadata policies that are defined by the data governance which includes:
- metadata model (e.g. schema, business glossaries) implementation
- tools that enable metadata visualisation, creation, modification, deletion, and data indexing
- search engine

A metadata management platform should enable diverse data users to surface relevant metadata when and where they need it.
It may contain one or more tools that enable following functionalities :
- Metadata discovery/creation/ingestion (e.g  business glossaries)
- Metadata repository (a catalog, inventory, or dictionary)
- Metadata lineage
- Metadata automation and intelligence (e.g. automate classification, key word extraction)
- Metadata sharing and federation (equitable metadata access and data democratization across the diverse organizations)


### 6.1 data catalog

A data catalog is a tool that organize all the data assets via metadata of an organization which allows all data professionals to 
- discover/search data
- understand the context of data (e.g. quality, profile, etc.)
- enrich data context

5 must-have features of a modern data catalog:

- can handle heterogeneous metadata
- Organizes and consolidates metadata in a single repository
- Enables embedded collaboration (be able to adapt skill-sets, and workflows of all data professionals (de, ds,da))
Provides granular governance and access control
Built on open API architecture

### 6.2 data lineage

Data lineage is a map of the data journey, which includes its origin, each stop along the way, and an explanation 
on how and why the data has moved over time. The data lineage can be documented visually from source to eventual 
destination — noting stops, deviations, or changes along the way. The process simplifies tracking for operational 
aspects like day-to-day use and error resolution.

Data lineage tools help you track your data's changes at every step. Data, as captured from the source, isn't of 
much use until it goes through a series of data engineering processes like cleaning, wrangling, integration, 
remodeling, etc. To get the most value from your data, you need to keep track of its origins and lifecycle.

Here are five popular open-source data lineage tools
1. Tokern 
2. Egeria 
3. Pachyderm 
4. OpenLineage 
5. TrueDat

Data lineage is paramount to understanding your data's ownership, origins, quality, and journey. Choosing 
a tool that provides you with the level of detail, flexibility, and scalability that you want is an arduous task.

If you have an existing data setup, you will have to choose a tool that works with the data sources, orchestration 
tools, ETL tools, and query engines you have in place, and opt for the tool that works well for you.

### 6.3 business glossary repository

A business glossary is a list of business terms and their definitions that organizations use to ensure the same 
definitions are used company-wide when analyzing data. A business glossary produces a common business vocabulary, 
used by everyone in an organization. A unified, common language is a key component of data governance.

A business glossary repository is a centralized repository that stores and organize all business glossary of the 
organization.

https://www.insee.fr/fr/metadonnees/cpfr21/section/A?champRecherche=true
