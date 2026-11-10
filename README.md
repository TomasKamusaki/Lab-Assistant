AI Lab Assistant

Self-Hosted AI Assistant for Homelab Infrastructure, Network Diagnostics & Automation

AI Lab Assistant is a self-hosted artificial intelligence assistant designed to simplify the management, monitoring, documentation, and interaction with complex homelab environments.

The project combines local large language model inference, a Python backend, a native macOS desktop client, and controlled integrations with real network infrastructure.

Its purpose is to create a centralized, intelligent interface for interacting with servers, networking equipment, virtual machines, and infrastructure services through natural language.

Project Status: Active Development
Project Type: Personal Engineering & Research
Deployment: Self-Hosted / Local AI
Source Code: Private — Public Project Showcase

⸻

1. Project Overview

Managing a modern homelab often requires working with multiple independent systems:

* Firewalls and network gateways
* Managed Ethernet switches
* Physical and virtual servers
* Linux and Windows environments
* Virtualization platforms
* Network monitoring and diagnostic tools
* Storage systems
* Remote management interfaces

Each system typically has its own dashboard, configuration interface, or command-line tools.

As infrastructure grows, understanding the environment and performing routine diagnostics becomes increasingly complex.

AI Lab Assistant aims to bring these systems together through a single conversational interface.

Rather than replacing existing infrastructure tools, the assistant provides an intelligent interaction layer above them.

The long-term vision is an infrastructure-aware assistant capable of understanding the environment, answering technical questions, generating documentation, and safely executing authorized operations.

⸻

2. Project Goals

The project focuses on six primary objectives.

Centralized Infrastructure Visibility

Provide a unified interface for understanding the devices, networks, services, and systems operating within the homelab.

Local AI Processing

Run the primary language model on personally controlled hardware without requiring a cloud-based inference service.

Natural Language Interaction

Allow infrastructure information and supported operations to be accessed through conversational requests.

Controlled Infrastructure Access

Use explicitly defined tools and permissions rather than unrestricted shell or administrative access.

Automated Technical Documentation

Generate structured, editable architecture diagrams based on actual infrastructure observations.

Security-Oriented Automation

Develop a foundation for future controlled automation with explicit authorization and verifiable execution.

⸻

3. Project Screenshots

The following sections showcase the desktop interface, infrastructure integrations, diagnostics, and automatically generated architecture documentation.

Desktop Assistant

Native macOS desktop assistant with a compact interface.

AI Conversation Interface

Conversational interaction with the locally hosted AI model.

Infrastructure Overview

Infrastructure-aware device information and system context.

Network Diagnostics

Read-only diagnostics and live network observations.

Architecture Diagram Generation

Automatically generated editable network and infrastructure diagrams.

Device Inventory

Structured inventory of registered infrastructure devices.

⸻

4. System Architecture

AI Lab Assistant uses a distributed architecture with clearly separated responsibilities.

Local AI Inference Server

A dedicated Windows-based server hosts the local language model.

The inference environment uses Qwen and llama.cpp to provide natural-language processing.

Primary responsibilities:

* Conversational AI
* User request interpretation
* Natural-language responses
* Interaction with available backend tools
* Technical explanations and contextual assistance

The model is not granted unrestricted access to operating systems or network infrastructure.

Python Backend

The backend is developed using Python and FastAPI.

It acts as the controlled integration layer between the language model and infrastructure services.

Core responsibilities include:

* Tool registration and execution
* Device inventory management
* Network diagnostics
* Infrastructure data collection
* Structured API responses
* Request correlation and tracing
* Architecture snapshot generation
* Deterministic infrastructure document planning

Native macOS Desktop Client

The desktop application is developed using Swift and SwiftUI.

It provides a dedicated interface for interacting with the assistant.

Implemented components include:

* Desktop assistant interface
* Compact assistant orb
* Expandable conversation panel
* Text-based interaction
* Voice-command functionality
* Backend communication
* Request tracing
* Selected local desktop actions
* Architecture document generation

Connectivity Layer

The desktop client communicates with the backend through controlled network access and an established SSH tunnel.

Remote connectivity infrastructure also includes Tailscale.

