# Writing Problem: Everyday Algorithms

## tl;dr

Write up algorithms to exhaustively describe in text and pseudocode, 
steps to brush one’s teeth, eat an orange, and something you do everyday.

## Step 1: Watch This.

Let’s start off by watching David’s video (from Ted-ED) on Algorithms.

{% video https://youtu.be/6hfOvs8pY1k %}

As we see from that video, algorithms are sets of instructions for completing a task step-by-step. Sometimes these algorithms can be quite simple. One way to express an algorithm for deciding how to dress based on the weather might be to say something like this.

```
Look out the window. If it is raining outside, put on 
your rain boots and raincoat. Then go outside.
```

Sometimes they can be a bit more complex. Dropbox, if unfamiliar, is a service that provides storage of files "in the cloud"—on physical machines that are not your own but rather are typically owned by a hosting company—and delivers those files to you via the Internet. It also can synchronize your files between all machines on which you’ve installed the Dropbox client and has a web interface for downloading your synchronized files, which is handier than e-mailing yourself a copy of the file you worked on at school so you can continue working on that same file at home.

As the company began to grow and have many users, Dropbox needed many more file servers and a way to organize their millions of users and their billions of files across those servers. As computer scientists might say, they had to develop algorithms for dealing with issues of *chunking and sharding*:

{% video https://youtu.be/VECV6r9s5SE %}

And don’t worry if you don’t yet understand the processes that Thomas and Alex described in that video. You certainly don’t need to understand either of those things for this assignment, but rest assured that by the time you’ve completed the course, you’ll have a much better appreciation for how this might work!

##Step 2: Read This.

The concept of an algorithm is fundamental in computer science. Recall from earlier in this chapter that we defined a computer as a device that accepts input, and processes it in some way to produce a result automatically. The critical word in that sentence when we are talking about algorithms is the word "processes".

Say you’re playing your favorite video game of all time. If you’re a fan of nostalgia, it might be this gem.

{% video https://youtu.be/zNBwkI0ytZo %}


Assume you’re racing Sonic around Green Hill Zone and you see a couple of rings up in the air, over Sonic’s head. Because they protect you in the event you are attacked by an enemy, you want to pick them up. In order to grab them, you have to press one of the buttons on the controller. When you press that button, Sonic jumps into the air to a consistent height. When and if he touches the ring, it disappears from the screen so it cannot be claimed multiple times, and the number of rings in his possession—​indicated by a ring counter—​increases by one.

Every step of that process involved multiple algorithms. Described informally, those algorithms (greatly simplified) might read as something like this:

```
If the jump button is pressed and if Sonic is standing on the ground, begin moving him upward
until he reaches the top of his arc. After he reaches the top of his arc, begin moving him downward
by simulating gravity's pull until he is standing on the ground again.
```

And for the rings:

```
If Sonic is touching a ring, remove the ring from the screen and increase Sonic's ring counter by one.
```

Let’s focus just on the jumping algorithm for now, because the "input" to that algorithm is a lot clearer. The device that is executing this algorithm is the Sega Genesis console (or, more likely nowadays, an emulator for the same) running the Sonic the Hedgehog software. What is the data or input? That would be you, holding your controller, pressing down on the button that makes Sonic jump. (In fact, as you may recall, it’s actually an electrical pulse that occurred when you pressed that button that likely "jump-started" this algorithm.[2])

What is the result? On the television screen or monitor you see Sonic’s height off the ground begin to change; what he looks like might begin to change, too. Instead of keeping the same appearance as he did when standing on the ground, typically when Sonic jumps his sprite (a term we’ll be seeing again soon) changes to a ball that rotates, indicating that his jump is actually more of a flip or somersault through the air. As in reality, one doesn’t jump off the ground and then just fly off into the sky. What goes up must come down and so eventually after reaching the top of his jump Sonic lands on the ground again.

All of this is a process. And, truly, the process is a lot more fine-grained than that. We’ve oversimplified for purposes of illustration. We’ve also glossed over the notion of multiple algorithms running simultaneously in separate threads (another term we’ll be seeing again soon). But hopefully this example suffices for now.

Because this process of what happens when the jump button is pressed can be described as a clear, unambiguous, series of steps (aka, algorithmically)—at least in the game’s source code—it is consistent and, importantly, repeatable. If Sonic is standing at the same point and we press the jump button again and again—if he is standing on the ground and nothing else gets in his way like an enemy, whose algorithm might at some point fly them over Sonic’s head—the result is the same, again and again. Sonic always jumps to the same height, he spins in the same way while jumping, and he lands on the ground after the same amount of time. Because of the jumping algorithm, the computer always knows exactly what to do when that jump button is pressed, and always does exactly what it is told to do.

Sometimes it is easiest to express an algorithm using common language. That’s what we have done so far. Look back to the very first algorithm mentioned above—about deciding what to wear in the event of rain. Maybe there’s a way to articulate the decision-making process of getting ready more clearly?

Instead of this:

```
Look out the window. If it is raining outside, put on your rain boots and raincoat. Then go outside.
```

you might see a computer scientist instead use what’s called pseudocode—short expressions in common language organized in a way that resembles what source code looks like—to write their algorithms. We’ll talk more about pseudocode soon, but getting in the habit of writing it before you dive into actual coding in Scratch, C, PHP, or JavaScript is a great idea, much like writing the first draft of an essay.

Here’s one possible way to translate that algorithm into pseudocode:

```
1   look out the window
2   if it is raining outside
3      put on your rain boots
4      put on your raincoat
5   go outside
```

We’ve numbered the lines for a reason you’ll see momentarily. But notice how regardless of whether it’s raining the algorithm instructs you to go outside. It just has a special extra set of things you do before stepping outside if it happens to be raining. We call something like "if it is raining outside" a condition. Some algorithms also have steps that get repeated many times over, like this one:

```
Secretly pick your favorite number from 1 to 50. When your friend gives you a number, if they are too
high tell them to guess lower and if they are too low tell them to guess higher. If they are right,
have your friend stop guessing.
```

We call such a repetition a loop, because you’ll keep going around and around the same steps until some condition (your friend guessing the right number) lets you stop. Here’s one of many possible ways to express the guessing game in pseudocode:

```
 1   secretly pick your favorite number from 1 to 50
 2   have your friend guess your favorite number
 3   if your friend guesses a lower number
 4      tell your friend to guess a higher number
 5      go back to line 2
 6   else if your friend guesses a higher number
 7      tell your friend to guess a lower number
 8      go back to line 2
 9   else
10      tell your friend to stop guessing
```

Notice here that until your friend guesses the correct number, they will go back to line 2 of the algorithm, which prompts them to make another guess. Only when they guess correctly can they proceed to line 10 and *break* out of the loop.


