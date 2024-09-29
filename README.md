# NikeStore_ERD.md
erDiagram
    PRODUCT {
        int ProductID PK
        string Name
        string Description
        float Price
        string Size
    }
    
    CUSTOMER {
        int CustomerID PK
        string FirstName
        string LastName
        string Email
        string Phone
    }
    
    SALE {
        int SaleID PK
        int CustomerID FK
        int ProductID FK
        date SaleDate
        int Quantity
        float TotalPrice
    }
    
    INVENTORY {
        int ProductID FK
        int StockLevel
    }
    
    PRODUCT ||--o{ INVENTORY : "tracked by"
    CUSTOMER ||--o{ SALE : "makes"
    PRODUCT ||--o{ SALE : "sold in"
    Entities and Attributes:

PRODUCT: Represents each shoe model the store sells. Attributes include:
ProductID: The primary key (PK) to uniquely identify each product.
Name, Description, Price, and Size: Basic product details.
CUSTOMER: Contains information about customers. Attributes include:
CustomerID: The primary key (PK) to uniquely identify each customer.
FirstName, LastName, Email, Phone: Customer contact details.
SALE: Records each sales transaction, linking customers to the products they buy. Attributes include:
SaleID: The primary key (PK) to uniquely identify each sale.
CustomerID: A foreign key (FK) linking the sale to the customer.
ProductID: A foreign key (FK) linking the sale to the product.
SaleDate, Quantity, TotalPrice: Transaction details.
INVENTORY: Manages stock levels of each product. Attributes include:
ProductID: A foreign key (FK) linking the stock level to a specific product.
StockLevel: The number of items available for that product.
Relationships:
PRODUCT to INVENTORY; CUSTOMER to SALE; and PRODUCT to SALE
