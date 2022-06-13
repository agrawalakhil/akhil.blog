---
layout: post
title: Core Accounting
---

<div class="message">
  This is a post to get someone started with core accounting concepts.
</div>

* Table Of Contents
{:toc}
# Introduction
The blog post on core accounting will cover the basics for accounting with different concepts like chart of accounts, double bookkeeping, accounting equations etc. Providing a broader view on the financial, managerial and cost accounting, how these tie together.

It will also cover the money flows between different entities and how it is accounted for using the accounting entity & time period. Different accounting systems of cash & accrual basis,  conventions around debit/credit & increase/decrease, account types of nominal & real accounts.

The core accounting concepts of journal, ledger and double bookkeeping, different financial reports, financial decision making, cost analysis & finally return on investment.

## Background
Accounting is primarily aimed  at better financial health & planning, generally it can be understood as composed of the following activities which can be broadly classified into financial, managerial & cost accounting. The target is to use accounting information to do the budgeting & forecasting & finally do capital allocation based on the return on investment (ROI).

<table>
  <tr>
    <th colspan="3">Financial Accounting</th>
    <th colspan="1">Only MA</th>
    <th colspan="2">Cost Accounting</th>
  </tr>
  <tr>
    <th colspan="2">Only FA</th>
    <th colspan="3">Managerial Accounting</th>
    <th colspan="1">Only CA</th>
  </tr>
  <tr>
    <th colspan="1">Transaction Bookkeeping</th>
    <th colspan="1">Financial Reporting</th>
    <th colspan="1">Analysis & Interpretation</th>
    <th colspan="1">Decision Making</th>
    <th colspan="1">Costing Control & Analysis</th>
    <th colspan="1">Costing Bookkeeping</th>
  </tr>
  <tr>
    <td align="center">Transactions / Events / Occurrences <br/> ↓ </td>
    <td align="center"> → <br />Financial Reporting (Equity Changes, Notes To Account)</td>
    <td align="center">Financial Statement Analysis <br /> ↓ </td>
    <td align="center">Budgeting <br /> <br />↓</td>
    <td align="center"> ← <br />Costing Techniques (marginal, absorption)</td>
    <td align="center">Identifying elements of costs <br/>↓</td>
  </tr>
  <tr>
    <td align="center">Recording (Journal Entry) Primary Books <br/> ↓ </td>
    <td align="center">↑ <br />Financial Statement (Balance Sheet, P/L, Cashflow)</td>
    <td align="center">Financial Ratio Analysis & Interpretation <br/> <br /> ↓ </td>
    <td align="center">Capital Allocation <br/> ↑↓ <br/> ROI (Return On Investment)</td>
    <td align="center">↑ <br/> Cost Control (Standard Costing & Variance Analysis)</td>
    <td align="center">Classifying elements of costs <br/>↓</td>
  </tr>
  <tr>
    <td align="center">Classifying (Ledger Entries) Secondary Books <br />→</td>
    <td align="center">↑ <br />Summarizing (General Ledger, Trial Balance)</td>
    <td align="center">Relative & Comparative Analysis (Time & Industry) <br />→</td>
    <td align="center">↑ <br /><br />Forecasting</td>
    <td align="center">↑ <br /> <br />Cost Analysis</td>
    <td align="center">(CVP & BE) <br />Cost determination (costing) <br/>←</td>
  </tr>
</table>

# Concepts
Various concepts that are important to understand before we get into the core accounting in general & for some of the products.

## Accounting Cycle
The accounting cycle is the first important concept to understand which basically represents the scope of accounting in terms of activities bounded by time & entity. The cycle starts with identifying the transactions (during time duration for a set of entities), recording journal entries, classifying into ledger entries, summarizing into general ledger & trial balance, auditing & balancing the accounts, generating the financial statements and closing the books.
<img src="" />

