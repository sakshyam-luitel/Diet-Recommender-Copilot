# DATABASE SCHEMA

## User Table
| Field          | Type         | Notes                                |
|----------------|--------------|--------------------------------------|
| user_id        | INT          | Primary Key, Auto Increment          |
| username       | VARCHAR(255) | Unique, User's account name         |
| email          | VARCHAR(255) | Unique, User's email address        |
| password_hash  | VARCHAR(255) | Hash of the user's password          |
| created_at     | DATETIME     | Timestamp for account creation       |
| updated_at     | DATETIME     | Timestamp for last update            |

### Data NOT Stored:
- Plain text passwords
- Login attempts by the user

## Cart Table
| Field          | Type         | Notes                                |
|----------------|--------------|--------------------------------------|
| cart_id        | INT          | Primary Key, Auto Increment          |
| user_id        | INT          | Foreign Key, Reference to User       |
| item_id        | INT          | Foreign Key, Reference to Items      |
| quantity       | INT          | Number of items in the cart          |
| created_at     | DATETIME     | Timestamp for cart creation          |
| updated_at     | DATETIME     | Timestamp for last update            |

### Data NOT Stored:
- Session data of the cart
- Temporary state of items during checkout

## Recommendation History Table (Optional)
| Field          | Type         | Notes                                |
|----------------|--------------|--------------------------------------|
| history_id     | INT          | Primary Key, Auto Increment          |
| user_id        | INT          | Foreign Key, Reference to User       |
| recommendation  | TEXT        | Recommended items for the user      |
| created_at     | DATETIME     | Timestamp for recommendation creation |

### Data NOT Stored:
- User preferences or selections
- Feedback on recommendations

---
This schema provides a clear structure for managing user accounts, their shopping carts, and optional recommendations while ensuring sensitive data is handled appropriately.