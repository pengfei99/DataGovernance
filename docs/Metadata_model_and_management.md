# Metadata, metadata model and management

## 1. What is metadata?

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

## 2. Metadata classification

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


## 3. Standardizing Metadata
Metadata is only useful if it is understandable to the software applications and people that use it. 
