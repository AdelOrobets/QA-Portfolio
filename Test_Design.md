## 🧪 Test Design

**Test Design** is the process of creating test cases based on system requirements, specifications, or other artifacts. 
Its main goal is to define **what to test**, **how to test it**, **under what conditions**, and **what the expected results should be**.

---

### 🔹 Key Stages of Test Design

1. **Requirements Analysis**
   Understand what the system is expected to do.

2. **Test Design Technique Selection**
   Choose appropriate methods based on the system's complexity and risk level.

3. **Test Case & Scenario Creation**
   Write detailed steps, inputs, and expected outcomes.

---

### 🔹 Common Test Design Techniques

| Category    | Technique                | Description                                                                         |
| ----------- | ------------------------ | ----------------------------------------------------------------------------------- |
| **Static**  | Requirements Analysis    | Review documentation to find inconsistencies or ambiguities.                        |
| **Dynamic** | Equivalence Partitioning | Divide input data into valid and invalid partitions with expected similar behavior. |
|             | Boundary Value Analysis  | Focus on values at the edge of allowed input ranges.                                |
|             | Pairwise Testing         | Test all possible pairs of input combinations to reduce test effort.                |
|             | Decision Table           | Represent combinations of conditions and actions in tabular format.                 |
|             | State Transition         | Useful for systems with different states and transitions.                           |
|             | Checklist-based          | Verify key features using predefined lists.                                         |

---

### 🔹 Example

**Age input field** (Valid values: 18–99)

* **Equivalence Classes**:

  * Invalid: `<18`, `>99`, letters, empty input
  * Valid: `18–99`

* **Boundary Values**:

  * 17, 18, 99, 100

---

### 🔹 Benefits of Test Design

* Improves test coverage
* Reduces the chance of missing critical defects
* Saves time by applying structured methods
* Helps detect bugs earlier in the development lifecycle

