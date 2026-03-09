# Project 1 - SDV Demonstration Platform

## Project 1 Name
SDV Demonstrator

## Nature of Project
Multi-processor embedded software architecture and system integration project for a Software-Defined Vehicle demonstration platform

## Location/s of Project
Novi, Michigan, USA

## Name of Your Employer
IAV Inc.

## Total Project Duration
From: 07/25
To: on-going

## Your Involvement
From: 07/25
To: on-going

## Client Details
Client's Business Name: IAV Inc.  
Business Address: 39525 MacKenzie Dr. Suite 1000, Novi, Michigan, 48377 USA
Web Address: www.iav.com/us  
General Email Address: info@iav.com
Contact Name/s: Chris Coyne
Contact Phone Number/s: +1 877 926 - 8428

## Project Resources
Your Team Size: 3
Total Project Team Size: 5

## Personal Involvement
- 07/25 to 07/25: Requirements and concept definition
- 07/25 to 08/25: Software architecture design and platform partitioning
- 08/25 to 08/25: Integration of processing environments and communication interfaces
- 08/25 to 09/25: Demonstration validation and customer presentation support - for the first showcase (Ford)
- 09/25 to 10/25: Update for showcasing to another customer (Stellantis)
- 12/25 to 01/26: Update for showcasing to another customer using Lego Raptor and RC Car (GM)

## Describe your role/s and responsibilities in the project.
I worked as a Senior Software Engineer on a Software-Defined Vehicle (SDV) demonstration platform at IAV. The project centered on a demonstration board containing NVIDIA Jetson, Renesas R-Car, and the IAV Dragoon ECU. Its purpose was to showcase IAV's SDV knowledge, architecture strategy, and deployment approach through a working embedded system that could be reused across different vehicles with minimal software change for customer-facing demonstrations. My primary responsibility was to lead the software architecture and integration of this multi-processor platform. I was responsible for defining how the major software and hardware components would interact, how responsibilities would be partitioned across the processing environments, and which technologies would be used to support the architecture, including Eclipse eCAL for communication and Docker-based containerization on the R-Car. After the design was established, I worked primarily on the R-Car side while another team member worked on the Jetson side. We jointly verified that communication between Jetson and R-Car was robust and consistent by sending large data sets in both directions, timing the transmission, and confirming stable behavior under loaded or stressed conditions appropriate for a demonstration platform. I also helped design how the Dragoon ECU software should behave so it could remain flexible across the Volkswagen ID.4, Ford Escape, Lego Raptor, and RC car setups, and I designed and implemented the build configuration for those different environments. A third team member implemented the signal-handling logic on the Dragoon based on that design. Because the Dragoon used a bootloader, updates could be performed efficiently over CAN. I also helped adapt the demonstration strategy when customer constraints changed, including a pivot from full vehicle demonstrations to smaller physical demonstrators that preserved the same architectural concept.

## Business Opportunity or Problem
The project addressed the need to demonstrate a scalable Software-Defined Vehicle architecture that could support multiple hardware platforms, multiple vehicles, and multiple customer scenarios. The challenge was not only to build a working prototype, but to show that a distributed embedded software architecture could separate responsibilities across different computing environments while still operating as a coherent system. The demonstration board had to show that one core platform could be installed into very different vehicles, in this case a 2021 Volkswagen ID.4 and a 2025 Ford Escape, with minimal software changes. The main software reflash was required only on the IAV Dragoon ECU because it communicated directly with each vehicle and therefore had to adapt to different signals, network topologies, and vehicle data. A further challenge emerged when GM requested a demonstration but did not allow vehicles inside its facility due to safety concerns. This required a pivot in the demonstration method while preserving the same SDV architecture and value proposition. The broader opportunity was to demonstrate how SDV concepts such as downloadable applications, modular deployment, and separated processing responsibilities could be applied in a practical automotive environment, even when the final showcase format had to change.

## Solution
I led the software architecture and integration of a multi-processor SDV demonstration platform using NVIDIA Jetson for internet connectivity and graphical user interface functions, Renesas R-Car for application hosting and execution, and the IAV Dragoon ECU for direct vehicle interfacing. The demonstration included an app-store concept connected to a cloud-based store capable of hosting different vehicle applications, ranging from convenience features to potential performance-related functions. My contribution focused on defining the software structure, assigning responsibilities to the different processing environments, and integrating the system components so that they operated as one platform rather than isolated devices. I selected Eclipse eCAL as the higher-level communication framework and Docker-based containerization on the R-Car so that downloaded applications could be isolated from the rest of the platform. Jetson to R-Car communication used eCAL over UDP, while R-Car to Dragoon used eCAL over SocketCAN so that SocketCAN handled the low-level CAN interface and eCAL provided the higher-level communication layer. I worked primarily on the R-Car implementation and integration, while coordinating with the Jetson implementation so the communication path remained robust during demonstrations. The integrated system then used the Dragoon ECU to command simple vehicle actions, such as blinking headlights or turn indicators in a defined pattern. When the GM demonstration constraint prevented the use of full vehicles, I helped pivot the showcase to a Lego Raptor and an RC car equipped with multiple LEDs to simulate headlights, brake lights, and indicator lights. This allowed us to preserve the same architectural demonstration while removing the dependency on full production vehicles.

