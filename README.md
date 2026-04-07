# Rust API client for cybrid_api_bank

# Cybrid API documentation

Welcome to Cybrid, an all-in-one crypto platform that enables you to easily **build** and **launch** white-label crypto products or services.

In these documents, you'll find details on how our REST API operates and generally how our platform functions.

If you're looking for our UI SDK Widgets for Web or Mobile (iOS/Android), generated API clients, or demo applications, head over to our [Github repo](https://github.com/Cybrid-app).

💡 We recommend bookmarking the [Cybrid LinkTree](https://linktr.ee/cybridtechnologies) which contains many helpful links to platform resources.

## Getting Started

This is Cybrid's public interactive API documentation, which allows you to fully test our APIs. If you'd like to use a different tool to exercise our APIs, you can download the [Open API 3.0 yaml](https://bank.production.cybrid.app/api/schema/v1/swagger.yaml) for import.

If you're new to our APIs and the Cybrid Platform, follow the below guides to get set up and familiar with the platform:

1. [Introduction](https://docs.cybrid.xyz/docs/introduction)
2. [Platform Overview](https://docs.cybrid.xyz/docs/platform-overview)
3. [Testing with Hosted Web Demo App](https://docs.cybrid.xyz/docs/hosted-demo-app)

In [Getting Started in the Cybrid Sandbox](https://docs.cybrid.xyz/docs/cybrid-sandbox), we walk you through how to use the [Cybrid Sandbox](https://id.sandbox.cybrid.app/) to create a test bank and generate API keys. In [Getting Ready for Trading](https://docs.cybrid.xyz/docs/trade-process), we walk through creating customers, customer identities, accounts, as well as executing quotes and trades.

## Working with the Cybrid Platform

There are three primary ways you can interact with the Cybrid platform:

1. Directly via our RESTful API (this documentation)
2. Using our API clients available in a variety of languages ([Angular](https://github.com/Cybrid-app/cybrid-api-bank-angular), [Java](https://github.com/Cybrid-app/cybrid-api-bank-java), [Kotlin](https://github.com/Cybrid-app/cybrid-api-bank-kotlin), [Python](https://github.com/Cybrid-app/cybrid-api-bank-python), [Ruby](https://github.com/Cybrid-app/cybrid-api-bank-ruby), [Swift](https://github.com/Cybrid-app/cybrid-api-bank-swift) or [Typescript](https://github.com/Cybrid-app/cybrid-api-bank-typescript))
3. Integrating a platform specific SDK ([Web](https://github.com/Cybrid-app/cybrid-sdk-web), [Android](https://github.com/Cybrid-app/cybrid-sdk-android), [iOS](https://github.com/Cybrid-app/cybrid-sdk-ios))

Our complete set of APIs allows you to manage resources across three distinct areas: your `Organization`, your `Banks` and your `Identities`. For most of your testing and interaction you'll be using the `Bank` API, which is where the majority of APIs reside.

*The complete set of APIs can be found on the following pages:*

| API                                                              | Description                                                 |
|------------------------------------------------------------------|-------------------------------------------------------------|
| [Organization API](https://organization.production.cybrid.app/api/schema/swagger-ui)   | APIs to manage organizations                                |
| [Bank API](https://bank.production.cybrid.app/api/schema/swagger-ui)                   | APIs to manage banks (and all downstream customer activity) |
| [Identities API](https://id.production.cybrid.app/api/schema/swagger-ui)                       | APIs to manage organization and bank identities             |

For questions please contact [Support](mailto:support@cybrid.xyz) at any time for assistance, or contact the [Product Team](mailto:product@cybrid.xyz) for product suggestions.

## Authenticating with the API

The Cybrid Platform uses OAuth 2.0 Bearer Tokens to authenticate requests to the platform. Credentials to create `Organization` and `Bank` tokens can be generated via the [Cybrid Sandbox](https://id.production.cybrid.app). Access tokens can be generated for a `Customer` as well via the [Cybrid IdP](https://id.production.cybrid.app) as well.

An `Organization` access token applies broadly to the whole Organization and all of its `Banks`, whereas, a `Bank` access token is specific to an individual Bank. `Customer` tokens, similarly, are scoped to a specific customer in a bank.

Both `Organization` and `Bank` tokens can be created using the OAuth Client Credential Grant flow. Each Organization and Bank has its own unique `Client ID` and `Secret` that allows for machine-to-machine authentication.

A `Bank` can then generate `Customer` access tokens via API using our [Identities API](https://id.production.cybrid.app/api/schema/swagger-ui).

<font color=\"orange\">**⚠️ Never share your Client ID or Secret publicly or in your source code repository.**</font>

Your `Client ID` and `Secret` can be exchanged for a time-limited `Bearer Token` by interacting with the Cybrid Identity Provider or through interacting with the **Authorize** button in this document.

The following curl command can be used to quickly generate a `Bearer Token` for use in testing the API or demo applications.

```
# Example request when using Bank credentials
curl -X POST https://id.production.cybrid.app/oauth/token -d '{
    \"grant_type\": \"client_credentials\",
    \"client_id\": \"<Your Client ID>\",
    \"client_secret\": \"<Your Secret>\",
    \"scope\": \"banks:read banks:write bank_applications:execute accounts:read accounts:execute counterparties:read counterparties:pii:read counterparties:write counterparties:execute customers:read customers:pii:read customers:write customers:execute prices:read quotes:execute quotes:read trades:execute trades:read transfers:execute transfers:read transfers:write external_bank_accounts:read external_bank_accounts:pii:read external_bank_accounts:write external_bank_accounts:execute external_wallets:read external_wallets:execute workflows:read workflows:execute deposit_addresses:read deposit_addresses:execute deposit_bank_accounts:read deposit_bank_accounts:execute invoices:read invoices:write invoices:execute identity_verifications:read identity_verifications:pii:read identity_verifications:write identity_verifications:execute persona_sessions:execute plans:execute plans:read executions:execute executions:read files:read files:pii:read files:execute\"
  }' -H \"Content-Type: application/json\"

# When using Organization credentials set `scope` to 'organizations:read organizations:write organization_applications:execute banks:read banks:write banks:execute bank_applications:execute users:read users:write users:execute counterparties:read counterparties:pii:read customers:read customers:pii:read accounts:read prices:read quotes:execute quotes:read trades:execute trades:read transfers:read transfers:write transfers:execute external_bank_accounts:read external_bank_accounts:pii:read external_wallets:read workflows:read deposit_addresses:read deposit_bank_accounts:read invoices:read subscriptions:read subscriptions:write subscriptions:execute subscription_events:read subscription_events:execute identity_verifications:read identity_verifications:pii:read identity_verifications:execute persona_sessions:execute plans:execute plans:read executions:execute executions:read files:read files:pii:read files:execute'
```
<font color=\"orange\">**⚠️ Note: The above curl will create a bearer token with full scope access. Delete scopes if you'd like to restrict access.**</font>

## Authentication Scopes

The Cybrid platform supports the use of scopes to control the level of access a token is limited to. Scopes do not grant access to resources; instead, they provide limits, in support of the least privilege principal.

The following scopes are available on the platform and can be requested when generating either an Organization, Bank or Customer token. Generally speaking, the _Read_ scope is required to read and list resources, the _Write_ scope is required to update a resource and the _Execute_ scope is required to create a resource.

| Resource              | Read scope (Token Type)                                    | Write scope (Token Type)                      | Execute scope (Token Type)                       |
|-----------------------|------------------------------------------------------------|-----------------------------------------------|--------------------------------------------------|
| Account               | accounts:read (Organization, Bank, Customer)               |                                               | accounts:execute (Bank, Customer)                |
| Bank                  | banks:read (Organization, Bank)                            | banks:write (Organization, Bank)              | banks:execute (Organization)                     |
| Customer              | customers:read (Organization, Bank, Customer)              | customers:write (Bank, Customer)              | customers:execute (Bank)                         |
| Counterparty          | counterparties:read (Organization, Bank, Customer)         | counterparties:write (Bank, Customer)         | counterparties:execute (Bank)                    |
| Deposit Address       | deposit_addresses:read (Organization, Bank, Customer)      | deposit_addresses:write (Bank, Customer)      | deposit_addresses:execute (Bank, Customer)       |
| External Bank Account | external_bank_accounts:read (Organization, Bank, Customer) | external_bank_accounts:write (Bank, Customer) | external_bank_accounts:execute (Bank, Customer)  |
| External Wallet       | external_wallet:read (Organization, Bank, Customer)        |                                               | external_wallet:execute (Bank, Customer)         |
| Organization          | organizations:read (Organization)                          | organizations:write (Organization)            |                                                  |
| User                  | users:read (Organization)                                  |                                               | users:execute (Organization)                     |
| Price                 | prices:read (Bank, Customer)                               |                                               |                                                  |
| Quote                 | quotes:read (Organization, Bank, Customer)                 |                                               | quotes:execute (Organization, Bank, Customer)    |
| Trade                 | trades:read (Organization, Bank, Customer)                 |                                               | trades:execute (Organization, Bank, Customer)    |
| Transfer              | transfers:read (Organization, Bank, Customer)              |                                               | transfers:execute (Organization, Bank, Customer) |
| Workflow              | workflows:read (Organization, Bank, Customer)              |                                               | workflows:execute (Bank, Customer)               |
| Invoice               | invoices:read (Organization, Bank, Customer)               | invoices:write (Bank, Customer)               | invoices:execute (Bank, Customer)                |

## Available Endpoints

The available APIs for the [Identity](https://id.production.cybrid.app/api/schema/swagger-ui), [Organization](https://organization.production.cybrid.app/api/schema/swagger-ui) and [Bank](https://bank.production.cybrid.app/api/schema/swagger-ui) API services are listed below:

| API Service  | Model                | API Endpoint Path              | Description                                                                                       |
|--------------|----------------------|--------------------------------|---------------------------------------------------------------------------------------------------|
| Identity     | Bank                 | /api/bank_applications         | Create and list banks                                                                             |
| Identity     | CustomerToken        | /api/customer_tokens           | Create customer JWT access tokens                                                                 |
| Identity     | Organization         | /api/organization_applications | Create and list organizations                                                                     |
| Identity     | Organization         | /api/users                     | Create and list organization users                                                                |
| Organization | Organization         | /api/organizations             | APIs to retrieve and update organization name                                                     |
| Bank         | Account              | /api/accounts                  | Create and list accounts, which hold a specific asset for a customers                             |
| Bank         | Asset                | /api/assets                    | Get a list of assets supported by the platform (ex: BTC, ETH)                                     |
| Bank         | Bank                 | /api/banks                     | Create, update and list banks, the parent to customers, accounts, etc                             |
| Bank         | Customer             | /api/customers                 | Create and list customers                                                                         |
| Bank         | Counterparty         | /api/counterparties            | Create and list counterparties                                                                    |
| Bank         | DepositAddress       | /api/deposit_addresses         | Create, get and list deposit addresses                                                            |
| Bank         | ExternalBankAccount  | /api/external_bank_accounts    | Create, get and list external bank accounts, which connect customer bank accounts to the platform |
| Bank         | ExternalWallet       | /api/external_wallets          | Create, get, list and delete external wallets, which connect customer wallets to the platform     |
| Bank         | IdentityVerification | /api/identity_verifications    | Create and list identity verifications, which are performed on customers for KYC                  |
| Bank         | Invoice              | /api/invoices                  | Create, get, cancel and list invoices                                                             |
| Bank         | PaymentInstruction   | /api/payment_instructions      | Create, get and list payment instructions for invoices                                            |
| Bank         | Price                | /api/prices                    | Get the current prices for assets on the platform                                                 |
| Bank         | Quote                | /api/quotes                    | Create and list quotes, which are required to execute trades                                      |
| Bank         | Symbol               | /api/symbols                   | Get a list of symbols supported for trade (ex: BTC-USD)                                           |
| Bank         | Trade                | /api/trades                    | Create and list trades, which buy or sell cryptocurrency                                          |
| Bank         | Transfer             | /api/transfers                 | Create, get and list transfers (e.g., funding, book)                                              |
| Bank         | Workflow             | /api/workflows                 | Create, get and list workflows                                                                    |

## Understanding Object Models & Endpoints

**Organizations**

An `Organization` is meant to represent the organization partnering with Cybrid to use our platform.

An `Organization` typically does not directly interact with `customers`. Instead, an Organization has one or more `banks`, which encompass the financial service offerings of the platform.

**Banks**

A `Bank` is owned by an `Organization` and can be thought of as an environment or container for `customers` and product offerings. Banks are created in either `Sandbox` or `Production` mode, where `Sandbox` is the environment that you would test, prototype and build in prior to moving to `Production`.

An `Organization` can have multiple `banks`, in either `Sandbox` or `Production` environments. A `Sandbox Bank` will be backed by stubbed data and process flows. For instance, funding source transfer processes as well as trades will be simulated rather than performed, however asset prices are representative of real-world values. You have an unlimited amount of simulated fiat currency for testing purposes.

**Customers**

`Customers` represent your banking users on the platform. At present, we offer support for `Individuals` as Customers.

`Customers` must be verified (i.e., KYC'd) in our system before they can play any part on the platform, which means they must have an associated and a passing `Identity Verification`. See the Identity Verifications section for more details on how a customer can be verified.

`Customers` must also have an `Account` to be able to transact, in the desired asset class. See the Accounts APIs for more details on setting up accounts for the customer.



## Overview

This API client was generated by the [OpenAPI Generator](https://openapi-generator.tech) project.  By using the [openapi-spec](https://openapis.org) from a remote server, you can easily generate an API client.

- API version: v0.128.109
- Package version: 0.128.109
- Generator version: 7.21.0
- Build package: `org.openapitools.codegen.languages.RustClientCodegen`

## Installation

Put the package under your project folder in a directory named `cybrid_api_bank` and add the following to `Cargo.toml` under `[dependencies]`:

```
cybrid_api_bank = { path = "./cybrid_api_bank" }
```

## Documentation for API Endpoints

All URIs are relative to *https://bank.sandbox.cybrid.app*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountsApi* | [**create_account**](docs/AccountsApi.md#create_account) | **POST** /api/accounts | Create Account
*AccountsApi* | [**get_account**](docs/AccountsApi.md#get_account) | **GET** /api/accounts/{account_guid} | Get Account
*AccountsApi* | [**list_accounts**](docs/AccountsApi.md#list_accounts) | **GET** /api/accounts | List Accounts
*AssetsApi* | [**list_assets**](docs/AssetsApi.md#list_assets) | **GET** /api/assets | Get assets list
*BanksApi* | [**create_bank**](docs/BanksApi.md#create_bank) | **POST** /api/banks | Create Bank
*BanksApi* | [**get_bank**](docs/BanksApi.md#get_bank) | **GET** /api/banks/{bank_guid} | Get Bank
*BanksApi* | [**list_banks**](docs/BanksApi.md#list_banks) | **GET** /api/banks | Get banks list
*BanksApi* | [**update_bank**](docs/BanksApi.md#update_bank) | **PATCH** /api/banks/{bank_guid} | Patch Bank
*CounterpartiesApi* | [**create_counterparty**](docs/CounterpartiesApi.md#create_counterparty) | **POST** /api/counterparties | Create Counterparty
*CounterpartiesApi* | [**get_counterparty**](docs/CounterpartiesApi.md#get_counterparty) | **GET** /api/counterparties/{counterparty_guid} | Get Counterparty
*CounterpartiesApi* | [**list_counterparties**](docs/CounterpartiesApi.md#list_counterparties) | **GET** /api/counterparties | Get counterparties list
*CustomersApi* | [**create_customer**](docs/CustomersApi.md#create_customer) | **POST** /api/customers | Create Customer
*CustomersApi* | [**get_customer**](docs/CustomersApi.md#get_customer) | **GET** /api/customers/{customer_guid} | Get Customer
*CustomersApi* | [**list_customers**](docs/CustomersApi.md#list_customers) | **GET** /api/customers | Get customers list
*CustomersApi* | [**update_customer**](docs/CustomersApi.md#update_customer) | **PATCH** /api/customers/{customer_guid} | Patch Customer
*DepositAddressesApi* | [**create_deposit_address**](docs/DepositAddressesApi.md#create_deposit_address) | **POST** /api/deposit_addresses | Create Deposit Address
*DepositAddressesApi* | [**get_deposit_address**](docs/DepositAddressesApi.md#get_deposit_address) | **GET** /api/deposit_addresses/{deposit_address_guid} | Get Deposit Address
*DepositAddressesApi* | [**list_deposit_addresses**](docs/DepositAddressesApi.md#list_deposit_addresses) | **GET** /api/deposit_addresses | List Deposit Addresses
*DepositBankAccountsApi* | [**create_deposit_bank_account**](docs/DepositBankAccountsApi.md#create_deposit_bank_account) | **POST** /api/deposit_bank_accounts | Create Deposit Bank Account
*DepositBankAccountsApi* | [**get_deposit_bank_account**](docs/DepositBankAccountsApi.md#get_deposit_bank_account) | **GET** /api/deposit_bank_accounts/{deposit_bank_account_guid} | Get Deposit Bank Account
*DepositBankAccountsApi* | [**list_deposit_bank_accounts**](docs/DepositBankAccountsApi.md#list_deposit_bank_accounts) | **GET** /api/deposit_bank_accounts | List Deposit Bank Accounts
*ExecutionsApi* | [**create_execution**](docs/ExecutionsApi.md#create_execution) | **POST** /api/executions | Create Execution
*ExecutionsApi* | [**get_execution**](docs/ExecutionsApi.md#get_execution) | **GET** /api/executions/{execution_guid} | Get Execution
*ExecutionsApi* | [**list_executions**](docs/ExecutionsApi.md#list_executions) | **GET** /api/executions | Get executions list
*ExternalBankAccountsApi* | [**create_external_bank_account**](docs/ExternalBankAccountsApi.md#create_external_bank_account) | **POST** /api/external_bank_accounts | Create ExternalBankAccount
*ExternalBankAccountsApi* | [**delete_external_bank_account**](docs/ExternalBankAccountsApi.md#delete_external_bank_account) | **DELETE** /api/external_bank_accounts/{external_bank_account_guid} | Delete External Bank Account
*ExternalBankAccountsApi* | [**get_external_bank_account**](docs/ExternalBankAccountsApi.md#get_external_bank_account) | **GET** /api/external_bank_accounts/{external_bank_account_guid} | Get External Bank Account
*ExternalBankAccountsApi* | [**list_external_bank_accounts**](docs/ExternalBankAccountsApi.md#list_external_bank_accounts) | **GET** /api/external_bank_accounts | Get external bank accounts list
*ExternalBankAccountsApi* | [**patch_external_bank_account**](docs/ExternalBankAccountsApi.md#patch_external_bank_account) | **PATCH** /api/external_bank_accounts/{external_bank_account_guid} | Patch ExternalBankAccount
*ExternalWalletsApi* | [**create_external_wallet**](docs/ExternalWalletsApi.md#create_external_wallet) | **POST** /api/external_wallets | Create ExternalWallet
*ExternalWalletsApi* | [**delete_external_wallet**](docs/ExternalWalletsApi.md#delete_external_wallet) | **DELETE** /api/external_wallets/{external_wallet_guid} | Delete External Wallet
*ExternalWalletsApi* | [**get_external_wallet**](docs/ExternalWalletsApi.md#get_external_wallet) | **GET** /api/external_wallets/{external_wallet_guid} | Get External Wallet
*ExternalWalletsApi* | [**list_external_wallets**](docs/ExternalWalletsApi.md#list_external_wallets) | **GET** /api/external_wallets | Get external wallets list
*FilesApi* | [**create_file**](docs/FilesApi.md#create_file) | **POST** /api/files | Create File
*FilesApi* | [**get_file**](docs/FilesApi.md#get_file) | **GET** /api/files/{file_guid} | Get File
*FilesApi* | [**list_files**](docs/FilesApi.md#list_files) | **GET** /api/files | List Files
*IdentityVerificationsApi* | [**create_identity_verification**](docs/IdentityVerificationsApi.md#create_identity_verification) | **POST** /api/identity_verifications | Create Identity Verification
*IdentityVerificationsApi* | [**get_identity_verification**](docs/IdentityVerificationsApi.md#get_identity_verification) | **GET** /api/identity_verifications/{identity_verification_guid} | Get Identity Verification
*IdentityVerificationsApi* | [**list_identity_verifications**](docs/IdentityVerificationsApi.md#list_identity_verifications) | **GET** /api/identity_verifications | List Identity Verifications
*InvoicesApi* | [**cancel_invoice**](docs/InvoicesApi.md#cancel_invoice) | **DELETE** /api/invoices/{invoice_guid} | Cancel Invoice
*InvoicesApi* | [**create_invoice**](docs/InvoicesApi.md#create_invoice) | **POST** /api/invoices | Create Invoice
*InvoicesApi* | [**get_invoice**](docs/InvoicesApi.md#get_invoice) | **GET** /api/invoices/{invoice_guid} | Get Invoice
*InvoicesApi* | [**list_invoices**](docs/InvoicesApi.md#list_invoices) | **GET** /api/invoices | List Invoices
*PaymentInstructionsApi* | [**create_payment_instruction**](docs/PaymentInstructionsApi.md#create_payment_instruction) | **POST** /api/payment_instructions | Create Payment Instruction
*PaymentInstructionsApi* | [**get_payment_instruction**](docs/PaymentInstructionsApi.md#get_payment_instruction) | **GET** /api/payment_instructions/{payment_instruction_guid} | Get Payment Instruction
*PaymentInstructionsApi* | [**list_payment_instructions**](docs/PaymentInstructionsApi.md#list_payment_instructions) | **GET** /api/payment_instructions | List Payment Instructions
*PersonaSessionsApi* | [**create_persona_session**](docs/PersonaSessionsApi.md#create_persona_session) | **POST** /api/persona_sessions | Create Persona Session
*PlansApi* | [**create_plan**](docs/PlansApi.md#create_plan) | **POST** /api/plans | Create Plan
*PlansApi* | [**get_plan**](docs/PlansApi.md#get_plan) | **GET** /api/plans/{plan_guid} | Get Plan
*PlansApi* | [**list_plans**](docs/PlansApi.md#list_plans) | **GET** /api/plans | Get plans list
*PricesApi* | [**list_prices**](docs/PricesApi.md#list_prices) | **GET** /api/prices | Get Price
*QuotesApi* | [**create_quote**](docs/QuotesApi.md#create_quote) | **POST** /api/quotes | Create Quote
*QuotesApi* | [**get_quote**](docs/QuotesApi.md#get_quote) | **GET** /api/quotes/{quote_guid} | Get Quote
*QuotesApi* | [**list_quotes**](docs/QuotesApi.md#list_quotes) | **GET** /api/quotes | Get quotes list
*SymbolsApi* | [**list_symbols**](docs/SymbolsApi.md#list_symbols) | **GET** /api/symbols | Get Symbols list
*TradesApi* | [**create_trade**](docs/TradesApi.md#create_trade) | **POST** /api/trades | Create Trade
*TradesApi* | [**get_trade**](docs/TradesApi.md#get_trade) | **GET** /api/trades/{trade_guid} | Get Trade
*TradesApi* | [**list_trades**](docs/TradesApi.md#list_trades) | **GET** /api/trades | Get trades list
*TransfersApi* | [**create_transfer**](docs/TransfersApi.md#create_transfer) | **POST** /api/transfers | Create Transfer
*TransfersApi* | [**get_transfer**](docs/TransfersApi.md#get_transfer) | **GET** /api/transfers/{transfer_guid} | Get Transfer
*TransfersApi* | [**list_transfers**](docs/TransfersApi.md#list_transfers) | **GET** /api/transfers | Get transfers list
*TransfersApi* | [**update_transfer**](docs/TransfersApi.md#update_transfer) | **PATCH** /api/transfers/{transfer_guid} | Patch Transfer
*WorkflowsApi* | [**create_workflow**](docs/WorkflowsApi.md#create_workflow) | **POST** /api/workflows | Create Workflow
*WorkflowsApi* | [**get_workflow**](docs/WorkflowsApi.md#get_workflow) | **GET** /api/workflows/{workflow_guid} | Get Workflow
*WorkflowsApi* | [**list_workflows**](docs/WorkflowsApi.md#list_workflows) | **GET** /api/workflows | Get workflows list


## Documentation For Models

 - [Account](docs/Account.md)
 - [AccountAssociation](docs/AccountAssociation.md)
 - [AccountList](docs/AccountList.md)
 - [AccountState](docs/AccountState.md)
 - [AccountType](docs/AccountType.md)
 - [ActivityLimit](docs/ActivityLimit.md)
 - [ActivitySide](docs/ActivitySide.md)
 - [ActivityType](docs/ActivityType.md)
 - [Asset](docs/Asset.md)
 - [AssetList](docs/AssetList.md)
 - [AssetTypes](docs/AssetTypes.md)
 - [Bank](docs/Bank.md)
 - [BankFeature](docs/BankFeature.md)
 - [BankList](docs/BankList.md)
 - [BankSupportedPayoutSymbolsInner](docs/BankSupportedPayoutSymbolsInner.md)
 - [BankType](docs/BankType.md)
 - [ComplianceCheck](docs/ComplianceCheck.md)
 - [ComplianceCheckOutcome](docs/ComplianceCheckOutcome.md)
 - [ComplianceCheckType](docs/ComplianceCheckType.md)
 - [ComplianceDecision](docs/ComplianceDecision.md)
 - [ComplianceDecisionState](docs/ComplianceDecisionState.md)
 - [ComplianceDecisionType](docs/ComplianceDecisionType.md)
 - [Counterparty](docs/Counterparty.md)
 - [CounterpartyAddress](docs/CounterpartyAddress.md)
 - [CounterpartyAliasesInner](docs/CounterpartyAliasesInner.md)
 - [CounterpartyList](docs/CounterpartyList.md)
 - [CounterpartyName](docs/CounterpartyName.md)
 - [CounterpartyState](docs/CounterpartyState.md)
 - [CounterpartyType](docs/CounterpartyType.md)
 - [Customer](docs/Customer.md)
 - [CustomerAddress](docs/CustomerAddress.md)
 - [CustomerAliasesInner](docs/CustomerAliasesInner.md)
 - [CustomerList](docs/CustomerList.md)
 - [CustomerName](docs/CustomerName.md)
 - [CustomerState](docs/CustomerState.md)
 - [CustomerType](docs/CustomerType.md)
 - [DepositAddress](docs/DepositAddress.md)
 - [DepositAddressFormat](docs/DepositAddressFormat.md)
 - [DepositAddressList](docs/DepositAddressList.md)
 - [DepositAddressState](docs/DepositAddressState.md)
 - [DepositBankAccount](docs/DepositBankAccount.md)
 - [DepositBankAccountAccountDetailsInner](docs/DepositBankAccountAccountDetailsInner.md)
 - [DepositBankAccountCounterpartyAddress](docs/DepositBankAccountCounterpartyAddress.md)
 - [DepositBankAccountList](docs/DepositBankAccountList.md)
 - [DepositBankAccountRoutingDetailsInner](docs/DepositBankAccountRoutingDetailsInner.md)
 - [DepositBankAccountRoutingNumberType](docs/DepositBankAccountRoutingNumberType.md)
 - [DepositBankAccountState](docs/DepositBankAccountState.md)
 - [ErrorResponse](docs/ErrorResponse.md)
 - [Execution](docs/Execution.md)
 - [ExecutionList](docs/ExecutionList.md)
 - [ExecutionTravelRuleInfo](docs/ExecutionTravelRuleInfo.md)
 - [ExternalBankAccount](docs/ExternalBankAccount.md)
 - [ExternalBankAccountBalances](docs/ExternalBankAccountBalances.md)
 - [ExternalBankAccountKind](docs/ExternalBankAccountKind.md)
 - [ExternalBankAccountList](docs/ExternalBankAccountList.md)
 - [ExternalBankAccountPiiInner](docs/ExternalBankAccountPiiInner.md)
 - [ExternalBankAccountPiiInnerAddressesInner](docs/ExternalBankAccountPiiInnerAddressesInner.md)
 - [ExternalBankAccountPiiInnerRoutingDetailsInner](docs/ExternalBankAccountPiiInnerRoutingDetailsInner.md)
 - [ExternalBankAccountState](docs/ExternalBankAccountState.md)
 - [ExternalWallet](docs/ExternalWallet.md)
 - [ExternalWalletEnvironment](docs/ExternalWalletEnvironment.md)
 - [ExternalWalletList](docs/ExternalWalletList.md)
 - [ExternalWalletState](docs/ExternalWalletState.md)
 - [FeeAssociation](docs/FeeAssociation.md)
 - [FeeDetail](docs/FeeDetail.md)
 - [IdentificationNumber](docs/IdentificationNumber.md)
 - [IdentityVerification](docs/IdentityVerification.md)
 - [IdentityVerificationBusinessAssociate](docs/IdentityVerificationBusinessAssociate.md)
 - [IdentityVerificationDocument](docs/IdentityVerificationDocument.md)
 - [IdentityVerificationDocumentFile](docs/IdentityVerificationDocumentFile.md)
 - [IdentityVerificationDocumentFileMetadata](docs/IdentityVerificationDocumentFileMetadata.md)
 - [IdentityVerificationList](docs/IdentityVerificationList.md)
 - [IdentityVerificationMethod](docs/IdentityVerificationMethod.md)
 - [IdentityVerificationOptions](docs/IdentityVerificationOptions.md)
 - [IdentityVerificationOutcome](docs/IdentityVerificationOutcome.md)
 - [IdentityVerificationPersonaState](docs/IdentityVerificationPersonaState.md)
 - [IdentityVerificationState](docs/IdentityVerificationState.md)
 - [IdentityVerificationType](docs/IdentityVerificationType.md)
 - [IdentityVerificationWithDetails](docs/IdentityVerificationWithDetails.md)
 - [IdentityVerificationWithDetailsPii](docs/IdentityVerificationWithDetailsPii.md)
 - [IdentityVerificationWithDetailsPiiAddress](docs/IdentityVerificationWithDetailsPiiAddress.md)
 - [IdentityVerificationWithDetailsPiiAliasesInner](docs/IdentityVerificationWithDetailsPiiAliasesInner.md)
 - [IdentityVerificationWithDetailsPiiName](docs/IdentityVerificationWithDetailsPiiName.md)
 - [IdentityVerificationWithDetailsPiiRegisteredAddress](docs/IdentityVerificationWithDetailsPiiRegisteredAddress.md)
 - [Invoice](docs/Invoice.md)
 - [InvoiceList](docs/InvoiceList.md)
 - [PatchBank](docs/PatchBank.md)
 - [PatchCustomer](docs/PatchCustomer.md)
 - [PatchExternalBankAccount](docs/PatchExternalBankAccount.md)
 - [PatchTransfer](docs/PatchTransfer.md)
 - [PatchTransferParticipant](docs/PatchTransferParticipant.md)
 - [PaymentInstruction](docs/PaymentInstruction.md)
 - [PaymentInstructionList](docs/PaymentInstructionList.md)
 - [PersonaSession](docs/PersonaSession.md)
 - [Plan](docs/Plan.md)
 - [PlanList](docs/PlanList.md)
 - [PlanTravelRuleInfo](docs/PlanTravelRuleInfo.md)
 - [PlatformFile](docs/PlatformFile.md)
 - [PlatformFileList](docs/PlatformFileList.md)
 - [PostAccount](docs/PostAccount.md)
 - [PostBank](docs/PostBank.md)
 - [PostBankAccountDetails](docs/PostBankAccountDetails.md)
 - [PostCounterparty](docs/PostCounterparty.md)
 - [PostCounterpartyAddress](docs/PostCounterpartyAddress.md)
 - [PostCounterpartyAliasesInner](docs/PostCounterpartyAliasesInner.md)
 - [PostCounterpartyName](docs/PostCounterpartyName.md)
 - [PostCustomer](docs/PostCustomer.md)
 - [PostCustomerAddress](docs/PostCustomerAddress.md)
 - [PostCustomerAliasesInner](docs/PostCustomerAliasesInner.md)
 - [PostCustomerName](docs/PostCustomerName.md)
 - [PostDepositAddress](docs/PostDepositAddress.md)
 - [PostDepositBankAccount](docs/PostDepositBankAccount.md)
 - [PostExecution](docs/PostExecution.md)
 - [PostExternalBankAccount](docs/PostExternalBankAccount.md)
 - [PostExternalBankAccountCounterpartyAddress](docs/PostExternalBankAccountCounterpartyAddress.md)
 - [PostExternalBankAccountCounterpartyBankAccount](docs/PostExternalBankAccountCounterpartyBankAccount.md)
 - [PostExternalBankAccountCounterpartyName](docs/PostExternalBankAccountCounterpartyName.md)
 - [PostExternalWallet](docs/PostExternalWallet.md)
 - [PostFee](docs/PostFee.md)
 - [PostFile](docs/PostFile.md)
 - [PostFileMetadata](docs/PostFileMetadata.md)
 - [PostIdentificationNumber](docs/PostIdentificationNumber.md)
 - [PostIdentityVerification](docs/PostIdentityVerification.md)
 - [PostIdentityVerificationAddress](docs/PostIdentityVerificationAddress.md)
 - [PostIdentityVerificationAliasesInner](docs/PostIdentityVerificationAliasesInner.md)
 - [PostIdentityVerificationName](docs/PostIdentityVerificationName.md)
 - [PostIdentityVerificationRegisteredAddress](docs/PostIdentityVerificationRegisteredAddress.md)
 - [PostInvoice](docs/PostInvoice.md)
 - [PostPaymentInstruction](docs/PostPaymentInstruction.md)
 - [PostPersonaSession](docs/PostPersonaSession.md)
 - [PostPlan](docs/PostPlan.md)
 - [PostPlanDestinationAccount](docs/PostPlanDestinationAccount.md)
 - [PostPlanSourceAccount](docs/PostPlanSourceAccount.md)
 - [PostPlanTravelRuleInfo](docs/PostPlanTravelRuleInfo.md)
 - [PostQuote](docs/PostQuote.md)
 - [PostQuoteEntry](docs/PostQuoteEntry.md)
 - [PostSupportedPayoutSymbols](docs/PostSupportedPayoutSymbols.md)
 - [PostTrade](docs/PostTrade.md)
 - [PostTransfer](docs/PostTransfer.md)
 - [PostTransferParticipant](docs/PostTransferParticipant.md)
 - [PostUltimateBeneficialOwner](docs/PostUltimateBeneficialOwner.md)
 - [PostWorkflow](docs/PostWorkflow.md)
 - [Quote](docs/Quote.md)
 - [QuoteEntry](docs/QuoteEntry.md)
 - [QuoteEntryDestinationAccount](docs/QuoteEntryDestinationAccount.md)
 - [QuoteEntrySourceAccount](docs/QuoteEntrySourceAccount.md)
 - [QuoteList](docs/QuoteList.md)
 - [QuoteSide](docs/QuoteSide.md)
 - [QuoteType](docs/QuoteType.md)
 - [Stage](docs/Stage.md)
 - [SymbolPrice](docs/SymbolPrice.md)
 - [Trade](docs/Trade.md)
 - [TradeFailureCode](docs/TradeFailureCode.md)
 - [TradeList](docs/TradeList.md)
 - [TradeSide](docs/TradeSide.md)
 - [TradeState](docs/TradeState.md)
 - [TradeType](docs/TradeType.md)
 - [Transfer](docs/Transfer.md)
 - [TransferAccountType](docs/TransferAccountType.md)
 - [TransferDestinationAccount](docs/TransferDestinationAccount.md)
 - [TransferEntry](docs/TransferEntry.md)
 - [TransferEntryDestinationAccount](docs/TransferEntryDestinationAccount.md)
 - [TransferFailureCode](docs/TransferFailureCode.md)
 - [TransferHoldDetails](docs/TransferHoldDetails.md)
 - [TransferIdentifiersInner](docs/TransferIdentifiersInner.md)
 - [TransferList](docs/TransferList.md)
 - [TransferParticipant](docs/TransferParticipant.md)
 - [TransferSide](docs/TransferSide.md)
 - [TransferSourceAccount](docs/TransferSourceAccount.md)
 - [TransferState](docs/TransferState.md)
 - [TransferType](docs/TransferType.md)
 - [TravelRuleInfoParty](docs/TravelRuleInfoParty.md)
 - [Workflow](docs/Workflow.md)
 - [WorkflowState](docs/WorkflowState.md)
 - [WorkflowType](docs/WorkflowType.md)
 - [WorkflowWithDetails](docs/WorkflowWithDetails.md)
 - [WorkflowsList](docs/WorkflowsList.md)


To get access to the crate's generated documentation, use:

```
cargo doc --open
```

## Author

support@cybrid.app

