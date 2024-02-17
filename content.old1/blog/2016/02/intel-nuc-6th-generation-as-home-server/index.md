---
titl
: "Hom
 l

 
xt

sio
 with 

 I
t
l 
UC 6th g




tio
"


t
: "2016-02-24T19:37:32.000Z"
c
t
go
i
s: 
  - "h


w


"
  - "hom
-l

"
t
gs: 
  - "hom
-l

"
  - "i
t
l-
uc"

utho
: Ivo 





s
---

- I
t
l 
UC6i3SYH
- I
t
l i3-6100u (Skyl
k
) 2.3 GHz 
u
l Co

, 3 M
 c
ch
, 15W T
P
- 2 m
mo
y slots fo
 


4-2133 SO
IMM m
mo
y, m
ximum is 32 G
 m
mo
y
- I
t
l H
 G

phics 520 GPU
- I
t
l I219-V Gig

it 

two
k 


pt

 


 I
t
l Wi

l
ss-
C 8260 WIFI 


pt


- Optio
 to i
st
ll 
 2.5" H

/S

 


 
 M.2 SS
 c


 (2242 o
 2280)
- 4 US
 3.0 po
ts (2 i
 th
 f
o
t 


 2 o
 th
 



)
- S
 c


 





 (S
XC c


s)
- C
s
 


 
 19V 
C-
C 


pt



[![IMG_9206](im
g
s/IMG_9206-300x250.jpg)](im
g
s/IMG_9206.jpg) [![IMG_9209](im
g
s/IMG_9209-300x228.jpg)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2016/02/IMG_9209.jpg)

Th
 I
t
l 
UC will 

 us

 
s m


g
m

t s

v

 fo
 my Softw


 

fi


 

t
C

t

 (S

C) hom
 l

 

vi
o
m

t. Th
 I
t
l 
UC will host VMs such 
s:

- 
om
i
 Co
t
oll

 + 

S
- vC

t

 S

v

 
ppli

c

- Vi
tu
l S

 wit

ss 
ppli

c

- V


m 

ckup
- 
tc.

Th
 VMs 


 sto


 o
 
 Sy
ology 

S. Th
 I
t
l 
UC will us
 
 
FS co


ctio
 to th
 Sy
ology 

S.  Th
 
UC will 
ot h
v
 

y 
isks. It will 
oot 
SXi f
om th
 US
 stick

**P
oc
sso
**

Th
 6th g




tio
 I
t
l 
UC l

v
s two choic
s fo
 choosi
g 
 CPU:

- I
t
l I3 Skyl
k
 
v
il

l
 o
 th
 
UC6i3SYH mo

l
- I
t
l I5 Skyl
k
 
v
il

l
 o
 th
 
UC6i5SYH mo

l


oth CPUs h
v
 2 co

s 


 suppo
t hyp

t



i
g. Th
 t

l
 

low giv
s 
 quick comp

iso
 

tw


 
oth p
oc
sso
s:

[![I
t
l](im
g
s/I
t
l-283x300.p
g)](http://

k.i
t
l.com/
l/comp


/88180,91160)

Fo
 this co
figu

tio
 th
 I
t
l 
UC with th
 I3-6100u p
oc
sso
 is suffici

t 


 s
v
s 100 
u
o. Th
 I3 h
s 2 co

s 


 hyp

t



i
g, so 4 logic
l p
oc
sso
s 


 
ispl
y

 i
 th
 hyp

viso
.

[![cpu](im
g
s/cpu-300x84.p
g)](im
g
s/cpu.p
g)

Oth

 

v

c

 t
ch
ologi
s such 
s VT-x, VT-
, 
PT 


 fully suppo
t

.

**M
mo
y**

Th
 I
t
l 
UC h
s 2 m
mo
y slots 


 suppo
t up to 32 G
 


4 2133 MHz SO
IMM m
mo
y. I 




  2 C
uci
l 16 G
 


4-2133(CT16G4SF
8213) mo
ul
s which m
k
s 
 tot
l of 32 G
 m
mo
y.

[![IMG_9186](im
g
s/IMG_9186-225x300.jpg)](im
g
s/IMG_9186.jpg) [![IMG_9190](im
g
s/IMG_9190-300x225.jpg)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2016/02/IMG_9190.jpg)

I us
 th
 s
m
 m
mo
y 
s sugg
st

 
y th
 
log "vi
t

.

t" [li
k](http://www.vi
t

.

t/2016/01/VMw


-hom
s

v

-
sxi-o
-6th-g

-i
t
l-
uc/).

**

two
k c


**

Th
 I
t
l 
UC h
s 

 I
t
l I219-V Gig

it 

two
k 


pt

 


 
 wi

l
ss 

two
k c


. O
ly th
 I
t
l I219-V c

 

 us

 with VMw


 
SXi.

