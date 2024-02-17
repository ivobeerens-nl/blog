---

utho
: Ivo 





s
titl
: "VMw


 
SX s

v

s u


l
 to m


g
 vi
 VIC, SSH o
 iLO s
ssio
"


t
: "2009-01-06T19:25:56.000Z"
c
t
go
i
s: 
  - "
ug"
  - "VMw


"
u
l: /2009/01/06/VMw


-
sx-s

v

s-u


l
-to-m


g
-vi
-vic-ssh-o
-ilo-s
ssio
/
---

To

y i h

 
 

sty p
o
l
m with 
 VMw


 

vi
o
m

t. Som
 VMw


 
SX s

v

s w


 
isco


ct

 f
om vC

t

. T
i

 to co


ct th
 VMw


 
SX hosts usi
g th
 VIC,  
ut th
t w
s 
ot possi
l
. I w
s u


l
 to logi
 vi
 SSH co


ctio
, co


ct with HP iLO to th
 HP 
l


 

closu

 


 
i
 
 

mot
 co


ctio
 to th
 co
sol
. Th


 wh


 H
 


o
s o
 th
 sc



. I t
i

 to log i
 th
 co
sol
, 
ft

 typi
g th
 p
sswo

 


 hit th
 

t

 
utto
 th
 logi
 p
ompt 

-
pp


s 
v

y tim
 i t
y.  **Th
 VMw


 
SX s

v

s w


 
ot m


g


l
 

ymo

, 

MM.**

Th
 VMs o
 th
 
isco


ct

 VMw


 
SX s

v

s w


 still 
u

i
g 


 h

 

P 



l

. Th
 o
ly solutio
 so f

 w
s to log i
 vi
 

P 


 shut
ow
 th
 VMs.  I 
i
 this fo
 o

 VMw


 
SX s

v

. 
ft

 shutti
g 
ow
 
ll VMs, i 
i
 
 col
 


oot of th
 VMw


 
SX s

v

. 
ft

 s
v


l mi
ut
s th
 VMw


 
SX s

v

 


pp


s i
 vC

t

. I w

t to th
 log fil
s 


 fou

 th
 followi
g 


o
:

fo
k: 

sou
c
 t
mpo


ily u

v
il

l


[![clip_im
g
002](im
g
s/clip-im
g
002-thum
.jpg "clip_im
g
002")](im
g
s/clip-im
g
002.jpg)


ft

 s


chi
g th
 VMw


 K
owl

g
 

s
 i fou

 th
 followi
g 

ticl
:

[

fu
ct cims

v


 p
oc
ss
s s


 o
 VMw


 
SX 3.5 
u

i
g h


w


 m


g
m

t 
g

ts](http://k
.VMw


.com/s
lfs

vic
/mic
osit
s/s


ch.
o?l

gu
g
=

_US&cm
=
ispl
yKC&
xt



lI
=1007887)

It looks lik
 w
 h
v
 th
 s
m
 symptoms:

- U


l
 to logi
 th
ough SSH to VMw


 
SX host
    
- U


l
 to logi
 o
 loc
l S

vic
 co
sol

    
- H
 


o
s.
    

I 
i
 “ps-
f” o
 th
 co
sol
 of oth

 VMw


 
SX s

v

s th
t w


 still wo
ki
g 


 

tu



 
 coupl
 of thous


s cims

v


 

fu
ct p
oc
ss
s. Holy shit.

[![clip_im
g
002[5]](im
g
s/clip-im
g
0025-thum
.jpg "clip_im
g
002[5]")](im
g
s/clip-im
g
0025.jpg)


ft

 

st

ti
g th
 p
g
sus s

vic
 o
 th
 host th
 cims

v


 

fu
ct p
oc
ss
s 


 
w
y. 
ow th


 


 134 p
oc
ss
s 
ctiv
.

It s

ms th
t o

 ISCSI t

g
t w
s offli

 


 th
t 
ll th
 VMw


 
SX s

v

s t
i

 to co


ct to th
 ISCSI t

g
t 
v

y 60 s
co

s, th
 f
il

 logi
 
tt
mps 

sults i
 thous


s of cims

v


 

fu
ct p
oc
ss
s. This is 
 
ug 


 VMw


 will 

l

s
 
 p
tch fo
 this 

sty p
o
l
m. W
tch you
 p
tch
s.

I 
i
 
 t
mpo


ily fix 
y sch

ul
 

st

ti
g th
 p
g
sus s

vic
 
v

y 

y o
 
v

y VMw


 
SX s

v

 usi
g th
 [pli
k](http://www.chi

k.g






.o
g.uk/~sgt
th
m/putty/
ow
lo

.html) utility.

W
tch you
 p
oc
ss
s f

qu

tly o
 you
 VMw


 
SX hosts!

\[


v

tic

l\]






