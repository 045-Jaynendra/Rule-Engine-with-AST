
# Application 1: Rule Engine using AST
~Jaynendra Sharma
![as1 1](https://github.com/user-attachments/assets/b6ed755a-adfa-464a-bc16-12f7892b9eb3)


Preview: 

## Overview

This application functions as a rule engine that assesses user eligibility based on various attributes, including age, department, salary, and experience. It employs an Abstract Syntax Tree (AST) for representing and managing conditional rules, facilitating the dynamic creation, combination, and evaluation of rules.

## Features

- **Rule Creation:** Users can define rules using a string format, which is then transformed into an AST.

  ![as1 2](https://github.com/user-attachments/assets/06f219d1-a3fc-4188-9ac2-914dfa9fc316)



- **Rule Combination:** Allows the merging of multiple rules into a singular AST to enable more intricate evaluations.

![as1 3](https://github.com/user-attachments/assets/37ce2a07-8b3e-4b9b-9976-7e241aef6a1a)



- **Rule Evaluation:** Assesses whether the provided data aligns with the criteria set by the AST.

![as1 4](https://github.com/user-attachments/assets/2f3c8f9d-1d28-4ad6-90f5-39b5bd6a4340)



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
   git clone "https://github.com/045-Jaynendra/Rule-Engine-with-AST.git"
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
    ![as1 5](https://github.com/user-attachments/assets/c2e24055-cae3-45d6-9d73-fe57614c4ad3)

   
     
     
2. **Combine Rules**
   - **Endpoint:** `/api/rules/combine_rules`
   - **Method:** POST
   - **Request Body:**
   - **Response:**
   ![as1 6](https://github.com/user-attachments/assets/01ee0f3f-72a4-450c-81a7-bad73a768656)




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
