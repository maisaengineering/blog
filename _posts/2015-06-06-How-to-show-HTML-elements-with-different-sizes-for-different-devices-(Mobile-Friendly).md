---
layout:     post
title:      How to show HTML elements with different sizes for different devices (Mobile Friendly)
date:       2015-06-06 05:55:55
summary:    
categories: Html5
author: Sadashiv
---

<p>We can show all HTML elements and screens with different sizes for different types of devices by using  css3  <b>Media Queries Break Points.</b> </p>

<h5>What is Media Query?</h5>
<p>Media Query is a CSS3 module allowing content rendering to adapt to conditions such as screen resolution (e.g. smartphone screen vs. computer screen). It became a W3C recommended standard in June 2012, and is a cornerstone technology of Responsive web design.</p>


<h5>Example:</h5>
<p>Here we are  showing below  300*300px square box in different dimensions according the the device resolution using  <b> Media Queries Break Points.</b>

<p>Default CSS:</p>

```ruby
.squarebox {
	width:300px;
	height:300px;
}
```


<p>Displaying above square box with 200*200px in smart phones view:</p>

```ruby
@media only screen 
and (min-device-width : 320px) 
and (max-device-width : 480px) {
	.squarebox {
		width:200px;
		height:200px;
	}
}
```

<p>Displaying the square box with 450*450px ipads and tablets view:</p>

```ruby
@media only screen 
and (min-device-width : 768px) 
and (max-device-width : 1024px) 
and (orientation : landscape) {
	.squarebox {
		width:450px;
		height:450px;
	}
}
```

<p>Displaying the square box with 800*800px in desktops and laptops view:</p>

```ruby
@media only screen 
and (min-width : 1224px) {
	.squarebox {
		width:800px;
		height:800px;
	}
}
```

<p>Displaying the square box with 1200*1200px in large screens view:</p>

```ruby
@media only screen 
and (min-width : 1824px) {
	.squarebox {
		width:1200px;
		height:1200px;
	}
}
```

<p>Thank you.</p>