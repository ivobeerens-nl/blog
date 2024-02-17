---
titl
: "VMw


 
SXi 

o

com 

t
 co

uptio
 p
o
l
m with th
 tg3 

iv

. Ch
ck you
 

vi
o
m

t!"


t
: "2014-02-19T09:41:32.000Z"
c
t
go
i
s: 
  - "
sxi"
  - "VMw


"
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

- Th
 syst
m is co
figu


 with g


t

 th

 4 G
 

M
- TCP S
gm

t
tio
 Offlo

 (TSO) is 



l

 o
 th
 


pt


- Th
 syst
m is 
u

i
g 
SXi/
SX 3.5, 4.x, 5.0, 5.1 


 5.5
- Th
 tg3 

iv

 v

sio
 is l
ss th

 v3.135


Th
 

vic
 is to up

t
 to th
 l
t
st tg3 

iv

 th
t fix th
 p
o
l
m. If you 


 usi
g 

o

com 


pt

s you 



 to ch
ck th
 followi
g compo


ts o
 you
 VMw


 
SXi hosts to 

t

mi

 if th
 

t
 co

uptio
 p
o
l
m c

 occu
:

- Wh
t is th
 

iv

 v

sio
 of th
 

o

com tg3 

iv

. 
ll th
 tg3 

iv

s 


li

 th

 v

sio
 3.135
.v50.1 must 

 up

t


- Is TSO 



l






 Ch
ck th
 

o

com tg3 

iv

 v

sio
 


 if TSO is 



l



- Op

 
 SSH s
ssio
 to th
 
SXi host.
- G
t 

 ov

vi
w o
 
ll th
 
ICs i
st
ll

 i
 th
 
SXi s

v

:  
sxcli 

two
k 
ic list

[![im
g
](im
g
s/im
g
_thum
.p
g "im
g
")](im
g
s/im
g
.p
g)

- 
ispl
y th
 

o

com tg3 

iv

 v

sio
, comm


: vmklo

\_mo
 -s tg3 | g

p V

sio


[![im
g
](im
g
s/im
g
_thum
1.p
g "im
g
")](im
g
s/im
g
1.p
g)

- Ch
ck if TSO is 



l

, comm


: 
sxcli syst
m s
tti
gs 

v

c

 list -o /

t/Us
HwTSO

[![im
g
](im
g
s/im
g
_thum
2.p
g "im
g
")](im
g
s/im
g
2.p
g) 

Is th
 I
t v
lu
 
qu
l to 1 th

 TSO is 



l

.

So if th
 tg3 

iv

 v

sio
 is 


li

 th

 v

sio
 3.135
.v50.1 


 TSO is 



l

 you 



 to up

t
 th
 

iv

!




 Up

t
 th
 

o

com tg3 

iv

 (st
ps fo
 up

ti
g 

 
SXi 5.1 host):

- 
ow
lo

 th
 

w tg3 

iv

:

- 
SXi 5.5: [v

sio
 3.135
.v55.1](https://my.VMw


.com/w

/VMw


/

t
ils?
ow
lo

G
oup=
T-
SXI55-

O

COM-TG3-3135
V551&p
o
uctI
=353) (

l

s

 o
 12/27/2013) o
 l
t


- 
SXi 5.0 / 5.1: [v

sio
 3.135
.v50.1](https://my.VMw


.com/w

/VMw


/

t
ils?
ow
lo

G
oup=
T-
SXI5X-

O

COM-TG3-3135
V501&p
o
uctI
=229) (

l

s

 o
 12/27/2013) o
 l
t


- Fo
 
SXi/
SX 3.5/4.x, th


 is cu



tly 
o fix. Th
 o
ly w
y is to 
is

l
 TSO. Fo
 mo

 i
fo
m
tio
 s

 th
 VMw


 K
 

ticl
 o
 th
 


 of th
 
log post.

- Pl
c
 th
 host i
 m
i
t



c
 mo

, comm


: 
sxcli  syst
m m
i
t



c
Mo

 s
t -
 t
u

- Uplo

 th
 

iv

 to 
 

t
sto


- I
st
ll th
 up

t

 

iv

, comm


: 
sxcli softw


 vi
 i
st
ll -
 /vmfs/volum
s/

t
sto

 loc
tio
/tg3-3.135
.v50.1-offli

\_
u

l
-1502404.zip
- 


oot  th
 host, comm


: 


oot
- Ch
ck th
 tg3 

iv

 v

sio
 
g
i
, comm


: vmklo

\_mo
 -s tg3 | g

p V

sio


[![im
g
](im
g
s/im
g
_thum
3.p
g "im
g
")](im
g
s/im
g
3.p
g) 

- Th
 tg3 

iv

 must h
v
 th
 

w v

sio

 
um



- 
xit m
i
t



c
 mo

. Comm


: 
sxcli syst
m m
i
t



c
Mo

 s
t -
 f
ls



x
cut
 th
 st
ps o
 
ll th
 
SXi host th
t h
v
 tg3 

iv

s i
st
ll

. Th
 VMw


 K
 

ticl
 c

 

 fou

 h


. [Li
k](http://k
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
=2072515
.Uv5y
Xq1Omc.twitt

)






