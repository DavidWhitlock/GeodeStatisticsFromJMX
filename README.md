# Geode Statistics From JMX

Periodically captures numeric and boolean attributes of JMX MBeans using the statistics facilities of Apache Geode.

## Why is this useful?

One of my favorite of features of Apache Geode is its ability to gather statistics about the internals of the distributed object cache and the environment in which the Geode node runs (JVM, host operating system, etc.).  Statistics are periodically harevested and persisted to a space-efficient binary file on disk.  GemStone's VSD tool can then be used to visualize the statistics and correlate trends across multiple statistics.

Geode statitics are great, but they are implemented using Geode-specific APIs.  JMX offers a standard API for expressing statistics and other diagnostic information and operations.  This project aims to marry the two to provide periodic harvesting of numeric and boolean attributes of JMX MBeans (which can then be visualized and manipulated in VSD).

There are other tools and technologies that provide insight into the internals of Java applications.  In particular, the Java Flight Recorder (JFR) that is part of Java Misson Control.  JFR is awesome, but it has some downsides: it can only be used in production with the Oracle JVM (and not OpenJDK) under a commercial license.  More importantly, JFR doesn't appear to have tools for correlating statistics across multiple JVMs which is essential when measuring in a distributed environment (e.g., microservices).  In a distributed environment, Geode statistics captured for multiple JVMs can be loaded into a single VSD environment.  Assuming that timestamps are consistent across JVMs (which can be a big assumption -- I don't remember if VSD helps with that or not), then statistics can be correlated across JVMs.

## How do I use this?

## How does this work, exactly?
