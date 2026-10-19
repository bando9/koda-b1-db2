# ERD E-Wallet Bank JAGO

```mermaid

erDiagram
    CUSTOMER {
        string id_customer
        string name
        string email
        string phone
        string address
        string NIK
        date register_date
    }

    ACCOUNT {
        string id_account
        int current_amount
        string id_transaction
        string name
        string account_number
    }

    CUSTOMER ||--}o ACCOUNT: have

    TRANSACTION {
        string id_transaction
        string id_account
        string id_customer
        date transaction_date
        string description
        string status "enum('PENDING', 'ACTIVE', 'PAID')"
        string account_number
        int total_amount


    }

    ACCOUNT ||--}o TRANSACTION:"have many"
    CUSTOMER ||--}o TRANSACTION: "have many"





```
