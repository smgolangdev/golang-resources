New Tools 
=========
### Charting tools

 1. [Fnordmetric](http://fnordmetric.io/) - FnordMetric allows you to write SQL queries that return SVG charts rather than tables. Turning a query result into a chart is literally one line of code.
 2. [MetricsGraphicsjs](http://metricsgraphicsjs.org/) - is a library built on top of D3 that is optimized for visualizing and laying out time-series data. It provides a simple way to produce common types of graphics in a principled, consistent and responsive way. The library currently supports line charts, scatterplots and histograms as well as features like rug plots and basic linear regression.

###New Programming Languages

 1. [Red](http://www.red-lang.org/) programming language
 2. [Duck](http://ducklang.org/) a simple scripting language based on the idea of duck-typing (or dynamic typing).
 
 ### Golang Libraries
 1.  [Topo](https://github.com/mdmarek/topo) A library to create in process topologies of goroutines connected by channels.
 2. [Consul](https://consul.io/) - Consul makes it simple for services to register themselves and to discover other services via a DNS or HTTP interface. Register external services such as SaaS providers as well. 

### Linux Containers
1. [Systemd for admins](http://0pointer.net/blog/systemd-for-administrators-part-xxi.html)
2. Getting Started With Docker - [Deploying ownCloud](http://dischord.org/blog/2013/07/10/docker-and-owncloud/)
3. Easiest way to install latest version of Docker. Run the following script.
```shell
 $ curl -sSL https://get.docker.com/ubuntu/ | sudo sh
```
4. [Getting Started with Java Development on Docker](http://blog.giantswarm.io/getting-started-with-java-development-on-docker?utm_source=Docker+News&utm_campaign=3432c436f6-Docker_Weekly_November_12th_201411_11_2014&utm_medium=email&utm_term=0_c0995b6e8f-3432c436f6-235885441)
5. [Using Docker in your development environment.](http://goodcode.io/blog/docker-in-development-environment/?utm_source=Docker+News&utm_campaign=3432c436f6-Docker_Weekly_November_12th_201411_11_2014&utm_medium=email&utm_term=0_c0995b6e8f-3432c436f6-235885441)
6. [A Docker development environment in 24 hours](https://blog.relateiq.com/a-docker-dev-environment-in-24-hours-part-2-of-2/)
7. [Running Netbeans on Docker](https://github.com/fgrehm/docker-netbeans)
8. Docker powered mini Heroku - [Dokku](https://github.com/progrium/dokku)


###Golang Libraries
1. [Bleve](http://www.blevesearch.com/) A modern text indexing library in Go.

###Python Libraries
1. [Online Python tutor](http://pythontutor.com/)
2. [Redis Python Datastructures](https://github.com/lethain/Redis-Python-Datastructures)
###Miscellenous
1. [Humans should learn maths](http://scattered-thoughts.net/blog/2014/11/15/humans-should-learn-maths/)
2. [Bash scripting guide](http://guide.bash.academy/)

###Scalability Resources
- First of all, motivate yourself by watching this tutorial using [nodejs + nginx + applying static caching + load balancing + testing, all this in 7 minutes](https://www.youtube.com/watch?v=FJrs0Ar9asY).
- Add these words and their meaning to your vocabulary: [scalability](http://en.wikipedia.org/wiki/Scalability), [failover](http://en.wikipedia.org/wiki/Fault_tolerance), single point of failure (SPOF), sharding, replication and load balancing; even if you don’t understand them completely.
- In order to have a general overview and the reasons/whys about scalable systems, I strongly recommend you to read [Scalable Web Architecture and Distributed Systems.](http://aosabook.org/en/distsys.html) This is a great introduction.
- After you get the general idea you can move on to understand how to use a load balancer and what decisions and problems you will face. And then you can try to run a haproxy and make it not a single point of failure too.
- Dare yourself to [serve 3 million requests per second](http://dak1n1.com/blog/10-3-million-http-cluster) but for this task you’ll need to [generate 3 million requests](http://dak1n1.com/blog/14-http-load-generate), [fine tune your web server](http://dak1n1.com/blog/12-nginx-performance-tuning) and finally [scale and test it](http://dak1n1.com/blog/13-load-balancing-lvs).
- Your application is already scalable, now you need to scale your databases. They are very important part of your application, here I recommend you to read at least how MongoDB scales with sharding and replication and Cassandra with its almost linear scalability and the ease of adding nodes to the cluster.
- Since your application and database are scalable and fault tolerant, it’s good to [save your servers unnecessary workload](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching?hl=en) and also make the responses to the user faster. Learn that a good request is the one that never reached the “real server”.
- Let’s assume we’re deploying the whole infrastructure within a single data center, now we have another SPOF. Since all servers are in the same space, some natural disaster might happen or even the simple power outages. Good news is that Cassandra have support to multiple data center out of the box and you can see how google face this issue. If your user is on Brazil, don’t make him travel longer than he needs and remember even with the best situation we still have latency.

**Good questions to test your knowledge:**

Why to scale? how people do that usually?
How to deal with user session on memory RAM with N servers? how LB know which server is up? how LB knows which server to send the request?
Isn’t LB another SPOF? how can we provide a failover for LB?
Isn’t my OS limited by 64K ports? is linux capable of doing that out of the box?
How does mongo solves failover and high scalability? how about cassandra? how cassandra does sharding when a new node come to the cluster?
What is cache lock? What caching policies should I use?
How can a single domain have multiple IP addresses (ex: $ host www.google.com)? What is BGP? How can we use DNS or BGP to serve geographically users?
Bonus round: sometimes simple things can achieve your goals of making even an AB test.

####See Also
[A Flock Of Tasty Sources On How To Start Learning High Scalability](http://highscalability.com/blog/2014/11/24/a-flock-of-tasty-sources-on-how-to-start-learning-high-scala.html)