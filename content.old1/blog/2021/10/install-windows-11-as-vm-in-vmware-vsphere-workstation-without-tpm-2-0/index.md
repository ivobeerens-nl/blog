---
titl
: "I
st
ll Wi

ows 11 
s VM o
 VMw


 vSph


 / Wo
kst
tio
 without TPM 2.0"


t
: "2021-10-06T10:18:20.000Z"
c
t
go
i
s: 
  - "wi

ows-11"
t
gs: 
  - "tpm"
  - "VMw


"
  - "wi

ows-11"

utho
: Ivo 





s
---

Th
 fi
st st
p is to 
ow
lo

 Wi

ows 11. This c

 

 
o

 
y visiti
g th
 Wi

ows 11 
ow
lo

 p
g
 ([li
k](https://www.mic
osoft.com/

-us/softw


-
ow
lo

/wi

ows11)) 


 
ow
lo

 th
 ISO im
g
 o
 c


t
 

 ISO im
g
 with th
 M

i
C


tio
Tool ([Quick Tip: 
ow
lo

 th
 l
t
st Wi

ows 10 ISO fil
](https://www.ivo





s.
l/2021/05/19/quick-tip-
ow
lo

-th
-l
t
st-wi

ows-10-iso-fil
/)). 
ft

 th
 
ow
lo

 put th
 ISO o
 
 

t
sto

 


 c


t
 
 VM with th
 followi
g sp
cific
tio
s:

- H


w


 Sp
cific
tio
s:
    - Comp
ti
ility: 
SXi 7.0 U2 


 l
t

 (I'm usi
g 
SXi 7)
    - Gu
st OS: Wi

ows 10 (64-
it)
        - 



l
 Wi

ows Vi
tu
liz
tio
 

s

 S
cu
ity: Ch
ck
    - CPU: 2
    - M
mo
y: 4 G

    - H


 
isk: 64 G

    - C
/
V
: 

t
sto

 o
 ISO
        - Co


ct: Ch
ck
- 
oot th
 VM with th
 ISO co


ct

 


 th
 i
st
ll
tio
 of Wi

ows 11 will 

gi
.
- S
l
ct th
 co


ct L

gu
g
, Tim
 


 cu



cy fo
m
t, 


 k
y
o


 l
yout

[![](im
g
s/1-300x248.jpg)](im
g
s/1.jpg)

- S
l
ct "I
st
ll 
ow"

[![](im
g
s/2-300x253.jpg)](im
g
s/2.jpg)

- 
 M
ss
g
 
pp


s th
t this PC c

't 
u
 Wi

ows 11

[![](im
g
s/3-300x253.jpg)](im
g
s/3.jpg)

- P

ss **Shift** + **F10**
- 
 
OS 
ox 
pp


s. Typ **

g

it** 


 hit **

t

**

[![](im
g
s/5-300x225.jpg)](im
g
s/5.jpg)

- 

vig
t
 to **HK
Y\_LOC
L\_M
CHI


SYST
M
S
tup** 


 c


t
 
 

w K
y 

m

 **L

Co
fig**
- C


t
 i
 th
 L

Co
fig K
y 
 **
yP
ssTPMCh
ck** 
WO

 (32-
it) with th
 v
lu
 of **1**
- Clos
 th
 

g

it wi

ow (click o
 th
 


 X i
 th
 
ight co



)
- Typ **
xit** to l

v
 th
 comm


 p
ompt
- Click o
 th
 


 X i
 th
 
ight co



 


 th
 s
tup will st

t 
g
i


[![](im
g
s/6-300x225.jpg)](im
g
s/6.jpg)

- Th
 s
tup is 
ow 

l
 to i
st
ll Wi

ows 11 
s VM i
 VMw


 
SXi o
 VMw


 Wo
kst
tio
.
- Wh

 th
 s
tup is fi
ish

 you h
v
 
 Wi

ows 11 VM 
u

i
g.

[![](im
g
s/7-300x225.jpg)](im
g
s/7.jpg)

With this p
oc

u

, you c

 
u
 Wi

ows 11 o
 h


w


 th
t 
o
s
't h
v
 
 TPM 2.0 chip.  This p
oc

u

 is 
ot offici
lly suppo
t

 of cou
s
! Fo
 
x
mpl
, you m
y 
ot 

c
iv
 s
cu
ity up

t
s i
 th
 futu

 if you 
yp
ss th
 h


w


 

qui

m

ts such 
s TPM.

VMw


 vSph


 suppo
ts 
 Vi
tu
l T
ust

 Pl
tfo
m Mo
ul
 (vTPM) th
t 
mul
t
s 
 physic
l TPM 2.0 without h
vi
g o

. W

t to k
ow mo

? 



 my oth

 
log post c
ll

 "[I
st
ll Wi

ows 11 o
 VMw


 vSph


 with 
 vi
tu
l TPM](https://www.ivo





s.
l/2021/10/07/i
st
ll-wi

ows-11-o
-VMw


-vSph


-with-
-vi
tu
l-tpm/)".






