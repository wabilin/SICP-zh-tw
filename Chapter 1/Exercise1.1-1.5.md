# 練習 (Exercise)

## Exercise 1.1.
Below is a sequence of expressions.What is the result printed by the interpreter in response to each expression?Assume that the sequence is to be evaluated in the order in which it is presented.

下為一系列的表達式。解譯器對每一條表達式打印的結果會是怎樣？假設如下表達式運算的順序和它們書寫的順序一致。

	10
	(+ 5 3 4)
	(- 9 1)
	(/ 6 2)
	(+ (* 2 4) (- 4 6))
	(define a 3)
	(define b (+ a 1))
	(+ a b (* a b))
	(= a b)
	(if (and (> b a) (< b (* a b)))
		b
		a)
	(cond 	((= a 4) 6)
			((= b 4) (+ 6 7 a))
			(else 25))
	(+ 2 (if (> b a) b a))
	(* (cond 	((> a b) a)
				((< a b) b)
				(else -1))
		(+ a 1))
		
## Exercise 1.2.
Translate the following expression into prefix form

將如下表達式翻譯為前綴格式(Lisp表達式)

	5 + 4 + (2 - (3 - (6 + 4/3)))
	-----------------------------
			3(6 - 2)(2 - 7)
				
## Exercise 1.3.
Define a procedure that takes three numbers as arguments and returns the sum of the squares of the two larger numbers.

定義一個程序，接收三個數字作為參數，然後返回其中較大的兩個數字的平方和。

## Exercise 1.4.
Observe that our model of evaluation allows for combinations whose operators are compound expressions.Use this observation to describe the behavior of the following procedure:

我們注意到我們的求值模型中允許組合式的操作子為組合表達式。根據這一觀察描述如下程序的行為:

	(define (a-plus-abs-b a b)
		((if (> b 0) + -) a b))
		
## Exercise 1.5.
Ben Bitdiddle has invented a test to determine whether the interpreter he is faced with is using applicative-order evaluation or normal-order evaluation.He defines the following two procedures:

Ben Bitdiddle發明了一個測試來判斷他用的解譯器是應用次序求值還是正常次序求值。他定義了如下兩個程序:

	(define (p) (p))
	(define (test x y)
		(if (= x 0) 
			 0 
			 y))
			 
Then he evaluates the expression

然後他對如下表達式求值

	(test 0 (p))
	
What behavior will Ben observe with an interpreter that uses applicative-order evaluation?What behavior will he observe with an interpreter that uses normal-order evaluation?Explain your answer.(Assume that the evaluation rule for the special form **if** is the same whether the interpreter is using normal or applicative order:The predicate expression is evaluated first,and the result determines whether to evaluate the consequent or the alternative expression.)

在一個使用應用次序求值的解譯器中Ben會觀察到什麼行為?在一個使用正常次序求值的解譯器中Ben會觀察到什麼行為?解釋你的答案。(假設無論在正常次序或者應用次序中特殊格式**if**的求值都是一樣的:首先對判定表達式進行求值,並且由其結果決定對結果還是其他候選表達式求值。)