## Case Study #1 - Danny's Diner👨🏻‍🍳
<img width="612" height="616" alt="image" src="https://github.com/user-attachments/assets/d755d3e3-2862-48dd-be68-210304ff1808" />

---

## Contents 
---

## Introduction
In early 2021, Danny follows his passion for Japanese food and opens "Danny's Diner," a charming restaurant offering sushi, curry, and ramen. However, lacking data analysis expertise, the restaurant struggles to leverage the basic data collected during its initial months to make informed business decisions. Danny's Diner seeks assistance in using this data effectively to keep the restaurant thriving.

---

## Problem Statement
Danny aims to utilize customer data to gain valuable insights into their visiting patterns, spending habits, and favorite menu items. By establishing a deeper connection with his customers, he can provide a more personalized experience for his loyal patrons.

He plans to use these insights to make informed decisions about expanding the existing customer loyalty program. Additionally, Danny seeks assistance in generating basic datasets for his team to inspect the data conveniently, without requiring SQL expertise.

Due to privacy concerns, he has shared a sample of his overall customer data, hoping it will be sufficient for you to create fully functional SQL queries to address his questions.

The case study revolves around three key datasets:

- Sales
- Menu
- Members

---

## Entity Relationship diagram
<img width="562" height="240" alt="image" src="https://github.com/user-attachments/assets/3251d727-0389-4c33-b493-e74b1ca7de9e" />

---

## Datasets

- sales:
  
  <img width="307" height="590" alt="image" src="https://github.com/user-attachments/assets/b296adbd-67bd-4555-9230-dca4d087b889" />

- menu:
  
  <img width="271" height="138" alt="image" src="https://github.com/user-attachments/assets/aeecd9f7-ba4b-468f-a19d-a2a2d9661e7d" />

- members
  
  <img width="206" height="110" alt="image" src="https://github.com/user-attachments/assets/b16b1c0f-1973-4adc-859a-88e99e355577" />

---

## Case Study Questions and Solutions

### 1. What is the total amount each customer spent at the restaurant?

```sql
SELECT S.customer_id, SUM(M.price) AS total_amnt
FROM sales S
JOIN menu M ON S.product_id = M.product_id
GROUP BY S.customer_id
ORDER BY customer_id;
