---
layout: post
title: Programming in Poetry
date: 2018-04-28
---

Who do we “speak” to when we code? Beginner programmers often hear that code is “instructions to the computer.” But as we take on larger projects with more collaborators, we learn to use code to communicate with humans, too - with our future selves, with potential employers, with coworkers. We use our code to document our thinking, but also to impress, instruct and even amuse.

I decided to take this multivocal quality of code to an extreme in my current project: designing a [poetry programming language](https://github.com/sarahwelzgeselowitz/poetry-lang/) (and its JavaScript interpreter). My goal has been to create a two-(or-more-)faced form of communication: one that makes it easy to speak to computers in commands, and to people in poetry.

This multi-vocality is made possible by an untraditional syntax. Many programming languages depend on keywords (e.g. “def”, “function”, “let”) and textual symbols (e.g. “}”, “:”, “;”) to instruct the computer. Using these tokens, it’s difficult for a programmer to write code that looks like "natural" English. By contrast, in my poetry language, syntax  generally consists of linguistic features such as rhyme and alliteration. This syntax imposes some (reasonably poetic) constraints on the text, while freeing programmers to choose their own words.

To illustrate, I’ve written a couple different implementations of the same function. This function takes a number and returns “true” if it is zero and “false” if it is not zero.  In JavaScript, we could implement it like this:

```
function isZero(n){
  return n===0;
}
```

This function, in poetry language, is much harder to read. So let’s start with the instructive flavor.  In this implementation, the poem’s speaker explains (roughly) to the human reader what each line means to the machine.

```
I'll show you what a function looks like
I here declare this function, and then my
Parameter goes in this line
Now I'll start the function body
Here I'm starting a code block
Now I'll use this line and its twin
To declare the integer zero in
That block, of which I'll later take stock
Fine stock indeed - it's happening - is my argument zero?
These lines close blocks, so don't let your rhymes get shoddy
You must use them to tie
things up. And now we're done - get out, take a hike!
```

Despite this code’s self-documenting nature, it’s pretty hard to read as machine instructions. A human reader scanning the code for a function would have to search not for the keyword "function" (as in JavaScript), but for a line whose first and last words rhyme. (In this case, that’s line 2.) The number zero looks not like the familiar symbol “0,” but like a rhyming couplet in which no words are alliterative with the first word (lines 6-7, "Now I'll...zero in") . And so on!

The upside of all this is that programmer-poets are free to use their code to express whatever they want. In this next implementation, the machine is asked to evaluate whether a number is zero, while the human reader is asked to ponder the nature of nothingness. (Because what else does one think about when comparing numbers to zero?) Though it reads quite differently from the previous implementation, this version is, as far as the machine is concerned, syntactically identical:

```
I wonder what nothingness looks like
Whether as light as a feather
Or as heavy as night
Whether as deep as dirt
Or as shallow as air
Is nothingess as loud as thunder
Or as soft as wonder?
And is it fair to call it fair?
Right there, right here, is nothing
Swimming somewhere beyond hurt
Beyond our shifting weather
Beyond whatever pains may strike
```

Not all programmer-poets want to be so wordy - there’s beauty in brevity. This final (also syntactically identical) version of the code uses the minimum necessary number of words to achieve the task at hand:

```
Strike
out, shout,
fill
pages.
Charts
of vain
pain
- arts.
Still hearts are
cages,
drought
like.
```

Programming in poetry may not be as romantic as it sounds - it turns out that trying to simultaneously satisfy a human and machine “ear” is downright frustrating. Still, it’s good practice. After all, we should always be striving to write code that communicates clearly with both humans and machines.
