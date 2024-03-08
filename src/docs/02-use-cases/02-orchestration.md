---
layout: default
title: Orchestration
permalink: /docs/use-cases/orchestration
---

# Microservice Orchestration and Saga

It is common that some business processes are implemented as multiple microservice calls.
And the implementation must guarantee that all of the calls must eventually succeed even with the occurrence of prolonged downstream service failures.
In some cases, instead of trying to complete the process by retrying for a long time, compensation rollback logic should be executed.
[Saga Pattern](https://microservices.io/patterns/data/saga.html) is one way to standardize on compensation APIs.

Cadence is a perfect fit for such scenarios. It guarantees that :workflow: code eventually completes, has built-in support
for unlimited exponential :activity: retries and simplifies coding of the compensation logic. It also gives full visibility into the state of each :workflow:, in contrast to an orchestration based on queues where getting a current status of each individual request is practically impossible.

Following are some real-world examples of Cadence-based service orchestration scenarios:

 * [Using Cadence workflows to spin up Kubernetes (Banzai Cloud Fork)](https://github.com/edmondop/cadence-helm-chart)
 * [Improving the User Experience with Uber’s Customer Obsession Ticket Routing Workflow and Orchestration Engine](https://eng.uber.com/customer-obsession-ticket-routing-workflow-and-orchestration-engine/)
 * [Enabling Faster Financial Partnership Integrations Using Cadence](https://doordash.engineering/2022/05/18/enabling-faster-financial-partnership-integrations-using-cadence/)
