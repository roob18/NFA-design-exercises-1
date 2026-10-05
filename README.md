# NFA-design-exercises-1
1. What gave me trouble
The biggest hurdle was getting used to NFA rules: no arrow just means that path dies. After that clicked, most problems went quickly.

The trickiest ones were #9's "does NOT contain 10" (you can't just flip accept states on an NFA) and "starts with 01 AND ends with 10" (I thought NFAs couldn't do AND, but they can; there's just no easy ε-trick for it).

I did not skip any problems, but I also have done some of the other harder problems by hand. I asked Claude (AI) to check my drawings and explain the NFA vs. DFA rules.

2. Gold strings
#12 (exactly three 1s): 10101 broke my first version. I only had 0 self-loops on the start and accept states, so a 0 between the 1s killed the path. To fix it, every state needs a 0 loop, since a 0 doesn't change the count.
Starts with 01 AND ends with 10: 010 was a case I needed to look at, because the middle 1 belongs to both patterns.
Going forward: figure out what each state "remembers," check every state against every symbol, and test edge cases (spread-out symbols, overlapping patterns, the empty string) in JFLAP.

3. A comment I do have is that NFA's do save lot's of time instead of building a DFA for certain problems.
