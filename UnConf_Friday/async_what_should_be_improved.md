#Async What Should Be Improved
	1. Cancellation - Select!
	2. Big toolkit + less guidance
	3. Async Drop
	4. Debugging + Tokio Console
	5. What are my tasks doing?
	6. Unproductive critiscism

You should be able to hook in a debugger and have a task exposed as a thread. What are your tasks actually doing. Would this be a GDB plug-in? There is a proposal by Micheal Woester on the compiler team.

People resources

An unsafe way to declare that this memory still exists and we will tell you again when you can clean it up

This is one of the problems of doing async usb on mac OS, this should be something that is more straightforward to do

Reading huge stack traces is hard because lots of the stuff in between that is not releavent is what you are looking at.

Compiler is nice?

Io_uring + ownership <-- Language feature

Tokio docs talk about queuing up an unbounded amount of work in memory and what technique should be used to avoid this from ever happening.

Echosystem coherence. For example there are so many different streams. Stalled stablization?

If you want to extract a tarball there is a tokio tar and there is just no something that is easy to use. Timers are still executor dependent and would be nice if this could just be in futures.

Transition or interfacing with sync code.

It is very time consuming to look though all of the code that looks throughout a call chain to find a blocking call to I/O or something.

What if you introduced marker traits but for functions so if a function calls blocking I/O it will auto inherent this marker trait.

If you want to do I/O in Go correctly you MUST use the standard library because it knows how to properly mark things (so it doesn't block the green threads I guess?)

If you I/O is capability orientended then that is another solution. But there is a concern that something that requires such a large change.

Is iterator_filter blocking if it is a really large iterator then it is. When do you need to cooperatively yield outside of I/O.

Some of these things is just like computers are hard. A lot of this is not a langauge problem but a diagnostic and documentation problem.

The challenge with cancellation is that you don't realize it is a problem and then suddenly it is like my whole code is f*#$(@

Who is working on AsyncDrop? It is a really hard problem and no one is working on it.

What is your workflow like when you use Tokio console? Hit a bug spin up Tokio console. Like you leave an DOS pending so you can find this that this left pending or background tasks getting hung.

