---
layout: post
title: Capturing "CAPTCHA" in Selenium IDE by INPUT BOX method
date: 2015-04-15 05:55:55
summary: 
categories: Selenium
author: Sailaja T
---


<p>If you are automating the app registration using Selenium IDE that contains captchas, record and replay would not work because the captchas would change every time new user registers into the application. </p>

<p>This can be achieved by using <b>storeEval</b> command. The execution of the automation script stops at that point, waits for the manual entry of code and it resumes execution of subsequent commands.</p>

<img src="/images/selenium_captcha.png"/>

<b>Source code:</b>

```ruby

<tr>
	<td>storeEval</td>
	<td>prompt(&quot;Please enter captcha&quot;);</td>
	<td>captcha</td>
</tr>
<tr>
	<td>type</td>
	<td>//*[@id='hip']</td>
	<td>${captcha}</td>
</tr>

```

<br/>