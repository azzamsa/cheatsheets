+++
title = "Applications"
description = "Applications"
date = 2021-12-01
updated = 2021-12-01
draft = false
weight = 10
sort_by = "weight"
template = "cheats/page.html"
toc = true

[extra]
toc = true
+++

### Sftp in Thunar

``` bash
sftp://user@10.10.10.10/
sftp://user@10.10.10.10/otp
```

### Compressing images

``` bash
# single
convert test-1024x.jpg -quality 50% test-1024x-50p.jpg

# many
for i in \*-1024x.jpg; do convert $i -quality 50% $i-50p.jpg; done;
```

- [How can I compress images? - Ask Ubuntu](https://askubuntu.com/questions/781497/how-can-i-compress-images)

### espeak

``` bash
espeak -v mb-id1 "Selamat anda telah berhasil"
```

- [Text to Speech Berbahasa Indonesia dengan eSpeak \| Catatan](https://arifnd.wordpress.com/2013/08/19/text-to-speech-berbahasa-indonesia-dengan-espeak/)

### dig

``` bash
dig @10.10.10.10 example.com SOA +tcp +short
```

### rsync

``` bash
-a, --archive
-v, --verbose
-r, --recursive
-P, --progres
-z, --compress


# sycn deletion
rsync -avrzP --delete --exclude '*.pyc' -e "ssh -i ~/keys/key.pem" . user@10.10.10.10:/opt/knot/app
# ignore deletion
rsync -avrzP --exclude '*.pyc' -e "ssh -i ~/keys/key.pem" . user@10.10.10.10:/opt/knot/app
```

### scp

``` bash
# remote to local
scp -i ~/keys/key.pem user@10.10.10.10:/tmp/file.tar.gz /tmp
# local to remote
scp -i ~/keys/key.pem -r ./* user@10.10.10.10:/opt/app
```

### Shutdown external hardisk

``` bash
lsblk
fdisk -l

udisksctl power-off -b /dev/sdb1
```


### mpv

``` bash
mpv marimbach-low-bat.ogg --loop --force-window
```

### telnet

``` bash
telnet 10.10.10.10 22
```

### docker

``` bash
# get into the running container

docker exec -it <container-id> ash
```

### Degugging Emacs package

Let's say I want to debug doom-modeline

``` bash
mkdir /tmp/dooms
touch /tmp/dooms/init.el
# then copy the code below into `init.el`

# starts emacs with non-interactive mode to see any error messages
# and check if all the packages downloaded successfully
emacs -q -l test-case/init.el --batch

# starts emacs inactively
emacs -q -l test-case/init.el
```

``` lisp
;; set user-emacs-directory to the directory where this file lives
;; do not read or write anything in $HOME/.emacs.d
(setq user-init-file (or load-file-name (buffer-file-name)))
(setq user-emacs-directory (file-name-directory user-init-file))

;; set custom-file to write into a separate place
(setq custom-file (concat user-emacs-directory ".custom.el"))
(when (file-readable-p custom-file) (load custom-file))

;; configure melpa (and other repos if needed)
(require 'package)
(add-to-list 'package-archives '("melpa" . "https://melpa.org/packages/") t)
(setq package-enable-at-startup nil)
(package-initialize)
(when (not package-archive-contents)
    (package-refresh-contents))

;; bootstrap `use-package'
(setq package-pinned-packages
      '((bind-key           . "melpa")
        (diminish           . "melpa")
        (use-package        . "melpa")))

(dolist (p (mapcar 'car package-pinned-packages))
  (unless (package-installed-p p)
    (package-install p)))

;; install and configure packages
(use-package doom-modeline
  :ensure t
  :init (doom-modeline-mode 1))
```

- [A standalone init.el for Emacs package debugging](https://gonewest818.github.io/2020/03/a-standalone-init.el-for-emacs-package-debugging/)
