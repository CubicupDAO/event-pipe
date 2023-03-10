# Feature List

## Functional Requirement

- chain types: tendermint,...
- event types: contract/module
  * related to NFT
  * block, transaction data
- dynamic configuration
- subscription changes through API
- MQ broadcast
- logging
- monitor metrics
- database persistence: optional
- common event data structure, event encoding/decoding RLP/BCS
- contract and its metadata
- listener/worker pattern
- same data structure and encoding for worker output
- more subtle filter and critia condition for subscription
- reduce costs instead of increasing fees;
- graphQL/API query
- local state rollback when  chain is forked
- event: confirmed/unconfirmed

## Non-functional Requirement

- Highly Available 
- Resilient
- Fork Tolerance(fork event)

# High-Level Design

## Introduction

This document outlines a high-level design solution for blockchain event subscription. Our solution will include the following components:

- A Subscription API
- Database Persistence
- Message Queue Broadcast

## Subscription API

Our subscription API will allow clients to subscribe to specific blockchain events. The API will expose endpoints to register and manage subscriptions. Clients can register to receive notifications when specific events occur on the blockchain. The API will also provide endpoints to manage client subscriptions, such as updating or deleting subscriptions.

## Database Persistence

We will use a database to persist subscription data. The database will store subscription details such as the client ID, the event type, and the notification endpoint. The database will also store metadata about the blockchain events, such as the event ID and timestamp.

## Message Queue Broadcast

When a blockchain event occurs, our system will broadcast a message to a message queue. The message queue will then distribute the message to all subscribed clients. We will use a message queue to ensure that notifications are delivered reliably and efficiently.
