+++
title = "Fish Shell"
description = "Fish Shell"
date = 2021-12-01
updated = 2021-12-01
draft = false
weight = 10
sort_by = "weight"
template = "cheats/page.html"

[extra]
toc = true
+++

### Change default shell to fish

``` bash
chsh -s `which fish`
```

### For-loop in Range

``` fish
for i in (seq 1 50); sleep 3 && curl -s -I "https://httpbin.org/anything"; end
```

``` fish
for i in (seq 1 50)
    sleep 3 && curl -s -I "https://httpbin.org/anything"
end
```


