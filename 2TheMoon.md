FlyMe2TheMoon

General Overview:
- Database Use and Options: Sets the database context to dbFlyMe2theMoon and configures options.
- Table Management: Drops existing tables if they exist and creates new ones.
- Table Creation: Defines and creates new tables with specified columns and constraints.
- Referential Integrity: Adds foreign key constraints to establish relationships between tables.
- Data Insertion: Inserts initial data into the tables.

Detailed Steps:
- Database Use and Options
  - USE dbFlyMe2theMoon: Specifies the database to use.
  - SET NOCOUNT ON: Prevents the message indicating the number of rows affected by a SQL statement.
  
Table Management
- Drop Table Statements: Checks if tables exist and drops them to ensure no conflicts when creating new tables.
Tables:
  - TPilotFlights, TAttendantFlights, TFlightPassengers, TMaintenanceMaintenanceWorkers, TPassengers, TPilots, TAttendants, 
   TMaintenanceWorkers, TEmployees, TFlights, TMaintenances, TPlanes, TPlaneTypes, TPilotRoles, TAirports, TStates.
    
Table Creation
- Creating Tables: Defines and creates tables with the specified columns and constraints.
  - TPassengers: Contains passenger details with primary key intPassengerID.
  - TPilots: Contains pilot details with primary key intPilotID.
  - TAttendants: Contains flight attendant details with primary key intAttendantID.
  - TMaintenanceWorkers: Contains maintenance worker details with primary key intMaintenanceWorkerID.
  - TStates: Contains state details with primary key intStateID.
  - TFlights: Contains flight details with primary key intFlightID.
  - TMaintenances: Contains maintenance records with primary key intMaintenanceID.
  - TPlanes: Contains plane details with primary key intPlaneID.
  - TEmployees: Contains employee details with primary key intEmployeeID.
  - TPlaneTypes: Contains plane type details with primary key intPlaneTypeID.
  - TPilotRoles: Contains pilot role details with primary key intPilotRoleID.
  - TAirports: Contains airport details with primary key intAirportID.
  - TPilotFlights: Maps pilots to flights with primary key intPilotFlightID.
  - TAttendantFlights: Maps attendants to flights with primary key intAttendantFlightID.
  - TFlightPassengers: Maps passengers to flights with primary key intFlightPassengerID.
  - TMaintenanceMaintenanceWorkers: Maps maintenance workers to maintenance tasks with primary key intMaintenanceMaintenanceWorkerID.
    
Referential Integrity
- Foreign Key Constraints: Establishes relationships between tables to maintain data integrity.
  - TPassengers references TStates (intStateID).
  - TFlightPassengers references TPassengers (intPassengerID).
  - TFlights references TPlanes (intPlaneID).
  - TFlights references TAirports for departure (intFromAirportID) and arrival (intToAirportID).
  - TPilotFlights references TFlights (intFlightID).
  - TAttendantFlights references TFlights (intFlightID).
  - TPilotFlights references TPilots (intPilotID).
  - TAttendantFlights references TAttendants (intAttendantID).
  - TPilots references TPilotRoles (intPilotRoleID).
  - TPlanes references TPlaneTypes (intPlaneTypeID).
  - TMaintenances references TPlanes (intPlaneID).
  - TMaintenanceMaintenanceWorkers references TMaintenances (intMaintenanceID) and TMaintenanceWorkers (intMaintenanceWorkerID).
  - TFlightPassengers references TFlights (intFlightID).
    
Data Insertion
- Inserting Initial Data: Adds sample data into the tables for initial setup.
  - TStates: Ohio, Kentucky, Indiana.
  - TPilotRoles: Co-Pilot, Captain.
  - TPlaneTypes: Airbus A350, Boeing 747-8, Boeing 767-300F.
  - TPlanes: Various planes with IDs and types.
  - TAirports: Cincinnati, Miami, Ft. Meyer, Louisville, Denver, Orlando.
  - TPassengers: Sample passengers with personal details.
  - TEmployees: Sample employees with roles.
  - TPilots: Sample pilots with employment details.
  - TAttendants: Sample flight attendants with employment details.
  - TMaintenanceWorkers: Sample maintenance workers with employment and certification details.
  - TMaintenances: Sample maintenance records for planes.
  - TFlights: Sample flights with flight details.
 
In conclusion, the script effectively sets up and manages the database for "FlyMe2theMoon". It ensures proper database configuration, clears any existing tables to avoid conflicts, and creates essential tables to store data about passengers, employees, flights, maintenance, planes, and airports. The script establishes necessary relationships between these tables using foreign key constraints, ensuring data integrity.
