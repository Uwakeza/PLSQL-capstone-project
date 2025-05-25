
🏘️Real Estate Managment System 
---
🧑‍🤝‍🧑Introduction 
---
- Student Name:UWAKEZA KAMIKAZI Merveille

- Student ID:27893

📌Problem statement  
---
The Real Estate Management System addresses the challenges faced by property owners, real estate agents, and tenants in managing properties effectively. 

These challenges include :

- Inefficient property listing and search mechanisms.
  
- Lack of a centralized platform for managing tenant records, property maintenance, and payments

- Manual processes leading to errors and delays.

🎯Objectives
---
The objective of the Real Estate Management System is to develop a comprehensive, user-friendly platform that simplifies and streamlines the management of real estate properties

This system aims to:

- Centralize Property Management: Provide a unified interface for property owners, agents, and tenants to manage property listings, tenant records, and transactions efficiently.

- Enhance User Experience: Deliver an intuitive platform for users to list, search, and filter properties based on their preferences, enabling seamless navigation and interaction.

- Improve Communication: Foster transparent and effective communication between stakeholders, ensuring quick resolution of inquiries, complaints, and updates.

- Ensure Data Security: Safeguard sensitive information such as personal details, financial records, and property documentation with robust security measures.

- Support Scalability: Build a system that can scale to accommodate an increasing number of users, properties, and transactions as the business grows.

 🕹Target Users
 ---
The Real Estate Management System is designed to serve the following target user groups:

- Property Owners:

Individuals or companies owning multiple properties who need a platform to manage listings, tenant records, and financial transactions efficiently.

Users who wish to monitor property performance and revenue through analytics.

- Real Estate Agents:

Professionals responsible for connecting property owners with potential buyers or tenants.

Users looking for a system to streamline property listings, inquiries, and client communication.

- Tenants
  
🗝Key Entities
  ---
- owner: Central to the system, representing all stakeholders and ensuring role-based access.

- Property: Core asset being managed; foundational for listings, leases, and transactions.

- Lease Agreement: Governs tenant-property relationships, ensuring transparency and legal compliance.

- Payment: Manages financial operations, ensuring accountability and smooth payment processes.

- Maintenance Request: Streamlines property upkeep, enhancing tenant satisfaction and operational efficiency.  
  

📰Business Process Model
---

This phase outlines a structured approach to effectively model a business process within a Management Information System (MIS)

🧩Relevance to MIS
---
The Real estate management system ensures the efficient flow of information between landlords, tenants, property managers, and supporting systems, enabling decision-making and streamlined operations.

⏲Business Process Model and Notation(BPMN)
---
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/cacfdcdbcc60b068393d92f16a030d2787b1b27f/real%20estate%20bpml%20.png)

🔍Description of the Diagram
---
- Swimlanes:

Tenants:

- Initiate the process by submitting a rental application.

- Receive notification about the outcome of the application.

- Property Managers:

- Review applications.

- Notify tenants of the decision.

- Coordinate with the maintenance team if needed.

🛠Maintenance:
---
- Receives and updates requests related to maintenance.

📎System (Database):

- Records the application and maintenance updates.

- Sends notifications and logs interactions.

♠Flow:
---
- The process begins with tenants submitting a rental application.

- Property managers review the application and decide whether to approve it.

- If approved, it may generate maintenance-related tasks.

- If not approved, tenants are notified of the decision.

- Maintenance teams handle specific requests, update statuses, and collaborate with the database for record-keeping.

- Notifications and reports are issued to ensure communication among stakeholders.

🧿Decision Points:
---
A key decision point is "Application Approved?" that branches to different outcomes based on the decision.

System Interaction:

The database serves as the backbone, ensuring all updates and notifications are tracked and stored efficiently.

🛒How It Supports MIS Functions
---
Improved Decision-Making:

- Centralized data in the database helps property managers and tenants track progress transparently.

- Streamlined Operations:

- Clearly defined roles and automated notifications reduce bottlenecks.

- Enhanced Communication:

- Notification systems ensure all parties stay informed.
 
  💡Logical Model Design(P3)
  ---
Deliverables for Logical Model Design

1. Entity-Relationship (ER) Model
Identify and Define Entities:

- Property: Represents real estate properties managed by the system.

- Owner: Represents individuals or organizations owning the properties.

- Tenant: Represents individuals or organizations leasing the properties.

- Lease Agreement: Represents lease agreements between owners and tenants for specific properties.

- Payment: Tracks payments made by tenants for leases.

- Maintenance Request: Represents requests for property maintenance by tenants.

Attributes and Keys:

- Property:

Attributes: PropertyID (PK), Address, Type (e.g., Residential, Commercial), Size, Status (Available/Leased), OwnerID (FK).

- Owner:

Attributes: OwnerID (PK), Name, ContactInfo, Address.

- Tenant:

Attributes: TenantID (PK), Name, ContactInfo, PaymentMethod.

- Lease Agreement:

Attributes: LeaseID (PK), PropertyID (FK), TenantID (FK), StartDate, EndDate, MonthlyRent.

- Payment:

Attributes: PaymentID (PK), LeaseID (FK), PaymentDate, Amount, PaymentStatus.

- Maintenance Request:

Attributes: RequestID (PK), TenantID (FK), PropertyID (FK), RequestDate, RequestDetails, Status.

2. Relationships and Constraints
   
