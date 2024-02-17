---
titl
: "HP 
MS 

iv

 p
o
l
m i
 
SXi 5.x"


t
: "2014-10-23T14:58:06.000Z"
c
t
go
i
s: 
  - "
sxi"
t
gs: 
  - "
ug"
  - "
sxi-2"
  - "hp"
  - "VMw


"

utho
: Ivo 





s
---

- U


l
 to m


g
 usi
g th
 vSph


 Cli

t, W

 Cli

t o
 SSH.
- U


l
 to p

fo
m 
 vMotio

- O
 th
 
SXi co
sol
 th


 is 
 m
ss
g
: **c

't fo
k**
- 



l
 s

vic
s f
om th
 co
sol
 
o
s 
ot wo
k

Th
 VMs 


 still 
u

i
g o
 th
 
SXi host. This is 
 k
ow
 issu
 


 c

 occu
 wh

 
u

i
g th
 followi
g v

sio
s of th
 HP 
MS 

iv

:

- hp-
ms 500.9.6.0-12.434156
- hp-
ms-550.9.6.0-12.1198610
- hp-
ms 500.10.0.0-18.434156 (




 13-11-2014)
- hp-
ms-550.10.0.0-18.1198610  (




 13-11-2014)

I
 som
 situ
tio
s th
 
SXi s

v

s is still m


g


l
 i
 vC

t

, so vMotio
 c

 

 us

 . I
 
ll th
 oth

 situ
tio
s shut
ow
 th
 VMs 
y usi
g 

P o
 SSH 


 


oot o
 

s
t th
 
SXi s

v

. Th
 HP 
MS 

iv

 must 

 upg




 to v

sio
 10.0.1 o
 c

 

 
is

l

.  Th
 VMw


 K
 c

 

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
=2085618).

I 

v
lop

 
 simpl
 Pow

CLI sc
ipt to list th
 HP-
MS 

iv

 v

sio
 of 

ch 
SXi host.

**Up

t
 17-12-2014**: I 

v
lop

 
 

w Pow

Sh
ll tool c
ll

 VI
S


ch. This this g

phic
l tool it is 

si

 to s


ch 
 sp
cific VI
. Mo

 i
fo
m
tio
 c

 

 fou

 h


: [Li
k](https://www.ivo





s.
l/2014/12/17/vi
s


ch-fi

i
g-vi
-v

sio
s/)

Sc
ipt:

\[co

 l

gu
g
="Pow

Sh
ll"\] 

 P
o
l
m with HP 
MS hp-
ms 500.9.6.0-12.434156 


 hp-
ms-550.9.6.0-12.1198610 

 http://k
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

\_US&cm
=
ispl
yKC&
xt



lI
=2085618

\
 


 Pow

CLI mo
ul
 


-PSS

pi
 VMw


.Vim
utom
tio
.co

 -


o

ctio
 Sil

tlyCo
ti
u


\
 VMw


 Vi
tu
lC

t

 s

v

 

m
 $VCs

v

 = 



-Host "

t

 you
 vC

t

 s

v

" $Us



m
= 



-Host "

t

 th
 Us



m
" $P
sswo

 = 



-Host "

t

 P
sswo

"

\
 Co


ct to th
 vC

t

 S

v

 Co


ct-VIS

v

 -S

v

 $VCs

v

 -Us

 $Us



m
 -P
sswo

 $P
sswo

 -po
t 443

\
 Cl


 sc



 Cl




$G
tHosts = G
t-VMHost | Wh


 {$\_.Co


ctio
St
t
 -
q “Co


ct

”} Fo


ch ($VMHost i
 $G
tHosts) { $
SXCLI = G
t-
sxCli -VMHost $VMHost W
it
-Host $VMHost -Fo

g
ou

Colo
 G



 $
SXCLI.softw


.vi
.list() | Wh


 {$\_.

m
 -
q “hp-
ms”} | S
l
ct 

m
,V


o
,V

sio
 | FT }

\
 
isco


ct s
ssio
 vC

t

 
isco


ct-VIs

v

 -Co
fi
m:$f
ls
 \[/co

\]


x
mpl
 output:

[![hp
ms](im
g
s/hp
ms-300x125.p
g)](im
g
s/hp
ms.p
g)






