# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

Asymptotic analysis ignores constant variables, looking at long term growth to compare 
timing instead, which can affect how a program actual performs in practice for smaller 
inputs. Actual performance also depends on hardware and software, which differ for each 
implementation of a program. Different programming langauges can also affect how a program
actually performs compared to its asymptotic analysis. 

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

Searching a binary search tree has a best case time complexity of $O(log(n))$. Given 1,000 elements took 5 seconds, 
and log_2(10,000) = ~13.3 and log_2(1,000) = 10. Then the best total time to search 10,000 elements would be 5 * (13.3/10), 
or about 6.65 seconds. The worst case time complexity is $O(n)$. Given $O(1,000) = 5$, I would guess that $O(10,000) = 50$.
So I would assume that finding the same element in a binary search tree with 10,000 elements would take somewhere between 6.65
and 50 seconds. 

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

//hardware/compiler
One way the code could be affected is branch prediction failures. The CPU uses branch prediction in an attempt to optimize the code, but as the tree size gets larger, the more likely it is to have irregular/unpredictable branches, therefore slowing down the CPU as it must discard previous instructions before beginning again. 

The way the tree was implemented (recursive calls, memory, etc.) could also affect how the program handled a much larger tree, therefore taking longer to search through. 

Another possible reason is that the tree was not properly balanced, which would become a much larger problem with the significantly larger tree size. The tree becomes more unorganized the deeper it goes, and in the worst cases essentially turns into a linked list, negating the optimal time complexity. 

Add your answers to this markdown file.

### Sources and Plagiarism 
Sources: 
https://cs.stackexchange.com/questions/84618/time-complexity-of-searching-an-element-in-binary-search-tree

https://www.geeksforgeeks.org/applications-advantages-and-disadvantages-of-binary-search-tree/

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