## Account Types & Golden Rules
To understand the Golden Rules of Accounting we must first understand the types of accounts. The account classification applies to all the types of general ledgers. In other words, every account will fall in one of the broad classifications given below. There are three types of accounts:

* A **Real Account** is a general ledger account relating to Assets and Liabilities other than people accounts. These are accounts that don’t close at year-end and are carried forward. An example of a Real Account is a Bank Account.
* A **Personal Account** is a General ledger account connected to all persons like individuals, firms and associations. An example of a Personal Account is a Creditor Account.
* A **Nominal Account** is a General ledger account pertaining to all income, expenses, losses and gains. An example of a Nominal Account is an Interest Account.

**Accounting Rules**

| Account Type | Rule |
|----------|:-------------:|
| For Personal Accounts | Debit the receiver, credit the giver |
| For Real Account | Debit what comes in, credit what goes out |
| For Nominal Account | Debit all the expenses, credit all the incomes |


## Chart Of Accounts
Chart of accounts is the general organizing technique used in accounting for structuring the transactions into various heads/buckets/bins which then roll up to general ledger & trial balance.

There are multiple different ways of structuring the chart of accounts and it is a very similar exercise like the data modeling exercise done whenever building any data application. The better schema design done for the database solves a lot of problems later, it is the same logic with a chart of accounts, we can consider this as data modeling for accounting data.

### Account Identification
* Generally speaking each account should be identified by the UUID but this alone is not useful in easily defining the ledger entries (which translates to governor rules & ledger config) without too much redundancy as well, we need another way of identifying accounts based on the identifying dimensions.
* Account identification using identifying dimensions will require combining the identifying dimensions of the parent & identifying dimensions of the sub account.

### Naming & numbering of the accounts
* Account numbers are like the bin numbers in a warehouse. Five-digit base account numbers work well (four for a very simple setup). Best practice is to use the 10000s for asset accounts, 20000s for liabilities, 29000s for equity, 30000s for sales, 40000s-50000s for direct/indirect costs, 60000-70000s for operating/overhead expenses, and 80000-90000s for non-operations accounts such as interest and taxes.
* Account naming can also be used to reflect both the hierarchy of accounts & identifying dimensions like [Account Id][Account Category][Account Type][Fund Account Type] - [Sub Account Id] which is basically a combination of parent identifying dimensions + sub account identifying dimensions.
* Account Naming & Numbering are both for making accounts more readable for users & are not to be used by the system for identification purposes.

### Account Hierarchy vs Account Dimensions
* Hierarchy is in general very strict & restrictive (inheritance is always tightly coupled as it causes tight coupling between parent/child and that is the reason composition is preferred in object oriented data modeling), but it makes sense to use hierarchy when inheriting the parent attributes in the child is required (parent account acting as template for the child accounts)
* Avoid more than 2 or 3 levels of child accounts. For example, 33000 Sales-Hardware could be further broken out to 33100 Sales-Hardware-Computers and 33200 Sales-Hardware-Printers. Hardware-Printers could be further broken out in 33210 Hardware-Printers-HP and 33220 Hardware-Printers-Canon. At that point, further detail may be more harmful than help and lead to inaccurate accounting.

## Double Bookkeeping 
**Single Bookkeeping Example (Mostly useful for tracking cash in single account)**

<table>
  <tr><th rowspan="2">Date</th><th rowspan="2">Description</th><th colspan="2">Transaction Value</th><th rowspan="2">Account Balance</th></tr>
  <tr><th>Income (Credit)</th><th>Expense (Debit)</th></tr>
  <tr><td>01/01/2022</td><td>Starting Monthly Balance</td><td align="right"></td><td align="right"></td><td align="right">&#8377;100000</td></tr>
  <tr><td>02/01/2022</td><td>Rent</td><td align="right"></td><td align="right">&#8377;20000</td><td align="right">&#8377;80000</td></tr>
  <tr><td>03/01/2022</td><td>Invoice Paid (Excel Tech)</td><td align="right">&#8377;50000</td><td align="right"></td><td align="right">&#8377;130000</td></tr>
  <tr><td>04/01/2022</td><td>Supplies (Furniture)</td><td align="right"></td><td align="right">&#8377;15000</td><td align="right">&#8377;115000</td></tr>
  <tr><td>05/01/2022</td><td>Ending Monthly Balance</td><td align="right"></td><td align="right"></td><td align="right">&#8377;115000</td></tr>
