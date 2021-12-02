+++
title = "Python"
description = "Python"
date = 2021-12-01
updated = 2021-12-01
draft = false
weight = 2
sort_by = "weight"
template = "cheats/page.html"

[extra]
toc = true
+++

### Test specific item using Pytest

``` bash
-s                    shortcut for --capture=no.
-v, --verbose         increase verbosity.
--pdb                 start the interactive Python debugger on errors

pytest -v -s tests/integration/
pytest -v -s tests/integration/test_base.py
pytest -vv -s tests/integration/test_base.py::test_get_user --pdb
```



