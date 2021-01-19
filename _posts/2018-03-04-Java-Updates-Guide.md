---
layout: post
title: Java Updates Guide
---



This page aims to tell and keep a log about updates in Java. Java is adopting a new cadence-based release cycle of the new releases and versions, and if you haven’t caught up yet – this is a good place to start. You can come back after each release to read and know more about it.

**Last update: 2020.09.16** *

## A word about the new Release Cycle

Now, a Java version arrives every six months, and this speeds up the development of Java. It is a good idea on its own but can confuse people that got used to waiting for a new Java version to be released after years and not six months. 
We’re also more expected to see new types of features labeled Preview, Incubating, and Experimental and an LTS versions will be released each three years.

## Java 9, 21 September 2017

Java 9 features [81 JEPs](https://openjdk.java.net/projects/jdk9/).

- The [Module System](https://openjdk.java.net/jeps/261) (aka Project Jigsaw) 
- [Variable Handles](https://openjdk.java.net/jeps/193) – equivalents of `java.util.concurrent.atomic` and `sun.misc.Unsafe` operations upon object fields and array elements

- [JShell](https://openjdk.java.net/jeps/222) – a dedicated REPL
- [G1](https://openjdk.java.net/jeps/248) – make G1 the default garbage collector on 32- and 64-bit server configurations
- [Stalk-Walking API](https://openjdk.java.net/jeps/259) – provide an API to access lazily the information in stack traces
- [Convenience Factory Methods for Collections](https://openjdk.java.net/jeps/269) – collections can be now initialized using `of()` methods

## Java 10, 20 March 2018

Java 10 features [12 JEPs](https://openjdk.java.net/projects/jdk/10/) and various small API additions.

- First one to be released under the new release cycle
-  [Local-Variable Type Inference (var)](https://openjdk.java.net/jeps/286) – enhance the language to extend type inference to declarations of local variables with initializers
-  [Garbage Collector interface](https://openjdk.java.net/jeps/304) – improve the source code isolation of different GCs by introducing a clean GC interface
- [Parallel Full GC for G1](https://openjdk.java.net/jeps/307) – improve G1 worst-case latencies by making the full GC parallel
- [Application Class-Data Sharing ("CDS")](https://openjdk.java.net/jeps/310) – improve startup and footprint, extend the existing CDS feature to allow application classes to be placed in the shared archive.
- Collectors to be used with unmodifiable collections

## Java 11, 25 September 2018

Java 11 is the first LTS release and includes [17 JEPs](https://openjdk.java.net/projects/jdk/11/).

- [HTTP Client](https://openjdk.java.net/jeps/321) – standardize the incubated HTTP Client API introduced in Java 9, and updated in Java 10
- [Flight Recorder](https://openjdk.java.net/jeps/328) – provide a low-overhead data collection framework for troubleshooting Java applications and the HotSpot JVM
- [A Scalable Low-Latency GC](https://openjdk.java.net/jeps/333)
- [A No-Op Garbage Collector](https://openjdk.java.net/jeps/318) – handles memory allocation but does not implement any actual memory reclamation mechanism
- [Java EE and CORBA modules](https://openjdk.java.net/jeps/320) got removed
- [Nashorn](https://openjdk.java.net/jeps/335) deprecated
- Addition to `Optional` API, `String` API

## Java 12, 19 March 2019

Java 12 features [12 JEPs](https://openjdk.java.net/projects/jdk/12/).

- [Switch Expressions](https://openjdk.java.net/jeps/325) – can be used as either a statement or an expression
- G1 improvements – [abortable mixed collections for G1](https://openjdk.java.net/jeps/344), [promptly return unused committed memory from G1](https://openjdk.java.net/jeps/346)
- [Shenandoah](https://openjdk.java.net/jeps/189) – a Low-Pause-Time Garbage Collector

## Java 13, 17 September 2019

Java 13 features [5 JEPs](https://openjdk.java.net/projects/jdk/13/).

- [Switch Expressions](https://openjdk.java.net/jeps/354)
- [Socket API](https://openjdk.java.net/jeps/353) – replace the underlying implementation used by the `java.net.Socket` and `java.net.ServerSocket` APIs
- [ZGC](https://openjdk.java.net/jeps/351) - support for Linux/AArch64

## Java 14, 17 March 2020

Java 12 features [16 JEPs](https://openjdk.java.net/projects/jdk/14/).

- [Pattern Matching for `instanceof`](https://openjdk.java.net/jeps/305) 
- [JFR Event Streaming](https://openjdk.java.net/jeps/349) – expose JDK Flight Recorder data for continuous monitoring.
- [Records](https://openjdk.java.net/jeps/359) – provide a compact syntax for declaring classes which are transparent holders for shallowly immutable data.
- [Helpful NullPointerExceptions](https://openjdk.java.net/jeps/358) – describe precisely which variable was `null`
- [Switch Expressions](https://openjdk.java.net/jeps/361)
- [Remove the Concurrent Mark Sweep (CMS) Garbage Collector](https://openjdk.java.net/jeps/363)

## Java 15, 15 September 2020

Java 15 features [14 JEPs](https://openjdk.java.net/projects/jdk/15/). The JEP list is frozen.

- [Nashorn](https://openjdk.java.net/jeps/372) removed
- [Biased Locking](https://openjdk.java.net/jeps/374) disabled and deprecated
- [Text Blocks](https://openjdk.java.net/jeps/378) standardized
- [ZGC](https://openjdk.java.net/jeps/377) became standard
- [Shenandoah GC](https://openjdk.java.net/jeps/379) became standard
- [Sealed classes/ interfaces](https://openjdk.java.net/jeps/360) – restrict which other classes or interfaces may extend or implement them, preview
- [Hidden Classes](https://openjdk.java.net/jeps/371) – classes that cannot be used directly by the bytecode of other classes
- [DatagramSocket API](https://openjdk.java.net/jeps/373) – replace the implementations of the `java.net.DatagramSocket` and `java.net.MulticastSocket` APIs
- [Records](https://openjdk.java.net/jeps/384), preview
- [Pattern Matching for `instanceof`](https://openjdk.java.net/jeps/375), preview
- [Foreign-Memory Access API](https://openjdk.java.net/jeps/383) – allow Java programs to safely and efficiently access foreign memory outside of the Java heap

## Java 16, 

Java 16 features [x JEPs](https://openjdk.java.net/projects/jdk/16/). 

Migrate the OpenJDK Community's source code repositories to [Git.](https://github.com/openjdk/ and Elastic meta space. 

More details on https://javaalmanac.io/, collection of information about the history and future of Java.