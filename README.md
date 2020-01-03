# Content-Management-System
Six important domains to be a part of the content management system :

a) Canadian Industries

b) Canadian Transport (Road)

c) Health Canada

d) Tourism Canada

e) Canadian schools

f) Energy (Power)


**Data sets** :

1.https://open.canada.ca/data/en/dataset/c63e8956-bd01-498b-875e-25fcfa544ee9

2.https://open.canada.ca/data/en/dataset/0323cc5a-c8b0-43c9-a3fc-99c6dc660138

3.https://open.canada.ca/data/en/dataset/f6e7e871-79b7-49e1-90a2-e3c913f1951d

4.https://open.canada.ca/data/en/dataset/835ef477-1ab6-4dbd-a3e2-229a529bcd1e

5.https://open.canada.ca/data/en/dataset/1433feac-853a-4efa-9c05-2133b93af638

6.https://open.canada.ca/data/en/dataset/8285e98c-c6fd-498f-9f58-2abf06b554de


**Initial Design**:The initial design seems fine except for a few factors. In the entity set School, I have an attribute
named student. The student itself could be an entity but I am just trying to display the number of
students per each school and hence naming the attribute as a student could be more generic and
can be changed. In all the entities, there is an attribute named location, it could have been split
into 2 or 3 attributes like geographical country, province etc. This might give a better idea on
which area we are dealing with. In the design, the entity Schools consume Power, but from the
design, it might be little confusing to determine if Energy(power) is consuming Industry or
industry is consuming power because of the way the activities are aligned. The design is trying to
convey that industries consume power. In the initial design, I have not defined the cardinality
and it will be represented in the final design. Also, historical data will not be maintained for any
of the entities. The possibilities of fan trap are not identified as the initial sketch does not define



**Final Design**:
The sketch for the final ERD is represented in Figure 2: Final ERD (next page). As these entities
are broad and generalized, there will be many to many relationships between these entities. For
example, the relationship between school and transport, industry and transport, school and health
services, school and energy, industry and energy will be a many to many relationships. This will
result in too many bridge tables and the performance of the database would be reduced in a reallife scenario. In order to avoid that, an entity named location is created. This ensures that all
these entities are connected to one main entity(location) and can retrieve data based on the
geographical location. So, the final design will have one extra entity named location apart from
the chosen entities. This makes it easier for the client to understand and sort out the records
based on the geographical location. The Final ERD has 7 connected Entities: -

I. Canadian Industries

II. Canadian Road Transport

III. Health Canada

IV. Canadian schools

V. Energy (Power)

VI. Tourism Canada

VII. Location


**Normalization**:

1NF Analysis:
All the entities were analyzed to check if they had to be normalized. After detailed analysis, it
was observed that the entities were already in 1NF as the attributes of all the entities were
functionally dependent on the primary key. The datasets were further analyzed to check if there
were any repeating groups. The attributes like ‘North American Product Classification
(NAPCS)of Industries entity or ’Electric power, component’ of Energy entity seemed like
repeating groups in the beginning. But on further analysis, it was observed that those are not
repeating groups as the attribute named ‘Value’ of these entities shows the sum of the products
or components.

**2NF Analysis**:
As the tables were already in 1NF, the entities were further scrutinized to check if there were any
partial dependencies. Partial dependencies were not observed in the entities as the primary key is
not composite and there is no candidate key. So, the concept of an attribute depending on a part
of the primary key is not observed. Hence, the tables are in 2NF.

**3NF Analysis**:
As the tables were already in second normal form, the entities were examined to detect transitive
dependencies. After detailed scanning, it was observed that none of the attributes depended
functionally on another non-key attribute. As there are no potential transitive dependencies, the
entities are already in 3NF.


The fact and dimension tables and were created for 3 domains

a) Industries

b) Road transport

c)Schools


**Industries**: The entity ‘Trade’ has been created as a fact table and this table has 3 main attributes.
The canadian_industries_id and location _id are the foreign keys in this entity and the attribute
‘Value’ I describe the quantitative information about the business process (i.e. Trade value)

**Road Transport**: The entity ‘Sales’ has been created as a fact table for road transport. This entity
describes the sale value of the motor vehicles.Canadian_road_transport_id and location_id are the
foreign keys of this table and the attribute ‘Value’ gives the motor sales.

**School**: The entity ‘Area’ basically gives the statistical area code for each of the school present in
the dimensions table of the domain of the school

Typically, the fact tables are not functional without the dimension tables. Dimension tables are the
descriptive entities that describe the quantitative numbers of the fact tables.

**Industries**: There are 2 main dimension tables for this domain:
a) Industries: The entity industries describe the nature of the industry and its classification. Its
combination with the fact table (Trade entity) describes the trade value of imports and export.

b) Location: The location entity describes the geographical location of the industry. It connects to
the fact table -Trade entity to describe the geographical location of the industrial value

**Road transport**: There are 2 dimensional tables for this domain

Road transport: This domain explains the type of vehicle being used in the form of road
transportation. It’s a connection with the ‘Sales’ table gives the sale value of that particular
vehicle.

Location: This entity describes the geographical location of the vehicles. Its connection with the
fact table describes the sale value of the vehicle for that geographical location.

**School**: It has 2 dimension tables
School: Describes the school name and its location.

Location: Location describes the geographical location of the students.








