+++
title = "Emacs Lisp"
description = "Emacs Lisp"
date = 2021-12-01
updated = 2021-12-01
draft = false
weight = 10
sort_by = "weight"
template = "cheats/page.html"
toc = true
+++

### Asynchronous Process

``` lisp
(start-process "my-process" "foo" "ls" "-l" "/bin")
(start-process "" nil "ls" "-l" "/bin")
```

- [Asynchronous Processes - GNU Emacs Lisp Reference Manual](https://www.gnu.org/software/emacs/manual/html_node/elisp/Asynchronous-Processes.html)

