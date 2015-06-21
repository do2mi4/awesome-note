# String

###Longest Palindromic Substring
Given a string S, find the longest palindromic substring in S. You may assume that the maximum length of S is 1000, and there exists one unique longest palindromic substring.

Example  
Given the string = "abcdzdcab", return "cdzdc".

##### Analysis
* Brute Force: $$O(n^3)$$

    Check each substring ($$O(n^2)$$) whether is palindromic $$O(n)$$.

* Dynamic Programming: $$O(n^2)$$ with space: $$O(n^2)$$

    Define `P[ i, j ] ← true` iff the substring $$S_{i ... j}$$ is a palindrome, otherwise false.

    Therefore, `P[ i, j ] ← ( P[ i+1, j-1 ] and Si = Sj )`
    
    The base cases are:

    `P[ i, i ] ← true`  
    `P[ i, i+1 ] ← ( Si = Si+1 )`

* Expand Around Center: $$O(n^2)$$ with no extra space

    We know that a palindromic mirrors around its center. Therefore we can check a palindromic by expanding from its center. For a string, we can have $$2N-1$$ centers (N single char, N-1 double chars). For each center, checking time is $$O(n)$$, eventually, we have $$O(n^2)$$ runtime complexity without extra space.
* 

