# Exercise1.6-1.8解析

## Exercise 1.6
從改寫后的程式碼中可以看到**if**形式被**new-if**程序所代替，本質的區別就是**new-if**是一個程序，由1.1.5節可知，程序在調用時有兩種替換模型，應用次序(Applicative Order)和正常次序(Normal Order)。

在本練習中，**new-if**被調用時，(guess-enough? guess x)、guess、(sqrt-iter (improve guess x) x)皆被當做參數傳入。當在應用次序下調用時，由求值規則可知，(sqrt-iter (improve guess x))將被求值后再被傳入**new-if**，而無論(good-enough? guess radicand)求值如何，(sqrt-iter (improve guess x))都將被求值而形成無限的求值調用。

值得注意的是，在正常次序求值下本練習可以得到預期的結果。