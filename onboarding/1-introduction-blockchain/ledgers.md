---
title: "Ledgers"
order: 4
description: 
tag: fast-track
---

--> Curtail content

# Ledgers

There are many different ways to look at blockchain technology. 
In order to give you a thorough understanding and a complete view, we do not restrict ourselves to one definition of blockchain but give you multiple throughout this module.


In the OSI network model fashion, one can break down blockchain technology in the following manner:

![Blockchain layers](images/blockchain-layers.png)

A **ledger** is a book or file that records and totals economic transactions.

To better understand ledgers and their relevance for blockchain technology, let us first take a look at transactions and then at ledgers.

## Transaction you say?

A transaction is an **atomic event** which means its components make no sense in isolation. 
If the word transaction conjures up a financial transaction in your mind, this is indeed appropriate.

A single transaction might look like this:

* reduce account A by $10;
* increase account B by $9;
* increase account C by $1.

It is easy to understand that this transaction is a payment.

If you were told only "Reduce account A by $10", you would rightfully ask: "Where did those $10 go?".

That’s what we mean when we say transactions are atomic - It comes from the Greek word for undividable. 
You need every component of the transaction to exist for it to make sense and therefore to take place. 
Otherwise you’re left with the question: "Where did those $10 go?".

Remember when we talked about databases, like SQL? 
If the word *transaction* conjures up an SQL transaction in your mind, this too is appropriate. 
Transactions happen there too.

For instance, technology permitting, a single transaction might look like:

* charge customer for $10;
* ship 1 widget;
* add 1 en-route shipment for customer;
* reduce widget stock by 1.

In the context of blockchain, a transaction is any atomic event that is allowed by the underlying **protocol**.

## How are transactions recorded? 

In blockchain, transactions are recorded as they are proposed by the lottery winner. 

The order of transactions is extremely important here and is one of the reasons why blockchain protocols are designed the way they are.

To better understand the significance of the ledger order, imagine:

* you have an account balance of 3,
* you transfer 3 to member A and 3 to member B in quick succession.

If the ledger is not **well-ordered**, both transactions could be issued even though your account balance would be insufficient. Well-order of execution prevents double-spending.

In order to get a picture of the state of accounts at any point, we have to add up all the transactions until that point. One by one, each transaction record alters the state of the ledger and contains an arbitrary set of data depending on their purpose.

The data recorded by a ledger depends on its structure and purpose. 
For instance, financial ledgers might contain the following data:

* **sender**,
* **recipient**,
* **amount**,
* **credit/debit**,
* **reference**.

This will be important later, so remember that transactions are ultimately well-ordered chunks of data.

Processing each transaction in the ledger enables us to derive all kinds of meta information, such as the number of transactions, activity per account, and individual account balances. 
An account balance, like the balance of your bank account, is an abstract representation of a list of transactions.

![Trusted Authority controls entry to the ledger](images/authority.png)

Traditionally ledgers are maintained by a trusted authority called a **ledger keeper**. 
Ledger keepers include insurance companies, banks, tax collectors, and many other entities. 

Carrying out a transaction entails the following steps:

1. identify yourself to the ledger keeper;
2. request data from the ledger keeper (e.g. about your account balance);
3. request the recording of a new transaction;
4. the ledger keeper will check the validity of the transaction - Is your balance sufficient? Is your account frozen? etc.;
5. the ledger keeper enters the transaction into the ledger and informs other ledger keepers of the transaction if necessary, for example in the case the recipient of your transaction is with another bank;
6. the recipient can now identify themselves with their ledger keeper and ascertain their updated balance.

This system works well as long as ledger keepers can be trusted or mechanisms are in place to ensure the ledger keeper's compliance. 

![Ledger Types -advantages and disadvantages between traditional/centralised ledgers and decentralised ledgers](images/TableLedgerType.png)

The advantages and disadvantages of traditional ledgers compared to decentralised ledgers, for example blockchain, are highly dependent on the degree of centralisation of authority.

