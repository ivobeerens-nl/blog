---
titl
: "
u
 Hom
 
ssist

t o
 VMw


 
SXi"


t
: "2021-06-21T09:24:09.000Z"
c
t
go
i
s: 
  - "hom
-
ssist

t"
t
gs: 
  - "hom
-
ssist

t"

utho
: Ivo 





s
---

**Up

t

: 

c
m


 2, 2022**. 


i

 10 is 
ot suppo
t

 

y mo

 fo
 
u

i
g Hom
 
ssist

t Sup

vis

. Fo
 
 suppo
t

 co
figu

tio
, you 



 


i

 11 (
ulls
y
). Th
 st
ps i
 this 
log 


 up

t

 to i
st
ll Hom
 
ssist

t 
s 


i

 11 VM i
 VMw


 
SXi.

Hom
 
ssist

t Sup

vis

 p
ovi

s th
 full Hom
 
ssist

t 
xp

i

c
 o
 
 

gul

 op


ti
g syst
m. Th
 Sup

viso
 is 
ot just 

 
pplic
tio
 
ut it is 
 full 
ppli

c
 th
t m


g
s th
 whol
 syst
m. Hom
 
ssist

t sup

vis

 is o
ly suppo
t

 o
 
 **


i

 12** Op


ti
g Syst
m. 

low 


 th
 st
ps 

sc
i


 o
 how to i
st
ll Hom
 
ssist

t Sup

vis

 
s Vi
tu
l M
chi

 o
 
 


i

 11 (
ulls
y
) Op


ti
g Syst
m i
 VMw


 
SXi.



 Co
figu

 th
 Vi
tu
l M
chi

 h


w


 sp
cific
tio
s

- 
ow
lo

 th
 


i

-liv
-12.1.0-
m
64-st





.iso, [Li
k](https://c
im
g
.


i

.o
g/


i

-c
/cu



t-liv
/
m
64/iso-hy

i
/)
- M
k
 
 co


ctio
 to th
 
SXi host: https://<ip-




ss>/ui
- Uplo

 th
 


i

 ISO to 
 

t
sto


- C


t
 
 

w vi
tu
l m
chi

 with th
 followi
g sp
cific
tio
s:
    - **

m
:** <

m
 of th
 VM>
    - **Comp
ti
ility:** 

f
ult (
SXi  8 


 l
t

)
    - **Gu
st OS f
mily:** Li
ux
    - **Gu
st OS v

sio
:** 


i

 G
U/Li
ux 12 (64-
it)
    - **Sto

g
:** 

t
sto

 with mo

 th

 30 G
 of f


 sp
c

    - **CPUs**: 2
    - **M
mo
y:** 2048 M

    - **H


 
isk 1:** 40 G

        - **
isk P
ovisio
i
g:** Thi
 p
ovisio



    - **SCSI Co
t
oll

 0:** VMw


 P


vi
tu
l
    - **US
 co
t
oll

 1:** US
 2.0 o
 3.0 

p


i
g o
 th
 
SXi h


w



    - **

two
k 


pt

 1:** S
l
ct th
 po
t g
oup
        - **


pt

 typ
:** 
1000

    - **C
/
V
 

iv
 1:** 

t
sto

 ISO fil

        - 

ows
 to th
 


i

 ISO
        - **Co


ct 
t Pow

:** ch
ck


    - **Vi

o C


:** 

f
ult s
tti
gs
    - 

xt
    - Fi
ish
    - Pow

 o
 th
 VM
    - Op

 
 co
sol
 s
ssio


Th
 VM is 
ow co
figu


 with 
 p


vi
tu
liz

 SCSI co
t
oll

 (PVSCSI) 


 VMX

T3 Vi
tu
l 
IC.



 I
st
ll 


i

 12 
s VM o
 VMw


 
SXi

- **I
st
ll

 M

u**: **St

t I
st
ll

** 
- **L

gu
g
:** 

glish
- **Loc
tio
**:  Oth

, 
u
op
, 

th

l


s
- **Loc
l
s**:  U
it

 St
t
s
- **K
ym
p**:  
m

ic

 

glish
- **

t

 th
 host

m
**: h
-


12-01
- **
om
i
 

m
**: <
om
i
 

m
>
- **
oot p
sswo

**: <

t

 th
 
oot p
sswo

>
- **Full 

m
 fo
 th
 us

**:<Full 

m
>
- **Us

 

