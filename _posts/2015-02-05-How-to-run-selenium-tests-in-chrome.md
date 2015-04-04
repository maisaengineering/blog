---
layout: post
title: How to run selenium tests in chrome
date: 2015-02-05 05:55:55
summary: 
categories: Selenium
author: Sukendhar
---

Before starting, we'll need to download the latest ChromeDriver binary executable. Once we have it, we'll need to tell Selenium where it is.

Add it to the System PATH
or
Specify it in the Selenium setup
or
Launch ChromeDriver and connect to it via Selenium Remote

Create one file as chrome.rb

```ruby
require 'selenium-webdriver'
require 'rspec/expectations'
include RSpec::Matchers

def setup
  Selenium::WebDriver::Chrome::Service.executable_path = File.join(Dir.pwd, 'chromedriver')
  @driver = Selenium::WebDriver.for :chrome
end

def teardown
  @driver.quit
end

def run
  setup
  yield
  teardown
end
```

Notice that in <b>setup</b> we are telling Selenium where the ChromeDriver exectuable is with <b>executable_path</b> before instantiating the browser.

Now add a simple test to chrome.rb

```ruby
run do
  @driver.get 'http://example.com/'
  expect(@driver.title).to eql 'The Internet'
end
```

If we save this file and run it (e.g., ruby chrome.rb) it will launch an instance of Chrome.

Now run your test cases.