## Description of the problem
Given 2 tables:
(fact) - a table that contains the history of transactions.

 load_dttm - date and time when the record was inserted
 account_id - Unique account number of the client
 text entry - Transaction data contains information:
                      - by month of accrual of funds,
                      - number of charges,
                      - the amount of one charge

(client) - a table of clients, filled by the operator in Excel
 account_id - Unique account number of the client,
 name - full name of the client
 birth_date - date of birth
 branch - client's branch

It is required to convert the data to a tabular format (see below) with the condition:
 1) Scatter payments in equal shares, except for the last day of the month
 2) On the last day of the month, payments are made for the entire remaining amount on the account
 3) Accruals take place when 0 rubles remain on the account
 4) On the day of accrual, payments are not made, except for the last day of the month
 5) Transactions with the account occur daily (there are no days when there are no payments and receipts)
