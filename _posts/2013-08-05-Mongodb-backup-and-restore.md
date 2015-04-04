---
layout: post
title: Mongo backup and restore
categories:
- MongoDB

published: true
author: Sukendhar
date: 2013-08-05 05:14:38
---

To take backup of mongodb database

<div class="highlight"><pre><code class="bash"><span class="nv">$ </span>monogodb -db database_name > database_name.bson
</code></pre>
</div>

    
To restore backup file to database

<div class="highlight"><pre><code class="bash"><span class="nv">$ </span>mongorestore -db database_name folder_name
</code></pre>
</div>


Take backup from heroku MongoHQ using heroku-mongo-sync

<div class="highlight"><pre><code class="bash"><span class="nv">$ </span>heroku mongo:pull --app app_name
</code></pre>
</div>

Take backup from heroku MongoHQ from MongoHQ url

<div class="highlight"><pre><code class="bash"><span class="nv">$ </span>mongodump -h hatch.mongohq.com:27021 -d database_name -u admin -p sekret -o ~/tmp/mongodump
</code></pre>
</div>

Restore heroku MongoHQ database with backup 

<div class="highlight"><pre><code class="bash"><span class="nv">$ </span>mongorestore -h hatch.mongohq.com:27021 -d database_name -u admin -p sekret ~/tmp/mongodump/database_name
</code></pre>
</div>

    