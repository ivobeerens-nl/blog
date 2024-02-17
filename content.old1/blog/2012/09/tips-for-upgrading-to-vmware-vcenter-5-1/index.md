---
titl
: "Tips fo
 upg


i
g to VMw


 vC

t

 5.1"


t
: "2012-09-13T12:53:12.000Z"
c
t
go
i
s: 
  - "vc

t

-2"
  - "vSph


51"
t
gs: 
  - "vc

t

"
  - "vSph


51"

utho
: Ivo 





s
---

- vSph


 5.1 upg


i
g gui

, fou

 [h


](http://pu
s.VMw


.com/vSph


-51/i


x.jsp?topic=%2Fcom.VMw


.vSph


.upg



.
oc%2FGUI
-18
7
4

-C24
-49C
-

76-13285157
29F.html)
- Upg


i
g to vC

t

 5.1 

st p

ctic
s, fou

 [h


](http://k
.VMw


.com/s
lfs

vic
/
ocum

tLi
kI
t.
o?mic
osit
I
=&popup=t
u
&l

gu
g
I
=&
xt



lI
=2021193)
- Ov

vi
w of upg


i
g f
om vC

t

 S

v

 5.0 to vC

t

 S

v

 5.1, fou

 [h


](http://k
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
=2032283)


ft

 th
 
TFM stuff ch
ck th
 followi
g:

- M
k
 su

 th
 SQL S

v

 
uth

tic
tio
 ch
ck
ox is s
t to **SQL S

v

 


 Wi

ows 
uth

tic
tio
 mo

** o
 th
 SQL s

v

. Mo

 i
fo fou

 [h


](https://www.ivo





s.
l/2012/09/11/vc

t

-5-1-si
gl
-sig
-o
-


o
-
u
i
g-i
st
ll
tio
/).
- Th
 SQL s

v

 s

vic
 is list

i
g to po
t 1433. You c

 ch
ck this 
y usi
g th
 followi
g comm


:

> **_

tst
t –
 | fi

 “1433”_**

if th
 SQL S

v

 is 
ot list

i
g o
 po
t 1433, us
 th
 followi
g st
ps:

1. Op

 SQL S

v

 Co
figu

tio
 M


g

2. 
xp


 th
 SQL S

v

 

two
k co
figu

tio

3. Click o
 th
 “P
otocols fo
 **SQL
XP\_VIM**”. **SQL
XP\_VIM** is th
 

m
 of th
 SQL i
st

c

4. S
l
ct TCP/IP – P
op

ti
s – IP 




ss
s t

 

 sc
oll 
ow
 to **IP
LL,** 

t

 v
lu
 **1433** i
 th
 TCP Po
t fi
l

5. 

st

t th
 SQL S

v

 s

vic


[![im
g
](im
g
s/im
g
_thum
8.p
g "im
g
")](im
g
s/im
g
9.p
g)

- Op

 th
 sql sc
ipt c
ll

 “
s
IMSLit
MSSQLS
tupT

l
sp
c
s.sql”  (fou

 i
 th
 vC

t

 ISO i
 …..
Si
gl
 Sig
 O



Sc
ipts
SSOS

v


sch
m

mssql
) 


 customiz
 th
 loc
tio
 of th
 \*.m
f, \*.

f 


 \*.lf
 fil
 to you
 



s. 
ft

 customizi
g th
 SQL fil
 
x
cut
 it 


 m
k
 su

 th
 
S
 

t


s
 is c


t

.

[![im
g
](im
g
s/im
g
_thum
9.p
g "im
g
")](im
g
s/im
g
10.p
g)

- If i
st
lli
g Si
gl
 Sig
 O
 i
 
 IPv6 

vi
o
m

t ch
ck [this](http://k
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
=2035454) K
 

ticl

- If 
ft

 upg


i
g th
 vC

t

 s

vic
s h

gs o
 st

tup ch
ck [this](http://k
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
=2035623) K
 

ticl

- Th
 w


i
g “**Th
 Fully Qu
lifi

 
om
i
 

m
 c


ot 

 

solv

. If you co
ti
u
 th
 i
st
ll
tio
, som
 f

tu

s might 
ot wo
k co


ctly**” 
pp


 
u
i
g th
 i
st
ll
tio
. M
k
 su

 th
 

v

s
 

S 

co

 
xist i
 th
 

v

s
 lookup Zo

s.  T
st this with th
 
slookup comm




[![im
g
](im
g
s/im
g
_thum
14.p
g "im
g
")](im
g
s/im
g
15.p
g)

- Th
 vC

t

 S

v

 s

vic
s h

g o
 st

up 
ft

 upg


i
g to vC

t

 S

v

 5.1. Mo

 i
fo c

 

 fou

 [h


](http://k
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
=2035623).






