---
layout: post
title: Creating your Ghost blog in Azure
date: '2015-08-26 16:58:15'
---

This guide will cover the steps I have followed to create this blog in Azure.

* Azure Installation of Ghost using One click deployment button
* Domain name configuration
* New theme installation
* More resources

### Background 
After lots of consideration I have chosen Ghost, as opposed to Blogger, Wordpress or even Orchard (Asp.net blogs) as it is simple, have nice templates, and is easy to modify.

## Azure Installation of Ghost using the One click deployment button

* Go to the [Ghost Azure branch in Github](https://github.com/AzureWebApps/Ghost-Azure)
* Click the deploy to Azure button ![Azure Deploy button](https://camo.githubusercontent.com/9285dd3998997a0835869065bb15e5d500475034/687474703a2f2f617a7572656465706c6f792e6e65742f6465706c6f79627574746f6e2e706e67)
* Enter your site details
![](/content/images/2015/09/ghost-deploy.PNG)
* Click next and after a few minutes your site will be installed and deployed.
* Finally go to your **yoursitename.azurewebsites.net/admin** to configure your site.

## Domain name configuration

If your website SKU is at least Shared allows you to point your domain to it.

* In your domain register you will need to add a **CNAME** record pointing to **yourwebsitename.azurewebsites.net**, for example [this is how you do it in 1&1](http://help.1and1.com/domains-c36931/manage-domains-c79822/dns-c37586/enter-a-cname-record-for-your-domain-a643600.html). 

Adding a CNAME record will allow you to verify with Azure that you own your domain, and create a redirection.

* Afterwards on the new portal, go to settings and select custom domains and SSL
![Select custom domains in azure](/content/images/2015/09/ghost-domain-1.PNG)
* Select bring external domains
* Finally add your domain.

## New theme installation
This will demonstrate how add the [Ghostium theme from Github](https://github.com/oswaldoacauan/ghostium) to your Ghost blog, there are plenty other free themes in Github, so if you prefer another theme, the installation will be the same.

* Open the console in Azure portal
* Navigate to themes 
<pre>    cd content/themes </pre>
* Clone the theme from github
<pre>    git clone https://github.com/oswaldoacauan/ghostium/ "ghostium"</pre>
![Using the console to clone a github repository](/content/images/2015/09/ghost-addthemeghostium.PNG)
### Configure the theme
To configure the [options of Ghostium as per Github](https://github.com/oswaldoacauan/ghostium), you can use use Visual Studio online.

* First enable visual studio in the configuration options in the classic portal
![Enable Visual Studio online in Azure Portal](/content/images/2015/09/ghost-enableconfigurationvs.PNG)
* Then from the dashboard in the classic launch it to edit the files.
## More resources
[Ghost for beginners](https://www.ghostforbeginners.com/) is a great place to get started on Markdown syntax to write your posts, and other general information on how to manage your ghost blog / site.
