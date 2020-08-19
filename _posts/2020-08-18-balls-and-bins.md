---
layout: post
title: Balls and Bins
---

I've been having some trouble with identifying distinguishable and indinguishable objects in probability problems and wanted to write a blog to clear up some concepts. 

post on how order is related to permutations, combinations, and common pitfalls I've encountered. 

We have four possible problems involving $m$ balls and $n$ bins:

-Distinguishable balls, distinguishable bins: $n^m$ \\
-Indistinguishable balls, distinguishable bins: $(m+n-1)C(n-1)$ \\
-Distinguishable balls, indistinguishable bins: casework on each of the possible partitions and duplicate sizes need to be accounted for \\
-Indistinguishable balls, indistinguishable bins: number of possible partitions

What happens when we move into probability? When we look at probability as $\\frac\{# of successes\}\{all possibilities\},$ it doesn't matter if we make order matter or if we don't care about order as long as we're doing the same thing in the numerator and denominator. Does this translate when we have the idea of balls and bins? The key lies in having a very clear idea about what your sample space is. 

Consider the problem where we have 5 chocolate chips and 3 cookies. What is the probability that each cookie has at least one chocolate chip per cookie? What is our sample space? We want to define our sample space as things that are equally likely to happen, so counting the number of times something happens is meaningful. 

What is the sample space if we look at this problem from the perspective of distinguishable cookies (bins) and distinguishable chips (balls)? enumerate chocolate chips 1, ..., 5 and the cookies a, b, c. We expect there to be $3^5$ possibilities The sample space $\Omega = \\{\|\|12345, \|1\|2345, \|2\|1345, \|3\|1245, \|4\|1235, \|5\|1234, \|12\|345, \|13\|245, \|14\|235, \|15\|234, \|23\|145, \|24\|135, \|25\|134, \|34\|125, \|35\|124, \|45\|123, etc\\}$. Each of these events happens with probability 1/243. How many of them have at least one chocolate chip per cookie? Do complementary counting: the number of elements in the sample space that have at least one cookie with no chips in it is (243-(3+30+60))/243 = (81-31) /81 = 50/81.

How about distinguishable cookies and indistinguishable chips? The sample space contains 7C2 = 21 elements. If we want to ensure that all the cookies have chips, we can prefill them with the indistinguishable chips. Now 2 chips remain to be inserted into any cookie. This can be done 4C2=6 ways. So the probability that each cookie has at least one chip is 6/21 = 2/7. 

Hold on, 50/81 != 2/7. What went wrong? It turns out that with distinguishable cookies and indistinguishable chips, each event in the sample space doesn't have the same probability of occuring, so we can't count the number of successes and divide by the number of total possibilities. For example, if the chips are ppppp and the cookies are abc, the probability that $\|ppppp\|$ occurs is less than the probability that $\|pp\|ppp$ happens. 

How about indistinguishable cookies and indistinguishable chips? Here our sample space is {005, 014, 023, 113, 122}. Also has unequal probabilities.  

The conclusion is to think of probability using distinguishable balls and distinguishable bins always. 

