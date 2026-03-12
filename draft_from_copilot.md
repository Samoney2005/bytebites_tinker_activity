---
title: ByteBites Restaurant Ordering System - Class Diagram
---
classDiagram
    class Customer {
        -String customerId
        -String name
        -List~Transaction~ purchaseHistory
        +addTransaction(Transaction)
        +getPurchaseHistory() List~Transaction~
    }
    
    class MenuItem {
        -String itemId
        -String name
        -double basePrice
        -String category
        -double popularityRating
        +getPrice() double
        +getCategory() String
        +getPopularityRating() double
    }
    
    class Menu {
        -List~MenuItem~ items
        -List~String~ categories
        +filterByCategory(String) List~MenuItem~
        +addItem(MenuItem)
        +removeItem(String)
        +getAllItems() List~MenuItem~
    }
    
    class Transaction {
        -String transactionId
        -Customer customer
        -Map~MenuItem,int~ selectedItems
        -double totalCost
        -String date
        +addItem(MenuItem, int)
        +removeItem(String)
        +calculateTotal() double
        +getDate() String
    }
    
    Customer "1" --> "*" Transaction : makes
    Transaction "1" --> "*" MenuItem : contains
    Menu "1" --> "*" MenuItem : manages