In a highly centralised traditional ledger, data reliability, information control, execution of transactions, and consensus about them depend on the trustworthiness of the central authority. 
Participation and transaction execution are restricted by oversight and/or intermediation in centralised ledgers, usually requiring third party involvement.

Further, power asymmetries favouring the central authority can lead to deviant behaviour and/or unintended consequences. 
For example, an authority in charge of updating the ledger could alter it maliciously. 
Centralised "traditional ledgers" are also more prone to be affected by malicious attacks due to their centralised point of failure and data storage compared to distributed ledgers.

On the other hand, distributed ledgers have a higher degree of transparency, security, lower transaction time, and lower transaction costs for participants.

<!-- Additional content about the disadvantages of traditional ledger compared to blockchain -->

<div class="b9-info">
	<p>There is reason to believe that the development of the Bitcoin protocol, the first successful implementation of blockchain technology, was in part motivated by the financial crisis in 2008.</p>
	<p>The financial crisis shook overall trust in traditional financial institutions and mechanisms, including central authorities' functioning and thus raison d'être.</p>
	<p>Blockchain's decentralisation can be seen as a mean to avoid unintended results due to moral hazards and asymmetric information.</p>
</div>

## Blockchain as a distributed ledger

To understand blockchain as a distributed ledger, remember:

* a **transaction** is an atomic event;
* the **blockchain** is the ordered list of all transactions since inception.

Banks, especially, are prone to identify blockchain as a distributed ledger, as it indeed dovetails with their world models. They have quickly seen the utility of distributed ledgers in their universe, both as a threat to their centralised authority and as an opportunity to lower costs and increase transaction time among many other things.

In this view, instead of each bank relying exclusively on their own table of accounts in their own siloed (SQL) databases, blockchain enables them to consolidate their tables of accounts to facilitate transactions between accounts. Without the shared nature of the blockchain, inter-bank transactions are done through netting and settlement via central bank or corresponding accounts. 
The non-blockchain process is more expensive and time-consuming, especially if the banks are located in different countries. 

![Distributed Ledger](images/blockchain_as_a_distributed_ledger.png)

In the elegant blockchain solution, a single transaction updates separate tables of accounts for the entire network, i.e. of all participating banks. For this reason, banks see blockchain as an opportunity to reduce operational costs by distributing a common ledger between their peers.

Let us now revisit the **double-spending problem**.

## Digital currency and the double-spending problem

Traditional currency systems rely on central authorities such as central banks or physical safeguards on banknotes to prevent double-spending and counterfeiting.

![Double-spending: Regular Transaction](images/doublespendingproblem1.png)

Things are different in the digital world. 
Consider the following:

* a malicious Alice sends digital coins to Bob in exchange for goods or services;
* Alice sends the same coins to Charlie in exchange for other goods or services;
* both Bob and Charlie deliver the goods or services, but only one of them will be able to spend the received coins.

![Double-spending Problem: Conflicting Transaction](images/doublespendingproblem2.png)

In earlier digital cash systems, Alice could double-spend if Bob and Charlie were sufficiently unaware of Alice's overall transactions.

In Bitcoin, Alice could double-spend if Bob first delivered the goods, and the Bitcoin network then switches to a fork that does not contain the Alice-to-Bob transaction.

Traditional currency systems have relied in the past on central authorities, such as central banks or physical aspects of coins and banknotes to prevent double-spending problems and counterfeiting.

Double-spending is important for digital tokens because they could theoretically be spent more than once. 
Double-spending refers in the blockchain context to a situation in which **one** token is spent **twice or more** times.

![Double-spending Problem: Transaction via Blockchain](images/doublespendingproblem3.png)

The double-spending problem in blockchain technology should be clearly distinguished from double-spending problems related to duplication and/or falsification. 
These can lead to inflation, currency devaluation, and distrust among currency holders. 
These are more related to digital cash systems and solved with a trusted central authority.