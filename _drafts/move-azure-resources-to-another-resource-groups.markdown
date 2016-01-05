---
layout: post
title: Move Azure resources to another resource groups
---

Now you can move resources to another resource groups, or even subscriptions, for example this way you can merge / demerge billing plans, or just move them to share the same farm.

## Web applications are not fully supported yet
Before we start, let's figure out what we cannot do with web applications. 

If you want to move a web application, at the moment you have 2 options. 

* Move all the resources (farm / app service plan / sites / certificate) to a group not containing another web applications
* Move only the site, pointing to the original farm / app service plan.

What does this mean? If you want to consolidate all your web applications in a single app service plan, you cannot yet.

## Azure PowerShell setup
The PowerShell is needed to manage resources, as it is not avaliable yet, or either the classic or new portal,

Download and install the latest Azure PowerShell from github. https://github.com/Azure/azure-powershell/releases.

Open Azure PowerShell and Add your azure account to be authenticated. You can add as many accounts as you like.
<pre class="language-clike">Add-AzureAccount
</pre>

Once done, switch to the Azure Resource Manager mode.
<pre class="language-clike">Switch-AzureMode AzureResourceManager</pre>

### Moving resources
#### 

