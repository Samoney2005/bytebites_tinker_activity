Client Feature Request
We need to build the backend logic for the ByteBites app. The system needs to manage our customers, tracking their names and their past purchase history so the system can verify they are real users.

These customers need to browse specific food items (like a "Spicy Burger" or "Large Soda"), so we must track the name, price, category, and popularity rating for every item we sell.

We also need a way to manage the full collection of items — a digital list that holds all items and lets us filter by category such as "Drinks" or "Desserts".

Finally, when a user picks items, we need to group them into a single transaction. This transaction object should store the selected items and compute the total cost.

The prompt that was put in Copilot: 
Create a UML-style class diagram for the ByteBites restaurant ordering system. Include these four classes:

1. Customer Class

Attributes: customerId, name, purchaseHistory (list of past transactions)
Purpose: Manage customers, store their names, and track their purchase history to verify they are real users
2. MenuItem Class

Attributes: itemId, name, basePrice, category, popularityRating
Purpose: Track individual food items with their name, price, category, and popularity rating
Include these specific items:
Burgers: Spicy Burger, Double Patty Burger, Hamburger, Cheeseburger (with automatic side of fries—can be replaced with Onion Rings or Mozzarella Sticks at upcharge)
Drinks: Fountain Drinks (all sodas), Extra Drinks with upcharge (Lemonade, Sweet Tea, Milkshake)
Desserts: Cookies, Brownies, Ice Cream, Pies (Apple Pie, Blueberry Pie, Lemon Pie, Pie of the Month special)
3. Menu Class

Attributes: items (list of MenuItem), categories
Methods: filterByCategory(), addItem(), removeItem(), getAllItems()
Purpose: Provide a way to manage the full collection of items—a digital list that holds all items and lets us filter by category such as "Mains," "Drinks," or "Desserts"
4. Transaction Class

Attributes: transactionId, customer, selectedItems (with quantities), totalCost, date
Methods: addItem(), removeItem(), calculateTotal()
Purpose: When a user picks items, group them into a single transaction that stores the selected items and computes the total cost
Show relationships between classes: Customer → Transaction, Transaction → MenuItem, Menu → MenuItem

Output format: Mermaid diagram or UML class diagram