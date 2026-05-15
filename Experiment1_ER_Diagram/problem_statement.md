t|M:N|Optional (A member may or may not register for an event)|Members can register for many events, and each event can have many members.|
|Speaker - Event|M:N|Optional (An event may or may not have a speaker)|An event can have multiple speakers, and a speaker can be assigned to multiple events.|
### Assumptions
- Member-Book Loan System: A Member can borrow multiple Books with a Loan representing each borrowing transaction, which includes the loan and return dates.
- Event Participation: Members can register for multiple Events, and each Event can have multiple Members attending, with optional speakers.
- Speaker-Event Association: Events may feature one or more Speakers, and a Speaker can be involved in multiple Events.

---

##  Scenario C: Restaurant Table Reservation & Ordering

###  Business Context
A popular restaurant wants to manage *reservations, orders, and billing*.

###  Requirements
- Customers can *reserve tables* or walk in.  
- Each reservation includes *date, time, number of guests*.  
- Customers place *food orders linked to reservations*.  
- Each order contains *multiple dishes; dishes belong to **categories* (starter, main, dessert).  
- *Bills* generated per reservation, including food and service charges.  
- *Waiters* assigned to serve reservations.  

###  ER Diagram
!WhatsApp Image 2025-08-29 at 14 35 17_70104f15

###  Entities and Attributes
| Entity    | Attributes (PK, FK) | Notes |
|-----------|----------------------|-------|
| Customer  | CustomerID (PK), Name, Contact | Makes reservations |
| Reservation | ReservationID (PK), Date, Time, Guests, CustomerID (FK), TableID (FK) | Booking info |
| Table     | TableID (PK), Capacity, Location | Dining tables |
| Order     | OrderID (PK), ReservationID (FK), Time | Linked to reservations |
| Dish      | DishID (PK), Name, Category, Price | Ordered item |
| OrderDetail | OrderID (FK), DishID (FK), Quantity | Resolves M:N |
| Bill      | BillID (PK), ReservationID (FK), Amount, ServiceCharge | Final payment |
| Waiter    | WaiterID (PK), Name | Assigned to reservations |

###  Relationships and Constraints
| Relationship | Cardinality | Participation | Notes |
|--------------|-------------|---------------|-------|
| Customer–Reservation | 1:N | Partial | A customer can have multiple reservations |
| Reservation–Table | 1:1 | Total | One reservation per table |
| Reservation–Order | 1:N | Total | Orders linked to reservation |
| Order–Dish | M:N | Total | Resolved using OrderDetail |
| Reservation–Bill | 1:1 | Total | One bill per reservation |
| Reservation–Waiter | 1:1 | Partial | Assigned waiter |

###  Assumptions
- Each reservation *occupies one table* only.  
- Bills always generated *per reservation*.  
- Service charges fixed percentage (not modeled).  

---
##  Instructions for Students
1. Complete *all three scenarios (A, B, C)*.  
2. Identify *entities, relationships, and attributes* for each scenario.  
3. Draw ER diagrams using *draw.io / diagrams.net* (or hand-drawn & scanned).  
4. Fill in *Entities, Relationships, Assumptions* tables.  
5. Export the completed Markdown (with diagrams) as a *single PDF*.  

---

  End of Submission Template
