---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# plugins

The  variable, in Netscape and Mozilla-based browsers, lists the plugins installed on the browser.


<!-- 

plugins.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  p  | Recognized plugins  | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Windows Media Player Plug-in Dynamic Link Library;Microsoft® DRM;  | Traffic > Technology > Plugins  |
