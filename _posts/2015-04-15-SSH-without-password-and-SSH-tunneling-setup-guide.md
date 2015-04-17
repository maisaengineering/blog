---
layout: post
title: SSH without password and SSH tunneling setup guide
date: 2015-04-17 05:55:55
summary: 
categories: SSH
author: Chandan
---

SSH without password and SSH tunneling setup in 3 steps

<p>1. Create ssh keys on host, or use existing keys if you have them already.</p>

Example: 

```ruby
ssh-keygen -t rsa -C "your_email@example.com"
```
<p>2. Add host pub key to authorized keys entry to all remote hosts(remote 0, remote 1, remote 2, etc)</p>
Example:

```ruby
# a single liner sample
cat ~/.ssh/id_rsa.pub | ssh $REMOTE -t 'mkdir -p ~/.ssh; touch ~/.ssh/authorized_keys; cat >> .ssh/authorized_keys’
```

<p>3. On your host VM, add remote host SSH configurations to: ~/.ssh/config </p>

Example:

```ruby
# these goes into ~/.ssh/config
Host REMOTE1
	Hostname remote1_fullpath
	IdentityFile ~/.ssh/id_rsa
	User chandan

Host REMOTE2
	Hostname remote1_fullpath
	IdentityFile ~/.ssh/id_rsa
	User chandan

Host REMOTE3
	ProxyCommand ssh REMOTE1 -W %h:%p 
	IdentityFile ~/.ssh/id_rsa
```

That’s it. Now you should be able to ssh to remote hosts. Or can do a ssh tunneling as simple as:

```ruby
ssh -fNL 8080:localhost:8080 REMOTE1
```

following tunnels via REMOTE1. See REMOTE3 connection goes via REMOTE1

```ruby
ssh -fNL 8080:localhost:8080 REMOTE3 
```

replace chandan with your ssh user id<br/>REMOTE 1 is a bastion
 
Enjoy!