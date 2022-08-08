# DataGovernance and all that

Data become more and more important for an organization. But how to govern and manage them is still quit challenging. 
In this repo, I will list all the thing that I learned about the data governance and management. 

## 1. What is data governance?


**Data governance is a collection of processes, roles, policies, standards, and metrics that ensure the availability, 
usability, integrity and security of the data.** It makes the use of data consistent, trustworthy, effective and efficient. 

**Data governance is a strategy, not technology**. It consists a set of decision-making process and rules which 
governs data throughout their entire life-cycle. It defines mainly three things:
- People: who has the right to make the decisions and accountable for them. For example, if someone asks to access data,
  who can decide whether we grant the access to the user or not.
  
- Policies: what decisions/rules must be made to ensure effective management and use of data (decision domains). For example, 
  before publishing data, the data must pass the quality control and privacy control, etc.

- Metrics: how to measure/evaluate if decisions/rules are respected. For example, to control the data quality, we need 
  to define the metrics for data accuracy, completeness, etc.

**Data management is an entire suite of practices, processes,  systems and tools which implement the data governance definitions**. 

### 1.1 Goals and benefits

## 2. The five decision domain for data governance

In previous section, we have said we need to make decisions to ensure effective management of data. In general, we have
five principle decision domains:
- **Data Principles**: defines behaviors of all stakeholders of a dataset and establish the link between them. For
  example, for a dataset, we define and assign role such as business owners and data professionals to people. We also 
  define their responsibility. For instance, business users need to help provide information about data quality as well as its 
  lifecycle, interpretability and access. Based on this information, data professionals implement data quality control,
  access control, etc. 
    
- **Data Quality**: Use the metrics defined by the data governance to evaluate the data quality. 
  
- **Metadata management**: Use metadata to ensure that the data discoverability, usability, traceability, auditability, etc. 
  
- **Data security**: Ensure the data confidentiality, integrity, and availability. 
  
- **Data life cycle**: Ensure the data life cycle conforms with the data governance policy. 

Below figures shows a graphical presentation of the above definitions

![introduction_of_data_governance_terms](https://raw.githubusercontent.com/pengfei99/DataGovernance/main/img/introduction_of_data_governance_terms.png)



### 2.1 Data principals definition and implementation

### 2.2 Data quality definition and implementation

[Data quality](https://github.com/pengfei99/DataGovernance/blob/main/docs/data_quality.md)

### 2.3 Metadata management definition and implementation

### 2.4 Data security definition and implementation

### 2.5 Data life cycle definition and implementation

## 3. Difference between data governance and data management

The main difference between the terms `data governance` and `data management` is that `data governance` refers to 
the policies and decisions that must be made and who can make these decisions.

Data management refers to the implementation of the policies and decisions. For more information, you can read below
papers:
1. Fu, Wojak, Neagu, Ridley, & Travis, `Data governance in predictive toxicology`
2. Khatri & Brown, `Designing data governance`. 

## 4. 