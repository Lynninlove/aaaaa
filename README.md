# 1. Refactoring Plan and Commentary
## Refactoring Plan:

- Unify Operations: To simplify the model and adhere to operations management standards, convert the distinct Make, Buy, and Ship variables into a single Exec[o, t] variable type.
- Build Operations Set: Consolidate Ship-Operations from HAS_DEMAND, Buy-Operations from CAN_BUY, and Make-Operations from BOMs into a single set.
- Reduce the Complexity of Resource Balance: Include resource stocking and scrapping as processes in the model itself. The limitations are made simpler by this integration, which also more accurately depicts the dynamics of resource management.
- Backlogging as an Operation: Backlogging may or may not be included as an operation, based on whether the demand is perishable and can wait or can be met right now.
  
## Commentary:

- The goal of the refactoring is to make the model structure more straightforward while maintaining an accurate representation of the business's operational intricacies. This method also makes maintenance simpler and better scalable.
- The initial complexity of comprehending the unified operations model and making sure that all behaviors are maintained without unexpected repercussions are examples of potential risks.

# 2. Document Model
For the AMPL model documentation:

## Header Comment: 
Summarize the main changes made during the refactoring process as well as the goal of the model.
## Comments on Sets and Parameters:
- Explain each set in detail, starting with OPERATIONS and going through Make, Buy, and Ship.
- Describe each parameter, such as materials_used[o, r], cost[o], and time[o], and what it means in relation to the activities.
## Variable Documentation:
Describe in detail the Exec[o, t] variable and its function in expressing the operation's execution level over time.
## Constraints Explanation:
- ResourceBalance: Describe how this restriction makes sure that the amount of materials used in all processes doesn't go above what is available.
- Demand Satisfaction: Describe how this guarantees that operational output either satisfies or surpasses demand.
  
# 3. Test Cases
## Develop tiny test cases that are easy to validate:

- Scenario 1: Test only one type of operation, like Make, with minimal data inputs.
- Scenario 2: Test a combination of Buy and Ship operations under tight resource constraints.
- Scenario 3: Test the system's response to a sudden increase in demand, assessing the model’s flexibility.

## Every test scenario will comprise:

- Anticipated results: Clearly stated using the logic of the model.
- Real results: The outcomes that were seen after the model was run.
- Methods to verify model accuracy by comparing expected and actual results are part of the validation strategy.
  
# 4. Data Set
Prepare the .dat file to reflect the new unified operations approach:

- Update the OPERATIONS Set: Include all operations as defined in the refactoring plan.
- Adjust Parameters: Ensure all parameters are correctly associated with the new operations.
- Validate Data: Check for consistency and completeness to ensure the model runs without errors.
  
# 5. Results

Results Documentation: Include detailed outcomes for each type of operation and overall model performance.
Comparison with Previous Homework: Ensure the results are consistent with HW 7, providing explanations for any discrepancies.
