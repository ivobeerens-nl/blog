---
titl
: "Wh
t 

out th
 VMw


 vC

t

 S

v

 
ppli

c
 (VCS
) v

sio
 5.1?"


t
: "2012-10-22T08:20:09.000Z"
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
t
gs: 
  - "vc

t

"
  - "vcs
"

utho
: Ivo 





s
---

Th
 vC

t

 S

v

 
ppli

c
 (VCS
) 5.1 is 
 64-
it SUS
 Li
ux 

t

p
is
 S

v

 11 OVF 
ppli

c
.  Th
 
ppli

c
 is i
st
ll

 

f
ult with 2 vCPUs, 8 G
 m
mo
y 


 co
sum
s 

tw


 
pp
oxim
t
 5 G
 


 80 G
 of 
isk sp
c
.  This is th
 co
figu

tio
 fo
 
 sm
ll i
v

to
y (up to 100 hosts 


 1000 VMs). If th
 

vi
o
m

t is l

g

 you 



 to sc
l
 up th
 
ppli

c
 h


w


 co
figu

tio
.


ft

 th
 

ploym

t th
 i
iti
l co
figu

tio
 c

 

 
o

 
y usi
g th
 wiz


.

O
 th
 VCS
 
ppli

c
 th
 followi
g compo


ts 


 p

i
st
ll

:

- vC

t

 Si
gl
 Sig
 O
 (SSO)
- I
v

to
y S

vic

- vSph


 W

 Cli

t
- vSph


 
uto 

ploy S

v


- Syslog Coll
cto

- 
SXi 
ump Coll
cto



u
i
g th
 w

 

s

 co
figu

tio
 th
 followi
g  

t


s
 optio
s c

 

 s
l
ct

:

- Th
 
m





 

t


s
 is 
 vPostg

s 

t


s
 th
t h
s suppo
t fo
 5 hosts 


 50 Vi
tu
l M
chi

s. This is wh
t th
 i
st
ll
tio
 gui

 s
ys 

out th
 vPostg

s:

> IMPO
T

T   Th
 
m





 

t


s
 is 
ot co
figu


 to m


g
 

 i
v

to
y th
t co
t
i
s mo

 th

 5 hosts  
> 


 50 vi
tu
l m
chi

s. If you us
 th
 
m





 

t


s
 with th
 vC

t

 S

v

 
ppli

c
, 
xc


i
g  
> th
s
 limits c

 c
us
 
um

ous p
o
l
ms, i
clu
i
g c
usi
g vC

t

 S

v

 to stop 

spo

i
g

- 
s 
xt



l 

t


s
 th
 VCS
 suppo
t O

cl
 o
ly! Usi
g  th
 O

cl
 

t


s
 h
s suppo
t fo
 1000 hosts 


 10.000 Vi
tu
l M
chi

s.

Th
 i
st
ll
tio
 


 co
figu

tio
 is v

y 

sily. Withi
 
 coupl
 mi
ut
s th
 VCS
 is up 


 
u

i
g.

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

**P
os:**

- V

y 

sy 


 quick to i
st
ll 


 co
figu


- 
o Wi

ows lic

s
 






- 

sy to i
st
ll 

 up

t
 


 upg




- Quick 

cov

y of th
 vC

t

 
ppli

c
  

**Co
s:**

- Th
 
m





 vPostg

s 

t


s
 h
s suppo
t fo
 5 hosts 


 50 VM’s.
- 
s 
xt



l 

t


s
 o
ly O

cl
 is suppo
t

.
- 
o Li
k

 mo

 suppo
t (

qui

s 


M (

 L
S)
- 
o SQL S

v

 
s 

ck


 

t


s
 suppo
t
- VMw


 Up

t
 M


g

 c

’t 

 i
st
ll

 i
 th
 VCS
, 


itio

l Wi

ows 

s

 VM o
 physic
l s

v

 





.
- vC

t

 H


t


t is 
ot suppo
t


- VMw


 Vi
w is 
ot suppo
t


- 
ot 
ll 3
 p

ty plugi
s will wo
k

**Co
clusio
:**

Th
 
m





 

t


s
 h
s limit

 suppo
t so it o
ly us

l
 i
 sm
ll SM
 


 t
st 

vi
o
m

ts o
 th
 mom

t. Fo
 th
 
xt



l 

t


s
 o
ly O

cl
 is suppo
t

. VMw


 Up

t
 M


g

 is 
ot p

i
st
ll

, so you 



 

 
xt

 Wi

ows S

v

 fo
 i
st
lli
g VMw


 Up

t
 M


g

.  Wh

 th
s
 


 

ov
 issu
s 


 fix

 i
 fu
th

 v

sio
s, it’s 
 g


t 


 

sy w
y to s
t up 

 vC

t

 S

v

 

vi
o
m

t without usi
g Wi

ows!






