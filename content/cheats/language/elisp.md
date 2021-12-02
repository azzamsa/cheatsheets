+++
title = "Emacs Lisp"
description = "Emacs Lisp"
date = 2021-12-01
updated = 2021-12-01
draft = false
weight = 3
sort_by = "weight"
template = "cheats/page.html"

[extra]
toc = true
+++

### Asynchronous Process

``` lisp
(start-process "my-process" "foo" "ls" "-l" "/bin")
(start-process "" nil "ls" "-l" "/bin")
```

- [Asynchronous Processes - GNU Emacs Lisp Reference Manual](https://www.gnu.org/software/emacs/manual/html_node/elisp/Asynchronous-Processes.html)

## String

### String to number

``` lisp
(string-to-number "256")
(number-to-string 256)
```

- [String Conversion - GNU Emacs Lisp Reference Manual](https://www.gnu.org/software/emacs/manual/html_node/elisp/String-Conversion.html)

## List

### Get list element

``` lisp
(nth 2 '(1 2 3 4))
```

- [List Elements - GNU Emacs Lisp Reference Manual](https://www.gnu.org/software/emacs/manual/html_node/elisp/List-Elements.html)

### Append a list

``` lisp
(append '("a" "b" "c") '("d" "e" "f"))
```

### Join a list

``` lisp
(mapconcat 'identity '("foo" "bar" "baz") ", ")
(string-join '("one" "two" "three") ", ") ; ==> "one, two, three"
(s-join "+" '("abc" "def" "ghi")) ;; => "abc+def+ghi"
(combine-and-quote-strings '("foo" "bar" "baz") ", ") "foo, bar, baz"
```

- [elisp - Is there a function that joins a string into a de&#x2026;](https://stackoverflow.com/questions/12999530/is-there-a-function-that-joins-a-string-into-a-delimited-string)


## Time

### Time of day

`(current-time-string)`

- [Time of Day - GNU Emacs Lisp Reference Manual](https://www.gnu.org/software/emacs/manual/html_node/elisp/Time-of-Day.html)

### Calculate time

``` lisp
`time-subtract`
`time-add`
```

- [Time Calculations - GNU Emacs Lisp Reference Manual](https://www.gnu.org/software/emacs/manual/html_node/elisp/Time-Calculations.html)
