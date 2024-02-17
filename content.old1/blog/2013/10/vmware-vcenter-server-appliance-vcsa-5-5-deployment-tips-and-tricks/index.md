---
titl
: "VMw


 vC

t

 S

v

 
ppli

c
 (VCS
) 5.5 

ploym

t tips 


 t
icks"


t
: "2013-10-09T12:02:21.000Z"
c
t
go
i
s: 
  - "vc

t

-2"
  - "vcs
"
  - "VMw


"
t
gs: 
  - "vc

t

"
  - "vcs
"
  - "VMw


"

utho
: Ivo 





s
---

- Th
 VMw


 vC

t

 S

v

 
ppli

c
 is 
 p

co
figu


 Li
ux-

s

 vi
tu
l m
chi

. Th
 VMw


 vC

t

 S

v

 
ppli

c
 (VCS
) is 
v
il

l
 
s OVF/ OV

- It 

s

 o
 Sus
 Li
ux 

t

p
is
 11 64-
it
- Li
k

 Mo

, Mic
osoft SQL o
 

2 is 
ot suppo
t


- 
s 

t


s
 you c

 us
 th
 
m





 vPostg

s o
 
xt



l O

cl
 

t


s

- Th
 mi
im
l co
figu

tio
 is: 2 vCPUs, 8 G
 m
mo
y, 
 25 G
 thi
 p
ovisio


 


 100 G
 thick 
isk. This co
figu

tio
 is fo
 10 o
 f
w

 hosts 


 100 o
 f
w

 vi
tu
l m
chi

s. Mo

 i
fo
m
tio
 o
 sizi
g th
 VCS
 c

 

 fou

 h


 li
k.
- I
 
 sm
ll hom
 l

 o
 PoC 

vi
o
m

t you c

 

c


s
 th
 m
mo
y of th
 VCS
. Fo
 
x
mpl
 my hom
 l

 VCS
 h
s 4 G
 m
mo
y. This is 
ot suppo
t

!
- Th
 VCS
 is 

ploy

 with  H


w


 V

sio
 7. If you up

t
 th
 vC

t

 S

v

 
ppli

c
 to h


w


 v

sio
 10, you c


ot 

it th
 vi
tu
l m
chi

 s
tti
gs fo
 th
 
ppli

c
 usi
g th
 vSph


 Cli

t!
- M
k
 su

 th
t th
 host

m
 is 

t



 
s Fully Qu
lifi

 
om
i
 

m
 (FQ

). 

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

- If you g
t “


o
: i
v
li
 host

m
. FQ

 is 

qui


 fo
 joi
i
g 
 
om
i
” you fo
got to ch

g
 th
 host

m
 of th
 VCS
 to 
 FQ

.

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

- To co
figu

 th
 VCS
, us
 th
 followi
g U
L: https://IP-




ss-VCS
:5480 to 
cc
ss th
  Vi
tu
l 
ppli

c
 M


g
m

t I
t

f
c
 (V
MI).
- Th
 

f
ult us

 

m
 is: 
oot
- Th
 

f
ult p
sswo

 is:  VMw



- Th
 
oot p
sswo

 will 
xpi

 
ft

 90 

ys! I
 th
 

mi
 p
g
 of th
 V
MI i
t

f
c
 it is possi
l
 to 
is

l
 th
 
oot p
sswo

 
xpi

tio
.
- Th
 

f
ult SSO us

 is: [

mi
ist

to
@vSph


.loc
l](m
ilto:

mi
ist

to
@vSph


.loc
l)
- Sy
ch
o
iz
 th
 vC

t

 S

v

 
ppli

c
 Clock with 
 
TP s

v

, VMw


 tools o
 
ctiv
 
i

cto
y (this optio
 is o
ly 
v
il

l
 if th
 VCS
 is joi


 with th
 
ctiv
 
i

cto
y).
- Mo

 i
fo
m
tio
 o
 

cki
g up 


 

sto
i
g th
 vC

t

 S

v

 
ppli

c
 (vPostg

s) 

t


s
 us
 th
 followi
g  [Li
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
=2034505).
- To us
 th
 vSph


 W

 Cli

t us
 th
 followi
g U
L: https://IP-




ss-VCS
:9443/
- SSH is 
y 

f
ult 



l

. To 



l
 o
 
is

l
 SSH toggl
 th
 SSH logi
 o
 th
 

mi
 t

 of th
 V
MI.
- Mic
osoft Sysp

p fil
s c

 

 uplo



 i
 th
 V
MI summ

y p
g
. Th
y 


 sto


 i
: **/
tc/VMw


-vpx/sysp

p/OS 
i

cto
y.**
- You c

 


 


itio

l softw


 such 
s S
MP to mo
ito
 th
 VCS
. 


i
g softw


 c

 

 
o

 with th
 “Y
t 

oth

 S
tup Tool” (Y
ST).
- To mo
ito
 vC

t

 S

v

 
ppli

c
 

t


s
 
isk us
g
 you c

 us
 this sc
ipt [Li
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
=2058187).