**Sto

g
**

Th
 
UC h
s 
 M.2 (PCI
 G

 3 x4) slot 


 
 I
t
l 
HCI S
T
-600 co
t
oll

. It is possi
l
 to i
st
ll 
 2.5" S

 o
 h



isk i
 th
 

iv
 c
g
.

[![IMG_9210](im
g
s/IMG_9210-300x225.jpg)](im
g
s/IMG_9210.jpg)

Th
 VMs 


 o
 
 Sy
ology 

S. So th
 
UC will 
ot h
v
 

y 
isks oth

 th

 
 US
 

iv
 fo
 
ooti
g VMw


 
SXi.

**VMw


 
SXi**



 US
 3 stick is us

 to 
oot VMw


 
SXi. O
 th
 US
 stick is **VMw


 
SXi 6.0 U1
** (VMw


-VMviso
-I
st
ll

-201601001 3380124.x86\_64) i
st
ll

. Fo
 c


ti
g 
 US
 stick with 
SXi 6 you c

 us
 th
 
logpost [h


](https://www.ivo





s.
l/2011/09/17/c


t
-
-
oot

l
-VMw


-
sxi-5-us
-stick-i
-wi

ows-


-p

fo
m-
-sc
ipt

-i
st
ll
tio
/). O
ly st
p 1 till 3 


 





.

Th


 is 
o 



 to 


 
xt

 

iv

s to th
 
SXI im
g
 

c
us
 th
 

two
k 


 sto

g
 


pt

 


 

cog
iz

 
y 

f
ult.

[![L

](im
g
s/L

-300x137.p
g)](im
g
s/L

.p
g) [![Sto

g
](im
g
s/Sto

g
-300x84.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2016/02/Sto

g
.p
g)

P
ssth
ough is suppo
t

 
y th
 CPU 


 moth


o


.

[![p
ssth
u](im
g
s/p
ssth
u-300x278.p
g)](im
g
s/p
ssth
u.p
g)



sti
g such 
s VMw


 i
 VMw


 


 Hyp

-V i
 VMw


 is possi
l
. 

low is 

 sc



shot of 
 Hyp

-V S

v

 with 
 VM host

 o
 
SXi.

[![hv](im
g
s/hv-300x216.p
g)](im
g
s/hv.p
g)

**Pow

 co
sumptio
**

Th
 
v


g
 pow

 co
sumptio
 of th
 
UC is 

tw


 20 


 30 w
tt with 
 coupl
 of VMs 
ctiv
.

**Costs**

<t

l
 styl
="h
ight: 149px;" wi
th="419"><t
o
y><t
><t
><st
o
g>&

sp;Compo


t</st
o
g></t
><t
><st
o
g>
mou
t</st
o
g></t
><t
><st
o
g>Tot
l</st
o
g></t
></t
><t
><t
>I
t
l 
UC 
UC6i3SYH</t
><t
>1</t
><t
>€ 299,00</t
></t
><t
><t
>C
uci
l 16 G
 


4-2133</t
><t
>2</t
><t
>€ 235,80</t
></t
><t
><t
>&

sp;US
3 Stick 16 G
</t
><t
>1</t
><t
>&

sp;€ 10,00</t
></t
><t
><t
><st
o
g>Tot
l</st
o
g></t
><t
></t
><t
><st
o
g>€&

sp;544,80</st
o
g></t
></t
></t
o
y></t

l
>

**Co
clusio
**

Th
 6th g




tio
 I
t
l 
UC is 

 g


t 


 

sy optio
 fo
 c


ti
g 
 sm
ll 
SXi hom
 l

. I us
 th
 I
t
l 
UC 
s m


g
m

t s

v

 with 
 coupl
 of VMs. 

oth

 us
 c
s
 is c


ti
g 
 2/3- 
o

 hy

i
 Vi
tu
l S

 (VS

) clust

. Put 
 S
msu
g 950 P
O i
 th
 M.2 slot fo
 c
chi
g 


 
 2.5" H

 
s c
p
city ti

. 

sy.

**P
os 


 co
s**

P
os:

- 
ll i
-o

-p
ck
g
 i
clu
i
g 
 moth


o


, p
oc
sso
, 

closu

 


 pow

 


pt

.
- Suppo
ts up to 32 G
 of m
mo
y
- 

sy to i
st
ll
- Sm
ll Fo
m F
cto

- Low 
ois
 & pow

 co
sumptio


Co
s:

- Th
 h


w


 is 
ot o
 th
 VMw


 HCL
- 



 
 co
v

t

 to co


ct to 
 
VI o
 VG
 mo
ito

- O
ly 2 co

s 
v
il

l

- 
o 
xp

sio
 possi
iliti
s such 
s 


i
g 

 
xt

 

tw

k c



- 
o 

mot
 m


g
m

t






