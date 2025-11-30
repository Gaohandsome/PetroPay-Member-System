
Release Notes - Fuel Card Recharge Business System V1.0.0

Version 1.0.0 - Initial Function Implementation

Release Date: November 2025

 Completed Tasks
 Core Function Development
- Recharge Function (save method)
  - Supports graded customer type upgrade based on recharge amount:
    - Recharge ≥ 5000 yuan: Upgrade to gold card customer and accumulate the recharge amount
    - Recharge ≥ 2000 yuan: Upgrade to silver card customer (if not a gold card holder) and accumulate the recharge amount
    - Recharge < 2000 yuan: Regular user, accumulate the recharge amount
  - Output personalized recharge prompts for different customer types

- Consumption Function (pay method)
  - Gold card users: Enjoy a 20% discount, and get a car wash coupon when consumption ≥ 200 yuan
  - Silver card users: Enjoy a 10% discount
  - Regular users: No discount, deduct the original amount
  - Prompt for recharge when the balance is insufficient for all user types

 Project Structure Setup
Created the `com.itheima.demo4` package containing core business classes:
```
com/
└── itheima/
    └── demo4/
        ├── Pos.java  // Contains core logic for recharge and consumption
        └── Card.java // Fuel card entity class (with type and balance attributes and get/set methods)
```

Logic Design
- Distinguish customer levels based on the `type` field of the `Card` class (0 = gold card, 1 = silver card, others = regular)
- Maintain the balance in the card through the `money` field to ensure the amount is correctly added/deducted during recharge/consumption

 Features Planned
- Add validity period management for customer levels
- Implement log function for recharge/consumption records
- Support batch recharge and preferential activity configuration
- Add card password verification mechanism

Team Collaboration
- Completed coding and testing of core business logic
- Defined interaction specifications between the `Card` entity class and the `Pos` business class

 Next Steps
- Write unit tests to cover recharge and consumption scenarios
- Optimize user prompt copy to improve interaction experience
- Connect to the database to store card information
- Develop a simple console interactive interface


