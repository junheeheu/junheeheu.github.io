---
layout: post
title:  "Ubuntu(Linux) USB 외장하드 Mount"
date:   2018-11-02
categories: [ubuntu]
tags: [2018, ubuntu, linux, mount]
---

Linux 외장하드 mount 시키기
================================

disk 정보 받기
--------------------------------
~~~
fdisk -l
~~~
![step1](https://lh3.googleusercontent.com/_Mf0BoxxHJPKCjrqK7PVylHJ2v8vUBfWI3OEnLoTBJ100TgFIAalKSZ3cAUSeBADFRGUY0ZbkF2yaFWLv4623zWd4wqDDaf2UTZ736lFaEDQ9cYZcZtDDfd7cEZ7Fxj62glQDvB9DbCB1lFCRZ6-PMrvZoD5mf-EQs3NqG2FexHxF1QbtiBmPYuG09SQb81g_a2qsNWNAN7LS2KFpaIGQRQEsCNEiK0spG4-6cVfTggv9w0PaTSZjxWpAgpt2aQHBDJRkG9clc8a3ry-cd2k-YbVnoEJB9iUrW-mhJorF6IKV1ZbfO4ijwaEeEP1Y5F4YXElMH3d4C9QroiVGqZC4dLVIh2_HrYpZUaO4o2GEBc7yxszWQXC6d7it0XDDIuBdR9Sv_aKM4nxRBdBaPNejBA1mygU0SA4V-9ghAVRnruaT6qIG0k0HmlIr_i1CLB0z3OM_PFNuHCI-rJl1UJSQs4G1tR3OMRvl8ex91-h_m3NGbVh-Unrdbzrz7X3qxpmRaBdeJy8Dwl4boZzLxdaiI2ljtNY2xPs9olO-95YV8Zltekjy_hvVmZYBnIPQrVU4JL9qX14MM8ZjSnkzFDI1q2AiTBgPmJdv4kcNbZzchvfK-I50xyx7Aq6hyZp9p4ddaqxjc2B34mLmYHsWX5SXM9IgQ=w686-h435-no)

그림에서 보면 NTFS Type인 것을 알 수 있다.

mount 시키기
-----------------------
* mount 위치 생성
~~~
mkdir ~/usb
~~~
* Mount (NTFS)
~~~
sudo mount -t ntfs-3g /dev/sdb1 ~/usb
~~~
* Mount (FAT32)
~~~
mount -t vfat /dev/sdb1 ~/usb -o uid=1000,gid=1000,utf8,dmask=027,fmask=137
~~~