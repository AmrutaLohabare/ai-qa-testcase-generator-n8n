#  Workflow Design (Detailed)

## 🎯 Objective

Design an intelligent QA automation workflow that converts SRS documents into structured test cases and automatically creates Jira artifacts.

---

## 🔄 End-to-End Workflow Breakdown

### 1. Chat Trigger

* Entry point of the system
* Accepts:

  * User email
  * SRS document (PDF format)

---

### 2. File Extraction

* Extracts raw text from uploaded PDF
* Handles structured/unstructured requirement content

---

### 3. Edit Fields (Pre-processing)

* Cleans and formats extracted content
* Removes noise and prepares prompt-ready input

---

### 4. LLM Processing (OpenAI)

The system uses OpenAI LLM to generate structured test cases.

### 🔹 Prompt Used:

Generate detailed and structured test cases based on the following requirements.

Ensure output includes:

* Test Case Title
* Domain
* Preconditions
* Test Steps
* Expected Result
* Priority
* Severity

Maintain clarity, avoid duplication, and ensure coverage of both positive and negative scenarios.

Input:
{SRS_CONTENT}

---

### 🔹 Key Considerations:

* Ensured structured output format for downstream processing
* Controlled verbosity to avoid irrelevant data
* Focused on functional coverage

---

## ⚠️ Handling Hallucination

One of the key challenges with LLMs is hallucination.

### Issues Observed:

* AI generating unrealistic or irrelevant test scenarios
* Over-generalized outputs
* Missing domain-specific constraints

### Solution Implemented:

* Provided **well-structured input context**
* Added **explicit output instructions in prompt**
* Restricted scope to **functional scenarios only**
* Ensured **clear formatting rules**

👉 This significantly improved output reliability and usability.

---

### 5. JavaScript Transformation Node

* Converts AI output into structured JSON
* Prepares payload for Jira APIs

---

### 6. Jira Story Creation

* Creates parent story for the feature
* Uses API integration

---

### 7. Split Out Node

* Iterates over each generated test case

---

### 8. Create Subtask (Jira)

* Creates individual subtasks
* Maps:

  * Title → Summary
  * Steps → Description
  * Priority & Severity

---

### 9. Merge & Aggregate

* Combines all execution results
* Tracks created issue IDs

---

### 10. Mapping & Formatting

* Formats final response
* Prepares structured output

---

### 11. Email Notification

* Sends:

  * Confirmation message
  * Summary of created Jira tickets

---

## Design Principles

* Modular workflow design
* Reusability of components
* Clear separation of responsibilities
* Scalable for larger SRS inputs
* Minimal manual intervention

---

## Outcome

The workflow demonstrates:

* AI-powered QA transformation
* Automation of repetitive QA tasks
* Seamless integration with enterprise tools (Jira)
* Practical implementation of AI in testing

---

## Future Scope

* Integration with automation frameworks
* Test execution pipeline
* Self-healing test case updates
* Multi-domain adaptability