</table>

**Double Bookkeeping - Same Example**
* Assets, Expense & Dividends (Debit means increase & credit means decrease)
* Liability, Revenue & Equity (Debit means decrease & credit means increase)

<table>
  <tr><th rowspan="2">Date</th><th rowspan="2">Description</th><th colspan="2">Double Bookkeeping</th><th rowspan="2">Cash Account Balance</th></tr>
  <tr><th>Debits</th><th>Credits</th></tr>
  <tr><td>01/01/2022</td><td>Starting Monthly Balance</td><td align="right"></td><td align="right"></td><td align="right">&#8377;100000</td></tr>
  <tr><td>02/01/2022</td><td>Rent</td><td align="right">[Expense][Rent] = &#8377;20000</td><td align="right">[Asset][Cash] = &#8377;20000</td><td align="right">&#8377;80000</td></tr>
  <tr><td>03/01/2022</td><td>Invoice Paid (Excel Tech)</td><td align="right">[Asset][Cash] = &#8377;50000</td><td align="right">[Revenue][Product] = &#8377;50000</td><td align="right">&#8377;130000</td></tr>
  <tr><td>04/01/2022</td><td>Supplies (Furniture)</td><td align="right">[Asset][Fixed] = &#8377;15000</td><td align="right">[Asset][Cash] = &#8377;15000</td><td align="right">&#8377;115000</td></tr>
  <tr><td>05/01/2022</td><td>Ending Monthly Balance</td><td align="right"></td><td align="right"></td><td align="right">&#8377;115000</td></tr>
</table>

Double bookkeeping is better for reducing financial errors, managing cash entries correctly (in accrual basis accounting), every transaction needs to have equal debits & credits, this can still result in deficit or surplus on aggregate level (for this the trial balance comes handy).

The debit & credit is the somewhat confusing nomenclature in accounting (due to different behavior for different account types), lot of new accounting standards are already moving to increase/decrease which remains the same for all account types.

## Accounting Equation
The accounting equation is a critical concept to understand and use the double bookkeeping, whenever the entries are made on opposite sides of the equation, will be of the same type (credit or debit) while if entries are on the same side of the equation, it will be opposite to each other.


* Balance Sheet Accounting Equation
  - **Assets = Liabilities + Shareholder’s Equity**

* Expanded Accounting Equation
  - **Assets = Liabilities + Share Capital + Retained Earnings**

* Fully Expanded Accounting Equation
  - **Assets = Liabilities + Contributed Capital + Earlier Retained Earnings + Revenue - Expenses - Dividend**
  - **Assets + Expenses + Dividend = Liabilities + Contributed Capital + Earlier Retained Earnings + Revenue**

