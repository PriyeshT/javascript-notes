JavaScript is a single threaded programming language, which means that it has a single call stack.

one thread = one stack = one thing at a time

<b>Call Stack</b> - it is a data structure which records basically where in the program we are. If we step into a function, we put something on the stack, if we return from a function, we pop off from the top of the stack.

Things which are slow and are on that stack is referred to as <i>blocking</i>. <b><i>Blocking</i></b> simply means the code that is slow. console.log() is not slow, while() loop to print one to billon numbers is kinda slow, network requests are slow, image requests are slow.

<b>Event Loop</b>: is something that looks at the stack and the task queue. If the stack is empty, it takes the first job from the task queue and pushes it on the stack, which effectively runs it. Event loop has to wait until the stack is clear to put things on to the stack.
