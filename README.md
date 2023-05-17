# FundamentalsCertificateApp


## **I. Overview**

The project was created using the empty-skeleton template, with the objective of allowing a customer to make purchases at a computer store and have a courier take those purchases to the customer's home. The customer has to have a bank account and a computer store account in order to do the shopping.

## **II. Workflow**
1.	The customer and the computer store must have a bank account;
2.	The customer must have an account at the computer store.
3.	When the customer has an account at the computer store, he can order a list of products that he wants to buy;
4.	The computer store accepts or rejects the order with the products and number of products chosen by the customer;
5.	After the computer store accepts the order it will immediately call a courier;
6.	The courier must always accept to take the purchases to the customer's home;
7.	The customer can accept or reject the purchases;
8.	After the customer accepts, a transaction is made from the customer's bank account to the computer store's bank account;
9.	Finally, an invoice is created with the customer's purchase.

## **III. Parties**

- Store – Computer store;
- Client – Person who buys the products in the computer store;
- Courier – Person who takes the products to the customer's home;
- Bank – Bank where the customer has money to pay for purchases at the computer store;
- Other – Other parties used to unhappy test.

## **IV. Choices**

| Template | Choice | Description |
| -------------------------- | -------------------------------- | ---------------- |
| Bank | CreateAccountBankProposal | This choice is the client's propose to the bank for creating an account |
| BankAccountProposal | RejectBankAccountProposal | This choice is for the bank to reject the account creation |
| BankAccountProposal | CreateAccountBank | This choice is for the bank to approve and create an account |
| BankAccount | CreditAmount | This choice is for the bank to accept the credit amount into the customer's account |
| BankAccount | DebitAmount | This choice is for the bank to accept the debit into the customer's account |
| Store | CreateAccountStoreProposal | This choice creates a new proposal to create an account in the store |
| Store | AddStockProducts | This choice is to add new products into the stock |
| ClientAccountStoreProposal | RejectStoreAccountProposal | This choice allows the rejection of the proposal to create an account |
| ClientAccountStoreProposal | CreateAccountStore | This choice is to create an account store |
| ClientAccountStore | N/A | N/A |
| StockProducts | AddProductToStock | This choice adds products to stock |
| StockProducts | OrderProductProposal | This choice create a proposal to order products |
| StockProducts | UpdateProductToStock | This choice update the product stock or not if the number of produtos is equals 0 or less |
| OrderProduct | ValidateOrderByStore | This choice validates the order by the store and accept or reject the order |
| OrderCourier | ApproveOrderByClient | This choice approves the purchase by the customer |
| OrderCourier | RejectOrderByClient | This choice rejects the order by the customer |
| TransactionPaymentDebit | ValidateTransactionPaymentDebit | This choice validates the debit amount transaction |
| TransactionPaymentCredit | ValidateTransactionPaymentCredit | This choice credits the amount to a new account |
| Transaction | N/A | N/A |


## **V. Diagram**

### End-to-end diagram
![happy](https://github.com/tiagsantos/texting/assets/133690802/9ab642d5-81f6-4544-bbc3-8eedf6aa6629)

### Bank rejects account diagram
![unhappy_1](https://github.com/tiagsantos/texting/assets/133690802/e28e55f5-909b-4b96-a893-978e06bfaee9)

### Store rejects client's account proposal diagram
![unhappy_2](https://github.com/tiagsantos/texting/assets/133690802/e3165779-e950-431a-8310-2297159702b8)

### Store rejects an order by client diagram
![unhappy_3](https://github.com/tiagsantos/texting/assets/133690802/bc9eac6f-5653-492c-b923-8dfc0771cc43)

## **VI. Tests**

- To test end-to-end success cases, use the UnitTests.MainEndToEndHappyTest module and see the result of the scripts;
- To test each module separately, with unhappy tests and see the result of the scripts, the following modules were created: 
   - UnitTests.ManagementBankTest; 
   - UnitTests.ManagementClientsTest; 
   - UnitTests.ManagementProductsTest; 
   - UnitTests.PaymentsTest. 

## **VII. Notes**

 - This project was created with Daml version 2.6.0;
 - To simulate some unhappy tests, it was necessary to create the first contracts and follow the workflow successfully to be able to do them.
   - Example: To create a transaction an order must exist.
