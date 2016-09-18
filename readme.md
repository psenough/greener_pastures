This code is my final source of the cow speak javascript interperter code golf challenge of pixelscamp quizshow qualifiers #2
http://quizchallenges.pixels.camp/challenge2.html

There are 2 branches, the master branch was the version i was originally working on and never managed to get accepted despite it seemingly passing all tests. The rewrite branch was the last day rewrite which was accepted and a bit golfed.

Both branches are based off http://www.frank-buss.de/cow.html sourcecode

My main version went through a lot of different undocumented version, adding tests and debugging the operators to try and get it accepted by the system (it was a black box system, didn't give you any feedback on what test had failed).

Asked mjamado for some tips and cer swapped me some additional tests (including proper input_char and output_char functions). Still wasn't able to get my "original" version accepted, so i went for the rewrite, restarted from frank's source, just replaced the input and output char functions and ran the tests, and it just worked (and got accepted by the system) straight away. So my main issue had been the weird handling of input_char and output_char of integers, and myself corrupting working code trying to fix it to pass the tests.

So i didn't end up with much time for actual golfing. Just a couple of hours converting while's into for's, replacing all var strings with single digit, initializing vars within for loops and converting the switch statement into a working if statement. But hey, atleast i managed to get some version accepted!

You can find my submitted code on cowtest2.html on the rewrite branch, it's babyproofed with a counter to avoid infinite loops, the submitted version removed the counter and wrapped the final for loop with a ```;``` instead.

Plenty of stuff i could have tried if i had had the time. :/

Some things i only learned now, after the challenge is over, from reading cer and naps62 discussing their versions on slack (with shared source).

So here is a short list of todo optimizations:
- The tokenizer loop could have been rewritten with a sliding window or regex
- The switch could have been reduced further into pure ?: statements
- .length could be reduced by using ```x = 'length'; t[x]```
- removed the returns

For my own reference later on, here are the other guys versions:

naps62's version: https://github.com/naps62/cow/tree/master/src

cer's version:
```
c=p=>{
    w='length';
    y=output_char;
    z=input_char;
    t=[];
    for(n=2;++n<=p[w];x="moo3mOo3moO3mOO3Moo3MOo3MoO3MOO3OOO3MMM3OOM3oom".split(3).indexOf(p.slice(n-3,n)),x<0?0:(t.push(x),n+=2));
    for(b=[p=r=0],e=n=f=-1;++n>=0&n<t[w];b[p]=b[p]||0) {
        m=f<0?t[n]:f;
        f=d=-1;
        u=b[p];
        if(!m){n--;while(d)!t[n--]?d--:t[n]^7?0:d++;n--}
        if(m==7&!u)for(n++;d;t[n++]^7?!t[n]?d++:0:d--);
        if(m==10)for(h of""+u)y(h);
        m^1?
            m^2?
                m^3?
                    m^4?
                        m^5?
                            m^6?
                                m^8?
                                    m^9?
                                        m^11?0:
                                        b[p]=z()-48:
                                    (e?(r=u,e=0):(b[e=-1,p]=r)):
                                b[p]=0:
                            b[p]++:
                        b[p]--:
                    (u?y(String.fromCharCode(u)):b[p]=z()):
                (u^3?(n--,f=u):n=-9):
            p++:
        p--
    }
}
``` 

According to the challenge master these were the top results:
```
tiago        |         426
jpbarraca    |         460
naps62       |         496
mluis        |         542
carlosefr    |         546
mjamado      |         579
JD557        |         580
```
My submitted version had over 800 bytes, so i was nowhere near the top. But again, considering all the difficulties, i'm pretty happy to atleast have a working version. There is supposed to be a writeup by tiago about his approaches to the challenge, i'll try to remember to link to that here, when it's out.