m
**: <us



m
>
- **Choos
 P
sswo

 fo
 th
 

w us

**: <

t

 th
 
oot p
sswo

>
- **P

titio
 
isks**: Gui


 - Us
 th
 

ti

 
isk 


 s
t up LVM
    - **S
l
ct 
isk to p

titio
**: SCSI1 (0,0,0) - 32,2 G
 VMw


 Vi
tu
l 
isk
    - **P

titio
 sch
m
**: 
ll fil
s i
 o

 p

titio
 (

comm




 fo
 

w us

s)
    - **W
it
 th
 ch

g
s to 
isk 


 co
figu

 LVM**: Y
s
    - **
mou
t of volum
 g
oup to us
 fo
 gui


 p

titio
i
g:** 42.4 G

    - **S
l
ct**: Co
ti
u

    - **W
it
 ch

g
s to 
isks**: Y
s
- **Co
figu

 th
 P
ck
g
 m


g

**: Y
s
- **


i

 

chiv
 mi

o
 cou
t
y**: S
l
ct th
 

chiv
 mi

o
 cou
t
y 




y. I s
l
ct

 

th

l


s
- **


i

 

chiv
 mi

o
**: 


.


i

.o
g
- **HTTP P
oxy**: L

v
 
mpty 


 s
l
ct co
ti
u

- **P

ticip
t
 i
 th
 p
ck
g
 us
g
 su
v
y**: 
o
- **Softw


 s
l
ctio
**:
    - Ch
ck: SSH s

v

 


 st





 syst
m utiliti
s
    - U
ch
ck: 


i

 

sktop 

vi
o
m

t
    - U
ch
ck: G
OM

- **I
st
ll th
 G
U
 
oot lo



 to th
 m
st

 
oot 

co

.** Y
s
- **

vic
 fo
 
oot lo



 i
st
ll
tio
?** /

v/s


- **I
st
ll
tio
 is compl
t
.** 
    - **Fi
ish th
 i
st
ll
tio
**: Co
ti
u


Th
 


i

 VM will 

 


oot

 


 is 



y fo
 us
. 
ft

 th
 i
st
ll
tio
, op

 
 co
sol
 s
ssio
 


 log i
.

**



l
 SSH**

