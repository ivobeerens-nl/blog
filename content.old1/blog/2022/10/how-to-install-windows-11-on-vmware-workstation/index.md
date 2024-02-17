---
titl
: "How to i
st
ll Wi

ows 11 o
 VMw


 Wo
kst
tio
"


t
: "2022-10-17T07:26:48.000Z"
c
t
go
i
s: 
  - "VMw


-wo
kst
tio
"
  - "wi

ows-11"
t
gs: 
  - "VMw


-wo
kst
tio
"
  - "wi

ows-11"

utho
: Ivo 





s
---

[![](im
g
s/3-300x226.p
g)](im
g
s/3.p
g)

Wi

ows 11 

qui

s th
 followi
g h


w


 sp
cific
tio
s:

- CPU: 1 GHz o
 f
st

 with 2 o
 mo

 co

s o
 th
 p
oc
sso

- 

M: 4 G
 

M
-  Sto

g
: 64 G
 o
 l

g


- Fi
mw


: U
FI, S
cu

 
oot
- TPM: T
ust

 Pl
tfo
m Mo
ul
 (TPM) 2.0

Mo

 i
fo: [li
k](https://www.mic
osoft.com/

-i
/wi

ows/wi

ows-11-sp
cific
tio
s?
=1)

Th
 followi
g optio
s 


 
v
il

l
 wh

 i
st
lli
g Wi

ows 11 usi
g VMw


 Wo
kst
tio
 P
o/Pl
y

 


 Fusio
:

**Optio
 1:** Th
 physic
l 


poi
t such 
s 
 l
ptop o
 PC h
s 
 TPM 2.0 

vic
. This 

qui

s 


i
g 

c
yptio
 


 


i
g 
 vTPM 

vic
.

**Optio
 2:** Th
 physic
l 


poi
t such 
s 
 l
ptop o
 PC h
s comp
ti
l
 h


w


 
ut 
o TPM 2.0 

vic
. VMw


 Wo
kst
tio
 16.2 P
o 


s 

 
xp

im

t
l vTPM 

vic
 th
t us
s 
 

w 

c
yptio
 mo

 with i
c


s

 p

fo
m

c
 ov

 fully 

c
ypti
g th
 VM i
 optio
 1.

**Up

t
 Octo


 17, 2022:** Wil v

 

tw

p

 h
s 
 goo
 
log post 

out th
 
isks of this 
xp

im

t
l f

tu

.  M
k
 su

 th
t you 



 th
 
log 

fo

 usi
g this f

tu

!

[Wh
t you shoul
 k
ow 

out VMw


's 
xp

im

t
l vTPM - Vim
li
](https://www.vim
li
.com/
log/wh
t-you-shoul
-k
ow-

out-VMw


s-
xp

im

t
l-vtpm/)

**Optio
 3:** Th
 physic
l 


poi
t such 
s 
 l
ptop o
 PC h
s 
o comp
ti
l
 h


w


 such 
s 
 TPM 2.0 

vic
. Us
 
 

gist
y h
ck to 
yp
ss th
 TPM ch
ck.

If you 
o
't h
v
 
 Wi

ows 10/11 ISO, you c

 c


t
 o

 followi
g this 
log post: [Quick Tip: 
ow
lo

 th
 l
t
st Wi

ows 10/11 ISO fil
s - ivo





s.
l](https://www.ivo





s.
l/2021/05/19/quick-tip-
ow
lo

-th
-l
t
st-wi

ows-10-iso-fil
/)

H


 


 th
 st
ps outli


 fo
 

ch optio
:

**Optio
 1. Th
 physic
l 


poi
t such 
s 
 l
ptop o
 PC h
s 
 TPM 2.0 chip**

St

t VMw


 Wo
kst
tio
 


 c


t
 
 

w Vi
tu
l M
chi

 with th
 followi
g co
figu

tio
:

- Typ
 of co
figu

tio
: Custom (

v

c

)
- Vi
tu
l M
chi

 h


w


 comp
ti
ility: **Wo
kst
tio
 16.2.x**
- Gu
st Op


ti
g Syst
m I
st
ll
tio
: I
st
ll

 
isc im
g
 fil
 (iso): Poi
t to th
 
ow
lo



 Wi

ows 11 ISO
- Gu
st op


ti
g syst
m: Mic
osoft Wi

