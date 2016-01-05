---
layout: post
title: Solidity contracts in Visual Studio Code
date: '2015-11-25 04:49:04'
---

After the recent release of [Visual Studio Code beta](https://code.visualstudio.com/), and its support for extensions, I decided to add support for the Ethereum Solidity smart contract language.

I started the extension using as a template the Javascript language, but I soon realised about the support for TextMate, which lead me to easily reuse the original created by David Krmpotic and Ralph Pichler for Sublime. https://github.com/davidhq/SublimeEthereum

But Visual Studio code can do much more, if we look at how the Javascript editor together with TypeScript, it can support debugging, type completion and checking. It will be great if we could add similar features for Solidity smart contracts in the future.

### How does it look like?
![Solidity using Visual Studio Code](/content/images/2015/11/SolidityExample.PNG)

### How to install it

* Install [Visual Studio Code](https://code.visualstudio.com/)
* Press Ctrl + P and type "ext install ". Note: The trailing space.
* Type "Solidity", click in the extension and you are done.

![](/content/images/2015/11/extinstall.png)

### How to create your own extension or contribute to this one.
Here are some resources to get you started, please feel free to submit any issues and pull requests on github to enhance this one.

* [Visual Studio Code Extension Tutorial](https://code.visualstudio.com/docs/extensions/example-hello-world)

* [Visual Studio Code Ethereum Solidity Extension in Github](https://github.com/juanfranblanco/vscode-solidity)