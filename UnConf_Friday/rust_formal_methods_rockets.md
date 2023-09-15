#Rust in Safety / Unsafe / Rocket Science
(Rockets! And Trains, Cars, …)

Rockets are cool!!!
Correctness is super important
Simi-formal methos / Formal methods
We have had issues that has persisted for decads but the landscape hasn't changed much. Other disiplices have a formal root causing process that drives policy
Audit correctness in code

Who where has looked at a safety standard? ISO-262?
Expressing as a mathmatical equation but not doing anything and then formal that allows you to express and then run tests in that way.

V-Modal (B-Modal?)

First thing that goes in is requirements and then in the end you need to test it and functional safety needs to show that the car or train can be stopped in a certain amount of time.

The way a safety standard works is that you need requirements and you need tests and what it expects from you is an argument for what requirement each test comes out of and covers and why are the tests that you are doing appropriate for showing adherance to the requirements.

For example is one of the things that you need for a test in a car is that you have to put the car in a street and try it in a vechical. Can you give not a gut feeling but an argument under what conditions it does work and not for example a break requires appropriate tires.

What constraints does the system require in order to work.

If I have an i32 that is a type mm then I could still construct this from a type that means a cm.

Something about safety is that safety assumes that errors happen and so how do you mitigate mistakes. It is about controlling mistakes. Rigger is not enough.

Hand verification of assymbly for the Rust compiler is being done, just to be clear.

AWS paper about Shard Store - They do a TLS+ construction of some parts of the system. How they made use of TLA+ approachable to engineers that don't have a PHd in this. How to make this work when hardware is failing and networks are failing.
Using lightweight formal methods to validate a key-value store

A lot of people that build these systems have no formal CS education and so we need direct invisable things. Brevity is not the thing.

Maybe following with the typestate pattern to only constrcut type-safe patterns, for correctness

The challenge is this can make it so you need to certify the whole system or do you need to certify libraries. Now that every car maker is competing with Telsa.

How do we validate this becomes a problem. This is called a safety element out of context. Can you consider all contexts that this is being used in and did you make an effort to figure that out. Sometimes that is hard and sometimes not so bad. For example image library easier but async library is harder.

What is correctness for a library. Because ultimately it is only about correctness of the brake, because when people do it what they do is have documentation that says we know what bugs to avoid and we know what to avoid and read the huge manual.

The difference between safety and security. Safety is concervitive and security 

Rust is getting interest because it makes these promises.

The ergonomics of the langauge is that it does away with inherentance which has the problem of putting state into more places than it needs to be and the challenges 

Likes a function that is super obvious in the name what it does but this is more adopted then it is enforced.

7 things that can happen with memory allocation and Rust rules that out so it is a piece of formal verification.

Stack allocation is allocation from the standpoint of safety. And one of the things that we lack in is a stack depth allocator. 

Cargo callstack will try and estimate the amount of stack your program will use. However no one has made an argument about why that is correct.

Someone has a tool he works on called cargo mutants that does mutation testing. How do you do coverage? It is a compliment to coverage and coverage will say every line ran and mutants will check if you check all of the effects.

It has a huristic to look for gaps in the test.

The whole process of gap anylsis. The nice thing about functional programming is those things can be so much easier to test. But at some point you need to manage state. One company that if you can show a function is pure then this can make it easier to formally prove that it can be tested.

Rust compiler only works if your chip works right. It is really high quality on x86 and arm.

Have looked into things with sparc8?

Then you run into things like the car hit the tree how do you make sure that it doesn't explode because of a spark coming out of the microcontroller. This is a look into the future. The number of software bugs when there is hardware involved.
