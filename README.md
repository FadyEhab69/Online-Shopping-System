# Online-Shopping-System
This UML Class Diagram represents an Online Shopping System with the following classes and relationships : 

WEB_USER: Includes attributes like login_id (String, primary key), password (String), and state (UserState enumeration: NEW, ACTIVE, BLOCKED, BANNED). A WEB_USER can be a CUSTOMER.
CUSTOMER: Contains attributes such as id (String, primary key), address (Address), phone (String), and email (String). A CUSTOMER is a WEB_USER (1:1 relationship) and can have multiple ACCOUNTS (1:0..*).
ACCOUNT: Has attributes like id (String, primary key), billing_address (Address), is_closed (Boolean), open (Date), and close (Date). An ACCOUNT belongs to one CUSTOMER (1:1) and can have multiple SHOPPING_CARTS (1:0..) and ORDERS (1:0..).
SHOPPING_CART: Includes the attribute created (Date). A SHOPPING_CART belongs to one ACCOUNT (1:1) and can contain multiple LINE_ITEMS (1:0..*).
LINE_ITEM: Contains attributes quantity (Integer) and price (Price). It represents items in a SHOPPING_CART or ORDER (ordered, unique relationship) and is linked to one PRODUCT (1:1).
PRODUCT: Includes attributes like id (String, primary key), name (String), and supplier (Supplier). A PRODUCT can be part of multiple LINE_ITEMS (1:0..*).
ORDER: Has attributes like number (String, primary key), ordered (Date), shipped (Date), ship_to (Address), status (OrderStatus enumeration: NEW, HOLD, SHIPPED, DELIVERED, CLOSED), and total (Real). An ORDER belongs to one ACCOUNT (1:1), can have multiple LINE_ITEMS (1:0..*), and is associated with one PAYMENT (1:1).
PAYMENT: Contains attributes like id (String, primary key), paid (Date), total (Real), and details (String). A PAYMENT is linked to one ORDER (1:1).
# Relationships:

A WEB_USER can be one CUSTOMER.
A CUSTOMER can have multiple ACCOUNTS.
An ACCOUNT can have multiple SHOPPING_CARTS and ORDERS.
A SHOPPING_CART can contain multiple LINE_ITEMS.
An ORDER can contain multiple LINE_ITEMS and is associated with one PAYMENT.
A LINE_ITEM is linked to one PRODUCT.
The diagram uses associations to show relationships, with multiplicities (e.g., 1, 0..*) and constraints (e.g., ordered, unique) to define the structure of the system.
