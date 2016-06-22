---
title: example template of a feature or scenario writeup
author:  jianyunt
---

>Note: provide a proposed descriptive title and a brief description

## PackageManagement (aka. OneGet) Improvements ##
There were some user experience gaps in the WMF 5.0 listed below. These are got improved in the 5.1. 

- **version** Alias


  Issue: Assuming you have version 1.0 and 2.0 of a package, P1, installed on your system, and you want to uninstall version 1.0, you can do "uninstall-package -name P1 -version 1.0" .   You expect version 1 is uninstalled after running the cmdlet. However the result is that the version 2.0 gets uninstalled. 
	
	Reason: The version is the alias of the minimumversion. When OneGet is looking for a qualitied package (in this case miniversion is 1.0), It finds the latest version. This  behavior is correct under normal case because finding the latest version is mostly what people want. But not in this case.
	
	Solution:removing -version alias entirely in OneGet and PowerShellGet. 
	
Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.

- **Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.
- **Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.

>Note: additional detail covering new concepts, implementation, examples, etc should be linked to the canonical technical documentation

**Learn more about using PowerShell Editions**
- [Determine running edition of PowerShell]()
- [Declare a module's compatibility to specific PowerShell versions]()
- [Filter Get-Module results by CompatiblePSEditions]()
- [Prevent script execution unless run on a comaptible edition of PowerShell]()
