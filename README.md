# QA_Challenge
Qa Challenge for Kantox

Please refer to this document for some additional context regarding the delivered tests.

----------------------------------------------------------------------------------

Part 1: Test Case Creation

The initial exercise does not specify whether the cashier function is part of a web application/form or purely a backend service embedded in code. 
For this reason, I didn't detail how users interact with the system (e.g., button clicks, form submissions) or how results are displayed (e.g., text boxes or labels), but instead I focused mainly on validating user inputs (products added to the cart) and expected outcomes (calculation of final price and application of discount rules). Since the exercise does not provide exact discount values for the ReducedPriceRule and FractionPriceRule, the expected outcomes for these are defined generically (e.g., “adjusted price applied” rather than specific values).


I decided to write them in a table/sheet like format since that's how most of the test creating applications I used worked. Additionaly, this format allowed me to structure them in a more intuitive way: starting with component (or unit) tests until to the functional E2E ones. I tried to cover the core functionalities such as product pricing, discount rule application, and cart logic, and also complete workflows where all rules are applied, ensuring the system works as expected in real-world scenarios.


I was conflicted on whether the rules should apply simultaneosly to all products, or just restrict each rule for one situation or specific product, so finally I decided to write the tests with 2 scenarios in mind:
Scenario 1: All discount rules are applicable to all products simultaneously, allowing them to be stacked together. This scenario is used to test maximum complexity and edge cases.
Scenario 2: Each discount rule applies to a single product. This approach represents a realistic user scenario that prevents customers from stacking discounts across multiple rules. For example:

GR1 → FreeRule

SR1 → ReducedPriceRule

CF1 → FractionPriceRule


----------------------------------------------------------------------------------

Part 2: API Test Structure

I structured the API tests into three separate folders: Posts, Comments and Profile.



For each operation, I included:


Pre-request tests to validate any setup or necessary conditions before API calls.


Post-request tests to validate the responses, ensuring that they meet expected formats and contain the correct data.



To minimize manual input, I utilized environment variables to store common values (e.g., IDs, titles, authors), making it easier to reuse them across multiple requests and tests.
