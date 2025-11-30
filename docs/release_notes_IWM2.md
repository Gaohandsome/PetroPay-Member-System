
# Release Notes - Fuel Card System V2.0.0
Version 2.0.0 - Full Core Function Implementation
Release Date: November 30, 2025


Core Features Implemented
1. Fuel Card Management Module 
   - Card entity class: Includes card number, balance, and customer type (0 = Gold / 1 = Silver / others = Regular)
   - Methods:
     - `getMoney()`/`setMoney()`: Read/write balance
     - `getType()`/`setType()`: Switch customer type

2. Recharge & Consumption Module 
   - Recharge function:
     - Recharge ≥ 5000 → Upgrade to Gold Card, prompt "Become Gold Card customer"
     - Recharge ≥ 2000 → Upgrade to Silver Card (if not Gold), prompt "Become Silver Card customer"
     - Recharge < 2000 → Regular user, directly add to balance
   - Consumption function:
     - Gold Card: 20% discount; get a car wash coupon if consumption ≥ 200 yuan
     - Silver Card: 10% discount
     - Regular user: Full-price deduction
     - Prompt "Please recharge" when balance is insufficient


 Testing Status
- Total test cases: 15
- Pass rate: 100%
- Test coverage:
  - Recharge scenarios (level-up logic for different amounts)
  - Consumption scenarios (discounts for each customer type, balance verification)
  - Accuracy of customer type switching


## Project Structure
```
PetroPay-Member-System/
├── .github/
│   └── workflows/
│       └── ci.yml
├── src/
│   ├── __init__.py
│   ├── product.py      (150 lines)
│   ├── sales.py        (130 lines)
│   └── main.py         (100 lines)
├── tests/
│   ├── __init__.py
│   ├── test_sample.py      (12 tests)
│   ├── test_sales.py       (17 tests)
│   └── test_integration.py (3 tests)
├── docs/
│   ├── release_notes_IWM1.md
│   └── release_notes_IWM2.md
├── screenshots/
├── Dockerfile
├── .dockerignore
├── requirements.txt
├── README.md
├── architecture.md
└── plan.md
```


## Next Steps
- Add card password verification
- Log recharge/consumption records
- Support batch recharge operations
