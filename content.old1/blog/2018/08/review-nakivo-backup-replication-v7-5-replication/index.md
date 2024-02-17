---
titl
: "

vi
w 

KIVO 

ckup & 

plic
tio
 v7.5 - 

plic
tio
"


t
: "2018-08-23T18:44:35.000Z"
c
t
go
i
s: 
  - "

kivo"
  - "

vi
w"
  - "

vi
ws"
t
gs: 
  - "

ckup"
  - "

plic
tio
"
  - "VMw


"

utho
: Ivo 





s
---

VM 

plic
tio
 p
ot
cts fo
 
x
mpl
 
g
i
st th
 followi
g typ
 of 
is
st

s:

- 

tu

l 
is
st

s  (


thqu
k
s, floo
s, to



os 
tc.)
- 

t
 c

t

  p
o
l
ms such 
s pow

 loss
s, fi

 


 w
t

 

m
g

- H


w


 p
o
l
ms such 
s host, 

two
k 


 sto

g
 f
ilu

s
- Hum

 


o
s
- VM f
ilu

s c
us

 
y up

t
s o
 p
tch
s, vi
us o
 m

u
lly 

mov
l

Th
 

plic
tio
 f

tu

 c

 

 us

 fo
 
usi

ss co
ti
uity 
s p

t of you'

 
is
st

 

cov

y pl

. Wh

 
 
is
st

 occu
s, th
 p
ot
ct

 VM(s) c

 

 quick f
il

 ov

 f
om th
 p
im

y sit
 to th
 

cov

y sit
.

[![](im
g
s/T
k

i
g1-300x139.jpg)](im
g
s/T
k

i
g1.jpg)

Wh

 th
 p
im

y sit
 is 

sto


 th
 VM(s) c

 

 f
il

 

ck to th
 p
im

y sit
.



oth

 us
 c
s
 it to us
 

plic
tio
 fo
 mig

ti
g th
 VMs to 
 

w VMw


 

vi
o
m

t fo
 
x
mpl
 wh

 movi
g f
om o
-p

mis
s to 
 clou
 p
ovi


.

**Co
figu

tio
**

Th
 co
figu

tio
 of th
 

plic
tio
 jo
 c

 

 
o

 
y usi
g  
 7 st
p wiz


:

[![](im
g
s/1-10-300x255.p
g)](im
g
s/1-10.p
g)

**1\. VMs.** S
l
ct th
 VM(s) th
t will 

 

plic
t

.

[![](im
g
s/2-10-300x185.p
g)](im
g
s/2-10.p
g)

2\. **

sti

tio
**. S
l
ct th
 

sti

tio
 host(s) 


 

t
sto

s th
 VM(s) will 

 

plic
t

 to.

[![](im
g
s/3-5-300x182.p
g)](im
g
s/3-5.p
g)

3\. **

two
ks**. If th
 VM o
 th
 p
im

y sit
 h
s 

oth

 

two
k th

 o
 th
 

cov

y sit
 you c

 m
k
 
 m
ppi
g 

tw


 th
m. I
 my t
st 

vi
o
m

t I h
v
 

 st

tch

 L2 

two
k so th
 sou
c
 


 t

g
t 

two
k 


 th
 s
m
.

[![](im
g
s/4-4-300x184.p
g)](im
g
s/4-4.p
g)

4\. **

-IP**. With this optio
 th
 

plic
t

 VMs will 

 m
pp

 to 
 

w IP 




ss. I
 my t
st 

vi
o
m

t I h
v
 

 st

tch

 L2 

two
k so th
 IP 




ss will 
ot ch

g
.

[![](im
g
s/5-1-300x172.p
g)](im
g
s/5-1.p
g)

5\. **Sch

ul
**.S
l
ct th
 sch

uli
g fo
 th
 

plic
tio
 jo
. Th
 VM 

plic
tio
 will 

 
x
cut

 
t th
 sch

ul
s. So 
ot
 th
t th
 VM(s) i
 p
im

y sit
 


 
ot sy
ch
o
ous 

plic
t

.

[![](im
g
s/6-2-300x183.p
g)](im
g
s/6-2.p
g)

6\. **

t

tio
**. S
t th
 

t

tio
 fo
 th
 

plic
t

 VMs. P

 VM you c

 h
v
 up to 30 

cov

y poi
ts.

[![](im
g
s/7-2-300x183.p
g)](im
g
s/7-2.p
g)

7\. **Optio
s**. S
t th
 optio
s fo
 th
 jo
.

[![](im
g
s/8-2-300x203.p
g)](im
g
s/8-2.p
g)

Click o
 Fi
ish & 
u
 to st

t th
 fi
st 

plic
tio
 jo
. Th
 VM will 

 

plic
t

 to th
 

cov

y sit
 i
 
 pow



 off st
t
 i
 th
 vSph


 cli

t.

[![](im
g
s/7-3-300x102.p
g)](im
g
s/7-3.p
g)