\[co

 l

gu
g
="t
xt"\] su
o 
pt i
st
ll op

ssh-s

v

 su
o 


o /
tc/ssh/ssh
\_co
fig \[/co

\]





l
 po
t 22 


 s
v
 th
 fil


\[co

 l

gu
g
="t
xt"\] syst
mctl 

st

t ssh \[/co

\]

**



l
 Su
o o
 th
 us

 
ccou
t**

\[co

 l

gu
g
="t
xt"\] 


o /
tc/su
o

s \[/co

\]

S
v
 U



 th
 "Us

 p
ivil
g
 sp
cific
tio
" 


 th
 us

 
ccou
t c


t

 
u
i
g th
 


i

 i
st
ll
tio
. 

pl
c
 th
 <us



m
> with th
 

m
 of th
 us

 you 

t



 i
 th
 i
st
ll
tio
 ph
s
.

\[co

 l

gu
g
="t
xt"\] us



m
 
LL=(
LL:
LL) 
LL \[/co

\]

[![](im
g
s/su
o

s-300x159.jpg)](im
g
s/su
o

s.jpg)

P

ss CT
L + X to s
v
 th
 fil
. 
ow it is possi
l
 to us
 th
 su
o 
ccou
t u



 you
 us



m
.

\[co

 l

gu
g
="t
xt"\] 
xit su
o -i \[/co

\]

Mo

 i
fo
m
tio
: [How to I
st
ll 


 



l
 SSH o
 


i

 12/11/10 - Li
uxC
p

l
](https://www.li
uxc
p

l
.com/how-to-i
st
ll-


-



l
-ssh-o
-


i

-li
ux/
:~:t
xt=How%20to%20I
st
ll%20


%20



l
%20SSH%20o
%20


i

,



s.%20...%203%20St
p%203%3
%20Co


ct%20with%20SSH)

**Up

t
 
ll 


i

 p
ck
g
s** \[co

 l

gu
g
="t
xt"\] 
pt up

t
 && su
o 
pt upg



 -y && su
o 
pt 
uto

mov
 -y \[/co

\]

**Fi

 th
 IPv4 




ss of th
 VM 
y usi
g th
 comm


:**

VMw


 Tools is i
clu


 i
 th
 


i

 
ist
i
utio
 so you 
o
't 



 to i
st
ll VMw


 Tools p
ck
g
. Fi

 th
 IP 




ss 
y usi
g th
 followi
g comm


:

\[co

 l

gu
g
="t
xt"\] ifco
fig 

s192 \[/co

\]

Look fo
 th
 **i

t** 




ss. Th
t's th
 IP 




ss.

**M
k
 

 SSH co


ctio
 to th
 VM**

Co


ct usi
g SSH to th
 IP 




ss of th
 


i

 VM 
y usi
g Putty fo
 
x
mpl
.

\[co

 l

gu
g
="t
xt"\] su
o -i \[/co

\]

**I
st
ll th
 

qui


 p
ck
g
s**

\[co

 l

gu
g
="t
xt"\] 
pt-g
t i
st
ll 
 
pp

mo
 
 jq 
 wg
t 
 cu
l 
 u
isks2 
 li
gli
2.0-
i
 
 

two
k-m


g

 
 

us 
 ls
-

l

s
 
 syst
m
-jou


l-

mot
 -y \[/co

\]

**I
st
ll 
ock

-C
**

\[co

 l

gu
g
="t
xt"\] cu
l -fsSL g
t.
ock

.com | sh \[/co

\]

**I
st
ll th
 l
t
st 
g

t**

Th
 l
t
st 
g

ts c

 

 fou

 h


: https://githu
.com/hom
-
ssist

t/os-
g

t/

l

s
s/l
t
st



pl
c
 th
 "os-
g

t\_1.5.1\_li
ux\_x86\_64.


" with th
 
g

t v

sio
 you 
ow
lo



.

\[co

 l

gu
g
="t
xt"\] wg
t https://githu
.com/hom
-
ssist

t/os-
g

t/

l

s
s/
ow
lo

/1.5.1/os-
g

t\_1.5.1\_li
ux\_x86\_64.


 
pkg -i os-
g

t\_1.5.1\_li
ux\_x86\_64.


 \[/co

\]

You c

 ch
ck if th
 i
st
ll
tio
 w
s succ
ssful 
y 
u

i
g th
 followi
g comm


.

\[co

 l

gu
g
="t
xt"\] g

us i
t
osp
ct --syst
m --

st io.h
ss.os --o
j
ct-p
th /io/h
ss/os \[/co

\]

This shoul
 
ot 

tu

 

 


o
.

**I
st
ll Hom
 
ssist

t Sup

vis

 


i

 P
ck
g
**

\[co

 l

gu
g
="t
xt"\] wg
t https://githu
.com/hom
-
ssist

t/sup

vis

-i
st
ll

/

l

s
s/l
t
st/
ow
lo

/hom

ssist

t-sup

vis

.


 
pkg -i hom

ssist

t-sup

vis

.


 \[/co

\]


 


oot of th
 


i

 VM is 

c
ss

y.

\[co

 l

gu
g
="t
xt"\] 


oot \[/co

\]

[![](im
g
s/


oot-300x220.jpg)](im
g
s/


oot.jpg)


ft

 th
 


oot, you 



 to w
it (

tw


 1 


 20 mi
ut
s) fo
 th
 i
iti
l Hom
 
ssist

t co
figu

tio
.  With th
 comm


 "
ock

 ps" you c

 vi
w th
 st
tus of th
 
ock

 co
t
i


s. Th
 st
tus must 

 Up xx mi
ut
s.

Co


ct to H
ss.io: http://;:8123

[![](im
g
s/Logi
-300x147.jpg)](im
g
s/Logi
.jpg)

Hom
 
ssist

t Sup

vis

 is 
ow i
st
ll

 


 
u

i
g 
s 
 Vi
tu
l M
chi

 o
 VMw


 
SXi. You c

 ch
ck th
 syst
m h

lth 
y 

owsi
g to:

S
tti
gs -> Syst
m -> 

p
i
s -> 3 
ots -> Syst
m I
fo
m
tio


[![](im
g
s/suppo
t

-300x141.jpg)](im
g
s/suppo
t

.jpg)

Mo

 i
fo
m
tio
:

[GitHu
 - hom
-
ssist

t/sup

vis

-i
st
ll

: I
st
ll

 fo
 
 g



ic Li
ux syst
m](https://githu
.com/hom
-
ssist

t/sup

vis

-i
st
ll

)






