# Introduction of DCAT

DCAT is a vocabulary based on RDF used to describe datasets in data catalogs. It enables interoperability between data portals (e.g., governmental open data platforms).



## **DCAT is built on RDF**

**DCAT is an RDF vocabulary** specifically designed for describing datasets and data catalogs. `RDF provides the 
data model and syntax`, while `DCAT defines a semantic schema (ontology) within that model` for a very specific 
purpose:
- describing datasets
- describing metadata of datasets
- how to access datasets.

## Core Classes

DCAT has the below classes:

- **dcat:Catalog**: A collection of datasets.
- **dcat:Dataset**: A single dataset (e.g., a CSV file, API endpoint).
- **dcat:Distribution**: A specific available form of a dataset (e.g., download URL, format).
- **foaf:Agent**: An entity responsible for datasets (e.g., organizations).


## A simple API catalog example in turtle

```text

@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://intranet.local/catalog> a dcat:Catalog ;
    dct:title "Internal API Catalog" ;
    dct:description "Catalog of internal APIs used across departments" ;
    dct:publisher <http://intranet.local/org/IT> ;
    dcat:dataset <http://intranet.local/dataset/user-api> ,
                 <http://intranet.local/dataset/inventory-api> .

<http://intranet.local/dataset/user-api> a dcat:Dataset ;
    dct:title "User Management API" ;
    dct:description "API for managing user profiles, roles, and permissions" ;
    dct:creator <http://intranet.local/org/IT> ;
    dcat:distribution <http://intranet.local/distribution/user-api-v1> .

<http://intranet.local/distribution/user-api-v1> a dcat:Distribution ;
    dct:title "User API v1 REST JSON" ;
    dcat:accessURL <https://internal.api.local/v1/users> ;
    dct:format "application/json" ;
    dct:conformsTo <https://www.openapis.org/specification> .

<http://intranet.local/dataset/inventory-api> a dcat:Dataset ;
    dct:title "Inventory API" ;
    dct:description "Exposes stock and warehouse data" ;
    dcat:distribution <http://intranet.local/distribution/inventory-api-v1> .

<http://intranet.local/distribution/inventory-api-v1> a dcat:Distribution ;
    dcat:accessURL <https://internal.api.local/v1/inventory> ;
    dct:format "application/json" ;
    dct:license <http://intranet.local/license/internal-use-only> .

```

## A simple example in JSON-LD

```json
{
  "@context": {
    "dcat": "http://www.w3.org/ns/dcat#",
    "dct": "http://purl.org/dc/terms/",
    "foaf": "http://xmlns.com/foaf/0.1/",
    "xsd": "http://www.w3.org/2001/XMLSchema#"
  },
  "@id": "http://intranet.local/catalog",
  "@type": "dcat:Catalog",
  "dct:title": "Internal API Catalog",
  "dct:description": "A catalog of internal APIs used by different business units",
  "dct:publisher": {
    "@id": "http://intranet.local/org/IT",
    "@type": "foaf:Agent",
    "foaf:name": "Internal IT Department"
  },
  "dcat:dataset": [
    {
      "@id": "http://intranet.local/dataset/user-api",
      "@type": "dcat:Dataset",
      "dct:title": "User Management API",
      "dct:description": "Handles operations related to users, roles, and permissions",
      "dct:creator": {
        "@id": "http://intranet.local/org/IT",
        "@type": "foaf:Agent",
        "foaf:name": "Internal IT Department"
      },
      "dcat:distribution": {
        "@id": "http://intranet.local/distribution/user-api-v1",
        "@type": "dcat:Distribution",
        "dct:title": "User API v1 (REST/JSON)",
        "dcat:accessURL": {
          "@id": "https://internal.api.local/v1/users"
        },
        "dct:format": "application/json",
        "dct:conformsTo": {
          "@id": "https://www.openapis.org/specification"
        }
      }
    },
    {
      "@id": "http://intranet.local/dataset/inventory-api",
      "@type": "dcat:Dataset",
      "dct:title": "Inventory API",
      "dct:description": "Provides access to inventory levels and warehouse tracking",
      "dcat:distribution": {
        "@id": "http://intranet.local/distribution/inventory-api-v1",
        "@type": "dcat:Distribution",
        "dcat:accessURL": {
          "@id": "https://internal.api.local/v1/inventory"
        },
        "dct:format": "application/json",
        "dct:license": {
          "@id": "http://intranet.local/license/internal-use-only"
        }
      }
    }
  ]
}

```