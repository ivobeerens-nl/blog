---
titl
: "


 HP o
 

ll 

iv

s to VMw


 Up

t
 M


g

 (VUM)"


t
: "2012-07-17T07:37:52.000Z"
c
t
go
i
s: 
  - "hp"
  - "VMw


-up

t
-m


g

"
  - "vum"
t
gs: 
  - "

ll"
  - "hp"
  - "

posito
y"
  - "VMw


-up

t
-m


g

"
  - "vum"

utho
: Ivo 





s
---

- HP 
SXi 5.0 M


g
m

t P
ovi


s 
u

l
 - i
clu

s th
 l
t
st HP Commo
 I
fo
m
tio
 Mo

l (CIM) P
ovi


s, HP I
t
g

t

 Lights-Out (iLO) 

iv

, HP Comp
q 
OM Utility (C
U) 

iv

, 


 th
 

w HP 
g

tl
ss M


g
m

t S

vic
 (
MS).
- HP 
SXi 5.0 Utiliti
s 
u

l
 - 
SXCLI utiliti
s such 
s HP
OOTCFG (
oot o



 co
figu

tio
),HPO
CFG (

mot
 iLO co
figu

tio
) 


 HP
CUCLI (Sm

t 



y 

po
ti
g 


 co
figu

tio
)
- HP 
SXi 5.0 
MI 
u

l
 - 
o
 M
sk

l
 I
t


upt (
MI) 

iv

 us

 to w
it
 VMw


® 


o
s to th
 I
sight M


g
m

t Log (IML)
- HP 
g

tl
ss M


g
m

t S

vic
 Offli

 
u

l
 - 
 s

vic
 th
t p
ovi

s suppo
t fo
 
g

tl
ss M


g
m

t 


 
ctiv
 H

lth. 
g

tl
ss M


g
m

t S

vic
 p
ovi

s 
 wi


 


g
 of s

v

 i
fo
m
tio
 (
.g. OS typ
 


 v

sio
, i
st
ll

 
pplic
tio
s, IP 




ss
s) 
llowi
g custom

s to compl
m

t h


w


 m


g
m

t with OS i
fo
m
tio
 


 
l

ti
g. 
g

tl
ss M


g
m

t p
ovi

s I
t
g

t

 Lights Out (iLO) 

s

 
o
ust m


g
m

t without th
 compl
xity of OS-

s

 
g

ts. 
ctiv
 H

lth p
ovi

s 24x7 missio
 co
t
ol fo
 s

v

s, 

liv

i
g m
ximum uptim
 th
ough 
utom
t

 mo
ito
i
g, 
i
g
ostics 


 
l

ti
g.
- 

vic
 

iv

s 
s us

 i
 th
 HP Customiz

 VMw


 im
g
s
- L
t
st P
oLi

t S

v

 


 optio
 fi
mw


 


 

iv

 v

sio
 

cip


Th
 VI
 

pot c

 

 us

 
y th
 followi
g tools:

- VMw


 Up

t
 M


g

 (VUM)
- 
SXCLI
- Im
g

uil




With th
 HP VI
 

pot i
t
g

tio
 fo
 
x
mpl
 i
 VUM th


 is 
o 



 to 
ow
lo

 


 i
st
ll th
 
u

l
s m

u
lly. I
 this 
log post I 
xpl
i
 how to 


 th
 HP VI
 

pot to VMw


 Up

t
 M


g

 (VUM) 
y usi
g th
 followi
g st
ps:





 


 th
 VI
 

pot to VUM

- Op

 th
 vC

t

 Cli

t
- S
l
ct u



 Solutio
 


 
pplic
tio
 i
 th
 m
i
 sc



 of th
 vC

t

 cli

t – Up

t
 M


g


- S
l
ct co
figu

tio

- I
 th
 
ow
lo

 sou
c
s s
l
ct - 


 
ow
lo

 Sou
c

- I
 Sou
c
 U
L us
:
    - Fo
 HP Up

t
s: http://vi
s

pot.hp
.com/i


x.xml
    - Fo
 

ll Up

t
s: http://VMw




pot.

ll.com/i


x.xml
- P

ss OK
- S
l
ct – 
ow
lo

 
ow to up

t
 th
 

s
li



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





 C


t
 
 

w 

s
li



- S
l
ct th
 

s
li

s 


 G
oups t


- C


t

- 

s
li

 

m
  – HP Up

t
s
- 

s
li

 Typ
 – Host 
xt

sio

- 
xt

sio
s to 


 – S
l
ct th
 
xt

sio
s you 



. I
 this 
x
mpl
 I s
l
ct

 th
 followi
g 
xt

sio
s:
    
    - hp
mi fo
 
SXi 5.0 v1.3
    
    - HP 
SXi 5.0 Compl
t
 
u

l
 Up

t
 1.3
    
    - HP 
SXi 5.0 M


g
m

t 
u

l
 1.2-26
    
    - HP Utility 
u

l
 
SXi 5.0 v 1.2

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

- Fi
ish





 
tt
ch th
 

s
li

 


 

m

i
t


- 
tt
ch th
 

s
li

 to th
 clust



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

- S
l
ct th
 

s
li

 


 sc

 fo
 p
tch
s 


 
xt

sio
s
- Th
 HP 
u

l
s th
t 


 missi
g 


 list



[![im
g
](im
g
s/im
g
_thum
4.p
g "im
g
")](im
g
s/im
g
4.p
g)

- Us
 

m

i
t
 to i
st
ll th
 HP 
u

l
s

Wh

 th
 hosts 


 


oot

 


 th
 

m

i
tio
 is fi
ish

, th
 Host Compli

c
 ov

vi
w is 100%.

[![im
g
](im
g
s/im
g
_thum
5.p
g "im
g
")](im
g
s/im
g
5.p
g)

 

Usi
g th
  HP VI
 

pot is g


t w
y of k

p you
 HP s

v

 up-to-

t
 with th
 l
t
st HP 
u

l
s.

Mo

 i
fo
m
tio
 c

 

 fou

 HP VI
 
u

l
 sit
 fou

 h


.

Up

t
 July 20 2012 : Vikto
 v

 


 


g t
st

 th
 

ov
 co
figu

tio
 


 fou

 out th
t this o
ly wo
ks with 

w  i
st
ll
tio
s. Fo
 
xisti
g i
st
ll
tio
 you 



 to c


t
 

 


itio

l Host P
tch 

s
li

. Vikto
 
xpl
i
s this o
 his cool 
log fou

 h


 [h


.](http://www.vikto
ious.
l/2012/07/17/up

ti
g-you
-hp-

iv

s-with-VMw


-up

t
-m


g

/)






