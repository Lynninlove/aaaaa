## Creating a Tiny Data Set

**Purpose:**  
A tiny data set is essential for testing and debugging the AMPL model without the complexity of full-scale data, ensuring the model behaves as expected under controlled conditions.

**Steps:**

1. **Identify Essential Elements:**  
   Select a small subset of materials, customers, and time periods that cover the core functionalities of your model.

2. **Simplify Data Points:**  
   Reduce the number of operations, resources, and demands to the minimum necessary to test the logic of your model.

3. **Create Data Entries:**  
   Include variations that test different parts of your model logic.

**Example Data Entries:**

```AMPL
data;
set MATERIAL := Mesh, Fleece;
set CUSTOMER := Store;
set TIME := Day1, Day2;

param cost := 
    Mesh 1,
    Fleece 2;

param supply {
    [Mesh, Day1] 50,
    [Fleece, Day1] 30
};

param demand {
    [Store, Mesh, Day1] 20,
    [Store, Fleece, Day1] 10
};

## Dealing with Indices

### Approach

- **Define Sets Explicitly:** Ensure all sets such as `MATERIAL`, `CUSTOMER`, and `TIME` are clearly defined in your model. This ensures that every data element is accurately represented and utilized.

- **Use Indices in Parameters and Variables:** Index parameters and variables appropriately to handle different scenarios and data dimensions. This allows the model to process data correctly across various dimensions like time periods, materials, or customer requirements.

## Incorporating an Offset Parameter

### Purpose

- An offset parameter is used to simulate delays or advance periods in operations, affecting resource usage or product delivery timing. This is crucial for models where timing impacts operational efficiency or customer satisfaction.

### Implementation

- **Define Offset:** Create a parameter for offsets that apply to specific operations or time-sensitive actions. This parameter can modify when resources are allocated or when products are delivered.

- **Adjust Constraints:** Incorporate the offset into model constraints to shift operational schedules as necessary.

### Example Implementation

```AMPL
param offset{OPERATIONS, TIME} default 0;

subject to SupplyConstraint{r in RESOURCE, t in TIME}:
    sum {o in OPERATIONS} Exec[o, t - offset[o, t]] * usage[o, r] <= supply[r, t];

## Running the Model
### Steps
**Load the Model:**
Use model filename.mod; to load your model file. This prepares the model with all defined sets, parameters, and constraints.

**Load the Data:**
Use data filename.dat; to load your data file. This imports all necessary data into the model for processing.

**Solve the Model:**
Use solve; to execute the solver. This command triggers the model to find solutions based on the constraints and objectives set.

**Display Results:**
Use display Exec; to show the results. This command outputs the values of the Exec variable, which represents the execution levels of operations across different times.
