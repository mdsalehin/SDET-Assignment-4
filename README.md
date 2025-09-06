# JMeter Chaining Project – dmoney API

## Overview  
This project demonstrates **JMeter Chaining**  using the dmoney API, simulating deposits, money transfers, and payments.
- The test plan (`dmoney_chaning.jmx`) uses CSV data files, random amounts, ramp-up configuration, and assertions to validate successful transactions.

## Service API Features  
- **Login** – `POST /auth`  
- **Deposit** – `POST /transaction/deposit`  
- **Send Money** – `POST /transaction/send`  
- **Payment** – `POST /transaction/payment`  

 ## Test Plan Workflow
1. **Admin Login** → Generate a token once and reuse for all threads.  
2. **Thread Groups**:  
   - **5 Agents** deposit for **10 Customers.**  
   - **5 Customers** send money to another **10 Customers.**
   - **5 Customers** make payments to **2 Merchants.** 
3. **CSV Files** manage test data:  
   - `deposit.csv`  
   - `sendMoney.csv`  
   - `payment.csv`  
4. **Random Variable Controller** → generates dynamic amounts.  
5. **Ramp-up Time** → 120 seconds for each thread.  
6. **Assertions** → ensure all transactions are successful.

## Scenario  
- **Deposits:** Agents → Customers.  
- **Send Money:** Customers → Customers.  
- **Payments:** Customers → Merchants.

## Technical Scope
- **Tool:** Apache JMeter.  
- **Test Plan:** `dmoney_chaning.jmx`  
- **Data Files:** `deposit.csv`, `sendMoney.csv`, `payment.csv`  
- **Execution:** Non-GUI mode with ramp-up 120s per thread.  
- **Assertions:** Ensure all transactions succeed.

## API Documentation  
- Admin login provides a **Bearer Token**, which is required for all transactions in the test plan.  
- APIs follow a RESTful structure (`/auth`, `/transaction/deposit`, `/transaction/send`, `/transaction/payment`).

## How to Run 
- jmeter -n -t dmoney_chaning.jmx -l dmoney.jtl -e -o Reports/

## Repository Structure
.
├── dmoney_chaning.jmx       # JMeter test plan
├── deposit.csv              # Agent deposit data
├── sendMoney.csv            # Customer send money data
├── payment.csv              # Customer payment data
├── Reports/                 # HTML dashboard
└── Resources/               # Screenshots of report
## Attachments:
- JMeter HTML Report.
<img width="1629" height="673" alt="image" src="https://github.com/user-attachments/assets/61c650e3-9ac8-477f-83e6-4036d7617a13" />




  