**P

fo
m 
 VM F
ilov

.**

If 
 
is
st

 occu
s 
t th
 p
im

y sit
 o
 som
thi
g h
pp

 with o

 o
 mo

 p
ot
ct

 VMs you c

 p

fo
m 
 f
ilov

 f
om th
 p
im

y to th
 

cov

y sit
. To p

fo
m 
 VM f
ilov

 follow th
s
 st
ps usi
g th
 followi
g wiz


:

I
 th
 

cov

 m

u s
l
ct VM f
ilov

 to 

plic
.

[![](im
g
s/1-11-256x300.p
g)](im
g
s/1-11.p
g)

1\. **Sou
c
**. S
l
ct th
 VM 


 

cov

y poi
t to us
.

[![](im
g
s/2-12-270x300.p
g)](im
g
s/2-12.p
g)

2\. **

two
ks**. If th
 VM o
 th
 p
im

y sit
 h
s 

oth

 

two
k th

 o
 th
 

cov

y sit
 you c

 m
k
 
 m
ppi
g 

tw


 th
m. I
 my t
st 

vi
o
m

t I h
v
 

 st

tch

 L2 

two
k so th
 sou
c
 


 t

g
t 

two
k 


 th
 s
m
.

[![](im
g
s/2-11-270x300.p
g)](im
g
s/2-11.p
g)

3\. **

-IP**. With this optio
 th
 

plic
t

 VMs will 

 m
pp

 to 
 

w IP 




ss. I
 my t
st 

vi
o
m

t I h
v
 

 st

tch

 L2 

two
k so th
 IP 




ss will 
ot ch

g
.

[![](im
g
s/4-6-268x300.p
g)](im
g
s/4-6.p
g)

4\. **Optio
s**. I
 th
 optio
s s
ctio
 

t

 th
 jo
 

m
. I ch
ck

 th
 "Pow

 off sou
c
 VMs" 
ox to p

v

t IP co
flicts.

[![](im
g
s/5-2-267x300.p
g)](im
g
s/5-2.p
g)

Click o
 th
 "**Fi
ish & 
u
**" 
utto
 to st

t th
 

cov

y jo
. Th
 VM i
 th
 p
im

y sit
 is pow



 off 


 th
 

plic
 VM is pow



 o
 i
 th
 

cov

y sit
. I
 th
 vSph


 cli

t, th
 

plic
 VM is 
u

i
g 
ft

 th
 f
ilov

.

[![](im
g
s/6-3-300x123.jpg)](im
g
s/6-3.jpg)

**VM F
il

ck.**


ft

 th
 
is
st

, th
 p
ot
ct

 VMs 


 
t th
 

cov

y sit
. Wh

 th
 i
f

st
uctu

 
t th
 p
im

y is 

sto


 you m
y w

t to 

tu

 th
s
 VMs 

ck. With th
 

plic
tio
 f

tu

 th
s
 VMs c

 

 t


sf




 

ck to th
 p
im

y sit
. T


sf


i
g th
 VMs 

ck i
volv
s p

fo
mi
g som
 m

u
l st
ps such 
s 

l
ti
g th
 

cov

y jo
 (with th
 k

p 

cov



 VMs optio
) 


 c


t
 
 

w 

plic
tio
 jo
.

[![](im
g
s/f
il

ck-300x139.jpg)](im
g
s/f
il

ck.jpg)

I
 
 

xt 

l

s
 of 

KIVO 

ckup & 

plic
tio
 
 

w f

tu

 c
ll

 "sit
 

cov

y" will 

 i
t
o
uc

. Sit
 

cov

y will 

h

c
 th
 

plic
tio
 f

tu

 with fo
 
x
mpl
 
utom
t

 t
sti
g 


 wo
kflow optio
s. With th
s
 optio
s you c

 t
st fo
 
x
mpl
 if th
 
is
st

 

cov

y pl

 wo
ks 
s 
xp
ct

 i
 
 isol
t

 

vi
o
m

t.

**Up

t
: 
ugust 27, 2018**. 

KIVO 


ou
c

 to

y v

sio
 8 with Sit
 

cov

y f

tu

. This pow

ful 

w f

tu

 
llows you to:

- 
uil
 
utom
t

 

cov

y wo
kflows
- 
u
 o

-click f
ilov

, f
il

ck, 


 

t
c

t

 mig

tio

- P

fo
m 
o
-
is
uptiv
 

cov

y t
sti
g M
k
 su

 you m

t you
 
TOs

Mo

 i
fo
m
tio
 

out th
 Sit
 

cov

y f

tu

 c

 

 fou

 h


 [li
k](https://www.

kivo.com/vm-
is
st

-

cov

y/).

I
 th
 

xt 

KIVO 

ckup & 

plic
tio
 

vi
w I will highlight th
 

itio
s, lic

si
g 


 co
clusio
 of my fou
 

vi
ws.






