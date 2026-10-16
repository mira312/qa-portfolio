# Checklist — Transfer Funds (ParaBank)

**Application:** ParaBank (https://parabank.parasoft.com/parabank/index.htm)
**Test type:** Functional, manual
**Date:** [date]

## 1. Positive Scenarios
- [ ] Transfer valid amount between own accounts
- [ ] Transfer full balance (balance = 0 after transfer)
- [ ] Transfer minimum amount ($0.01)
- [ ] Transfer with two decimal places ($10.50)
- [ ] Check that balance updates in Accounts Overview
- [ ] Check that transaction appears in transaction history

## 2. Boundary Values
- [ ] Transfer $0 (should be blocked)
- [ ] Transfer negative amount (should be blocked)
- [ ] Transfer amount > balance (should show "insufficient funds")
- [ ] Transfer amount = balance (edge case, should succeed)
- [ ] Transfer maximum allowed amount

## 3. Validation
- [ ] Amount field accepts only digits and decimal separator
- [ ] Amount field rejects letters and special characters
- [ ] Amount field rejects more than two decimal places
- [ ] Empty amount field shows validation error

## 4. Negative Scenarios
- [ ] Transfer without selecting source account
- [ ] Transfer without selecting destination account
- [ ] Transfer to the same account (should be blocked or handled)
- [ ] Transfer during network outage

## 5. UI / UX
- [ ] Success message appears after completed transfer
- [ ] Error message is clear and in English
- [ ] Loading state is shown during processing
- [ ] Double-click on "Submit" does not create duplicate transfer

## 6. Security
- [ ] Session expires after inactivity
- [ ] Transfer requires re-authentication (if applicable)
