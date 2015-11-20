---
title: API
layout: rancher-default
---

## externalVolumeEvent

Collection Test Description

​
### Resource Fields

Field | Type | Create | Update | Default | Notes
---|---|---|---|---|---
id | int | - | - | - | The unique identifier for the externalVolumeEvent
kind | string | - | - | - | 
state | enum | - | - | - | The current state of the externalVolumeEvent. The options are [created, creating, removed, removing, requested].
eventType | string | - | - | - | 
externalId | string | - | - | - | 
reportedAccountId | [account]({{site.baseurl}}/rancher/api/account/) | - | - | - | 
volume | [volume]({{site.baseurl}}/rancher/api/volume/) | - | - | - | 
accountId | [account]({{site.baseurl}}/rancher/api/account/) | - | - | - | The unique identifier for the associated account
created | date | - | - | - | The date of when the externalVolumeEvent was created.
transitioning | enum | - | - | - | Whether or not the externalVolumeEvent is in a transitioning state
transitioningMessage | string | - | - | - | The message to show while in a transitioning state
transitioningProgress | int | - | - | - | The percentage remaining in the transitioning process of the externalVolumeEvent
uuid | string | - | - | - | The universally unique identifier for the externalVolumeEvent. This will always be unique across Rancher installations.












​
### Actions

<span class="action">
<span class="header">
remove
<span class="headerright">POST:  <code>${action.remove}</code></span>
</span>
<div class="action-contents">
To remove the externalVolumeEvent
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