## List the major deliverables of the project that you were responsible for or contributed to.
- Multi-processor SDV software architecture definition
- Integration approach for NVIDIA Jetson, Renesas R-Car, and IAV Dragoon ECU
- Communication architecture using Eclipse eCAL across the platform, with eCAL over UDP between Jetson and R-Car, and eCAL over SocketCAN between R-Car and Dragoon
- Software partitioning across cloud, GUI, application, and vehicle-interface responsibilities
- Application hosting concept with cloud-connected app-store workflow
- Integrated embedded software demonstrator for customer-facing scenarios
- Adapted demonstration platform using Lego Raptor and RC car with LED-based vehicle signal simulation
- Validation and demonstration support materials for platform evaluation

## Describe any design or problem-solving methods you used during this project.
I approached the work by treating the platform as a distributed embedded system with clearly separated functional responsibilities. I first identified the major system roles required for the demonstration, including internet connectivity, graphical user interaction, application execution, and vehicle interfacing. I then mapped those responsibilities to the most appropriate processing environments and defined how they should communicate as part of a unified architecture. Communication across the platform leveraged Eclipse eCAL as the higher-level communication framework. The Jetson and R-Car communicated using eCAL over UDP while connected through a router, and the R-Car communicated with the Dragoon ECU using eCAL over SocketCAN, where SocketCAN handled the low-level CAN interface. From the Dragoon ECU, a wire harness carrying power and CAN connected the demonstrator into the vehicle. My design approach focused on modularity, partitioning, scalability, and practical software integration so that the demonstrator could be reused across different vehicles with minimal software change. I also used containerization on the R-Car to separate application responsibilities and reduce the risk that one application could affect the rest of the platform. To validate the communication path, we exchanged large data sets between Jetson and R-Car, measured transmission timing, and confirmed stable operation under loaded conditions suitable for demonstration use. When the GM facility restriction prevented the use of actual vehicles, I applied the same architectural principles to a Lego Raptor and an RC car outfitted with LEDs to simulate vehicle lighting behavior. Iterative integration and validation were then used to confirm that both the full-vehicle and reduced demonstrator versions supported the same architectural message and demonstration objectives.

## Was your solution/s implemented? If so, describe the role you had, if any, in the implementation.
Yes. The solution was implemented as a working SDV demonstration platform. I was directly involved in the software architecture and integration activities required to move the platform from concept to a demonstrable system. My role included defining the architecture, supporting the integration of the key processing environments, and helping validate that the platform behaved as intended during demonstrations in multiple vehicle platforms as well as in the adapted Lego Raptor and RC car demonstrators.

## Results
The project successfully demonstrated a scalable software-defined vehicle architecture across multiple hardware platforms, multiple vehicles, and customer-facing scenarios. The integrated platform showed how cloud connectivity, graphical user interaction, application execution, and vehicle interfacing could be distributed across separate computing environments while still functioning as a coherent system. It also demonstrated that one board could be adapted for use in different vehicles with minimal software changes, with the main vehicle-specific software adjustments concentrated in the Dragoon ECU. After the demonstration approach was adapted for GM, the Lego Raptor and RC car versions made the showcase more portable and easier to deploy without relying on full vehicles. This expanded the usefulness of the demonstrator beyond the original full-vehicle setups and helped validate the technical feasibility of the architecture for broader customer-facing use cases.

## In retrospect, what would you have done differently on this project?
In retrospect, I would have introduced a more service-oriented architecture earlier in the project. When the first showcases were prepared in July 2025, the turnaround was very fast and Eclipse eCAL was effective because the demonstration objective was relatively simple: move data through the platform and trigger visible behaviors such as blinking lights. As the project has continued, the showcase has become more sophisticated and is moving beyond simple data transfer into higher-level vehicle features such as seat comfort scenarios, for example a relax mode that reclines the seat and sets a specific seat massage pattern. Because of this evolution, I would now move the design toward Eclipse S-CORE so the demonstration can be restructured around service-oriented architecture principles rather than primarily data movement. That would provide a stronger long-term foundation for expanding the demo as an ongoing platform.
