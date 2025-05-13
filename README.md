# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.


In quicksort, a pivot is considered to be "good" if it splits an array into two roughly equal sizes. This ensures balanced recursion and optimal performance of ($\Theta$(n log n)). However, in an array of n elements, a pivot is considered "good" if it falls in the middle third of the array's rank order.
Therefore, for a large n, the probability that the first element is a good pivot is 33%.
For a Median of Three Pivot, this method picks the median value among the first, middle, and last elements in the current array. This results in a 44% probability that a "good" pivot will be chosen. Therefore, the Median of Three has a statistically higher chance of picking a "good" pivot.

First Element Probability:
Middle Range = $[n/3 +1, 2n/3]$
P= $([2n/3] - [n/3] +1)/n ≈ (n/3)/n = 1/3 = 33%$

Median of Three Probability:
Divide the array into 3 equal parts, take 3 samples
Left range: $[1, n/3]$
Middle range: $[n/3, 2n/3]$;
Right range: $[2n/3, n]$; 

Case 1:
6 permutations where smallest is from the Left(L), largest is from the Right(R), and median is from Middle (M)
(LMR, LRM, MLR, MRL, RLM, RML)
P_1 = $6 \times (1/3)^3$= $6/27$

Case 2:
3 Permutations where 2 are from the Middle, 1 is from the Left
(MML, MLM, LMM)
P_2 = $3 \times (1/3)^3 \times (1/3) = 3/27$

Case 3:
3 permutations where 2 are from the Middle, and 1 is from Right
(MMR, MRM, RMM)
P_3 = $3 \times (1/3)^2 \times (1/3) = 3/27$

P(median in middle third) = P1 + P2 + P3 = $(6/27) + (3/27) + (3/27) = 12/27 = 4/9$ \approx 44%

“I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.”


For this assignment, I asked Chat GPT for help regarding the formatting and readability of my writing. I also used the website (upyesp)[https://www.upyesp.org/posts/makrdown-vscode-math-notation/] as a quick guide for improving the presentation of the mathematical expressions.