Relationships:

- Owner to Property: One-to-Many (One owner can own multiple properties).

- Property to Lease Agreement: One-to-One or One-to-Many (A property can have one active lease agreement but may have historical leases).

- Tenant to Lease Agreement: One-to-Many (A tenant may lease multiple properties over time).

- Lease Agreement to Payment: One-to-Many (Each lease agreement has multiple payments).

- Tenant to Maintenance Request: One-to-Many (Tenants can submit multiple requests for maintenance).

Constraints:

- NOT NULL: Primary and foreign keys, essential attributes like Name, ContactInfo.

- UNIQUE: Attributes like PropertyID, LeaseID, OwnerID.

- CHECK: E.g., MonthlyRent > 0, Status IN ('Pending', 'Completed', 'In Progress').

- DEFAULT: Default status values, e.g., Status = 'Available' for properties.

  

3. Normalization
Ensure:

- 1NF: Atomic attributes, unique rows.

- 2NF: No partial dependency, every non-key attribute is fully dependent on the primary key.

 - 3NF: Eliminate transitive dependencies. Ensure all non-key attributes depend only on the primary key.

4. Handling Data Scenarios
   
- Real-world scenarios include:

- Multi-tenancy: Handle properties leased by multiple tenants across different time periods.

- Late payments: Include fields to track payment delays and statuses.

- Maintenance escalations: Link unresolved maintenance requests to agents or escalation mechanisms.

 🖥Database Creation(P4)
  ---
  
  Pluggable Database (PDB) named:Thur_27893_Uwakeza_realestateMS_DB 
  
  I used my  first name as the password and grant the user super admin privileges.
  
   ALTER SESSION SET CONTAINER = CDB$ROOT;

  ALTER PLUGGABLE DATABASE Thur_27893_Uwakeza_realestateMS_DB  OPEN;
  
  GRANT ALL PRIVILEGES TO admin;

  SELECT NAME, OPEN_MODE FROM V$PDBS;
  
📊Oracle Enterprise Manager (OEM) 

_ Demonstrating the PDB is active, open, and monitored.

_ Admin user roles shown to confirm setup.

_ System activity and SQL execution visible.

📸Screenshots

🖥Database creation and granting privileges


  ![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/d1c3ca794d84831780e830870f4637faf008b1af/Cap1.png)
  

📊OEM Diagram

  
  ![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/0c15df538edd2f5fe6415d8439da584368fc7f83/OEM%20DIAGRAM1.png)
  
  
  📘Table Implementation and Data Insertion (P5)

  Objective: Translate the logical data model into physical database tables.

  Tables implemented:
  
  - Tenant
  
  - Property

  - Owner

  - Lease

 -  Maintenance Request

  - payment
  - 
2. Data Insertion

 Objectives : Populate the tables with realistic and meaningful data

📸screeshots

![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/d6e18ec5be7ff6e258c5558fc1589cd954ea7bce/T1.png)
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/fa6f8d08a7555c8eee809021f085d1695804c1e4/T2.png)
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/433a6e5d71359e6bb3bdbd4ca6ca08a5c21a7a2a/T6.png)
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/83133c3ca14d35913b448e6bd4c11fa87748ccec/T7.png)
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/30458f90e7f56830f33a632b31649f2d56656a20/T17.png)
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/71e4e560e3d70e6b94c48b83aba26866848a44f9/T18.png) 
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/7881ddf196d0d48995bcb627b07d4ec7bc71846f/insert2.png)
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/bd5a4ad428e70366e793682a073c753ee6a29dca/insert3.png)

Database Interaction and Transactions 
---

🧩Data operations


Update
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/c55edc0198dc7bb89f1adb45f645ce2686cbc243/T20.png)
Delete
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/3024ef8cbc83bcfd1cb0201afcfae574589f14e3/T22.png)
Table Creation
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/701a4950f516ff7b4addeaedbead376077c6d985/T24.png)
Drop
![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/94fda1054863f795b7d03944bf63febe5ee294bf/T25.png)

🔍Windows Function Analysis(P6)

- Parametirized Procedure

  ![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/f868d9abde9104998759bbf0c25ccfb87c882325/parametized%20for%20fetch%20output.png)

- Cursor
  ![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/022176f43e8293ae6e4a9fc2a770e545a7729be5/CURSOR%20OUTPUT.png)
  
- Testing

  ![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/a898c1360e64c5b7d8604777361e8d7ea750c73b/testing%20result.png)
  
- Packages

  ![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/96c7573979096c66ed8dbfffb2a98b153c1e0efa/package%20output.png)

  Advanced Database Programming and Auditing (P7)
  
   ![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/d0b1efd702a3c61d0affe7d794c5b6350a7096a5/PHASE7%2C1.png)
 ![image alt](https://github.com/Uwakeza/PLSQL-capstone-project/blob/ef4a6d446b55caa9d8ced975f4be4ac3dea5ecf3/PHAS7%2C2.png)


🛒Conclusion
---
Conclusion
    The development of the Real Estate Management System (REMS) highlights the potential of technology in streamlining the operations of real estate
    businesses. 
    This project demonstrates how digital solutions can centralize data, automate processes, and enhance decision-making, ultimately 
    improving organizational efficiency and customer satisfaction. Key accomplishments include:
    Efficient property listing management, reducing manual errors.
    Enhanced client-agent interactions through automated workflows.





