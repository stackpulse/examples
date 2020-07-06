# redis-teams-playbook



## What is it

This is a [StackPulse](https://stackpulse.com) playbook that can be triggered when a monitoring system reports a problem with a REDIS Server / Cluster. The goal of the playbook is to enrich the information provided to the **Site Reliability Engineer** dealing with the incident and to help identify the cause faster.

Among other things, the playbook performs the following steps:

* Retrieve high-level numbers on Connected / Blocked clients
* Retrieve high-levle data on memory consumption, uptime and replication backlog
* Retrieve detailed information about the connected clients
* Investigate "big" keys
* Retrieve and investigate slow queries log



## What does it need to work

In order to use the provided playbook as-is, the [StackPulse](https://stackpulse.com) environment needs to contain the following configuration elements:

* `TEAMS_ALERTS_CONNECTOR` secret should be configured to contain the Microsoft Teams Incoming Webhook Connector URL, as described in the [documentation for Microsoft Teams integration](https://docs.stackpulse.io/getting_started/#microsoft-teams)
* `REDIS_PASSWORD` secret should be configured to contain a password for authenticating to relevant REDIS instances (for retrieving and investigating information)
* `redis-env`  self-hosted SPD should be defined in the system and deployed in an environment where the REDIS instance(s) can be accessed
* `trigger.Scope_PodName` trigger variable is expected to contain a DNS name or an IP address of a REDIS instance for investigation.

Naturally, when using the playbook in your environment, above secrets/variables can be renamed in order to match the existing ones that may already be defined.