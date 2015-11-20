---
title: API
layout: rancher-default
---

## cluster

Collection Test Description

​
### Resource Fields

Field | Type | Create | Update | Default | Notes
---|---|---|---|---|---
id | int | - | - | - | The unique identifier for the cluster
kind | string | - | - | - | 
name | string | Optional | Yes | - | 
state | enum | - | - | - | The current state of the cluster. The options are [activating, active, deactivating, inactive, purged, purging, registering, removed, removing, requested, restoring, updating-active, updating-inactive].
agentState | string | - | - | - | The state of the agent
computeTotal | int | - | - | - | 
discoverySpec | string | - | - | - | 
info | json | - | - | - | 
labels | map[string] | - | Yes | - | 
physicalHostId | [physicalHost]({{site.baseurl}}/rancher/api/physicalHost/) | - | - | - | The unique identifier of the physical host
port | int | Optional | Yes | - | 
accountId | [account]({{site.baseurl}}/rancher/api/account/) | - | - | - | The unique identifier for the associated account
created | date | - | - | - | The date of when the cluster was created.
description | string | Optional | Yes | - | 
removed | date | - | - | - | The date of when the cluster was removed
transitioning | enum | - | - | - | Whether or not the cluster is in a transitioning state
transitioningMessage | string | - | - | - | The message to show while in a transitioning state
transitioningProgress | int | - | - | - | The percentage remaining in the transitioning process of the cluster
uuid | string | - | - | - | The universally unique identifier for the cluster. This will always be unique across Rancher installations.





### Operations



<span class="action">
<span class="header">
Create
<span class="headerright">POST:  <code>${links.self}</code></span>
</span>
<div class="action-contents">
{% highlight json %} 
{

	"description": "string",

	"name": "string",

	"port": 0

} 
{% endhighlight %}
</div>
</span>













<span class="action">
<span class="header">
Update
<span class="headerright">PUT:  <code>${links.self}</code></span>
</span>
<div class="action-contents">
{% highlight json %} 
{

	"description": "string",

	"labels": "map[string]",

	"name": "string",

	"port": 0

} 
{% endhighlight %}
</div>
</span>







<span class="action">
<span class="header">
Delete
<span class="headerright">DELETE:  <code>${links.self}</code></span>
</span>
<div class="action-contents">
{% highlight json %} 
 
{% endhighlight %}
</div>
</span>






​
### Actions

<span class="action">
<span class="header">
activate
<span class="headerright">POST:  <code>${action.activate}</code></span>
</span>
<div class="action-contents">
To activate the cluster
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/host/">host</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
addhost
<span class="headerright">POST:  <code>${action.addhost}</code></span>
</span>
<div class="action-contents">
To addhost the cluster
<br>

<span class="input">
<strong>Input:</strong>​​​ addRemoveClusterHostInput


Field | Type | Required | Default | Notes
---|---|---|---|---
hostId | reference[host] | No | <no value> | The unique identifier for the associated host


<br>
{% highlight json %}{

	"hostId": "reference[host]"

}{% endhighlight %}

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/cluster/">cluster</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
deactivate
<span class="headerright">POST:  <code>${action.deactivate}</code></span>
</span>
<div class="action-contents">
To deactivate the cluster
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/host/">host</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
dockersocket
<span class="headerright">POST:  <code>${action.dockersocket}</code></span>
</span>
<div class="action-contents">
To dockersocket the cluster
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/hostAccess/">hostAccess</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
purge
<span class="headerright">POST:  <code>${action.purge}</code></span>
</span>
<div class="action-contents">
To purge the cluster
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/host/">host</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
remove
<span class="headerright">POST:  <code>${action.remove}</code></span>
</span>
<div class="action-contents">
To remove the cluster
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/host/">host</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
removehost
<span class="headerright">POST:  <code>${action.removehost}</code></span>
</span>
<div class="action-contents">
To removehost the cluster
<br>

<span class="input">
<strong>Input:</strong>​​​ addRemoveClusterHostInput


Field | Type | Required | Default | Notes
---|---|---|---|---
hostId | reference[host] | No | <no value> | The unique identifier for the associated host


<br>
{% highlight json %}{

	"hostId": "reference[host]"

}{% endhighlight %}

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/cluster/">cluster</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
restore
<span class="headerright">POST:  <code>${action.restore}</code></span>
</span>
<div class="action-contents">
To restore the cluster
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/host/">host</a> resource
</span>
</div>
</span>
</span>
</span>

