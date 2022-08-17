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

Below figure shows a general representation of data governance and management


### 1.1 Benefits
As we mentioned before, the objective of data governance is to ensure the availability, usability, integrity and 
security of the data. A well-designed data governance system can provide below benefits:

- data harmonization
- data quality guarantee
- data security guarantee
- data efficiency 
- government regulation appliance (e.g. GDPR)


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
- mission statement for the governance program 
- how its success will be measured (e.g. rules and metrics)
- data professional roles(e.g. CDO, data owner, etc.),what decision they can make, decision-making responsibilities, 
   and decision-making accountability
- organizational structures and collaboration between different roles
- data lifecycle
- development of governance policies
- documentation of the process
- the creation of `data management tool` (e.g. data catalog, quality control, etc.)

An organization's governance framework should be documented and shared internally, so everyone who is involved 
understand how the data governance program will work.

On the technology side, a data governance tool can be used, but not mandatory. The objective of such tool is to 
facilitate and automate all the aspects of managing a governance program which we have mentioned above

Note the data governance is a continuous effort, and the governance policies should be review regularly to meet 
the requirement of new emerging data asset.

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

People often confuse about the terms `data governance` and `data management`, and don't know the difference between them.
- **data governance**: refers to the process of making policies and decisions, and who can make these decisions of how the
data should be governed. 

- **data management**: refers to the implementation of the policies and decisions made by the data governance. 

For more information, you can read below papers:
1. Fu, Wojak, Neagu, Ridley, & Travis, `Data governance in predictive toxicology`
2. Khatri & Brown, `Designing data governance`. 

## 4. Data governance program execution

In general, we should follow below steps when we run a data governance program.
1. identifying the data assets (e.g. origin, type, format, etc.) and all the people who are working with these data 
   assets(e.g. data owners who produce the data, data stewards who clean and transform, data consumers who use data to produce
   report, stats, etc.).
2. Gathering requirements of the identified data assets by discussing with all the data professionals. 
3. Defining the objectives of the data governance program based on requirements and budget.
4. Defining the mission statement for the governance program 
5. Defining the rules and metrics on how to measure the success of each mission
6. Defining different roles of the data professionals (e.g. CDO, data owner, data steward, etc.) and their 
   decision-making responsibilities/accountability
7. Defining the organizational structures of these roles and how different roles should collaborate between them
8. Defining data life-cycle(e.g. data collection, data cleaning, data cataloging, data publication, data archiving) and
   which roles are involved in each step.
9. Development of governance policies and measurement metrics (e.g. metadata management, data quality, data security, etc.)
10. Documenting the process of how the governance policies are developed and the procedure of policies update
11. Review the data governance program regularly to meet the new requirement of new emerging data asset.

## 5. Best practices for developing a successful data governance program

### 5.1 Avoid data policing
Because data governance typically imposes restrictions on how data is handled and used, and usually, it's the IT 
and data management teams that lead data governance program. As a result, they'll be seen as the `data police` 
by business users. 

To avoid resistance of the business users to governance policies, we recommend that programs be business-driven, 
with data owners involved and the data governance committee making the decisions on standards, policies and rules.

### 5.2 Education is the key
Training and education is the key of a successful data governance program. Particularly to familiarize business users 
and data analysts with data usage rules, privacy mandates and their own responsibility for helping to keep data 
sets consistent. 

### 5.3 Commit to openness, awareness, communication and training
Several of these practices build on a shared understanding of the data governance process across the organization. Data governance can't be effective if data users don't know about the program.

- Be open about the program, its goals and its measures of success. Publish the governance strategy, describe the processes and share the metrics.
- Awareness of the program should be part of all employee onboarding policies. If compliance training exists for subjects like harassment issues, work with those teams and HR to get data governance onto a similar track.
- In all technical training related to data, such as the deployment of BI tools, include relevant elements of the governance strategy and how it pertains to the tools and platforms under review.
- Training also needs to cover the importance of data quality, the policies associated with it and how to discover and reuse sanctioned data sources. Data analysts and report authors in particular shouldn't feel like they're being asked to trade agility for policy. Instead, they should see governed data as a resource that opens up possibilities for working confidently within the guidelines.
- Implementing a "governance assured" stamp of approval can be added to dashboards, reports and other artifacts to show that the data has been governed properly.

Communication with all data professionals and end users about the progress of the data governance program is also a 
must, through a combination of reports, email newsletters, workshops and other outreach methods.

### Review your data governance policy regularly
An effective data governance program requires a continuous effort. New roles will emerge. Regulations will change. Determine what's needed to keep pace and adopt the necessary technologies and platforms.

Repeatedly evaluate governance policies. An annual assessment makes sense at a minimum because a lot can change in one year. Other reviews will be ad hoc, for example, when a merger or acquisition brings new data, new people and new tools on board. Some sectors, such as financial services, may see frequent changes not only to data legislation, but also to rules concerning money laundering, sanctions, liquidity, credit and so on.

A well-conceived and consistent review process can be an eye-opening exercise.

### Don't take data privacy protections on trust
Consumers worldwide are increasingly concerned about data privacy and, for good reason, they don't believe enterprises have their best interests at heart. A data governance program can improve customer confidence in the company's way of doing business.

- Be straightforward about your company's privacy policies and give customers control over their information. We are all familiar now with websites that ask visitors to specify their cookie policy. Ask customers for permission to use their data for different purposes, such as demographics research, product improvements and market trends.
- Put policies in place at every level of the enterprise that enforce preferences as rules. Some rules can be applied in code or technical procedures. For example, avoid extracting demographic data from a customer record and storing it in a data warehouse without the customer's permission. Other rules may be more like policies, such as "Don't use these customer records for product research."

### Secure your data close to the source
Security today is a specialized field. Threats are growing in sophistication. Protecting enterprise systems from external harm is a full-time job. Staying on top of access rules and permissions in a large, constantly changing business presents a real challenge.

Collaboration is essential between the security and data governance teams. The governance team should ensure that policies about data access are applied as close to the source data as possible. Customer data, for example, can be created and maintained in a transactional system's database but analyzed and reported on from a data warehouse. The data is regularly extracted from the transactional system and loaded into the warehouse. If security and privacy rules are applied on the source system, unnecessary data is eliminated from the data warehouse and governance of the data in it is greatly simplified.

Don't rely on client tools like business intelligence or data visualization platforms to apply security rules. By the time a BI user sees the data, it could have already passed through easily accessible, unsecured channels. Security for BI is a useful feature but should not be regarded as mission-critical.



### Create a virtual compliance team with data practitioners
Many of us work in highly regulated sectors, including public service, healthcare and finance. Even though compliance can't be guaranteed, it's important to achieve consistency and confidence. A virtual team can stay on top of compliance issues with a specific eye on data policy.

The team should be comprised of data practitioners such as database architects, software developers and business analysts who work directly with the governance program's data sources but don't report to a more formal compliance department. The team should continuously reevaluate legislation that relates to the governance program, identify where to improve or add new coverage to the program's policies and monitor the program for incidents, issues and progress.

Good governance policies clear the pathway to compliance without creating obstacles to business operations. Taking compliance seriously as part of a governance program helps take some of the burden and anxiety off other employees. A hospital's database administrator, for example, would have a heavy responsibility to keep the company's systems running and stay abreast of new healthcare data-handling legislation.



