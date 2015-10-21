# Exercise 1.6-1.8

## Exercise 1.6:
Alyssa P.Hacker doesn't see why **if** needs to be provided as a special form. "Why can't I just define it as an ordinary procedure in terms of **cond**?" she asks.Alyssa's friend Eva Lu Ator claims this can indeed be done,and she defines a new version of **if**:

Alyssa P.Hacker 不明白為什麼**if**需要被當成一個特殊的形式。她疑惑道：“為什麼我不能就使用**cond**來定義一個普通的程序來代替它呢？”。Alyssa的朋友Eva Lu Ator說這確實可以辦到，於是她定義了一個新版本的**if**:

	(define (new-if predicate then-clause else-clause)
	  (cond (predicate then-clause)
	  		 (else else-clause)))
	  		 
Eva demonstrates the program for Alyssa:

Eva為Alyssa演示了程式:

	(new-if (= 2 3) 0 5)
	5
	(new-if (= 1 1) 0 5)
	0
	
Delighted,Alyssa uses **new-if** to rewrite the **square-root** program:

Alyssa非常高興地使用**new-if**來重寫了**square-root**程式:

	(define (sqrt-iter guess x)
	  (new-if (good-enough? guess x)
	  		   guess
	  		   (sqrt-iter (improve guess x) x)))
	  		   
What happens when Alyssa attempts to use this to compute square roots?Explain.	  		   