<table>
  <tr><th rowspan="2">Date</th><th rowspan="2">Description</th><th colspan="4">Accounting Equation</th><th rowspan="2">Cash Account Balance</th></tr>
  <tr><th>Assets = </th><th>Liabilities + </th><th>Revenue -</th><th>Expenses</th></tr>
  <tr><td>01/01/2022</td><td>Starting Monthly Balance</td><td align="right"></td><td align="right"></td><td align="right"></td><td align="right"></td><td align="right">&#8377;100000</td></tr>
  <tr><td>02/01/2022</td><td>Rent</td><td align="right">[Asset][Cash] = -&#8377;20000 (cr)</td><td align="right"></td><td align="right"></td><td align="right">[Expense][Rent] = +&#8377;20000 (dr)</td><td align="right">&#8377;80000</td></tr>
  <tr><td>03/01/2022</td><td>Invoice Paid (Excel Tech)</td><td align="right">[Cash] = +&#8377;50000 (dr)</td><td align="right"></td><td align="right">[Product] = +&#8377;50000 (cr)</td><td align="right"></td><td align="right">&#8377;130000</td></tr>
  <tr><td>04/01/2022</td><td>Supplies (Furniture)</td><td align="right">[Fixed] = +&#8377;15000 (dr) <br />[Cash] = -&#8377;15000 (cr)</td><td align="right"></td><td align="right"></td><td align="right"></td><td align="right">&#8377;115000</td></tr>
  <tr><td>05/01/2022</td><td>Ending Monthly Balance</td><td align="right"></td><td align="right"></td><td align="right"></td><td align="right"></td><td align="right">&#8377;115000</td></tr>
</table> 

## Accounting System
The accounting system is quite different based on the recognition of revenue & expense as it has implications for a lot of things like balance sheet, income statement & cash-flow statement. The major difference comes with respect to taxes & cash-flow, some more detailing below.

### Cash Basis Accounting
In the cash basis accounting system, every transaction is recognised only at the time of cash movement (when money changes hands).
Many small businesses opt to use the cash basis of accounting because it is simple to maintain. It’s easy to determine when a transaction has occurred (the money is in the bank or out of the bank) and there is no need to track receivables or payables.

The cash method is also beneficial in terms of tracking how much cash the business actually has at any given time; looking at bank balance gives understanding of the exact resources at disposal.

### Accrual Basis Accounting 
Accrual basis accounting is a method of accounting where revenues and expenses are recorded when they are earned, regardless of when the money is actually received or paid.

The accrual basis gives a more realistic idea of income and expenses during a period of time, therefore providing a long-term picture of the business that cash accounting can’t provide.

But accrual accounting doesn’t provide any awareness of cash flow; a business can appear to be very profitable while in reality it has empty bank accounts. Accrual basis accounting without careful monitoring of cash flow can have devastating consequences on business operations.
Comparison Between Cash & Accrual 

| | Cash Basis Accounting | Accrual Basis Accounting |
|----------|-------------|-------------|
| Revenues | Recognizes revenue when cash has been received | Recognizes revenue when it’s earned (eg. when the project is complete) |
| Expenses | Recognizes expenses when cash has been spent | Recognizes expenses when they’re billed (eg. when you’ve received an invoice) |
| Taxes | Taxes are not paid on money that hasn’t been received yet | Taxes paid on money that you’re still owed |
| Usages | Mostly used by small businesses and sole proprietors with no inventory | Required for businesses with revenue over $25 million |

Examples of Cash & Accrual Basis

| Transaction | Cash Basis Accounting | Accrual Basis Accounting |
|----------|-------------|-------------|
| Revenue From Project | Revenue accounted when billed amount for the project comes to the bank account | Revenue accounted when invoice for the billed amount is raised |
| Expenses For Project | Expenses accounted when booked amount for project expense deducted from bank | Expenses accounted when amount for project expense booked | 
| Tax Implication | Tax implication is at the time of revenue collected & expense deducted | Tax implication is at the time of invoice raised & expense booked |

The accrual basis system is much more relevant today due to the dependency and popularity of the credit over cash. Almost everywhere you see the credit as a product (Debentures, Bonds, Overdraft for businesses while BuyNowPayLater, Credit Card, Credit Line like products for consumers) is becoming more popular than the cash.

There are a lot of other benefits of accrual basis accounting as it is much closer to real life situations where companies give customers credit (postpaid after order is delivered) and pay the vendors (after invoice is raised). The real complication comes with taxes particularly the GST which is based on recognition of revenue & expense (instead of realization).

### Accounting Across
Many times accounting for one time period or one entity is not good enough, we need to incrementally do accounting for across time periods & across entities.

