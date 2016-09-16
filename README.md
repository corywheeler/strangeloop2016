# StrangeLoop 2016
My notes from the StrangeLoop 2016 Conference

* [Full list of all speakers at the conference](http://www.thestrangeloop.com/2016/sessions.html)

* Table of Contents for what I attended:
  * [GOVERNMENT HACKING AND HUMAN RIGHTS: THE WHY AND THE HOW... Amie Stepanovich](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#government-hacking-and-human-rights-the-why-and-the-how-amie-stepanovich)
  * [IDEALIZED COMMIT LOGS: CODE SIMPLIFICATION VIA PROGRAM SLICING...Alan Shreve](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#idealized-commit-logs-code-simplification-via-program-slicingalan-shreve)
  * [PROJECT JIGSAW IN JDK 9: MODULARITY COMES TO JAVA...Simon Ritter](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#project-jigsaw-in-jdk-9-modularity-comes-to-javasimon-ritter)

## [GOVERNMENT HACKING AND HUMAN RIGHTS: THE WHY AND THE HOW... Amie Stepanovich](http://www.thestrangeloop.com/2016/government-hacking-and-human-rights-the-why-and-the-how.html)


* FBI hacking
* Early days, not a lot of information
* Finally a judge, Judge Smith, denied an FBI's request to hack a system under the 4th Amendment
* Rule 41
* Tracking Warrents - You don't have to re-issue the warrent
* Judge dind't know if "Premises Unknown" would fall under Rule 41 
* FBI lobied
* ECMA - The wiretap act. Have an increased standard than other types of warrants
* Congress has not put any laws in place for new requirements with todays technological taxonomy
* ECMA is long outdated and is being stretched to allow governmental hacking
* FBI is about to gain the power they want by the mere fact that Congress isn't doing a damn thing.
* James Otis: Against Writs of Assistance
* Australia - has one of the oldest laws on the books for governmental hacking. The also allow "bulk hacking".
* Australian hacking data was handed over to the US and used
* A look around the world shows that really all governments are hacking their citizens, or peoples devices in their country.
* Governments are being provided tools from private organizations
* Operaton Ominous
* Warrior Pride
* UK Investigatory Policy Bill
* We need to be looking at International Law
* Human Rights - Universal Declaration of Human Rights (from the UN)
* Messaging Control
* Causal Damage - External or Internal damage is the result
* Commission of Survailance or Intelligence Gathering
* Human Rights that are violated
  * Due Process
  * Can deprive you of your property rights
  * Privacy - Protected information
  * Freedoms of Expression and Opinion
* There needs to be a presumptive prohibition as it relates to hacking. There needs to be some safeguards in place as it relates to governmental hacking
* Governmental hacking will continue to take place
* What she thinks safeguards look like
  * We need some law that the government needs to abide by
  * Officials need to explain why hacking is the way to get the information
  * Hacking operations must never occur perpetually
  * Applications for hacking should be indepenently reviewed and approved by experts
  * Governments must provide actual notice to the target
  * Officials should publish reports
  * Private entities should never be compelled to engage in activities that impact their own products
  * If scope is exceeded, the operations needs to report back to the judicial authority as such
* None of this is easy
* Human rights should not be sacrificed entirely

## [IDEALIZED COMMIT LOGS: CODE SIMPLIFICATION VIA PROGRAM SLICING...Alan Shreve](http://www.thestrangeloop.com/2016/idealized-commit-logs-code-simplification-via-program-slicing.html)
* Code is read much more often than written
* We don't talk about reading code
* When it comes to reading code, we have almost nothing to say
* Most of the code you work with is code you did not write
* Bug in a dependency you have: Complain about it on the internet
* Why not fix the bug in your dependency? Because it's code you will have a hard time understanding
* The program comprehension task is a critical one
* One time cost to comprehend the software is high and the benefit is marginal
* Software is hard to understand
* How do we solve the problem?
  * Documentation is for users, not you, and often out of date
  * Debugger step through
  * Print log
  * Whiteboard (What does that arrow even mean)
  * Read the code - a horrible serialization format for software... a bad layer of abstraction
* When thinking about software you don't think about in terms of source code, you are at a higher layer of abstraction
* Can we build mental models from code faster? 
* The code is always up to date
* Small programs are easy to read.
* They become arcane with noise from edge cases, workarounds, additional features
* Idea: Can we take a larger program and simplify back down to smaller units we can understand
* Algorithm:
  * Write a test case
  * Run a code coverage report
  * Prune all statements not marked by coverage
  * Clean up AST
  * Write code back out
  * Properties you get out of the above
    * It compiles
    * You have tests
* This is called Program Slicing
* Program Slicing first described by Mark Weiser in 1979
  * Forward Slicing
  * Dynaminc Slicing
  * Observational Slicing
  * This Slicing
* Static Slice
  * How to analyze
   * Dataflow Algorithm
   * Program Dependance Graph
   * Control Dependance
   * Data Dependance
* Dynamic Slice
  * We are excuting the program
  * Multiple Algorithms
    * Dataflow
    * Dynamic Dependance Relations
    * Program Dependance Graph
* Slicing Applicaitons
  * Better Context in maintenance or debugging
  * Automatic Parrallism
  * Skip tests
  * Reduce codebase size
  * Optimize JS code loading (Amazon is doing this)
  * Debugging
  * Understanding + Learning
* Does it work?
* Everyone does them and uses them, we're just usually slicing in our heads
* Proof studies are either very old, or done in University
* Not well studied or understood
* Tools
  * Indus
  * Giri
  * Wala
  * Frama-C plugin
  * JSlice
  * CodeSurfer (commercial, gone)
* Tools are old, mostly java
* Writing them is really hard
* Idealized Commit Log
  * When you take a slice, you come out with a smaller piece that is easier to understand
  * All of the code you sliced away is important eventually, once you understand the whole bit
  * Algorithm
    * Run code coverage for each test case 
    * Heuristically chose a best ordering of test cases
    * Then iteratively
      * Create slice from Test0
      * Slice from Test0..TestN_1
      * diff these slices
* He built a prototype tool for this Idealized Commit Log
* We need more tools.
  * Program slicing can be an effective tool
    * Reduce large programs into smaller conceptual pieces
    * Practical dynmaic slicing 

## [PROJECT JIGSAW IN JDK 9: MODULARITY COMES TO JAVA...Simon Ritter](http://www.thestrangeloop.com/2016/project-jigsaw-in-jdk-9-modularity-comes-to-java.html)

* API Structure Changes
* There are Public API's
  * java.*
  * javax.*
  * some com.sun.*, some jdk.*
* Unsupported, not for public use
  * Mostly sun.*
  * Most infamous is sun.misc.Unsafe
* Incompatible Changes
  * Encapsulate most JDK internal APIs, so you can't use them any more
  * Remove a small number of API's
    * 6 in total
    * Nothing that has ever been marked as depricated has ever been removed
  * Change the binary structure
  * New version string format
  * A single underscore will no longer be allowed as an identifier in source code
  * Endorsed standard API override mechanism
  * Extension mechanism
* Internal API Classification
  * Non-Critical
    * Little or no use outside of the JDK
  * Critical
    * Functionality would be difficult, if not impossible to implement outside of the JDK
* JEP 260 Proposal
  * Encapsulate all non-critical JDK internal APIs
  * Encapsulate all critical JDK-internal APIs, for which supported replacements exist in JDK 8
* jdeps tool
### Introduction to JigSaw
* Goals
  * Make Java SE more scalable and flexible
  * Improve security, maintainability and performance
  * Simplify construction, deployment and maintenance of large scale applications
  * Eliminate classpath hell
  * It's all about simplifying things
* Module fundamentals
  * A grouping of code
    * For java is a collection of packages
  * Module can contain other things
    * Native code
    * Resources
    * Configuration data
* Module Declaration:
  * module com.azul.zoop {}
  * 'module' is becoming a restricted reserved word
* Module Dependencies:
  * com.azul.zoop { requires com.azul.zoop }
* This all allows us to create a module dependency graph
  * Must be an acyclic graph
* Package Visiblity - you have to give exports of packages you want to export to other modules
* Accessibility
  * For package to be visible
    * Package must be exported by the containing module
      * Implicitly to all modules
      * Explicitly ot a specific module
    * The containing module must be read by the using module
  * Public types from those packages can then be used.
* Java Accessibility (pre-JDK-9)
  * public 
  * protected
  * <package>
  * private
* Java Accessibility (after JDK-9)
  * public to everyone
  * public, but only to specific modules
  * public, only within a module
  * protected
  * <package>
  * private

## SYSTEMS PROGRAMMING AS A SWISS ARMY KNIFE...Julia Evans
* TCP
* All bugs are easy with the right tools
* Don't be scared to go deeper
* strace
* ngrep
* netstat
* strace - she loves it. it traces system calls.
* strace -f -e open bash
* opensnoop - it's fast and strace is much slower
* python profiler
* dstat
* top
* htop
* perftop - which functions are running slow on your computer
* ngrep - grep for your network 
* perf
* perftop
* sudo perf record -g find /
* flamegraphs - FlameGraph.pl
* ngrep - look at network traffic
* tcpdump - save network traffic to analyze later
* sudo tcpdump port 80 -w file.pcap
* wireshark - analyze your packets
* learn your operating system and it's tools
* she wrote a zine, Linux Debugging Tools. jvns.ca/zines

## DISTRIBUTED COMMIT LOG: APPLICATION TECHNIQUES FOR TRANSACTION PROCESSING...David McNeil

* Amazon Kinesis Streams. 
* It's basically a hosted Kafka
* Goals:
  * Model of distributed commit log
  * Patterns for transaction processing
* They wanted to account for every event processed
* Patterns, not "best practices" is what he's trying to show
* Commit Log - Immutable, append only
* Read in sequence, non-destructively
* Old data is trimmed with Kinesis every 24 hrs by default
* Iterator Types
  * Oldest
  * Sequence Number
  * Newest
* Record Data - key, data - key associates many of the records together. Also has sequence number (Record Metadata)
* Kinesis Stream - slurps up commits in bulk and get order out
* Stream is sharded
  * Shards preserve ordering of records by key
* Can write up to 50K p/s and read 2MB/s (5 reads/s/shard)
* Distributed commit log
* Log is sharded
* Data read by shard
* You can control which workers get which subset of your keys and they are in order
* Workers get leases for shards
* Single worker can hold many leases
* You are reading records in batches
* On the read side, you get at least once delivery, which means you will get duplicates
* Pattern: Idempotent record processing
* Pattern: Track checkpoints for last key processed
* Pattern: Parallel processing by key
* Pattern: SubSequence processing
* Errors
  * In some domains loss of some records don't matter, in others it does
  * Is it an Intrinsic Error
  * Is it an Environment Error
* Pattern: Could retry processing
* Pattern: Context Exceptions
* Enables multiple Apps to all read from the same shards. Be careful because there is an implied latency
* Pattern: Composite Application
* Pattern: Track shard state by pertition key
