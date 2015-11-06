---
layout: post
title: "Opening Sublime from Powershell"
date: 2015-11-06 14:23:26 -0500
comments: true
categories: ["environment", "Windows", "PowerShell","Sublime"]
---
Lately I've been setting up my environment on my Windows laptop. What really bothered me is that I was unable to open Sublime directly from Windows Powershell.  Turns out it's not that hard to do! 

So first, open Windows Command Prompt.  Make sure you choose "Run as Administrator" so that you can make the modifications necessary. 

Next, paste the following code into the prompt: 
``` sh
REM Begin Copy
powershell
Set-Content "C:\Program Files\Sublime Text 2\subl.bat" "@echo off"
Add-Content "C:\Program Files\Sublime Text 2\subl.bat" "start sublime_text.exe %1"
if (!($Env:Path.Contains("Sublime"))) {[System.Environment]::SetEnvironmentVariable("PATH", $Env:Path + ";C:\Program Files\Sublime Text 2", "Machine")}
exit
REM End Copy
```

Close the Command Prompt window and restart PowerShell.  Check it out! Now you can use the command `subl` to open Sublime or basic file commands such as `subl .` to open the folder you are currently in in Sublime. 

Happy Coding! 