Smart Parking Lot System
========================

Overview
--------

This project aims to design the low-level architecture for a backend system of a smart parking lot. The system efficiently manages vehicle entry and exit, parking spot allocation, and fee calculation. It is designed to handle multiple floors, various parking spot sizes, and real-time updates on spot availability.

Functional Requirements
-----------------------

1.  Parking Spot Allocation:

    -   Automatically assign an available parking spot to a vehicle based on its size (e.g., motorcycle, car, bus).
2.  Check-In and Check-Out:

    -   Record the entry and exit times of vehicles.
3.  Parking Fee Calculation:

    -   Calculate fees based on the duration of stay and vehicle type.
4.  Real-Time Availability Update:

    -   Update the availability of parking spots in real-time as vehicles enter and leave.

Design Aspects
--------------

### Data Model:

The system manages three main entities: Parking Spots, Vehicles, and Parking Transactions. The corresponding database schema includes tables with attributes such as spot_id, floor_number, spot_number, size, license_plate, entry_time, exit_time, fee, and more.

### Algorithm for Spot Allocation:

A dynamic algorithm is employed to efficiently assign parking spots to incoming vehicles. This involves querying the database for available spots based on the vehicle size and using a mechanism, such as round-robin or nearest spot, to assign a suitable spot.

### Fee Calculation Logic:

Upon vehicle exit, the system calculates fees by determining the duration of stay and considering the type of vehicle. The calculated fee is then stored in the database.

### Concurrency Handling:

The system employs database transactions to ensure atomicity. Additionally, optimistic concurrency control is implemented to handle multiple vehicles entering or exiting simultaneously. A distributed database is used for scalability and availability.

Diagrams
--------

-   Architecture Diagram - Illustrates the overall architecture of the system.
-   [ERD Diagram](https://chat.openai.com/c/database-design.erd) - Entity-Relationship Diagram for the database schema.
-   [Deployment Diagram](https://chat.openai.com/c/deployment.diagram) - Depicts the deployment of the system on AWS.
-   [UML Diagram](https://chat.openai.com/c/uml-design.uml) - Represents the system flow and interactions.

AWS Deployment
--------------

The system is deployed on AWS, utilizing services such as Amazon RDS for the database, EC2 instances for API servers, ElastiCache for caching, and CloudFront for CDN. The architecture ensures high availability, scalability, and fault tolerance.

For detailed deployment instructions and design notes, refer to [DeploymentAWS.md](https://chat.openai.com/c/DeploymentAWS.md) and [Smart Parking Lot System DESIGN.md](https://chat.openai.com/c/Smart%20Parking%20Lot%20System%20DESIGN.md) respectively.

Usage
-----

-   The API provides endpoints for vehicle entry, exit, spot availability, and real-time updates.
-   Ensure to follow the provided API documentation for seamless integration.

License
-------

This project is licensed under the MIT License. Feel free to use, modify, and distribute as per the license terms.
