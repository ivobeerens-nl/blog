---
titl
: "Co
figu

 VS

 o
 HP S

v

s"


t
: "2016-06-09T10:13:33.000Z"
c
t
go
i
s: 
  - "vs

"
t
gs: 
  - "
uc"
  - "s

c"
  - "vs

"

utho
: Ivo 





s
---

- HP Wo
klo

 
cc
l


to
 
s c
chi
g 

vic

- HP Sm

t 



y P440 co
t
oll

 with s
v


l 10k S
S 
isks 
s c
p
city ti



To 



l
 VS

 th
 th
 fi
st thi
g to 
o is to ch
ck th
 VS

 HCL([li
k](https://www.VMw


.com/

sou
c
s/comp
ti
ility/s


ch.php?

vic
C
t
go
y=vs

))

[![HCL1](im
g
s/HCL1-300x51.p
g)](im
g
s/HCL1.p
g)

[![HCL2](im
g
s/HCL2-300x58.p
g)](im
g
s/HCL2.p
g)

Th
 VS

 HCL giv
s impo
t

t i
fo
m
tio
 

out:

- Wh
t h


w


 is suppo
t

?
- Wh
t co
figu

tio
 
o
s th
  HP Sm

t 



y co
t
oll

 suppo
t?
- VS

 suppo
t

 v

sio
(s)
- 

vic
 

iv

 


 fi
mw


 v

sio
s i
clu
i
g th
 
ow
lo

 loc
tio
 of th
 

iv

.


ll th
 h


w


 is suppo
t

 


 th
 fi
mw


 l
v
ls 


 list

 i
 th
 HCL. So th
 

xt st
p is to 
o is to co
figu

 th
 HP Sm

t 



y P440 co
t
oll

 i
 P
ss-Th
ough mo

. HP c
lls this "H

 mo

". I
 H

 mo

, 
ll physic
l 

iv
s 


 p

s

t

 
i

ctly to th
 op


ti
g syst
m 


 th
 h


w


 

I
 

gi

 is 
is

l

. This c

 

 
o

 i
 th
 Sm

t Sto

g
 

mi
ist

to
.

[![H

mo

](im
g
s/H

mo

-300x193.p
g)](im
g
s/H

mo

.p
g)


ft

 



li
g th
 H

 mo

 th
 hosts 



s 
 


oot.

Th
 

xt st
p it to i
st
ll th
 s

v

 with th
 HP Custom 
SXi im
g
 . 
ft

 th
 i
st
ll
tio
 th
 
SXi, th
 HP Sm

t 



y Co
t
oll

 is 
ot 

cog
iz

 

c
us
 th
 

iv

 is 
ot i
clu


. This s
m
 is fo
 th
 HP Wo
klo

 
cc
l


to
 th
t will s

v
 fo
 th
 c
chi
g ti

. 
ow
lo

 
oth 

iv

s 


 


 th
m to vSph


 Up

t
 M


g

. 
ft

 
oth 

iv

s 


 i
st
ll

 ch
ck th
 HP Sm

t 



y Co
t
oll

 
y usi
g th
 followi
g comm


 (i
clu


 i
 th
 HP Custom

 
SXi im
g
):

\[co

 l

gu
g
="Pow

Sh
ll"\] 
sxcli hpss
cli cm
 -q "co
t
oll

 "slot=1" show co
fig 

t
il" \[/co

\]

[![
sxi comm


](im
g
s/
sxi-comm


-300x170.p
g)](im
g
s/
sxi-comm


.p
g)

_Th
 "slot=" optio
 

p


s o
 th
 slot 
um


 th
 HP Sm

t 



y P440 co
t
oll

 is i
st
ll

._

To list th
 

iv
s 
tt
ch

 to th
 co
t
oll

 with th
 followi
g comm


:

\[co

 l

gu
g
="Pow

Sh
ll"\] 
sxcli hpss
cli cm
 -q "co
t
oll

 slot=1 physic
l

iv
 
ll show" \[/co

\]

Th
 Wo
klo

 
ccc
l


to
 st
tus c

 

 
ispl
y

 with th
 followi
g comm


:

\[co

 l

gu
g
="Pow

Sh
ll"\] fio-st
tus \[/co

\]

Th
 l
st st
p is to  op

 th
 vSph


 W

 Cli

t, st

t 



li
g VS

 


 cl
imi
g th
 
isks.






