The core components and relationships of the gas station payment system are as follows:


Main System Components
1. Card Class (Card Entity) 
   - Encapsulates core card attributes: owner's name (name), balance (money), phone number (phone), card number (cardId), and card type (type, where 0 = Gold Card / 1 = Silver Card / 2 = Regular Card).  
   - Provides getter/setter methods for accessing and modifying card information.

2. Pos Class (Payment Terminal) 
   - Core functions: Handles business logic for deposits (`save` method) and payments (pay method).  
   - Deposit logic: Automatically upgrades the card type based on the recharge amount (≥5000 → Gold Card, ≥2000 → Silver Card) and updates the balance.  
   - Payment logic: Applies discounts according to the card type (20% off for Gold Card, 10% off for Silver Card, no discount for Regular Card), checks if the balance is sufficient, and provides a free car wash ticket when Gold Card consumption exceeds 200 yuan.

3. Test Class (Test Entry) 
   - Responsible for creating card instances and payment terminal instances, simulating user deposit and consumption processes, and verifying system functionality.


Component Relationship Diagram (Simplified)

+----------------+       +----------------+       +----------------+
|                |       |                |       |                |
|    Test Class  |-----> |    Pos Class   |<----->|    Card Class  |
|  (Test Entry)  |       | (Business Logic)|      |  (Data Entity) |
|                |       |                |       |                |
+----------------+       +----------------+       +----------------+
       |                        |                        |
       |  Create instances and  |  Manipulate card      |  Store card
       |  call methods          |  attributes (deposit/ |  data
       |                        |  payment)             |
       +------------------------+------------------------+
```


Component Collaboration Process
1. The `Test` class creates a `Card` object (initializing owner information) and a `Pos` object (payment terminal).  
2. The `Pos` object’s `save` method is used to recharge the `Card`, and `Pos` modifies the `type` and `money` of `Card` based on the amount.  
3. The `Pos` object’s `pay` method is used for consumption. `Pos` calculates discounts based on the `type` of `Card`, deducts the balance, and triggers corresponding rules (e.g., car wash tickets).  
4. All data changes are stored in the `Card` object. `Pos` is responsible for business logic judgment, and `Test` simulates user operation processes.
