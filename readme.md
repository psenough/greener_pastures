This code is my source of the cow speak javascript interperter code golf challenge of pixelscamp quizshow qualifiers #2

There are 2 branches, the master branch was the version i was originally working on and never managed to get accepted despite it seemingly passing all tests

Both branches are based off http://www.frank-buss.de/cow.html sourcecode

The rewrite branch is a last day rewrite, i restarted from frank's source and replaced the input and output char functions and ran the tests, and it just worked (and got accepted by the system) straight away, so my main issue had been the input_char of integers and myself  corrupting working code trying to fix it to pass the tests.

So i didn't end up with much time for actual golfing (you can find my submitted code on cowtest2.html on the rewrite branch).

Plenty of stuff i could have tried if i had had the time. :/

Some things i also learned from cer and naps62 discussing their versions (with shared source) after the challenge was done.

So here is a short list of todo optimizations:
- The tokenizer loop could have been rewritten with a sliding window or regex
- The switch could have been reduced further into pure ?: statements
- .length could be reduced by using ```x = 'length'; t[x]```
