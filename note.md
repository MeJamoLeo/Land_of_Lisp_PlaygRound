# Land of Lisp draft note

- write on a file
```clisp
sbcl --script file.lisp
```


- Addition
```clisp
[1]> (+ 3 ( * 2 4))
11
```

- Exit Clisp
```clisp
[2]> (quit)
Bye.
```
- Global Variables
    - 'defparameter'
    ```clisp
    [5]> (defparameter *small* 12)
    *SMALL*
    [5]> *small*
    12
    [5]> (defparameter *small* 0)
    *SMALL*
    [5]> *small*
    0
    ```
        - 上書き可能
    - 'defvar'
    ```clisp
    [5]> (defparameter *small* 12)
    *SMALL*
    [5]> *small*
    12
    [5]> (defparameter *small* 0)
    *SMALL*
    [5]> *small*
    0
    ```
        - 上書きできない
- Global Function `defun`
    ```
    (defun function_name (arguments) ... )
    ```
- `ash`
looks at a number in binary form, then shifs its binary bits to the left or right.
11 = 8 + 2 + 1 = 1011 (base 2)
Shift left ... 10110 = 16 + 4 + 2 = 22
Shift right ... 101 = 4 + 1 = 5
```
[1]> (ash 11 1)
22
[2]> (ash 11 -1)
5
```

- `guess-my-number`
```lisp
(defparameter *small* 1)
(defparameter *big* 100)

(defun guess-my-number () 
  (ash (+ *small* *big*) -1 ))
```
101 -> 
