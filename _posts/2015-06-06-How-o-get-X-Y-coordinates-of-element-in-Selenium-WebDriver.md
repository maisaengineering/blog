---
layout: post
title: How to get X Y coordinates of element in Selenium WebDriver
date: 2015-06-06 05:55:56
summary: 
categories: Selenium
author: Sravan Reddy
---

Any web element has Its own position on page and generally it is measured In x and y pixels and known as x y coordinates of element. X pixels means horizontal position on page from left side and Y pixels means vertical position on page from top side. You can find x y coordinates of any element.

In selenium webdriver, You can get x y coordinates of element using Point class. I have created simple example to demonstrate you how to get x y coordinates of any Image on page.

```ruby
@Test
 public void getCoordinates() throws Exception {
  //Locate element for which you wants to retrieve x y coordinates.
       WebElement Image = driver.findElement(By.xpath("//img[@border='0']"));
       //Used points class to get x and y coordinates of element.
        Point classname = Image.getLocation();
        int xcordi = classname.getX();
        System.out.println("Element's Position from left side"+xcordi +" pixels.");
        int ycordi = classname.getY();
        System.out.println("Element's Position from top"+ycordi +" pixels.");
 }
}
```

Results will be displayed in console panel.

This way you can find x y coordinates of any element In selenium test and use It whenever required. This thing can help you to perform pixel to pixel testing using selenium webdriver.

<b>How to get element size in Selenium WebDriver</b>

Now let us learn how to get size of element. I have prepared a simple example to explain how to get height and width of Image In selenium webdriver.see In bellow example, I have used getSize() method to get height and width of element.

```ruby
@Test
 public void getSize() throws Exception {
  //Locate element for which you wants to get height and width.
        WebElement Image = driver.findElement(By.xpath("//img[@border='0']"));
        
        //Get width of element.
        int ImageWidth = Image.getSize().getWidth();
        System.out.println("Image width Is "+ImageWidth+" pixels");
        
        //Get height of element.
        int ImageHeight = Image.getSize().getHeight();        
        System.out.println("Image height Is "+ImageHeight+" pixels");
 }
}
```
Results will be displayed in console panel.


