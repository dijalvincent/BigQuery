1.Present a compilation of product names along with their respective prices?
```SQL
SELECT name,retail_price price
FROM `bigquery-public-data.thelook_ecommerce.products`;
```

![image](https://github.com/dijalvincent/BigQuery/assets/154268649/7e6a45bc-93b2-412f-b558-1357b7353e51)

2.Determine the total count of orders?
```SQL
SELECT COUNT(*) AS total_orders
FROM `bigquery-public-data.thelook_ecommerce.orders`;
```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/b2ea12ad-bb3d-4818-817b-421eeea378d1)

3.Find the top 10 most expensive products?
```SQL
SELECT name, retail_price
FROM `bigquery-public-data.thelook_ecommerce.products`
ORDER BY retail_price DESC
LIMIT 10;
```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/a32a8eef-6432-4278-bc9d-7a0b7d72c037)

4.Find the number of orders placed in each month?
```SQL
SELECT EXTRACT(MONTH FROM created_at) AS month, COUNT(*) AS num_orders
FROM `bigquery-public-data.thelook_ecommerce.orders`
```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/7e0b7103-37e6-4c37-9bf4-6d1be3f165ad)

5.Find the total number of games played in each season?
```SQL
SELECT season, COUNT(*) AS num_games
FROM `bigquery-public-data.ncaa_basketball.mbb_games_sr`
GROUP BY season
ORDER BY season;
```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/d637ac22-cf38-4e9a-b8ad-faca59032f6f)

6.Find the most common mascot names across all teams ?
```SQL
SELECT mascot, COUNT(*) AS team_count
FROM `bigquery-public-data.ncaa_basketball.mascots`
GROUP BY mascot
ORDER BY team_count DESC;
```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/955eabda-8fc1-4677-87e8-fca077cf627b)

7.Count the total number of games played?
```SQL
SELECT COUNT(*) AS TOTAL_GAMES
FROM `bigquery-public-data.ncaa_basketball.mbb_games_sr`
```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/11491026-1bc7-4f8c-b330-6a26d30ce2f6)

 8.	Provide the names of all teams along with their associated mascots?
```SQL
SELECT m.name AS team_name, ma.name AS mascot_name
FROM `bigquery-public-data.ncaa_basketball.mbb_teams` AS m
JOIN `bigquery-public-data.ncaa_basketball.mascots` AS ma
ON m.name = ma.name;
```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/8411541f-c119-438e-84ae-ed65e5a9d6e7)

9.Find the total number of products purchased by each user along with id?
```SQL
SELECT
  users.id,
  users.first_name,
  COUNT(products.id) AS total_products_purchased
FROM
  `bigquery-public-data.thelook_ecommerce.users` AS users
JOIN
  `bigquery-public-data.thelook_ecommerce.products` AS products
ON
  users.id = products.id
GROUP BY
  users.id,
  users.first_name
```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/ff7e5842-ba79-47af-8801-6e3a7f5f3236)

10. Find the list of products purchased by each user?
 ```SQL
   SELECT
  users.id,
  users.first_name,
  products.name
FROM
  `bigquery-public-data.thelook_ecommerce.users` AS users
JOIN
  `bigquery-public-data.thelook_ecommerce.products` AS products
ON
  users.id = products.id
 ```
![image](https://github.com/dijalvincent/BigQuery/assets/154268649/02ceb9d8-48db-4830-8b2a-7ee95e649c06)


