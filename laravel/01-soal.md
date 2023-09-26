# Table

**Classrooms**
| Column | Type |
| ----------- | ----------- |
| id | INT |
| grade | INT |

**Students**
| Column | Type |
| ----------- | ----------- |
| id | INT (PK) |
| classroom_id | INT (FK) |
| name | Varchar |

**Subjects**
| Column | Type |
| ----------- | ----------- |
| id | INT (PK) |
| name | Varchar |

**Exams**
| Column | Type |
| ----------- | ----------- |
| id | INT (PK) |
| student_id | INT (FK) |
| subject_id | INT (FK) |
| score | INT |

# Input / Request

## Get Student's scores

`GET | {BASE_URL}/api/students/{student_id}/scores`

**Expected Output**

```json
{
    math: [95, ...],
    english: [90, ...],
    ...
}
```

## Class' average score

`GET | {BASE_URL}/api/classrooms/average`

**Expected Output**

```json
{
    grade_10: {
        math: 85.5,
        english: 75.2,
        ...
    },
    grade_11: {
        math: 85.5,
        english: 75.2,
        ...
    },
    ...
}
```

## Best Students

`GET | {BASE_URL}/api/best-students?grade=12`

**Expected Output**

```json
{
    math: {
        student_id: 1,
        name: "Abraham",
        grade: 12,
        score: 100
    },
    ...
}
```
