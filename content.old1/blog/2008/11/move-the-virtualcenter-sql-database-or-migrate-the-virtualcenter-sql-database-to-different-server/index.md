---

utho
: Ivo 





s
titl
: "Mov
 th
 Vi
tu
lC

t

 SQL 

t


s
 o
 mig

t
 th
 Vi
tu
lC

t

 SQL 

t


s
 to 
iff



t s

v

."


t
: "2008-11-29T20:39:42.000Z"
c
t
go
i
s: 
  - "vC

t

"
  - "VMw


"
t
gs: 
  - "vC

t

"
  - "VMw


"
u
l: /2008/11/29/mov
-th
-vi
tu
lc

t

-sql-

t


s
-o
-mig

t
-th
-vi
tu
lc

t

-sql-

t


s
-to-
iff



t-s

v

/
---

VMw


 

l

s

 two 

w h


y K
 

ticl
s 

out how to mov
 o
 mig

ti
g  th
 SQL Vi
tu
lC

t

 

t


s
 to 
iff



t s

v

.

To mov
 th
 

t


s


Wh

 

loc
ti
g you
 SQL 

t


s
:
- To mov
 SQL S

v

 

t


s
s to 
 

w loc
tio
 
y usi
g 

t
ch 


 
tt
ch fu
ctio
s i
 SQL S

v

, s

 Mic
osoft K
 

ticl
 [](http://suppo
t.mic
osoft.com/k
/224071/

-us)[http://suppo
t.mic
osoft.com/k
/224071/

-us](http://suppo
t.mic
osoft.com/k
/224071/

-us)
- If you 


 usi
g th
 Copy 

t


s
 Wiz


 i
 SQL S

v

 2000.
- Up

t
 th
 

t
sou
c
 (
S
) i
 th
 O

C 

mi
ist

to
 to 

fl
ct 

y ch

g
s m


.
- If 
ith

 th
 

t


s
 logi
 o
 p
sswo

 ch

g

 
u
i
g th
 

loc
tio
, Vi
tu
lC

t

 must 

 up

t

 to with th
 

w c




ti
ls. Fo
 mo

 i
fo
m
tio
, s

 th
 _Mo
ifyi
g th
 us



m
 


 p
sswo

 Vi
tu
lC

t

 us
s to co


ct to th
 

t


s
 s

v

_ s
ctio
 of [T
ou
l
shooti
g th
 

t


s
 

t
 sou
c
 us

 
y Vi
tu
lC

t

 S

v

 (1003928)](http://k
.VMw


.com/k
/1003928).
[



 th
 K
 

ticl
 h


.](http://k
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
=7960893)

Mig

t
 th
 

t


s
 to 
 

w s

v

:
- Shut
ow
 th
 Vi
tu
lC

t

 S

v

 s

vic
. Fo
 mo

 i
fo
m
tio
, s

 [Stoppi
g, st

ti
g, o
 

st

ti
g th
 Vi
tu
lC

t

 S

v

 s

vic
 (1003895)](http://k
.VMw


.com/k
/1003895).
- T
k
 
 

ckup of th
 SQL 

t


s
.
- If th
 SQL 

t


s
 is 
lso 

i
g mov

, c


t
 
 s
co

 i
st

c
 of you
 

t


s
 


 us
 th
 v


o
's tools to mig

t
 th
 

t
.**
ot
**: Fo
 SQL S

v

, us
 Mic
osoft's Copy 

t


s
 Wiz


.
- C


t
 th
 
pp
op
i
t
 Syst
m 
S
 co


ctio
s o
 th
 

w Vi
tu
lC

t

 S

v

 host.
- 

gi
 th
 i
st
ll
tio
 of th
 Vi
tu
lC

t

 softw


 o
 th
 

w s

v

. If you 


 i
st
lli
g Vi
tu
lC

t

 i
 
 vi
tu
l m
chi

, gui

li

s fo
 

ployi
g Vi
tu
lC

t

 i
 
 vi
tu
l m
chi

, i
clu
i
g sizi
g, i
st
ll
tio
 


 fu
ctio

lity.
- Wh

 p
ompt

, s
l
ct **Us
 
xisti
g 

t


s
**, 


 p
ovi

 th
 co


ct c




ti
ls to th
t 

t


s
.
- Wh

 p
ompt

, s
l
ct to **
ot 

-i
iti
liz
 th
 

t
**, 
s this 


s
s 
ll you
 i
v

to
y 

t
.
- 


oot th
 vi
tu
l m
chi

 wh

 th
 i
st
ll
tio
 is fi
ish

.
- Wh

 you fi
st st

t th
 Vi
tu
lC

t

 Cli

t, it m
y 
sk fo
 lic

s
s. Co
figu

 th
 lic

s
s 
s you h

 p

viously i
 you
 

vi
o
m

t. Fo
 mo

 i
fo
m
tio
 

out lic

si
g fo
 
SX S

v

 3 hosts, s

 th
 I
st
ll
tio
 Gui

. Fo
 mo

 i
fo
m
tio
 

out lic

si
g fo
 
SX S

v

 3i hosts, s

 th
 S
tup Gui

. You 


 
ow 

l
 to s

 th
 s
m
 s
tti
gs 


 co
figu

tio
 

t
ils.**
ot
**: If th
 IP 




ss of th
 

w Vi
tu
lC

t

 S

v

 h
s ch

g

 you
 
SX S

v

s must 

 m


 
w


 of th
t ch

g
, oth

wis
 th
 
SX S

v

s co
ti
u
 to s


 th
i
 h


t


ts to th
 o
igi

l IP 




ss of Vi
tu
lC

t

 


 
pp


 
s 
ot 

spo

i
g.To co


ct this situ
tio
: 
    1. Log i
 
s 
oot with 

 SSH cli

t to 

ch 
SX host. 
    2. Us
 
 t
xt 

ito
 to ch

g
 th
 IP 




ss i
si

 th
 <s

v

Ip>xxx.xxx.xxx.xxx</s

v

Ipt
gs th
 followi
g fil
:/
tc/opt/VMw


/vpx
/vpx
.cfg (Vi
tu
lC

t

 2.5.x) /
tc/VMw


/vpx
.cfg (Vi
tu
lC

t

 2.0.x). 
    3. S
v
 you
 ch

g
s 


 
xit.
    4. 

st

t th
 m


g
m

t 
g

ts. Fo
 mo

 i
fo
m
tio
, s

 [

st

ti
g th
 M


g
m

t 
g

ts o
 

 
SX S

v

 (1003490)](http://k
.VMw


.com/k
/1003490).
    5. 

p

t fo
 
ll 
SX hosts co


ct

 to th
 Vi
tu
lC

t

 S

v

.

[



 th
 K
 

ticl
 h


.](http://k
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
=5850444)






