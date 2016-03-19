## GemFire-Resource-Hunter


Is a tool that will spelunk memory, and other resources inside of 

GemFire. This is not a unheard of concept, but there are a few wrinkles. 

This tool is comprised on a few mechanisims. 

It uses a Java Jar to interact with GemFire - Since GemFire is written in Java.

As we all know, Java has some intersting use cases. I'm not a Java hater, but more of a polygot mindset. I'll step off my soapbox now. 

I've decided to use Erlang to interact with Java - there is a niffy library included in Erlang called the Jinterface. 

This allows me to interact with Java and be nice to the JVM while taking advantage of Erlang's internal messaging framework. 

Which gives me an advantage when it comes to scaling workloads, requests, threads, etc. 

Earlangs library allows for 1 to 1 thread management between Java and Erlang. So, there's no need to worry about beating up the JVM. 

The Erlang Caller will be housed as a micro-service, again leveraging framework in order to deal with discovery, event driven requests. 

The API and Microservices will use LepTus which use cowboy, jiffy, and msgpack

Setting up:

1. Java runtime 8
2. Latest Erlang build
3. JavaErlang library http://babel.ls.fi.upm.es/~fred/JavaErlang/downloads.html

Erlang docs are located here http://www.erlang.org/
  	
Using Erlang to call Java - 

erl -sname "instance name"
{ok,NodeId} = java:start_node().

Erlang creates java processes and calls them nodes. 

Similar to how Erlang communicates internally.

This allow natural distributed programming. 



