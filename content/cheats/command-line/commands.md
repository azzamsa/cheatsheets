+++
title = "Commands"
description = "Commands"
date = 2021-12-01
updated = 2021-12-01
draft = false
weight = 10
sort_by = "weight"
template = "cheats/page.html"
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


rsync -avrzP --delete --exclude '*.pyc' -e "ssh -i ~/keys/key.pem" . centos@10.10.10.10:/opt/knot/app
```

### scp

``` bash
scp -i /path/to/key.pem app.tar <username>@<public-ip>:~/your/destination/dir/
```

## Shutdown external hardisk

``` bash
lsblk
fdisk -l

udisksctl power-off -b /dev/sdb1
```





