---
titl
: "Co
v

t VMw


 to Hyp

-V VMs with Mic
osoft Vi
tu
l M
chi

 Co
v

t

"


t
: "2012-07-30T12:33:14.000Z"
c
t
go
i
s: 
  - "hyp

-v"
  - "v2v"
  - "VMw


"
  - "vSph


"
t
gs: 
  - "hyp

-v-2"
  - "v2v"
  - "VMw


"
  - "vpsh


"

utho
: Ivo 





s
---





 Wh
t’s suppo
t



Suppo
t

 VMw


 pl
tfo
ms to co
v

t f
om :

- vC

t

 S

v

 5.0
- vC

t

 S

v

 4.1
- VMw


 
SXi S

v

 5.0
- VMw


 
SXi/
SX S

v

 4.1

Suppo
t

 Wi

ows pl
tfo
ms to co
v

t to:

- Wi

ows S

v

® 2012 

l

s
 c


i

t

- Mic
osoft Hyp

-V S

v

 2012 

l

s
 c


i

t

- Mic
osoft Hyp

-V S

v

 2008 
2 SP1
- Wi

ows S

v

 2008 
2 SP1

Gu
st op


ti
g Syst
ms suppo
t

 to co
v

t:

- Wi

ows S

v

 2003 SP2 x86 & x64
- Wi

ows S

v

 2008 & 2008 
2 x86 & x64
- Wi

ows Vist
 & 7 x86 & x64

MVMC will succ
ssfully p

fo
m vi
tu
l m
chi

 co
v

sio
s wh

 th
 followi
g co

itio
s 


 m
t:

- Th
 vi
tu
l m
chi

 to 

 co
v

t

 is i
 
 
u

i
g st
t

- Th
 vi
tu
l m
chi

 h
s VMw


 tools i
st
ll

 (**m
k
 su

 th
 VMw


 tools 


 up-to-

t
**!)
- Th
 VMw


 VM is stopp

 
u
i
g th
 VM
K copy p
oc
ss
- Th
 vi
tu
l m
chi

 is joi


 to 

 
ctiv
 
i

cto
y® 
om
i
.
- 

mot
 
cc
ss th
ough Wi

ows M


g
m

t I
st
um

t
tio
 (WMI) is 



l

 o
 th
 VMw


-

s

 vi
tu
l m
chi

 to 

 co
v

t

 


 th
 

sti

tio
 Hyp

-V host. S

 th
 “T
ou
l
shooti
g” s
ctio
 i
 this gui

 fo
 mo

 

t
ils.
- Th
 
ccou
t us

 fo
 co


cti
g to th
 VMw


-

s

 vi
tu
l m
chi

 th
t 



s to 

 co
v

t

 is p

t of 

 
ctiv
 
i

cto
y 
om
i
 


 
lso 
 loc
l 

mi
ist

to
 o
 th
t m
chi

.
- You h
v
 th
 co


ct c




ti
ls to co


ct to th
 

qui


 

vi
o
m

ts.
- Th
 Wi

ows us

 
ccou
t th
t you 


 usi
g h
s w
it
 
cc
ss to th
 U
C p
th sp
cifi

 o
 th
 

sti

tio
 Hyp

-V host fo
 copyi
g th
 vi
tu
l h


 
isks.
- Th
 Hyp

-V host h
s th
 

qui


 
isk sp
c
 
v
il

l
 fo
 th
 co
v

t

 vi
tu
l h


 
isks.

 





 How it wo
ks

Mic
osoft Vi
tu
l M
chi

 Co
v

t

 co
t
i
s th
 followi
g compo


ts:

- MVMC.
x
, 
 comm


-li

 utility th
t co
v

ts VMw


-

s

 vi
tu
l m
chi

s to Hyp

-V-

s

 vi
tu
l m
chi

s
- MVMC.GUI.
x
, 
 wiz


-

iv

 GUI th
t h
lps co
v

t VMw


-

s

 vi
tu
l m
chi

s to Hyp

-V-

s

 vi
tu
l m
chi

s
- MV
C.
x
, 
 comm


-li

 utility th
t co
v

ts VMw


 vi
tu
l 
isks (VM
K) to Hyp

-V-

s

 vi
tu
l h


 
isks (VH
)

Th
 MVMC.GUI.
x
 p
ovi

s 
 wiz


-

iv

 GUI. Th
 co
v

sio
 t
k
s th
 followi
g st
ps:

- T
k
s s

pshot VMw


 VM
- U
i
st
ll VMw


 tools
- Shut
ow
 VM
- Copy th
 VM
Ks to co
v

sio
 m
chi


- 

mov
 s

pshot
- 

p


i
g o
 “fi

l st
t
” s
tti
gs th
 VMw


 VM will 

 st

t

 o
 stopp


- Co
v

