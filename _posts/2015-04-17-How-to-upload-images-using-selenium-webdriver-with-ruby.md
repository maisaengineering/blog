---
layout: post
title: How to upload images using Selenium webdriver with ruby
date: 2015-04-17 05:55:55
summary: 
categories: Selenium
author: Sravan Reddy
---

There are different ways to handle file uploads with Selenium Webdriver.

In Ruby, the image cannot be uploaded directly from the system local path. So this can be achieved using AutoIt software.

Following are the steps to achieve this.<br/>
1. First you need to install [AutoIt](https://www.autoitscript.com/site/autoit/downloads/) and [sciTE4AutoIt3](https://www.autoitscript.com/site/autoit-script-editor/downloads/)

It has a customized Lexer for AutoIt3 which handles the Syntax Highlighting.

<p>2. Open the sciTEScript Editor and copy the following code.</p>

```ruby
WinWaitActive("File Upload") 
Send("D:\images\m.jpg")		//Select image path.
ControlClick("","Open", "Button1")
```

Save it as "<b>Test.au3</b>" and run the code using 'F7' key or Click on tools and select the build option.
After running the script, it will automatically create the ".exe" file in same folder. 

For example, if the name of the file is Test.au3, the .exe will be generated with the same name but with .exe extension say "<b>Test.exe</b>".

<p>3. The generated .exe needs to be called in the automation script (Ruby) where the image needs to be uploaded.</p>

Syntax:

```ruby
f = IO.popen("D:/a/web/U/test.exe")
puts f.readlines
```