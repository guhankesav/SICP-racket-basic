# SICP-racket-basic


The Racket language is a modern dialect of Lisp and a descendant of the Scheme. It is designed as a platform for programming language design and implementation.

![language-racket-andremayer](https://user-images.githubusercontent.com/47454368/147880113-7718f311-f339-4495-9dd2-5743fc1be6df.jpg)

Basic racket programs of SICP course

1. Factorial Recursive.rkt

```
#lang racket
(define (factorial n)
   (if (= n 1)
     1
      (* n (factorial (- n 1))))) 
```
      
2. Factorial Iterative.rkt

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
 
 3. Fibonacci Tree Recursive.rkt

```
#lang racket
(define (fib n)
   (cond ( (= n 0) 0)
             ( (= n 1) 1)
             (else ( + (fib (-  n 1))
                            (fib (- n 2))
                      )
              )
    )
)
```

4. Fibonacci Iterative.rkt

```
#lang racket
(define (fib-iter a b count)
   (if (= count 0)
        b
        (fib-iter (+ a b) a (- count 1))))
(define (fib n)
(fib-iter 1 0 n))
```

5. Exponential Recursive.rkt

```
#lang racket
(define (expt b n)
   
   (if (= n 0)
        1
        (* b (expt b (- n 1)))))
        
```

6. Exponential Iterative.rkt

```
#lang racket
(define (expt-iter b counter product)
   (if (= counter 0)
        product
        (expt-iter b 
                        (- counter 1)
                        (* b product))))

(define (expt b n)
   (expt-iter b n 1))
```


7. Fast Exponential.rkt

```
#lang racket
(define (even? n) (= (remainder n 2)  0))

(define (square n) (* n n))

(define (fast-expt b n)
   (cond ((= n 0) 1)
             ((even? n) (square (fast-expt b (/ n 2))))
             (else (* b (fast-expt b (- n 1))))))
             
```

8. GCD Recursive.rkt

```
#lang racket
(define (gcd a b)
(if (= b 0)
   a
   (gcd b (remainder a b))))
```
