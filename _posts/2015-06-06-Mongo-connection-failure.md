---
layout:     post
title:      Mongo connection failure
date:       2015-06-06 05:55:55
summary:    
categories: MongoDB
author: Sukendhar
---

If connection failed during mongo start:

Follow these steps:

	$ sudo rm /var/lib/mongodb/mongod.lock
	$ mongod --repair
	$ sudo start mongodb
	$ sudo status mongodb
	$ mongo

connection established message will be displayed.