I think I am in the Rewrite it in Rust talk

When I joined they are talking about Go.

What are the projects that are a bad idea to try to rewrite in Rust?

Are you the only one on the team that wants this?

Maybe because you don't want to take on the huge maintainership duty

Or for a huge monolithic project and requires you rewrite everything for 6 months and not deliver business value

I think the concept to rewrite something in Rust is that you need to be able to break it apart so at the end of every week you have something that works.

It can be a concern to not advocate to rewrite it in Rust if there is not organizational buy-in.

In a big organization you might try this from a green field project and maybe even do it without permission and then show that hey it works great.

Talked about using Data Science in Rust. What kind of issues did people experience?

A lot of the issues were piping, serialization and it was bottlenecked by Python because they were going through so much data and just moving it to rust and using Rayon was a huge performance improvement.

What about plotting?

A lot of those tools were still in Python and the MattLab stuff was still in Python and so the things that don't need to run as fast like training models are still in Python.

Python has a huge ecosystem so what libraries would you use other than Ryathon? MDArray and internal things for the specific data operations that you were using. Trying using polars but the use case they were using it wasn't really a good fit for the timeline or use case.

Did you look into `plotters`? Hadn't heard of it?

Someone else tried it and he needed to draw a certain chart and it wasn't supported and then he was able to post an issue and someone manually put the code into the issue to address the issue and so he was able to do that to work around the problem that just manually drew into a rect.

Embedded applications? What other fields make sinse?

Why do it? Fun. Was interviewing to be maintainer of zmap and this is written in C and didn't get job because he told them that he didn't really want a Go job. But this put him on a path of how could this be written in Rust. Has been writing a Zmap alternative in Rust as a personal project. To do this he looked at the paper and then saw the approach from the paper and implimented something from that point rather than from looking at code.

Someone else thought about rewritting lib dot p. What about rewritting from C to Rust. I have used C2Rust and this gives you a good starting point but then what do you do?

Someone who is working on C2Rust…unforchantaly it does generate extra cruft. The idea is to use C2Rust and then clean up the code. If there is a need to get algorthimic complexity then C2Rust can help ensure that this is still right.

Reasons to rewrite in Rust?
*Speed
*Maintainability
*Security, memory safety this is the one that gets money spent
*Productivity, spend time working on features rather than bugs compared to C++ and it scales easier because it is harder for the new guy to add something that causes scalability issues and so you need to put a lot into place to prevent that from getting to production

Go does not have safe concurrence and it has a GC

Wells Fargo as of March is now listed by NIST as a safe language so this helped get it approved for Wells Fargo. Maybe the way to frame it is that it is boring rather than fun because the maintainability cost is so much better.

When not to rewrite in Rust. When it is in maintaince mode and this would require taking it out of maintaince mode.

What about REST APIs?

What about Rust it is only on LLVM archiectures.

Would you write a Linux device driver in Rust? No answer not enough experience.

The DOM as a tree maps poorly to Rust. It is currently an open research question because currently it doesn't really feel right in Rust.

There are companies that are in a state where they should rewrite in Rust but because of reasons they never will and at some point someone is going to come by and rewrite it in Rust and take away market share because it is twice as fast.

This is already happening in HFT (I don't know what that is)

Basically think about everything that needs to be high performance and low latency?

We need a web server that replaces Apache and NGINX something that is written in Rust. A full on web server.

Someone at F5 is working on writing modules for NGINX in Rust.

From a security perspective having a web server in Rust is compelling.

At F5 they bought NGINX

Servo is the original project and that is the joke that Rust is not really well suited to rewrite the browser in Rust. But this is really a problem of scope and scale. Money. Dealing with trees in Rust is not that great but it does work.

There are some things to sandbox modules that Mozzila is doing to host it in webassembly and then cross compile it back to C or something to that effect?

What about the Rust ecosystem keeps you from porting any type of project to Rust? There are some challenges in representing abtritraily sized data. C++ interop is a big obstical. You are like 10x less productive while working through the gory FFI issues. But when you are working with hardware it is hard to get around this.

There is the CC crate to integrate with cargo but there is not really a good way to integrate with cargo because you don't want to switch the entire build system first becase when you start the build system is mostly not Rust. So it would be great to be able to drive the Rust build system from another build system, like make and cmake and such.

Axix web frameworks. There is nothing quite like Jango or something. Right now you are better to refactor and use IPC and such.
