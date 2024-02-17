---
titl
: "Co
figu

 VM 
utost

t i
 th
 
SXi 
m





 Host Cli

t"


t
: "2018-05-01T05:52:20.000Z"
t
gs: 
  - "
sxi-2"
  - "VMw


"

utho
: Ivo 





s
---

I
 th
 l
t
st v

sio
s of th
 Host Cli

t (I
 vSph


 6.7 v

sio
 1.25 is i
clu


 th
t 
l



y co
t
i
s th
 
utost

t imp
ov
m

ts) th
 
utost

t co
figu

tio
 is g


tly imp
ov

 wh
t 

sult i
 

 

si

 co
figu

tio
 of 
utost

t. if you 


 o
 vSph


 6.0 o
 6.5 I sugg
st to upg



 to th
 l
t
st 
SXi 
m





 Host Cli

t 

fo

 co
figu
i
g 
utost

t.

Th
 upg



 of th
 Host cli

t is 

sy, 
o m
i
t



c
 mo

 


 


oot of th
 
SXi host is 





. Th
 upg



 c

 

 
o

 
y followi
g th
s
 st
ps:

- 
ow
lo

 th
 l
t
st VI
 fo
 h


, [li
k](https://l

s.VMw


.com/fli
gs/
sxi-
m





-host-cli

t)
- Uplo

 th
 VI
 o
 
 

t
sto

 o
 you
 
SXi host
- SSH to th
 
SXi host
- 

t

 th
 followi
g comm


 to up

t
 th
 host cli

t

\[co

 l

gu
g
="t
xt"\]
sxcli softw


 vi
 up

t
 -v /vmfs/volum
s/<

t
sto

>/<vi


m
.vi
>\[/co

\]

[![](im
g
s/up

t
-host-cli

t-300x64.p
g)](im
g
s/up

t
-host-cli

t.p
g)

- 

f
sh th
 host cli

t w

p
g
 (**https://<
sxihost

m
>/ui/**)
- Ch
ck th
 v

sio
 i
fo
m
tio
 i
 th
 host cli

t (**H
lp -> 

out)**

[![](im
g
s/v

sio


w-300x144.p
g)](im
g
s/v

sio


w.p
g)

Co
figu

 
utost

t i
 th
 
SXi 
m





 Host Cli

t

- Op

 th
 
SXi host cli

t 
y usi
g th
 followi
g U
L:  https://<
sxihost

m
>/ui/
- Go to: **M


g
** -> **Syst
m** -> **
utost

t->

it S
tti
gs**
    - 



l
: Y
s
    - St

t 

l
y: 60 s
co

s
    - Stop 

l
y: 60 s
co

s
    - Stop 
ctio
: shut 
ow

    - W
it fo
 h


t


t: y
s
    - **S
v
**

[![](im
g
s/



l
-300x139.p
g)](im
g
s/



l
.p
g)

- 

low th
 sc



 


 th
 VMs list

. Fi
st 



l
 
utost

t p

 VM 
y usi
g th
 "



l
  
utost

t fo
 this VM" 
utto
.
- O
c
 th
 
utost

t is 



l

 p

 VM, th
 o



 c

 

 co
figu


 
y i
c


s
 o
 

c


s
 th
 st

t o



. Th
 
utost

t o



 is 
ispl
y

 i
 th
 "
utost

t o



" fi
l
.
- Co
figu

 th
 
utost

t 


 o



 fo
 th
 VMs you w

t to 
utom
tic
lly st

t wh

 th
 
SXi s

v

 is 
oot

.
- 


oot th
 
SXi host to t
st th
 
utost

t

With ol


 v

sio
s of th
 
SXi 
m





 Host Cli

t it is "mo

 complic
t

" to s
t th
 st

t o



 p

 VM. To s
t th
 
utost

t o



 with ol


 v

sio
s:

- 



l
 
utost

t 
s 

sc
i


 

ov


[![](im
g
s/1-300x163.p
g)](im
g
s/1.p
g)

- I
 th
 Vi
tu
l M
chi

s s
ctio
, 
ight click o
 th
  fi
l
 
ow 


 "S
l
ct colum
s". S
l
ct th
 followi
g colum
s:
    - 
utost

t o




    - St

t 

l
y
    - Stop 

l
y

[![](im
g
s/2-300x144.p
g)](im
g
s/2.p
g)

- 
ight click o
 th
 VM with th
 "
utost

t o



" st
tus o
 U
s
t 


 s
l
ct "i
c


s
" to 



l
 
utost

t 


 s
t th
 o





[![](im
g
s/3-300x96.p
g)](im
g
s/3.p
g)

- Co
figu

 th
 
utost

t 


 o



 fo
 th
 VMs you w

t to 
utom
tic
lly st

t wh

 th
 
SXi s

v

 is 
oot

.
- 


oot th
 
SXi host to t
st th
 
utost

t