Backend services are designed to remain locally bound rather than unnecessarily exposed to the public internet.

⸻

5. Core Features

5.1 Local AI Assistant

The project uses a locally hosted language model for conversational interaction.

Key characteristics:

* Local inference
* Self-hosted infrastructure
* Integration with backend capabilities
* Technical question answering
* Natural-language interaction
* No mandatory cloud LLM dependency for primary inference

5.2 Native Desktop Experience

The macOS application provides a dedicated assistant experience rather than relying exclusively on a browser or API client.

The interface includes a compact assistant component and an expandable interaction panel.

5.3 Voice and Text Interaction

The assistant supports text input and implemented voice-command functionality.

Voice features include wake-word interaction and selected spoken commands.

Speech recognition quality, vocabulary handling, and interaction flow remain under active development.

5.4 Device Inventory

The system maintains a structured inventory of infrastructure devices.

Inventory information can include:

* Device identity and aliases
* Operating system
* Device type and role
* IP addresses
* MAC addresses
* Network placement
* Identity verification status

The inventory provides persistent context for infrastructure-aware queries and documentation.

5.5 Network Diagnostics

The backend provides controlled, read-only access to supported OPNsense network information.

Available diagnostic capabilities include:

* ARP table inspection
* Neighbor discovery information
* Routing table inspection
* Interface information
* Firewall live-view data
* Network connection information
* System activity
* System health

These capabilities allow the assistant to retrieve actual infrastructure observations instead of relying entirely on language-model knowledge.

5.6 Controlled Desktop Actions

The native desktop client supports selected local actions through explicitly defined capabilities.

Demonstrated operations include:

* Opening websites
* Locking the macOS screen

The design avoids granting the assistant unrestricted command execution.

5.7 Request Tracing

The project includes request correlation and diagnostic tracing.

This helps connect user interactions with backend operations and provides greater visibility into the behavior of the assistant.

5.8 Automated Architecture Documentation

The assistant includes a working architecture-document generation pipeline.

The system can collect infrastructure observations and transform them into structured, editable draw.io documents.

Supported documentation includes:

* Physical infrastructure architecture
* Logical network topology
* Service connectivity
* Virtualization views
* Device inventory tables
* Network interface information
* VLAN information
* Routing information
* Evidence-backed infrastructure relationships

The generated documentation supports multiple pages and editable diagram objects.

Technical tables are automatically paginated to improve readability.

⸻

6. Evidence-Based Infrastructure Mapping

A major design principle of AI Lab Assistant is the separation of verified infrastructure facts from assumptions.

Network discovery does not always reveal physical connectivity.

For example, observing a device through ARP does not prove which Ethernet port or physical cable connects it to the network.

The architecture generation system distinguishes between:

Verified Relationships

Connections supported by authoritative infrastructure evidence.

Observed Relationships

Information obtained through network observations such as ARP.

Inferred Relationships

Logical associations derived from available data but not independently verified.

Unknown Relationships

Connections or associations that cannot currently be established from available evidence.

The system avoids presenting unverified physical connections as confirmed facts.

This approach improves the reliability of generated technical documentation.

⸻

7. Infrastructure Environment

AI Lab Assistant is developed and tested against a real multi-device homelab.

The environment contains networking, compute, storage, and monitoring infrastructure.

Infrastructure	Function
Windows AI Server	Local LLM inference and backend
macOS Workstation	Native assistant client
OPNsense Firewall	Routing, firewall, VLAN gateways
Managed L2+ Switch	Main Ethernet switching
Secondary Switch	Separate network segment
Proxmox Host	Virtualization
Linux Network Sensor	Network traffic observation
Raspberry Pi	Lightweight infrastructure services
NAS	Network-attached storage

The environment includes multiple VLANs and network segments.

The assistant is designed to use available infrastructure data to maintain context and generate technical documentation.

⸻

8. Technology Stack

Category	Technology
AI Model	Qwen
Local Inference	llama.cpp
Backend	Python / FastAPI
Desktop Application	Swift / SwiftUI
Backend Operating System	Windows 10
Desktop Operating System	macOS
Firewall	OPNsense
Virtualization	Proxmox
Remote Connectivity	SSH Tunnel / Tailscale
Architecture Documentation	draw.io / diagrams.net
Structured Data	JSON / SQLite
Network Infrastructure	Ethernet / VLAN / TCP/IP

