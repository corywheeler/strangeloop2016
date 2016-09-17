# StrangeLoop 2016
My notes from the StrangeLoop 2016 Conference. I have tried to account for all of my spelling errors, but should you stumble on one then please accept my apologies

* [Full list of all speakers at the conference](http://www.thestrangeloop.com/2016/sessions.html)

* Table of Contents for what I attended:
  * [GOVERNMENT HACKING AND HUMAN RIGHTS: THE WHY AND THE HOW... Amie Stepanovich](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#government-hacking-and-human-rights-the-why-and-the-how-amie-stepanovich)
  * [IDEALIZED COMMIT LOGS: CODE SIMPLIFICATION VIA PROGRAM SLICING...Alan Shreve](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#idealized-commit-logs-code-simplification-via-program-slicingalan-shreve)
  * [PROJECT JIGSAW IN JDK 9: MODULARITY COMES TO JAVA...Simon Ritter](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#project-jigsaw-in-jdk-9-modularity-comes-to-javasimon-ritter)
  * [SYSTEMS PROGRAMMING AS A SWISS ARMY KNIFE...Julia Evans](https://github.com/corywheeler/strangeloop2016/#systems-programming-as-a-swiss-army-knifejulia-evans)
  * [DISTRIBUTED COMMIT LOG: APPLICATION TECHNIQUES FOR TRANSACTION PROCESSING...David McNeil](https://github.com/corywheeler/strangeloop2016/#distributed-commit-log-application-techniques-for-transaction-processingdavid-mcneil)
  * [FAILING (AND RECOVERING) ASYNCHRONOUSLY: A SAGA...Daniel Solano Gómez](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#failing-and-recovering-asynchronously-a-sagadaniel-solano-gómez)
  * [PRACTICAL DATA SYNCHRONIZATION WITH CRDTS...Dmitry Ivanov](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#practical-data-synchronization-with-crdtsdmitry-ivanov)
  * [THE FUTURE OF THE MOBILE WEB...Paul Kinlan](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#the-future-of-the-mobile-webpaul-kinlan)
  * [COMMANDER: BETTER DISTRIBUTED APPLICATIONS THROUGH CQRS AND EVENT SOURCING...Bobby Calderwood](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#commander-better-distributed-applications-through-cqrs-and-event-sourcingbobby-calderwood)
  * [BUILDING A DISTRIBUTED TASK SCHEDULER WITH AKKA, KAFKA, AND CASSANDRA...David van Geest](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#building-a-distributed-task-scheduler-with-akka-kafka-and-cassandradavid-van-geest)
  * [THE ZEN OF HIGH PERFORMANCE MESSAGING WITH NATS...Waldemar Quevedo Salinas](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#the-zen-of-high-performance-messaging-with-natswaldemar-quevedo-salinas)
  * [FRONTIERS IN CRYPTOGRAPHY...Tony Arcieri](https://github.com/corywheeler/strangeloop2016/blob/master/README.md#frontiers-in-cryptographytony-arcieri)

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
### [Introduction to JigSaw](http://www.thestrangeloop.com/2016/project-jigsaw-in-jdk-9-modularity-comes-to-java.html)
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

## [SYSTEMS PROGRAMMING AS A SWISS ARMY KNIFE...Julia Evans](http://www.thestrangeloop.com/2016/systems-programming-as-a-swiss-army-knife.html)
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

## [DISTRIBUTED COMMIT LOG: APPLICATION TECHNIQUES FOR TRANSACTION PROCESSING...David McNeil](http://www.thestrangeloop.com/2016/distributed-commit-log-application-techniques-for-transaction-processing.html)

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

## [FAILING (AND RECOVERING) ASYNCHRONOUSLY: A SAGA...Daniel Solano Gómez](http://www.thestrangeloop.com/2016/failing-and-recovering-asynchronously-a-saga.html)

* The saga pattern
* How it can be used to undo side effects in asynchronous systems
* For every action there is an undo action
* Begin the saga pattern
* Started 30 years ago, Long Lived Transactions... paper at Princeton
  * A LLT as a saga
  * Guarantee Compensating actions are executed
* Sagas get revived in SOA patterns.
* How can we get transaction likeness between distributed services
* Implement the saga pattern, use sagas as an alternative to distributed transactions
* May be managed internally or externally
* Add Asynchronous Sagas
  * Add undo semantics to concurrency constructs
  * Not concerned with persistance
  * Operations may or may not be distributed
* Primitives:
  * A forward flow
  * A rollback flow
* Sagas are not just for streams
* Is it possible to build a monadic saga-aware future
* However, futures do not know their context
* How do you create a pleasant API
* Sagas are a useful way of tinking about processes that can fail
* It is possible to enhance concurrency libraries by creating sagas as a library

## [PRACTICAL DATA SYNCHRONIZATION WITH CRDTS...Dmitry Ivanov](http://www.thestrangeloop.com/2016/practical-data-synchronization-with-crdts.html)

* Users expect their applications still work even when they lose their connections.
* Users expect thier data changes to merge to an expected value.
* Bad programmers worry about code. Good programmers worry about data structures - Linus Torvalds
* CRDT - a data type with it's own algebra
* C: Conflict Free
  * Merge Operation - Idempotent, Communative and Associative
* Local Updates
* Local Merge of receiving data
* All local merges converge
* Examples
  * G-Counter - Grow Only Counter
  * G-Set - Grow Only Set
  * LWW-Element-Set
  * OR-Set
  * OUR-Set
* CRDT tend to grow because of Tombstones
* Prune deleted elements, but when?
* Applie Time-to-Live for tombstones
* Send and reply with a Diff - Client modifies and sends only updated elements (Diff). Server responds with a full merge result (ineffecient). Can use a Scoped Diff as an answer. Server responds only with the elements that have won.
* Introduce a clock per element.
* There is no reliable time
* Causality is ordering of events is important
* Time can be good enough
* Academia is not as scary as it sometimes seems to pragmatic devs.
* We need better and simpler abstractions to develop Offline-Friendly apps
* CRDTs give a great value, but there are some caveats
* Things like Lasp

## [THE FUTURE OF THE MOBILE WEB...Paul Kinlan](http://www.thestrangeloop.com/2016/the-future-of-the-mobile-web.html)

* The difference engine changed the world, Charles Babbage 1822ish
* Analytical Machine
* Punch Cards, ex. of removable storage
* 1960's to mid 1980's, still using punch cards
  * Start of the computing world
* Then we get magnetic tape, invented in 1977, demise in the 1980's
* Then Floppy Disk, 1982, lasted to 2005
* CD's, invented 1988, lasted to 2009
* Along here we start to get this thing called The Web
  * At the time, far less capable
* Along came AJAX
* At every phase some sort of friction was removed for delivering things to the user
* Distribution was one of the hardest parts of building software
* We get to the point of just entering a url and we're able to do stuff
* Mobilithic era
* App store is a distribution thing
* Facebook is a distribution thing
* Cost of distribution has been decreasing over time, massively
* In a consumer mobile app, every step you make a user perform results in a loss on the order of 20% of your users
* Need to get closer to... give user a url... user uses app. Each step that interferes with this results in some of your potential users leaving your site
* Engagement is the killer feature
* 40% of people leave a site that takes more than 3 seconds to load
* 20% of households rely solely on cellular data
* 60% of the rest of the world are only on 2G
* People's first computing devices are more and more becoming mobile devices
* Performance is EVERYTHING
* Rise of the meta platform - Web, Facebook, Line, Kakao, WeChat
* The web is the meta platform
* Performace is the selling point - Takes 8 seconds to load the average website on a mobile platform
* The google AMP project
* Each "App" wants to be "the next browser"
* If you look at the api space, you're starting to see things like messenger box. 
* They are using all of the web things around to accomplish this.
* What is the future of the mobile web?
  * Match Native on features
  * Focus on Performance
  * **Increase Engagement**
  * Profit
* Get browser vendors to fix their mess. 
* Credential Management API
* Payment API
* Nobody likes entering data into forms
* Generic Sensor API
* WebUSB
* Native Sharing - Share from Native to Web
* Web VR
* Look at his big list of API's
* Focus on Performance
* RAIL - Respond (under 100ms), Animation (render frames every 16ms), Idle (), Load (ready to use in 1s)
* Look at progressive rendering + bootstrapping
* Increase Engagement - provide good experience to the users
  * What's misisng? - Homescreena ccess, Push Notifications, Offline support
  * Progressive Web Apps
  * http://infrequently.org
  * Originate from a Secure Origin
  * Load while offline
  * Reference a Web API manifest
  * Responsive
  * Instant
  * Reliable
  * Smooth
  * Engaging
  * Works offline
* Service Worker API - look at it... W3C.
  * Lives outside of the site and controls things for the site
  * Sort of like a client side proxy in some sense
  * Service Worker puts you in control with how the offline experience works
* Progressive Web App experience
  * Reliable
  * Fast
  * Engaging
  * Secure
* Service Workers are to Progressive Web Apps as XMLHttpRequest was to AJAX
* Where are we going, we don't need no browser
* The headless web
* He Rick Rolled the entire audience, clever
* Schema.org
* Headless Chrome
* PageSpeed Tools - Insights
* Lighthouse

## [COMMANDER: BETTER DISTRIBUTED APPLICATIONS THROUGH CQRS AND EVENT SOURCING...Bobby Calderwood](http://www.thestrangeloop.com/2016/commander-better-distributed-applications-through-cqrs-and-event-sourcing.html)
* Was chatting with him a bit, he recommended giving this a watch... https://www.youtube.com/watch?v=FihU5JxmnBg
* Immutability is central to informations systems (distributed systems)
* Action and percepettion are not the same, and immutability facilitates their seperation
* Businesses services are not databases, they're event stream reactors
  * We sometimes think of them as they are
* Cross-cutting concerns must be satisfied in the presense of Conways Law
  * We have to respect that and use it to our advantage
* His slide on problematic architecture is familiar
* Immutability is central to information systems
* Event Sourcing - store all events that build state rather than an aggregate picture of state. You have the whole story of what happened and you have the whole story of current state. You capture the whole narrative.
* Writes != Reads
* 80% of our system is probably a read load
* 3NF is not performant for Read or Write. Kind of an average line for both worlds.
* Database Leaking is an abstraction that leaks out.
* Conways Law, yep totally a thing
* Let's use it for our benefit.
* There are cross cutting concerns.
* How do we handle those things in a distributed organization
* We can do better than the grey box
* Commander Pattern
  * REST + CQRS + Event Sourcing + Reactive Stream Processors + ... (i missed the rest of his formula)
  * Commander Architecture
* Embrace Immutability
* Expressing actions in the language of the business domain (not in database language)
* A command is an action and a data, phrased in the imperitaitive, ex. transfer_money
* A event, phrased in the past tense, money_transfered, with data
* Seperate Action from Perception
* From 1 Log => n Data Views, as many data views as we want. We don't have to all agree on a data schema
* Why Commander Component
  * Single writer to commands topic
  * Ensuring schema conformance
  * Indexing all Commands and Events for reads and server-push
  * Provides optional illusion of synchorony to clients
* How do we implement the Reactive Services?
  * Kafka Streams - allows you to express given a set of source topics, map (do x to it), and reduce those to a set out outbound topics
* Should CommitStream be sending back a 202 rather than a 201?
* https://tinyurl.com/capital-one-cmdr
* [FOR US] CommitStream, should we be recording our Error Events?
* Event Schemas?
* All views are projections off of the event log.

## LIES, DAMN LIES, AND METRICS...André Arko

* Metrics, are important, tell you what is happening. 
* Find video, Metrics Metrics Everywhere
* Only way to know business value is to measure it
* Metrics convince you you undertstand
* Specific ways metrics mislead you
* The biggest problem is Averages convince you you understand. Averages are lie-candy for your brain. Brains are really good at finding patterns. When you see an average your brain says aha, an average is a number and a standard distribution.
* The problem is your numbers are not random. So you are actively misinforming yourself. 70% of values are within 1 std. dev of the middle of the bell curve. In real life, not so much. Real life data is NOT a standard bell curve!!!!!
* If you put one hand in a bucket of ice and the other in a bucket coals, on average you're comofortable.
* Graph the median - shows you what did actually happen in real life. The value that was higher or lower than half the values you collected
* Graph 95th percentile... shows you the 5% with the highest values
* Graph the 99th percentile... 1% is the amount that you probalby want to pay attention to trouble shoot on large scales
* Another problem with averages, Aggregate Graphs, Your averaging, for example, across multipel servers.
* You can breakout the Aggregate Graphs, to see individul servers, for example.
* Visualizing your data is the only way to get good information out of your data.
* Breakout alerts should be on the first dead server, not ever on an aggregate of servers
* Servers: you have no idea what is going on
  * Ex. Runtime Lag - Runtimes do things that you didn't write code for. There are times when your program is running when your code is not. How do you tell you lost consciousness. How bad is runtime lage. Do a sleep(1) in a loop and take the dif between how many runs and your sleeps, gives you how much time is spent running other stuff.
  * VM lag - you have it.
* Routing - you have it (a la a router and a la a Server router). How slow is routing? Look at your real life Request Time. New Relic can tell you how much time is spent inside your app, but that is not the whole story. There is app rout time, load balancers, transite time, hardware router time. Wall clock time from real clients. Pingdom, Runscope.
* Metrics are good, but know what your measureing and how those things effect your business value


## [BUILDING A DISTRIBUTED TASK SCHEDULER WITH AKKA, KAFKA, AND CASSANDRA...David van Geest](http://www.thestrangeloop.com/2016/building-a-distributed-task-scheduler-with-akka-kafka-and-cassandra.html)

* He works for PagerDuty, sounds interesting, monitor outages.
* Reliability and uptime are #1
* Most important piece is the notification pipeline
* Infrastructure lives in 3 different data centers, and things need to work always
* The Problem (that he's discussing)
  * Email someone 2 days before they're on-call
  * Push notify 1 minute after an incident
  * Retry a failed SMS delivery in 30 seconds
  * Actually it's arbitrary Scala code that needs to run at an arbitrary time
  * Regardless of changing broken infrastructure
  * While maintaining task ordering
  * Taks1 only guranteed to execute before Task2
    * They ahve the same orderingId
    * Time of T1 < Time of T2
    * schedultTask(T1) comes before scheduleTask(T2)
  * Tasks are idempotent, if you run it again, nothing bad will happen
* New Hotness
* Build in Scala
* Uses:
  * Apached Kafka - for task buffereing
  * Apache Cassandra - for task persistance
  * Akka - task execution
* Challanges:
  * Dynamic Load
  * Data center outages
  * Task ordering
* Kafka - dynamic load - scales horizontally
  * For a topic, Kafka has N replicated partitions
  * Adding a broker causes partitions to be rebalanced
  * Partitions are brokered by Kafka
* Dynamic Load - Service
  * Can scale horizontally via Kafka
  * Casandra scales horizontally
* Datacenter Outages

## [THE ZEN OF HIGH PERFORMANCE MESSAGING WITH NATS...Waldemar Quevedo Salinas](http://www.thestrangeloop.com/2016/the-zen-of-high-performance-messaging-with-nats.html)

* High performance messaging system
* Originally built for Clout Foundry
* Open Source
* 7MB in size in Docker Image
* Acts as an always available dial-tone for clients to communicate with
* NATS = Performance + Simplicity
* Simplicity Matters
* Simplicity buys uou opportunity - Rich Hickey, look at his link
* Less is better
* Does nothing but pure pub/sub
* No built in persistance of messages
* Nats chose TCP/IP
* Fire and forget, at most once delivered
* Payload is opaque to the server, to the server it's just bytes
* Most clients have asynchronous behavior
* The server will disconnect slow clients and protect itself.
* So NATS is resilliant as well
* You can wildcard match subjects
* Building systems with NATS
* What does NATS give us
  * Pub/Sub with low latency for 1 to 1, 1 to N nodes, wtih an always on Tcp connection
* NATS can be clustered
* Communicating
  * Can be used for heartbeats for announcing liveness, services could publish heartbeats
  * Can be used for distribution queues among a set of workers
  * Lowest Latency Response
* Need to understand the reason things fail, NATS is fire and forget. A Client Can time out for many reasons.
  * Each service node could have it's own inbox
* NATS is useful for internal communication of a distributed system
* Read the wikipedia article on the End To End Principal
* Replayability can be better than guarnteed delivery
* Idempotency can be better than exactly once dlelivery
* Communicativity can be better than ordered delivery.

## [FRONTIERS IN CRYPTOGRAPHY...Tony Arcieri](http://www.thestrangeloop.com/2016/frontiers-in-cryptography.html)

* The Past
* Some crypto is more invented than discovered
* A look at history
* Diffie-Hellman-Merkle (1976)
* Rivest-Shamir-Adleman
* James Ellis, Clifford Cocks, Malcolm Williamson - Non-Secret Encryption
* Pollard's Rho algorithm
* Lenstra's Method
* Shor's Algorithm
* Symmetric Encryption
* Where is cryptography going?
* End to End
* Main problem that is run into is Indistinguishability
* Property Preserving Encryption
* Order Revealing Encryption
* Searchable Symmetric Encryption
* Oblivious RAM (ORAM)
* Functional Encryption
* Lattices
* Homomorphic Encryption
* SEAL
* CryptoNets
* VC3
* Post-Quantum Cryptography
