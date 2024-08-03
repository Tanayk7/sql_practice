# SQL Challenge Assignment

## Problem Statement

You are working on the database for an e-commerce platform that handles a variety of products and customer transactions. The platform has several tables: `customers`, `products`, `orders`, `order_items`, `reviews`, and `promotional_codes`.

Please complete the following SQL challenges based on the given tables and sample data.

### 1. Order By

**Task**: As the platform grows, customers want to see the list of products sorted by the highest rating first. Your task is to write a query that retrieves all products along with their average ratings, sorting them from highest to lowest rating.

**Example Table: `products`**

| product_id | name         | category    | price | average_rating | dimensions |
| ---------- | ------------ | ----------- | ----- | -------------- | ---------- |
| 101        | Laptop       | Electronics | 1200  | 4.5            | NULL       |
| 102        | T-Shirt      | Clothing    | 20    | 4.0            | 10x10x1    |
| 103        | Coffee Maker | Home Goods  | 80    | 4.7            | 15x15x12   |
| 104        | Headphones   | Electronics | 150   | 4.2            | 8x8x3      |

### 2. And/Or

**Task**: The marketing team needs a report on customers who have purchased either 'Electronics' or 'Clothing' items. Specifically, they want to target customers who have made purchases in both categories or only one of them. Your query should find customers who have made purchases in either category.

**Example Tables:**

- `customers`

| customer_id | name        | email                   | phone    |
| ----------- | ----------- | ----------------------- | -------- |
| 1           | Alice Smith | alice.smith@example.com | 555-1234 |
| 2           | Bob Johnson | bob.johnson@example.com | NULL     |
| 3           | Carol Davis | carol.davis@example.com | 555-5678 |

- `orders`

| order_id | customer_id | order_date | total_amount |
| -------- | ----------- | ---------- | ------------ |
| 5001     | 1           | 2024-07-15 | 1220         |
| 5002     | 2           | 2024-07-16 | 20           |
| 5003     | 1           | 2024-07-18 | 80           |

- `order_items`

| order_item_id | order_id | product_id | quantity |
| ------------- | -------- | ---------- | -------- |
| 1             | 5001     | 101        | 1        |
| 2             | 5001     | 102        | 1        |
| 3             | 5002     | 102        | 1        |
| 4             | 5003     | 103        | 1        |

### 3. Not

**Task**: The platform's customer service team needs to identify customers who have not left any reviews for the products they’ve purchased. Your query should find all customers who have made purchases but do not have any corresponding entries in the `reviews` table.

**Example Tables:**

- `customers` (same as above)

- `orders` (same as above)

- `reviews`

| review_id | product_id | customer_id | rating | review_text         |
| --------- | ---------- | ----------- | ------ | ------------------- |
| 1         | 101        | 1           | 5      | "Excellent laptop!" |
| 2         | 102        | 2           | 3      | "Okay T-Shirt."     |

### 4. Insert Into

**Task**: The platform is adding a new feature where customers can now add product reviews. Write a query to insert a new review into the `reviews` table with columns for `review_id`, `product_id`, `customer_id`, `rating`, and `review_text`. Ensure that `review_id` is auto-generated.

**Example Table: `reviews`**

| review_id | product_id | customer_id | rating | review_text         |
| --------- | ---------- | ----------- | ------ | ------------------- |
| 1         | 101        | 1           | 5      | "Excellent laptop!" |
| 2         | 102        | 2           | 3      | "Okay T-Shirt."     |

### 5. Null Values

**Task**: A recent update introduced an optional field for product dimensions. The inventory team needs to identify all products that do not have dimension information provided (i.e., the dimension fields are NULL). Write a query to find these products.

**Example Table: `products` (same as above)**

### 6. Update

**Task**: Due to a recent sale, the prices of all 'Clothing' items in the `products` table need to be reduced by 20%. Write a query to update the prices for these products.

**Example Table: `products` (same as above)**

### 7. Delete

**Task**: The platform has a policy to remove all outdated promotional codes that have expired. Write a query to delete all entries in the `promotional_codes` table where the `expiration_date` is less than the current date.

**Example Table: `promotional_codes`**

| promo_code_id | code     | discount | expiration_date |
| ------------- | -------- | -------- | --------------- |
| 1             | SAVE10   | 10%      | 2024-08-01      |
| 2             | SUMMER20 | 20%      | 2024-06-30      |
| 3             | WINTER30 | 30%      | 2024-07-15      |

### 8. Complex Where Clause

**Task**: To improve customer experience, the platform wants to analyze customer orders for a special report. Write a query to select all orders placed in the last 6 months where the total amount is greater than $100 and where the customer has purchased items from both 'Electronics' and 'Home Goods' categories.

**Example Tables:**

- `orders` (same as above)

- `order_items` (same as above)

- `products` (same as above)

### 9. Insert with Null Values

**Task**: A new feature allows customers to provide feedback on their orders, but the feedback is optional. Write a query to insert a new order into the `orders` table with optional fields like `feedback` and `delivery_date` left NULL.

**Example Table: `orders` (same as above)**

### 10. Conditional Update

**Task**: The platform needs to update the order status for all orders based on their shipping information. Write a query to update the `status` in the `orders` table to 'Shipped' if the `shipped_date` is not NULL and to 'Pending' if the `shipped_date` is NULL.

**Example Table: `orders`**

| order_id | customer_id | order_date | total_amount | shipped_date | status  |
| -------- | ----------- | ---------- | ------------ | ------------ | ------- |
| 5001     | 1           | 2024-07-15 | 1220         | 2024-07-17   | Shipped |
| 5002     | 2           | 2024-07-16 | 20           | NULL         | Pending |
| 5003     | 1           | 2024-07-18 | 80           | 2024-07-20   | Shipped |
