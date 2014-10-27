---
layout: post
title: "Implementing a Queue with PHP and MongoDB"
date: 2013-03-01 23:51:09 +0800
comments: true
categories: tech
---

And finally, I&#8217;ve decided to release my code for a queue I implemented in PHP and MongoDB. For those who want to look at the code, <a href="https://github.com/laurenceputra/Codeigniter-Mongo-Queue" target="_blank">here</a it is.</p> <p>
  So first, why use MongoDB as a queue?
</p>

<ol>
  <li>
    I already had a distributed cluster of mongodb nodes
  </li>
  <li>
    Single back end server app thingy to reduce complexity of app. Since I had already been using mongodb as my backend datastore, and mongo&#8217;s gridfs as my filesystem, it naturally makes sense for me to continue using mongodb for other parts of the system as well
  </li>
  <li>
    I already had knowledge of mongodb
  </li>
  <li>
    mongodb has a pretty neat feature that actually makes sense to run a queue on (more on that in a bit)
  </li>
</ol>

<p>
  Components of the Queue
</p>

<ol>
  <li>
    A PHP daemon<br />A daemon is basically a long running process that will do stuff, in this case, call on other process to do the job. In the daemon, one of the more important aspects of it would be memory management, to prevent it from spiraling out of control.
  </li>
  <li>
    PHP scripts to do your job<br />The php daemon will essentially call on these scripts to do the job.
  </li>
  <li>
    A mongodb capped collection<br />This is by far in my opinion one of the most amazing aspects of mongodb. They have a collection(table in rdbms) called capped collections that you can actually tail. Yea, the <code>tail -f</code> command in unix. This means that you can literally have a persistent connection with the database, and it&#8217;ll just give you the new documents that have been added to the collection. Note that capped collections have a cap on it&#8217;s size, hence it&#8217;s name, and you cannot delete the entries. It&#8217;ll overwrite the earliest entry in the collection when it is full.
  </li>
</ol>

<p>
  How it works
</p>

<p>
  Basically, there&#8217;s 2 loops to keep the queue process running, the outer loop to recover from db going down, and the inner loop to basically run the queue process. It uses the tail function on capped collections to check for new additions to the table, and will then process each new job that comes in by running the <code>exec</code> function, which basically forks off a new process. This was done to limit memory usage since it&#8217;s a long running php process, and tests done have put it&#8217;s memory consumption at 13MB RAM.
</p>

<p>
  If you&#8217;re using Codeigniter and is considering having a queue that&#8217;s implemented in MongoDB, check it out <a href="https://github.com/laurenceputra/Codeigniter-Mongo-Queue" target="_blank">here</a>!
</p>

<p>
</p>