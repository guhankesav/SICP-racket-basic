# SICP-racket-basic
Contains basic racket programs of SICP course

-  1. Factorial Recursive.rkt

```
#lang racket
(define (factorial n)
   (if (= n 1)
     1
      (* n (factorial (- n 1))))) 
```
      
 - 2. Factorial Iterative.rkt

```
#lang racket
(define (fact-iter product counter max-count)
   (if (> counter max-count)
        product
        (fact-iter (* counter product)
                       (+ counter 1)
                       max-count)
    )
)
(define (factorial n)
(fact-iter 1 1 n))
 ```
 
 
