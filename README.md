
# Application 1: Rule Engine using AST by Y Teresha
![image](https://github.com/user-attachments/assets/dfb4461a-21f7-4560-b5f1-bc23d946ace4)

Preview: 

## Overview

This application functions as a rule engine that assesses user eligibility based on various attributes, including age, department, salary, and experience. It employs an Abstract Syntax Tree (AST) for representing and managing conditional rules, facilitating the dynamic creation, combination, and evaluation of rules.

## Features

- **Rule Creation:** Users can define rules using a string format, which is then transformed into an AST.

  ![image](https://github.com/user-attachments/assets/b24780d5-5041-4707-9b31-2cbf573fcf03)


- **Rule Combination:** Allows the merging of multiple rules into a singular AST to enable more intricate evaluations.

![image](https://github.com/user-attachments/assets/f80b0a7b-0201-4d0f-9c7c-eb4acd42ad06)


- **Rule Evaluation:** Assesses whether the provided data aligns with the criteria set by the AST.

![image](https://github.com/user-attachments/assets/d154eb35-eb66-459e-9452-2dcc286eb121)


- **Tree Visualization:** When defining or combining rules, a tree representation will be displayed for better understanding.

## Tech Stack

- **Backend:** Built with Node.js and Express.js
- **Database:** Utilizes MongoDB

## Getting Started

### Prerequisites

- Ensure Node.js and npm are installed.

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone "https://github.com/Tereshaa/Application-1-Rule-Engine-with-AST.git"
   ```
2. **Install the Backend Dependencies**
   ```bash
   npm install
   ```
2. **Create a .env file and add ur Mongo_url**
   ```bash
   MONGO_URL=""
   ```
4. **Launch the Server**
   ```bash
   npm start
   ```

## API Endpoints

1. **Create a Rule**
   - **Endpoint:** `/api/create_rule`
   - **Method:** POST
   - **Request Body:**
     ```json
     {
       "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
       "ruleName": "Rule-1"
     }
     ```
   - **Note:** Ensure that there are appropriate spaces in the rule for accurate results. The rule should follow this format: 
   `variable operator value`
   - **Response:**
    <img src="https://github.com/user-attachments/assets/4f66d741-c025-45cd-b602-acc027f0a9c6" alt="Response Image" width="300" />

   
     
     
2. **Combine Rules**
   - **Endpoint:** `/api/rules/combine_rules`
   - **Method:** POST
   - **Request Body:**
   - **Response:**
   <img src="https://github.com/user-attachments/assets/908bbdc4-0d21-4a33-ac39-5a8041100b99" alt="Response Image" width="300" />



3. **Evaluate a Rule**
   - **Endpoint:** `/api/rules/evaluate_rule`
   - **Method:** POST
   - **Request Body:**
     ```json
     {
       "rule": { ... },
       "data": {
         "age": 35,
         "department": "Sales",
         "salary": 60000,
         "experience": 3
       }
     }
     ```
   - **Response:**
     ```json
     {
       "result": true
     }
     ```

## Running Tests

You can implement and execute tests to verify that everything is functioning as expected.
