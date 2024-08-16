# capstone-project
using an ecommerce dataset, we were required to:
1. create the table for the datset and then,
2. injest the data into the table.

1. Here is the postgres-code for the creation of the dataset:
 CREATE TABLE olist_customers_dataset (
    customer_id SERIAL PRIMARY KEY,
    customer_unique_id VARCHAR(255),
    customer_zip_code_prefix NUMERIC,
    customer_city VARCHAR(50),
    customer_state VARCHAR(50)
);

 CREATE TABLE product_category_name_translation (
    product_category_name VARCHAR(100),
    product_category_name_english VARCHAR(100)
);

 CREATE TABLE olist_seller_dataset (
    seller_id VARCHAR(255) PRIMARY KEY,
    seller_zip_code_prefix NUMERIC,
    seller_city VARCHAR(50),
    seller_state VARCHAR(50)
);

 CREATE TABLE olist_products_dataset (
    product_id SERIAL PRIMARY KEY,
    product_category_name VARCHAR(50),
    product_name_length NUMERIC,
    product_description_length NUMERIC,
    product_photos_qty NUMERIC,
    product_weight NUMERIC,
    product_length_cm NUMERIC,
    product_height_cm NUMERIC,
    product_width_cm NUMERIC
);

 CREATE TABLE olist_order_dataset (
    order_id SERIAL PRIMARY KEY,
    customer_id VARCHAR(255),
    order_status VARCHAR(50),
    order_purchase_timestamp TIMESTAMP,
    order_approved_at TIME,
    order_delivered_carrier_date TIMESTAMP,
    order_delivered_customer_date TIMESTAMP,
    order_estimated_delivery_date TIMESTAMP
);

 CREATE TABLE olist_geolocation_dataset (
    geolocation_zip_code_prefix NUMERIC,
    geolocation_lat NUMERIC,
    geolocation_lng NUMERIC,
    geolocation_city VARCHAR(50),
    geolocation_state VARCHAR(50)
);

 CREATE TABLE olist_order_items_dataset (
    order_id VARCHAR(255),
    order_item_id NUMERIC,
    product_id VARCHAR(255),
    seller_id VARCHAR(255),
    shipping_limit_date TIMESTAMP,
    price NUMERIC(10, 2),
    freight_value NUMERIC(10, 2)
);

 CREATE TABLE olist_order_reviews_dataset (
    review_id SERIAL PRIMARY KEY,
    order_id VARCHAR(255),
    review_score NUMERIC,
    review_comment_title VARCHAR(100),
    review_comment_message VARCHAR(255),
    review_creation_date TIMESTAMP,
    review_answer_timestamp TIMESTAMP
);

 CREATE TABLE olist_order_payments_dataset (
    payment_id SERIAL PRIMARY KEY,
    order_id VARCHAR(255),
    payment_sequential NUMERIC,
    payment_type VARCHAR(50),
    payment_installments NUMERIC,
    payment_value NUMERIC(10, 2)
);

2. The injestion of the file was carried out using Dbeaver.
3. These are the answers to the analytical questions.
   The Answers to the Analytical Questions:
1. Product Categories with the Highest Sales:
   	- The top product categories by sales are:
     	- Beleza Saude: $1,258,681.34.
     	- Relogios Presentes: $1,205,005.68.
     	- Cama Mesa Banho: $1,036,988.68.
     	- Esporte Lazer: $988,048.97.
     	- Informatica Acessorios: $911,954.32.


2. Average Delivery Time for Orders:
   - The average delivery time for orders is 12.1 days.

3. States with the Highest Number of Orders:
   - The top states by order count are:
     - SP (São Paulo): 41,746 orders.
     - RJ (Rio de Janeiro): 12,852 orders.
     - MG (Minas Gerais): 11,635 orders.
     - RS (Rio Grande do Sul): 5,466 orders.
     - PR (Paraná): 5,045 orders.

