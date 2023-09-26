# Table

**Products**
| Column | Type |
| ----------- | ----------- |
| id | INT |
| name | VARCHAR |
| price | INT |

**Transactions**
| Column | Type |
| ----------- | ----------- |
| id | INT |
| product_id | INT (FK) |
| buyer | VARCHAR |
| qty | INT |
| bought_at | TIMESTAMP |

# Input / Request

## Get Transaction's Summery by year

`GET | {BASE_URL}/api/transactions/summary?year=2023`

**Expected Output**

```json
{
    january: 80,
    february: 70,
    ...
}
```

## Best Seller (3 Products)

`GET | {BASE_URL}/api/products/best-seller`

**Expected Output**

```json
[
  {
    "product_id": 1,
    "name": "Poco F4",
    "total_transaction": 500
  },
  {
    "product_id": 2,
    "name": "Samsung s12",
    "total_transaction": 400
  },
  {
    "product_id": 3,
    "name": "Iphone 12",
    "total_transaction": 200
  }
]
```

## Average Monthly Transactions

`GET | {BASE_URL}/api/transactions/daily-average`

```json
{
    "january": 2, // 2 item per day
    ...
}
```
