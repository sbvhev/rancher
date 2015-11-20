---
title: API
layout: rancher-default
---

## externalDnsEvent

Collection Test Description

​
### Resource Fields

Field | Type | Create | Update | Default | Notes
---|---|---|---|---|---
id | int | - | - | - | The unique identifier for the externalDnsEvent
kind | string | - | - | - | 
state | enum | - | - | - | The current state of the externalDnsEvent. The options are [created, creating, removed, removing, requested].
eventType | string | - | - | - | 
externalId | string | - | - | - | 
fqdn | string | - | - | - | The fqdn of a service when the [Route 53 DNS service]({{site.baseurl}}/rancher/rancher-services/dns-service/) has started. The format will be `<serviceName>.<stackName>.<environmentName>.<yourHostedZoneName>`.
reportedAccountId | [account]({{site.baseurl}}/rancher/api/account/) | - | - | - | 
serviceName | string | - | - | - | 
stackName | string | - | - | - | 
accountId | [account]({{site.baseurl}}/rancher/api/account/) | - | - | - | The unique identifier for the associated account
created | date | - | - | - | The date of when the externalDnsEvent was created.
transitioning | enum | - | - | - | Whether or not the externalDnsEvent is in a transitioning state
transitioningMessage | string | - | - | - | The message to show while in a transitioning state
transitioningProgress | int | - | - | - | The percentage remaining in the transitioning process of the externalDnsEvent
uuid | string | - | - | - | The universally unique identifier for the externalDnsEvent. This will always be unique across Rancher installations.












​
### Actions

<span class="action">
<span class="header">
remove
<span class="headerright">POST:  <code>${action.remove}</code></span>
</span>
<div class="action-contents">
To remove the externalDnsEvent
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/externalEvent/">externalEvent</a> resource
</span>
</div>
</span>
</span>
</span>