The project brings together local AI inference, software engineering, networking, systems administration, and infrastructure automation.

⸻

9. Security Design

Security is an important part of the project’s architecture.

Local-First Processing

The primary language model runs on privately managed hardware.

Restricted Backend Exposure

Backend and inference services are designed to operate through local interfaces and controlled connectivity.

Explicit Tool Access

The assistant uses registered, purpose-specific tools rather than unrestricted shell access.

Read-Only Infrastructure Diagnostics

Network inspection capabilities are designed to retrieve information without modifying infrastructure configuration.

Device Identity Awareness

The system distinguishes registered device identities from temporary network observations.

Evidence-Based Documentation

Generated architecture diagrams distinguish confirmed relationships from observations and unknown connections.

Controlled Automation

Future operations that modify device or system state are intended to use explicit authorization and confirmation mechanisms.

⸻

10. Architecture Diagram Generator

The architecture generator is one of the project’s key implemented components.

It uses a structured workflow:

Infrastructure Data → Topology Snapshot → Factual Architecture Model → draw.io Document

The resulting document contains multiple editable pages.

Physical Architecture

Organizes infrastructure into a hierarchy of routing, switching, and endpoint devices.

Logical Network Topology

Visualizes interfaces, networks, VLANs, and observed logical relationships.

Service Connectivity

Represents supported relationships between infrastructure services and devices.

Virtualization

Documents virtual infrastructure while preserving unknown host relationships.

Technical Tables

Generates editable, paginated technical records from the factual topology data.

The generator is designed to remain functional without requiring the language model to invent network relationships.

⸻

11. Development Roadmap

AI Lab Assistant is under active development.

Conversational Intelligence

* Improved contextual understanding
* More reliable multi-step interactions
* Bounded conversation history
* Better technical vocabulary handling

Voice Interaction

* Improved speech recognition
* Better wake-word handling
* More natural voice interaction
* Expanded supported voice commands

Infrastructure Awareness

* Additional read-only diagnostics
* Improved device context
* Better infrastructure relationship visualization
* Additional supported integrations

Architecture Documentation

* Improved automatic diagram layouts
* More compact logical network views
* Better presentation of large infrastructure environments
* Simplified generation directly from conversational requests

Controlled Automation

* Confirmation workflows for sensitive actions
* Authorized power-management operations
* Wake-on-LAN support
* Additional carefully scoped device actions

Future Interfaces

* Improved desktop interaction
* Additional user-interface capabilities
* Mobile or PWA access in a later development phase

Roadmap items represent planned work and are not necessarily available in the current version.

⸻

12. Current Development Status

Status: Active Development

The current project includes:

* Operational local LLM inference
* Working Python backend
* Native macOS desktop application
* Text and voice interaction components
* Persistent device inventory
* Read-only OPNsense integrations
* Selected desktop actions
* Request correlation and tracing
* Working multi-page architecture-document generation
* Editable draw.io output
* Paginated infrastructure documentation

The system is a functional engineering prototype with deployed components.

Further development focuses on improving usability, expanding controlled integrations, and increasing infrastructure awareness.

⸻

13. Repository Information

This repository is a public showcase of the AI Lab Assistant project.

It contains project documentation, screenshots, architectural explanations, and development information.

The source code is maintained privately.

This repository does not provide application binaries, internal infrastructure configurations, credentials, or deployment instructions.

Its purpose is to demonstrate the design, capabilities, and engineering principles behind a self-hosted AI infrastructure assistant.

⸻

14. Engineering Focus

The project demonstrates practical work across several technical disciplines:

* Local artificial intelligence
* Backend API development
* Native desktop application development
* Network infrastructure
* Firewall diagnostics
* Virtualization
* Systems integration
* Secure tool execution
* Infrastructure documentation
* Automation design

⸻

AI Lab Assistant — Making homelab infrastructure easier to understand, document, and interact with through local AI.