t VM
Ks to VH
s
- Impo
t th
 VM i
 Hyp

-V
- I
st
lls i
t
g

tio
 s

vic
s
- 

p


i
g o
 “fi

l st
t
” s
tti
gs th
 Hyp

-V VM will 

 st

t

 o
 stopp



I t
st

 
 co
v

sio
 


 

ploym

t of 
  Wi

ows 2008 
2 VM, host

 o
 
 VMw


 vSph


 5 up

t
 1 

vi
o
m

t usi
g th
 GUI. I 
x
cut

 th
 followi
g st
ps:

- I
st
ll Mic
osoft Vi
tu
l M
chi

 Co
v

t

. Fo
 

st p

fo
m

c
, it is 

comm




 th
t you 
u
 th
 co
v

sio
 o
 th
 

sti

tio
 host (Hyp

-V host)
- St

t MVMC.GUI.
x

- 

t

 th
 vC

t

 o
 
SXi i
fo
m
tio


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
9.p
g)

- S
l
ct 
 **
u

i
g** VM. 

 
w


 th
t th
 VM will 

 stopp

 
u
i
g th
 co
v

sio
!

[![im
g
](im
g
s/im
g
_thum
10.p
g "im
g
")](im
g
s/im
g
10.p
g)

- Sp
cify 
ccou
t 

t
ils 

 s
l
ct th
 fi

l st
t
 of th
 sou
c
 


 t

g
t

[![im
g
](im
g
s/im
g
_thum
11.p
g "im
g
")](im
g
s/im
g
11.p
g)

- S
l
ct th
 t
mpo


ily loc
tio
 to sto

 th
 
isks. M
k
 su

 it h
s 

ough f


 sp
c
 (
ou
l
 siz
 of th
 sou
c
 VM
Ks). It will sto

 th
 VM
Ks 


 co
v

t th
 VM
Ks to VH
s.

[![im
g
](im
g
s/im
g
_thum
12.p
g "im
g
")](im
g
s/im
g
12.p
g)

- 

t

 th
 Hyp

-V s

v

 i
fo
m
tio
 


 s
l
ct th
 sh


 to sto

 th
 VH
. M
k
 su

 you h
v
 

ough f


 sp
c
 to sto

 
ll th
 VH
s

[![im
g
](im
g
s/im
g
_thum
13.p
g "im
g
")](im
g
s/im
g
13.p
g)

- Som
 w


i
gs will 
pp


. 



 th
m 


 click Fi
ish

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
14.p
g)

- Th
 copy 


 co
v

sio
 st
ps 


 
x
cut



[![im
g
](im
g
s/im
g
_thum
15.p
g "im
g
")](im
g
s/im
g
15.p
g)

- Th
 VM is co
v

t

 succ
ssfully

[![im
g
](im
g
s/im
g
_thum
16.p
g "im
g
")](im
g
s/im
g
16.p
g)

- I
 Wi

ows S

v

 2012 th
 VM c

 

 st

t

. It h
s th
 I
t
g

t

 Compo


ts i
st
ll



[![im
g
](im
g
s/im
g
_thum
17.p
g "im
g
")](im
g
s/im
g
17.p
g)

 





 Co
clusio


Mic
osoft Vi
tu
l M
chi

 Co
v

t

 is 
 v

y 

sic VMw


 to Hyp

-V co
v

sio
 p
og

m. H


 


 som
 P
os 


 Co
s:

**P
os**

- Suppo
t fo
 Wi

ows S

v

 2012
- Comm


 li

 sc
ipti
g possi
l


**Co
s**

- It 
o
s 
ot p

-ch
ck fo
 
x
mpl
 if th


 is suffici

t 
isk sp
c
 
v
il

l
. 
u
i
g th
 copy 


 co
v

sio
 p
oc
ss you g
t 
 


o
 wh

 th
 
isk is full. This cost 
 lot of 
xt

 tim
!
- Th
 VMw


 tools must 

 up to 

t
. With out

t

 VMw


 tools it is 
ot possi
l
 to co
v

t
- Hot clo
i
g 
ot possi
l
. 
ow
tim
 





!
- 
o Li
ux suppo
t
- P

-ch
cks 


 
ot
- 
o 
isk 
lig
m

t of Wi

ows 2003

 

If you lik
 it to 
o th
 oth

 w
y, VMw


 h
s 
 tool c
ll

 “[VMw


 vC

t

 Co
v

t

 St



lo

 5.0](https://my.VMw


.com/w

/VMw


/

t
ils/co
v

t

5/
HclY

qZ

iZ

l
w==)” which co
v

t Hyp

-V 

s

 VMs to VMw


 vSph


 VMs with mo

 

v

c

 fu
ctio
s to us
 such 
s hot clo
i
g 


 
isk 
lig
i
g.






