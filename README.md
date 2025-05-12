- **Payments Agent**: Dedicated to managing tasks related to submitting payments. It interacts with multiple APIs, MCP, and tools, such as ScanInvoice (backed by Azure Document Intelligence), Account Service to retrieve account and payment methods info, Payment Service to submit payment processing and Transaction History service to check for previous paid invoices.

- **Existing Business APIs**: Interfaces with the backend systems to perform operations related to personal banking accounts, transactions, and invoice payments. These APIs are implemented as external spring boot microservices providing the necessary data and functionality consumed by agents to execute their tasks.

  - **Account Service (Microservice)**: Provides functionalities like retrieving account details by username, fetching payment methods, and getting registered beneficiaries. This microservice supports all 3 agents.

  - **Payments Service (Microservice)**: Offers capabilities to submit payments and notify transactions. It is a critical component for the Payments Agent to execute payment-related tasks efficiently.

  - **Reporting Service (Microservice)**: Enables searching transactions and retrieving transactions by recipient. This service supports the Transactions Agent in providing detailed transaction reports to the user and the Payment Agent as it needs to check if an invoice has not been already paid.
