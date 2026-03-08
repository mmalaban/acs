# Project 2 - InfraDID Config

## Project 2 Name

InfraDID Config

## Nature of Project

Internal diagnostic automation and base software configuration tool development

## Location/s of Project

Auburn Hills, Michigan, USA

## Name of Your Employer

BorgWarner, Inc.

## Total Project Duration

From: 02/22  
To: 04/22

## Your Involvement

From: 02/22  
To: 04/22

## Client Details

Client's Business Name: BorgWarner  
Business Address: 3800 Automation Ave #100, Auburn Hills, Michigan 48326, USA  
Web Address: [www.borgwarner.com](www.borgwarner.com)
General Email Address: [fill later]  
Contact Name/s: [fill later]  
Contact Phone Number/s: (+1 248 754 - 9600)

## Project Resources

Your Team Size: 1  
Total Project Team Size: 1

## Personal Involvement

- 02/22 to 02/22: Requirements analysis and problem definition
- 02/22 to 03/22: Tool architecture, parser design, and implementation
- 03/22 to 04/22: Output generation, integration support, and rollout

## Describe your role/s and responsibilities in the project

I was the sole software designer and developer for this internal BorgWarner project. I defined the tool concept, analyzed the AUTOSAR diagnostic configuration inputs, designed the parsing and generation flow, implemented the tool in Python, and validated the generated outputs for integration into the base software. I coordinated with system engineers, software architects, managers, supervisors, and other software engineers to confirm the required infrastructure Diagnostic Data Identifiers (DIDs), expected data content, and memory placement constraints. These participants acted as stakeholders and reviewers, while I remained the only developer working on the project itself. My responsibilities included ensuring that the generated C source and linker configuration outputs were consistent with AUTOSAR diagnostic configuration and suitable for customer-deliverable base software.

## Business Opportunity or Problem

The project addressed an internal software engineering inefficiency in the implementation of infrastructure-level Diagnostic Data Identifiers within AUTOSAR-based diagnostic software. Although the implementation logic for these DIDs was largely similar across programs, the actual data values and memory placement differed by project. Before this tool existed, there was no standardized implementation approach. Engineers had to manually review AUTOSAR ARXML client-server configuration, interpret data from the Complex Diagnostic Database (CDD), and implement the corresponding C code and linker configuration by hand. This process was slow, inconsistent, and prone to defects, especially when data needed to be placed correctly in ROM or Flash memory regions. The lack of automation increased turnaround time and created rework during integration and testing.

## Solution

I designed and implemented a Python-based automation tool called InfaDID Config. The tool parsed AUTOSAR ARXML configuration files, identified the client-server definitions associated with infrastructure DIDs, and cross-referenced the relevant diagnostic data definitions from the CDD file. Based on that information, it automatically generated the required C implementation and linker file configuration needed to integrate the DIDs into the base software platform. I used the Mako templating engine to define reusable interface templates for each DID type supported by a given project or program, which allowed the generated outputs to remain standardized while still accommodating project-specific data and memory-location parameters. This reduced manual interpretation effort, improved consistency across programs, and made the implementation process more repeatable and less error-prone.

## List the major deliverables of the project that you were responsible for or contributed to

- Python automation tool for infrastructure DID configuration
- ARXML parsing logic for AUTOSAR diagnostic definitions
- CDD parsing logic for diagnostic data extraction
- Mako-based templates for DID interface generation across supported projects/programs
- Generated C source/configuration outputs for infrastructure DIDs
- Generated linker file configuration for ROM/Flash placement

## Describe any design or problem-solving methods you used during this project

I approached the work by first analyzing the recurring implementation pattern used for infrastructure DIDs across projects. I separated the problem into three core parts: input interpretation, rules mapping, and output generation. I treated the ARXML file as the authoritative source for the diagnostic client-server configuration and the CDD file as the authoritative source for the DID-specific data content. I then designed the tool so that shared implementation logic would remain constant while configurable inputs would drive the generated output. To support this, I used the Mako templating engine to create reusable templates for DID interfaces, allowing project- or program-specific variations to be applied without rewriting the underlying generation logic. This reduced duplication and improved maintainability. I also considered embedded memory constraints as part of the design, since certain data had to be placed correctly in ROM or Flash. I validated the generated outputs against expected integration behavior and adjusted parsing and generation logic where inconsistencies were identified. The diagram below shows the high-level design flow I implemented for the InfaDID Config tool, from diagnostic configuration inputs through automated generation of C and linker configuration outputs.

## Was your solution/s implemented? If so, describe the role you had, if any, in the implementation

Yes. My solution was implemented and became part of the internal software development workflow. I was responsible for the complete implementation of the tool, initial validation, and support for integrating its outputs into the base software. The generated C and linker configuration artifacts were used as part of the software delivered to customers.

## Results

The project was successful. During my involvement between February 7, 2022 and April 21, 2022, implementation and testing for approximately 20 to 30 infrastructure DIDs typically required 1 to 2 weeks of engineering effort when performed manually. With the automation tool in place, the same work could be completed in about 3 days including testing. The main remaining effort shifted from manual implementation to clarifying which infrastructure DIDs were required and determining where the associated data should be stored in memory. The tool improved consistency, reduced manual coding errors, and provided a standardized method for implementing infrastructure DIDs across multiple programs.

## In retrospect, what would you have done differently on this project?

In retrospect, I would have extended the tool to automatically generate test cases for each supported DID. That would have further reduced manual validation effort and improved confidence in the generated outputs during integration and regression testing.
