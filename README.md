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

### 1.1 Benefits
As we mentioned before, the objective of data governance is to ensure the availability, usability, integrity and 
security of the data. A well-designed data governance system can provide below benefits:

- data harmonization
- data quality guarantee
- data security guarantee
- data efficiency 


#### 1.1.1 Data harmonization

In general, an organization contains many `data silos`, which is commonly built when individual business units 
deploy separate transaction processing systems without centralized data governance. These data silos makes data hard to
be reused due to different standard (e.g. schema, vocabulary, measurement units, etc.). 

Data governance can harmonize the data in those systems by defining a centralized standard and a collaborative process, 
with stakeholders from the various business units participating. And these standard and process will break down all data
silos inside the organization, thus improve the **availability** and **usability** of the data.

#### 1.1.2 Data quality guarantee

Data governance also defines the quality standard and treatment process of all incoming data, if the quality does not
meet the quality requirement, the data treatment process need to be applied to the data until the data quality meets
the requirement. 

#### 1.1.3 Data security guarantee

Data governance defines uniform data security policies on who can use the data, and how the data can be used (e.g. extraction, 
modification, deletion, etc.). It also defines who can modify the data security policies, along with procedures to 
monitor all policy modification, usage and enforcement. 

This can give you a guarantee of your data security and the compliance with data security regulatory laws. 

#### 1.1.4 Data efficiency

All above benefits can lower the costs of data usage when data scientists, analysts and business users want to access 
needed data. And the decision made based on the data are more accurate. 

Ideally, that will lead to competitive advantages and increased revenue and profits of the organization.

### 1.2 Who's responsible for data governance?

Below are the key participants and their primary governance responsibilities.

#### 1.2.1 Chief data officer. 

The chief data officer (CDO): if there is one -- is often the senior executive who oversees a data governance 
program and has high-level responsibility for its success or failure. The CDO's role includes securing approval, 
funding and staffing for the program; playing a lead role in setting it up; monitoring its progress; and acting as 
an advocate for it internally. If an organization doesn't have a CDO, another C-suite executive will usually serve 
as an executive sponsor and handle the same functions.

#### 1.2.2 Data governance manager and team. 
In some cases, the CDO or an equivalent executive -- the director of enterprise data management, for example -- 
may also be the hands-on data governance program manager. In others, organizations appoint a data governance manager 
or lead specifically to run the program. Either way, the program manager typically heads a data governance team that 
works on the program full time. Sometimes more formally known as the data governance office, it coordinates the 
process, leads meetings and training sessions, tracks metrics, manages internal communications and carries out 
other management tasks.

#### 1.2.3 Data governance committee. 

The governance team usually doesn't make policy or standards decisions, though. That's the responsibility of the data 
governance committee or council, which is primarily made up of business executives and other data owners. 
The committee approves the foundational **data governance policy** and associated policies and rules on things like data 
access and usage, plus the procedures for implementing them. It also resolves disputes, such as disagreements between 
different business units over data definitions and formats.

##### What is a data governance policy?
A data governance policy is a documented set of guidelines for ensuring that an organization's data and information 
assets are managed consistently and used properly. Such guidelines typically include individual policies for data 
quality, access, security, privacy and usage, and they specify different roles and responsibilities for implementing 
those policies and monitoring compliance with them.

A well-crafted policy is the foundation of an organization's data governance program. The data governance policy 
should articulate the principles, practices and standards that senior business and IT leaders have determined are 
necessary to ensure that the organization has high-quality data and that its data assets are protected against both 
internal misuse and external threats.

Ideally, the policy-forming group, called a data governance committee or data governance council, is primarily made 
up of business executives and other data owners. The policy document this group creates, in a process coordinated by 
data governance managers, clearly defines the organization's data governance structure and a set of governance rules 
and procedures for the executive team, business managers, data analysts and operational workers to follow.

For example, a data governance policy formally outlines how data processing and data management should be carried 
out to make sure that data is accurate, consistent and accessible throughout an organization's systems. The policy 
also establishes who is responsible for data under various circumstances. In addition, it can incorporate 
risk management and data ethics principles to reduce potential business problems from the improper use of data.

#### 1.2.4 Data stewards. 
The responsibilities of data stewards include overseeing data sets to keep them in order. They're also in charge of 
ensuring that the policies and rules approved by the data governance committee are implemented and that end users 
comply with them. Workers with knowledge of particular data assets and domains are generally appointed to handle the 
data stewardship role. That's a full-time job in some companies and a part-time position in others. 
There can also be a mix of IT and business data stewards.

#### 1.2.5 Other data professionals
Data architects, data modelers and data quality analysts and engineers are usually part of the governance process, too.
They work with the governance team to setup standards and quality metrics, etc.


### 1.3 Data governance framework

A data governance framework should help us to define all aspects of managing a data governance program and its workflow 
- objectives of the data governance program
- mission statement for the program 
- how its success will be measured (e.g. rules and metrics)
- decision-making responsibilities 
- decision-making accountability///////////////
- collaboration between different roles
- development of governance policies
- documentation of the process 
- organizational structures 
- the creation of `data management tool` (e.g. data catalog, quality control, etc.)

An organization's governance framework should be documented and shared internally, so everyone who is involved 
understand how the data governance program will work.

On the technology side, a data governance tool can be used, but not mandatory. The objective of such tool is to 
facilitate and automate all the aspects of managing a governance program which we have mentioned above


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