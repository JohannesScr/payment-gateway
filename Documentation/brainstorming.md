# Payment Gateway Brainstorming
### Documentation Standards
- max line length is 80 characters
### List of Definitions
- *Collections*: Monetary terms collected from a third-party
- *Payments*: Monetary terms payed out to a third-party
- *Allocations*: Payments that are to be mapped a different transaction 
definition

### List of Tools
- *[StarUML](http://staruml.io/)*
- *[Sketch](https://www.sketchapp.com/)*
- *PostgreSQL*
- *Node.js*
- *Kafka*
- *Nats*

### List of Diagrams
- Debit Order Engine: `../UML/debit_order.mdj`
- Payment Gateway Engine: `../UML/debit_order.mdj`

### List of Sketch Diagrams
- Debit Order Web App: `../Sketch/debit_order.sketch`

- - -
## Introduction
### Background
The Payment Gateway (PGW) is a collection of micro services that do the 
following tasks:
- Payment Processing (Debit Orders and Payouts)
- Credit Card Processing
- Account Management
- Scheduling of Collections and Payments 
- Notifications Services

### Allocation of Responsibilities
#### Payment Gateway
The Payment Gateway is an App that is the general interface for any kind/form 
of processing. All the other micro services are stand alone Engines/Services
that manage themselves. Applications only communicate with the Payment Gateway.

The Payment Gateway manages:
- request validation
- file uploads
- un-managed requests
- account integrity
- reporting
    - dashboard
        - operational
        - 
    - transaction monitoring
    - transaction history
    - statements
- process restarting and tracking

#### Accounting Services
The accounting service manages
- fee management
- invoicing
- statements
- transaction mapping
- payment routing 
    - payment in (request/response) -> trigger logic -> payment out (request)

#### Scheduler Engine
The Scheduler Engine manages
- managed and un-managed payments
    - once-off payments and/or collections
    - scheduling  over a period of time
        - number of repetitions
        - running balance
        - indefinite frequency
- process restarting and tracking

#### Payment Processing Engine
The Payment Processing Engine manages
- during processing
    - transaction management
    - transaction monitoring
    - transaction allocation
- allocation
- payment splitting
- payment roll-up
- payment routing 
- process restarting and tracking


- - -
### IDEAS
- accounting management (incl. mapping process)
- fee management
- invoicing
- statements
- email/sms/push notifications
- payment processing
- reporting
    - dashboard
        - operational
        - 
    - transaction monitoringj
    - transaction history
    - statements
- managed and un-managed payments
    - once-off payments and/or collections
    - scheduling  over a period of time
        - number of repetitions
        - running balance
        - indefinite frequency
- payment exception management
- during processing
    - transaction management
    - transaction monitoring
    - transaction allocation
- allocation
- payment splitting
- payment roll-up
- payment routing 
    - payment in (request/response) -> trigger logic -> payment out (request)
- process restarting and tracking





