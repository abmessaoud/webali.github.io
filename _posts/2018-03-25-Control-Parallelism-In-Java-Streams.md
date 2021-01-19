---

layout: post
title: Control Parallelism In Java Streams
---

Previously, I had a task to write a transformation pipeline of gigantic data sets. I will not speak about complexity due to the difference in the environments, and the size of data to handle is variable, as my first concern was the performance and how to speed up the execution. Besides the methods to play with data in Java `Streams`, it provides parallelism to use `concurrency` and multiple `cores` efficiency. In this tutorial, we’ll see how to use this API effectively. 

## Sample as 1, 2, 3

A stream represents a sequence of elements and supports different kind of operations to perform computations upon those elements:

<script src="https://gist.github.com/alibenmessaoud/fcf064e59b6d997159949bde7f2c4ac7.js"></script>

Stream methods are either intermediate or terminal. Intermediate methods return a stream. Terminal methods are either void or return a non-stream result.

Streams can be created from different data sources, especially `Collections`. Collections support `stream()` and `parallelStream()` methods to either create a sequential or a parallel stream.

The same code above can use `parallelStream()`. Let's focus on parallel streams for now.

## How it works?

The Stream API uses [`ForkJoinPool`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ForkJoinPool.html) to execute concurrent tasks.

>  Parallel streams work under the hood by employing the fork/join framework introduced in Java 7.

Also, a `ForkJoinPool` may be constructed with a given target parallelism level; by default, equal to the number of available processors. So the idea was to configure the parallelism level based on the environment. 

So now we have how to do it right.

## Control the parallelism with custom fork/join pool

### Solution #1

The intention is to construct a custom fork-join pool with the desired number of threads and execute the parallel stream within it:

<script src="https://gist.github.com/alibenmessaoud/6a5eb7c8772dfe16cd1ef1cb9044fe3e.js"></script>

So the idea is to execute the `parallelStream` statement inside of the `submit` block which will hand the job to the framework.

For demonstration reasons, we created, started, and stopped the pool in the method. That’s not a good approach to take. 

You have to be careful when using the `ForkJoinPool`. This object must be created when the application started and shut it down when the application before the application is stopped. 

### Solution #2

It stills another way to customize the number of threads. You can set the system property `java.util.concurrent.ForkJoinPool.common.parallelism` to the value you want:

<script src="https://gist.github.com/alibenmessaoud/761d890d730558c1a27af6c8e6cf6845.js"></script>

or by setting a JVM argument as follow:

<script src="https://gist.github.com/alibenmessaoud/5e4e0bf15b0794cd389473435ae46d45.js"></script>

By using this solution, you limit the thread pool size of the entire application. The idea is to use parallelism in specific places of the application logic but not everywhere because it can affect the application performance and limits the hardware utilization extremely.

## Conclusion

We have seen how Parallel Stream with the cooperation of `ForkJoinPool` can help to enhance the performance of a Java application.

