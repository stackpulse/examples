# ssh-slack-playbook



## What is it

This is a [StackPulse](https://stackpulse.com) playbook that can be triggered when a monitoring system reports a problem with a  virtual (or physical) machine. The playbook executes remote SSH commands on the machine(s) and communicates with **Site Reliability Engineers** via Slack. 

This playbook implements interactive process, asking a human *SRE* via Slack to approve performing additional investigative actions on the machine.



## What does it need to work

In order to use the provided playbook as-is, the [StackPulse](https://stackpulse.com) environment needs to contain the following configuration elements:

* `SSH_KEY` secret should be configured to contain the SSH Key allowing to connect to the relevant SSH servers (virtual or physical machines)
* `SlackEnv` a Slack integration that needs to be defined, according to the [StackPulse Documentation](https://docs.stackpulse.io/getting_started/#step-3-configure-a-new-slack-integration) 
* `trigger.Scope_PodName` trigger variable is expected to contain a DNS name or an IP address of a relevant SSH server
* `private-env`  self-hosted SPD should be defined in the system and deployed in an environment where the SSH Server(s) can be accessed

The playbook currently contains a default _ec2-user_ user name for the connection. This should be modified for usage in specific environments.

Naturally, when using the playbook in your environment, above secrets/variables can be renamed in order to match the existing ones that may already be defined.