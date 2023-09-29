# Table

**Members**
| Column | Type |
| ----------- | ----------- |
| id | INT |
| name | VARCHAR |

**Categories**
| Column | Type |
| ----------- | ----------- |
| id | INT |
| name | VARCHAR |

**Books**
| Column | Type |
| ----------- | ----------- |
| id | INT |
| category_id | INT (FK) |
| title | VARCHAR |

**Borroweds**
| Column | Type |
| ----------- | ----------- |
| id | INT |
| book_id | INT (FK) |
| member_id | INT (FK) |
| borrowed_at | TIMESTAMP |
| returned_at | TIMESTAMP |

# Input / Request

## Get Books

`GET | {BASE_URL}/api/books`

```json
{
    {
        "id": 1,
        "title": "Atomic Habit",
        "is_available": true
    },
    ...
}
```

## Member's Borrowed Books

`GET | {BASE_URL}/api/student/{student_id}/borrowed-books`

Note: only take books that are being borrowed, ignore books that have been returned

```json
[
    {
        "id": 1,
        "book": {
            "id": 1,
            "title": "Atomic Habit"
        },
        "borrowed_at": "2023-10-10 10:00:00"
    },
    ...
]
```

## Get late return the book

`GET | {BASE_URL}/api/borroweds/late`

Note: books returned late (more than 30 days after the date of borrowing)

```json
[
    {
      "id": 1,
      "member": {
        "id": 1,
        "name": "Abraham"
      },
      "book": {
        "id": 1,
        "title": "Atomic Habit"
      },
      "borrowed_at": "2023-10-10 10:00:00"
    },
    ...
]
```

## TOP 3 Books

`GET | {BASE_URL}/api/borroweds/top-3`

Note: get the 3 most frequently borrowed books

```json
[
    {
        "id": 1,
        "title": "Atomic Habit",
        "total_borrowed": 10
    },
    ...+2
]
```
