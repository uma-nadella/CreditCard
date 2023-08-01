# 🛠️ Daml CreditCard Application🛠️ 
Daml Credit Card Application is a Credit Card application built in Daml.
Credit is an application built on DAML that offers 
customer's to apply Create Card with, Bank Can Approve/Reject the customer application and provide card to Customer's once the application approved. Customer start using card.

### I. Overview 
This project was created by using the `empty-skeleton` template. The project adopts and exemplifies the `proposal-accept` design pattern. 

Apply card by customer's and Approve/Reject CreditCard Application design.Once Customer received card can start using Card. CreditCard Issued once the Application is approved

### II. Workflow
  1.Customer can apply credit Card with Bank 
  
  2.Bank Can Approve or Reject CreditCard Application submitted by Customer
  
  3.Once the Bank Accepts Application , Credit Card is Issued
  
  4.Customer start using the Card in Outlets 
  
  5.Credit Balance Reduced when the transaction done using Card

  In CardApplication.daml File defined all fields related paties of Customer and Bank
  
> In CreditCard.daml File defined templates and choices excercised

> In TestCreditCard.daml , maintained Test scripta , Party Allocation and data related to Testing

> Template "CreditCardApplication" to apply for Credit Card with Choice "SubmitApplication"

> Template "CreditCard" maintains fields/record of Credit Card

> Choices "ApproveApplication" or "RejectApplication" of CreditCardApplication submitted

> If Bank approves Application the "CreditCard" issued with the name of customer

> If Bank Rejects the it's archived

> Template "Transaction" for  transaction data

> Choice "SpentOutlet" records transaction Data on Card and Choice "UpdateBalance" update the card balance

### III. Challenge(s)
* The project was created by using empty-skeleton and the following was commented from daml.yaml:
```
sandbox-options:
   - --wall-clock-time
```
and the following was added:

```
init-script: TestCreditCard:testApp
exposed-modules:
  - Main
```

### IV. Compiling & Testing
To compile and test, run the pre-written script in the `TestCreditCard.daml` under /daml OR run:
```
$ daml start
```

> daml test --show-coverage

Test Summary

daml/TestCreditCard.daml:testApp: ok, 2 active contracts, 8 transactions.

Modules internal to this package:
- Internal templates
  
  3 defined
  
  3 (100.0%) created
  
  internal templates never created: 0
  
- Internal template choices
- 
  8 defined
  
  4 ( 50.0%) exercised
  
  internal template choices never exercised: 4
  
    CreditCard:CreditCard:Archive
  
    CreditCard:CreditCardApplication:Archive
  
    CreditCard:CreditCardApplication:SubmitApplication
  
    CreditCard:Transaction:Archive
  
- Internal interface implementations
  0 defined
    0 internal interfaces
    0 external interfaces
- Internal interface choices
  0 defined
  0 (100.0%) exercised
  internal interface choices never exercised: 0
Modules external to this package:
- External templates
  0 defined
  0 (100.0%) created in any tests
  0 (100.0%) created in internal tests
  0 (100.0%) created in external tests
  external templates never created: 0
- External template choices
  0 defined
  0 (100.0%) exercised in any tests
  0 (100.0%) exercised in internal tests
  0 (100.0%) exercised in external tests
  external template choices never exercised: 0
- External interface implementations
  0 defined
- External interface choices
  0 defined
  0 (100.0%) exercised in any tests
  0 (100.0%) exercised in internal tests
  0 (100.0%) exercised in external tests
  external interface choices never exercised: 0

