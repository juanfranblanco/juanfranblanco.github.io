---
layout: post
title: Windows 10, Taskbar, Start menu and / or other programs not responding
date: '2015-08-29 12:35:43'
---

Following a restart my Start menu, taskbar and other "modern" applications did not work.  To fix this I found out two options. System file check and Register again all the modern applications, to me it did the trick the last option, but nevertheless I found some corrupted files using the system file check.

###System file check
This will scan for corrupted files in windows and replace them with the original ones.

First we need to run the command with administrative privileges, nothing works at the moment so I have to do it the long way. Normally you should just right click on the windows start button, and the option will appear.

<pre class="language-bash">1. Windows button + R (Run window)
2. Type taskmgr 
3. On task manager, File, Run
4. Type cmd
5. Tick "Create this task with administrative privileges."
</pre>

Once in the command prompt just type.
<pre>sfc /scannow
</pre>

###Registration of modern applications
This will disable development option in windows 10 and register again all the modern applications, this is done via a powershell command, which iterates through all the applications manifest files.

First we need to open the powershell with administrative privileges, this is the long way to do it as nothing works (still after doing the system file check).

<pre class="language-bash">1. Windows button + R (Run window)
2. Type taskmgr 
3. On task manager, File, Run
4. Type powershell
5. Tick "Create this task with administrative privileges."
</pre>

Then we will run this command
<pre class="language-bash">Get-AppXPackage | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppXManifest.xml"}
</pre>

As it iterates through all the applications, these will start working again (at least for me), calendar, sound, cortana, start menu etc.

Very interesting to see that Windows 10 start menu is also a "modern" app (I hate that term), sadly if the sandbox that the applications runs break, it breaks too.

My biggest thank to Jeff Spicer in [this thread](http://answers.microsoft.com/en-us/windows/forum/windows_10-other_settings/windows-10-taskbar-and-start-menu-are-not-working/6c3cc7f9-e040-41cd-ad7c-e7019bd95346?page=2). 