### Accounting Across Time
Accounting can be done at different intervals of time - Day, Week, Month, Quarter, Year and the reason for doing accounting across time is to enable us to see or monitor financial health at different time granularities.

### Accounting Across Entities
Accounting can be done across different entities like departments or business units, rolling up with entities like departments to organization. We can also do scoped accounting for an entity like accounting for another business upto the extent data is available and it makes sense.

With both time & entities, the accounting can be done at a granular level & also roll-up to provide both a granular & wider view of financial health for entities x times dimensions.

# Money Movement
Various money movements in general from firm to stockholders, between firm & financial system but before we go into the details of the money movement, it is important to understand the interrelation between various statements.

## Relationship Between Financial Statements
How different kinds of statements are linked to each other and how it helps in doing accounting for next week, month or year.

<img src="https://akhil.blog/public/images/balance_sheet_income_cashflow_retained_earnings.jpeg" width="720" />

## References
**Chart of Accounts**
* [Design Your Chart of Accounts](https://support.accountingseed.com/hc/en-us/articles/360016176513-Design-Your-Chart-of-Accounts)
* [Blog – SoftLedger: Accounting Software and API](https://softledger.com/blog/creating-a-chart-of-accounts)

**Accounting**
* [Accounting Memento For Entrepreneurs (US GAAP) — Odoo Business 0.1 documentation](https://www.odoo.com/documentation/functional/accounting.html)
* [Accounting Applications - Banana Accounting Software](https://www.banana.ch/doc/en/node/7687)

**Double Entry Bookkeeping**
* [Books, an immutable double-entry accounting database service](https://developer.squareup.com/blog/books-an-immutable-double-entry-accounting-database-service/)
* [Bookkeeping - Outline - AccountingCoach](https://www.accountingcoach.com/bookkeeping/outline)
* [A Relatively Painless Guide to Double-Entry Accounting](https://bench.co/blog/accounting/double-entry-accounting/)

**Accounting System**
* [Cash Basis Accounting vs. Accrual Accounting - Bench Accounting](https://bench.co/blog/accounting/cash-vs-accrual-accounting/)
* [Golden Rules of Accounting - Overview & Types](https://cleartax.in/s/accounting-golden-rules)

**Foreign Currency**
* [Guide to multi-currency accounting](https://cdn2.hubspot.net/hubfs/2304371/Product_Docs/Guide_to_Brightpearl_multi-currency_accounting_1.0.pdf)

**Accounting Equation**
* [Expanded Accounting Equation - Overview, Formula, Examples](https://corporatefinanceinstitute.com/resources/knowledge/accounting/expanded-accounting-equation/)
* [What is the expanded accounting equation? - AccountingCoach](https://www.accountingcoach.com/blog/expanded-accounting-equation)
* [The Basic Accounting Equation - Financial Accounting](https://courses.lumenlearning.com/sac-finaccounting/chapter/the-basic-accounting-equation/)

**Books**
* [Fundamentals Of Corporate Finance](https://www.wiley.com/en-us/Fundamentals+of+Corporate+Finance%2C+4th+Edition-p-9781119371434)
* [Financial Shenanigans](https://www.amazon.in/Financial-Shenanigans-Fourth-Accounting-Gimmicks/dp/126011726X)
* [Financial Intelligence](https://www.amazon.in/Financial-Intelligence-Revised-Managers-Knowing-ebook/dp/B00AXS5EAK)  

**Udemy Courses**
* [The Complete Financial Analyst Course 2022 - Udemy](https://www.udemy.com/course/the-complete-financial-analyst-course/)
* [Financial Accounting - #1 Ranked University: Course 1 of 5 - Udemy](https://www.udemy.com/course/learnaccountingforfree/)
* [Managerial Accounting- #1 Ranked University: Course 2 of 5 - Udemy](https://www.udemy.com/course/managerial_accounting/)
