---
titl
: "
VM
 SS
s 


 
ot 

cog
iz

 

ymo

 
ft

 upg


i
g to VMw


 
SXi 7"


t
: "2020-04-09T09:47:19.000Z"
c
t
go
i
s: 
  - "hom
-l

"
  - "VMw


"
t
gs: 
  - "hom
l

"
  - "VMw


"

utho
: Ivo 





s
---

- S
msu
g SS
 970 
VO 1T
 
VM

- S
msu
g SS
 950 P
O 512G
 
VM


My coll
g
 


 f
llow v
xp

t J
sp

 
l


ts 

cou
t



 th
 s
m
 p
o
l
m with his Sup

mic
o X9

L-iF 


 S
msu
g 970 
VO MZ-V7
1T0
W 
VM
 SS
 hom
l

.

To fix this, p

fo
m 
 cl


 i
st
ll
tio
 of VMw


 
SXi 7. 
ft

 th
 cl


 i
st
ll
tio
, th
 
VM
 
isks 


 

cog
iz

.

[![](im
g
s/1-300x78.p
g)](im
g
s/1.p
g)

**Up

t
 M
y 16, 2020**: [J
ff

y Kust

s](https://www.j
ff

ykust

s.
l/2020/04/14/VMw


-
vm
-pci
-

iv

-missi
g-o
-
sxi-7-0-
ft

-upg



/) 
xp

i

c

 th
 s
m
 p
o
l
m 


 w
s 

l
 to p
ovi

 Willi
m L
m th
 suppo
t 
u

l
 of th
 host th
t f
il

 th
 upg



. Willi
m L
m 


 th
 VMw


 suppo
t t

m 
iscov



 quickly th
t w
 us

 th
 w
o
g 
sxcli up

t
 comm


 (**
sxcli softw


 vi
 up

t
)**. Th
 co


ct comm


 to upg



 

 
SXI host is: **
sxcli softw


 p
ofil
 up

t
.** Willi
m 
xpl
i
s th
 comm


s i
 his 
log fou

 h


, [li
k](https://www.vi
tu
llygh
tto.com/2020/04/impo
t

t-
vm
-ss
-
ot-fou

-
ft

-upg


i
g-to-
sxi-7-0.html).

So th
 st
ps wh

 upg


i
g 
 st



lo

 
SXi host 


:

- Stop th
 VMs o
 th
 
SXi host
- 

t

 M
i
t



c
 Mo


- Copy to VMw


 
SXI offli

 
u

l
 to 
 

t
sto

 with 

ough sp
c
 
v
il

l
. I
 this 
x
mpl
 I us
 th
 "
fs01" 

t
sto


- SSH to th
 host 


 p

fo
m th
 followi
g comm


: 
sxli softw


 sou
c
s p
ofil
 list -
 /vmfs/volum
s/**<

t
sto

>**/**<
SXoffli


u

l
.zip>**

\[co

 l

gu
g
="t
xt"\] \[
oot@
sxi01:~\] 
sxcli softw


 sou
c
s p
ofil
 list -
 /vmfs/volum
s/
fs01/ISO/VMw


-
SXi-7.0.0-15843807-

pot.zip 

m
 V


o
 
cc
pt

c
 L
v
l C


tio
 Tim
 Mo
ific
tio
 Tim
 ---------------------------- ------------ ---------------- ------------------- ----------------- 
SXi-7.0.0-15843807-st





 VMw


, I
c. P

t


Suppo
t

 2020-03-16T10:48:54 2020-03-16T10:48:54 
SXi-7.0.0-15843807-
o-tools VMw


, I
c. P

t


Suppo
t

 2020-03-16T10:48:54 2020-03-16T10:48:54 \[/co

\]

- This list th
 im
g
 p
ofil
s 
v
il

l
 f
om th
 offli

 
u

l

- 
x
cut
 th
 comm


: 
sxcli softw


 sou
c
s p
ofil
 up

t
 -
 /vmfs/volum
s/**<

t
sto

>**/**<
SXiOffli


u

l
.zip>** -p <**Im
g
 p
ofil
**\>

\[co

 l

gu
g
="t
xt"\] \[
oot@
sxi01:~\] 
sxcli softw


 sou
c
s p
ofil
 up

t
 -
 /vmfs/volum
s/
fs01/ISO/VMw


-
SXi-7.0.0-15843807-

pot.zip -p 
SXi-7.0.0-15843807-
o-tools \[/co

\]

- Wh

 th
 upg



 is compl
t

 succ
ssfully, 


oot th
 
SXi host
- Log i
 


 
xit th
 m
i
t



c
 mo

 o
 th
 
SXi host

Th

ks, to  J
ff

y 


 Willi
m fo
 solvi
g this p
o
l
m. G


t commu
ity wo
k!






