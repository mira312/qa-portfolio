# Test Cases — ParaBank

**Application:** ParaBank (https://parabank.parasoft.com/parabank/index.htm)
**Test type:** Functional, manual
**Date:** 16.10.2026

---

## Transfer Funds

### TC-001: Transfer valid amount between own accounts
**Preconditions:** User is logged in. User has at least one account with sufficient balance.

**Steps:**
1. Open "Transfer Funds" page.
2. Select source account.
3. Select destination account.
4. Enter amount: $10.00.
5. Click "Transfer".

**Expected result:**
- Success message is displayed.
- Balance of source account decreased by $10.00.
- Balance of destination account increased by $10.00.
- Transaction appears in transaction history.

---

### TC-002: Transfer with amount = 0
**Preconditions:** User is logged in.

**Steps:**
1. Open "Transfer Funds" page.
2. Select source and destination accounts.
3. Enter amount: $0.
4. Click "Transfer".

**Expected result:**
- Transfer is blocked.
- Error message is displayed: "Amount must be greater than 0" (or similar).

---

### TC-003: Transfer amount greater than balance
**Preconditions:** User is logged in. Source account balance is $515.50.

**Steps:**
1. Open "Transfer Funds" page.
2. Select source and destination accounts.
3. Enter amount: $1000.00.
4. Click "Transfer".

**Expected result:**
- Transfer is blocked.
- Error message is displayed: "Insufficient funds" (or similar).

---

### TC-004: Transfer full balance (edge case)
**Preconditions:** User is logged in. Source account balance is $515.50.

**Steps:**
1. Open "Transfer Funds" page.
2. Select source and destination accounts.
3. Enter amount: $515.50.
4. Click "Transfer".

**Expected result:**
- Transfer is successful.
- Source account balance = $0.00.
- Destination account balance increased by $515.50.

---

### TC-005: Transfer with negative amount
**Preconditions:** User is logged in.

**Steps:**
1. Open "Transfer Funds" page.
2. Select source and destination accounts.
3. Enter amount: -$50.
4. Click "Transfer".

**Expected result:**
- Transfer is blocked.
- Error message is displayed.
- Balance remains unchanged.

---

### TC-006: Transfer with letters in amount field
**Preconditions:** User is logged in.

**Steps:**
1. Open "Transfer Funds" page.
2. Enter amount: "abc".
3. Click "Transfer".

**Expected result:**
- Field validation error is displayed.
- Transfer is not processed.

---

## Bill Pay

### TC-007: Pay a bill with valid data
**Preconditions:** User is logged in. Account balance is sufficient.

**Steps:**
1. Open "Bill Pay" page.
2. Fill in payee name, address, city, state, zip code, phone.
3. Enter account number and amount: $50.00.
4. Select source account.
5. Click "Send Payment".

**Expected result:**
- Payment is processed successfully.
- Balance decreased by $50.00.
- Payment appears in transaction history.

---

### TC-008: Pay a bill with amount greater than balance
**Preconditions:** User is logged in. Account balance is $515.50.

**Steps:**
1. Open "Bill Pay" page.
2. Fill in valid payee data.
3. Enter amount: $1000.00.
4. Select source account.
5. Click "Send Payment".

**Expected result:**
- Payment is blocked.
- Error message about insufficient funds is displayed.

---

### TC-009: Pay a bill with empty required fields
**Preconditions:** User is logged in.

**Steps:**
1. Open "Bill Pay" page.
2. Leave all fields empty.
3. Click "Send Payment".

**Expected result:**
- Validation errors are displayed for all required fields.
- Payment is not processed.

---

### TC-010: Pay a bill with amount = 0
**Preconditions:** User is logged in.

**Steps:**
1. Open "Bill Pay" page.
2. Fill in valid payee data.
3. Enter amount: $0.
4. Click "Send Payment".

**Expected result:**
- Payment is blocked.
- Error message is displayed.