ows
    - V

sio
: **Wi

ows 10 


 l
t

 x64**
- Vi
tu
l M
chi

 

m
: 

m
 of th
 VM such 
s: Wi

ows 11
    - Loc
tio
: fo
 
x
mpl
: c:
vms
wi
11
- Fi
mw


: U
FI
    - S
cu

 
oot: Ch
ck
- P
oc
sso
s: 2 o
 mo


    - 
um


 of co

s: 1 o
 mo


- M
mo
y (M
): 4096 o
 mo


- 

two
k Typ
: Us
 

two
k 




ss t


sl
tio
 (

T)
- SCSI Co
t
oll

: LSI Logic S
S o
 P


vi
tu
liz

 SCSI
- Vi
tu
l 
isk Typ
: 
VM

- 
isk: C


t
 
 

w vi
tu
l 
isk
    - M
ximum 
isk siz
 (G
): 64 o
 mo


- 
isk fil
: Wi

ows 10 


 l
t

 x64.vm
k
- **Th
 

w VM will 

 c


t

**.
- 

it th
 vi
tu
l m
chi

 s
tti
gs
- Click o
 th
 optio
s t

, choos
 
cc
ss Co
t
ol, 


 s
l
ct 

c
ypt

[![](im
g
s/1-2-300x284.p
g)](im
g
s/1-2.p
g)

- 

t

 
 vi
tu
l m
chi

 p
sswo

 twic


[![](im
g
s/2-2-300x284.p
g)](im
g
s/2-2.p
g)

- Th
 VM will 

 

c
ypt


- S
l
ct th
 H


w


 t

 


 s
l
ct 



- S
l
ct th
 T
ust

 Pl
tfo
m Mo
ul
 


 click Fi
ish 


 OK

[![](im
g
s/3-1-300x284.p
g)](im
g
s/3-1.p
g)

- St

t th
 VM to i
st
ll Wi

ows 11

Th
 VM is 

c
ypt

 


 h
s 
 TPM 

vic
 co
figu


.

 

**Optio
 2:** Th
 physic
l 


poi
t such 
s 
 l
ptop o
 PC h
s comp
ti
l
 h


w


 
ut 
o TPM 2.0 

vic
.

Si
c
 VMw


 Wo
kst
tio
 16.2 th


 is 

 
xp

im

t
l f

tu

 without th
 



 fully 

c
ypt th
 VM. Us
 it with c


 


 



 th
 
log f
om Wil v

 

tw

p

 

fo

 usi
g this f

tu

!

- Follow th
 st
ps i
 st
p 1 till  " **Th
 

w VM will 

 c


t

"**
- 

fo

 st

ti
g th
 VM clos
 VMw


 Wo
kst
tio

- 

it th
 VMX fil
 of th
 c


t

 VM i
 
ot
p

 fo
 
x
mpl

    - 


 th
 followi
g li

 to th
 


 of th
 fil
:
    - _m


g

VM.
uto


VTPM = "softw


"_
    - This li

 


s 
 TPM 2.0 

vic
 to th
 VM
    - S
v
 th
 VMX fil


[![](im
g
s/2-1-300x156.jpg)](im
g
s/2-1.jpg)

- Op

 VMw


 Wo
kst
tio

- St

t th
 VM to i
st
ll Wi

ows 11

**Optio
 3:** Th
 physic
l 


poi
t such 
s 
 l
ptop o
 PC h
s 
o comp
ti
l
 h


w


 such 
s 
 TPM 2.0 

vic
. Us
 
 

gist
y h
ck to 
yp
ss th
 TPM ch
ck.

I
 2021 I 
l



y 
logg

 

out this h
ck. Mo

 i
fo
m
tio
 c

 

 fou

 h


: [I
st
ll Wi

ows 11 
s VM o
 VMw


 vSph


 / Wo
kst
tio
 without TPM 2.0 - ivo





s.
l](https://www.ivo





s.
l/2021/10/06/i
st
ll-wi

ows-11-
s-vm-i
-VMw


-vSph


-wo
kst
tio
-without-tpm-2-0/)

 

With th
s
 3 optio
s, you 


 

l
 to i
st
ll Wi

ows 11 o
 VMw


 Wo
kst
tio
 P
o/Pl
y

 


 Fusio
 i
 most situ
tio
s.






