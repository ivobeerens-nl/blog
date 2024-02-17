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

ckup 


 

cov

y"


t
: "2018-08-16T06:36:40.000Z"
c
t
go
i
s: 
  - "

kivo"
  - "

vi
ws"
t
gs: 
  - "

ckup"

utho
: Ivo 





s
---



 **

ckup**

To 

gi
 with 

ckup 


 

cov

y w
 fi
st 



 
 

ckup jo
. Co
figu
i
g 
 

ckup jo
 co
t
i
s th
 followi
g fiv
 st
ps:

- **1\. VMs**: S
l
ct th
 VMs to 

ckup f
om th
 i
v

to
y of th
 vC

t

 S

v

 o
 
SXi host.

[![](im
g
s/1-2-267x300.p
g)](im
g
s/1-2.p
g) [![](im
g
s/2-3-271x300.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/2-3.p
g)

- **2\. 

sti

tio
**: S
l
ct th
 

sti

tio
 to sto

 th
 VMs. S
l
ct th
 o

o


 

posito
y with 


uplic
tio
 


 comp

ssio
 



l

 fo
 sto

g
 sp
c
 s
vi
gs.

[![](im
g
s/3-1-268x300.p
g)](im
g
s/3-1.p
g)

- **3\. Sch

ul
**: C


t
 o

 o
 mo

 

ckup sch

ul
s

[![](im
g
s/4-267x300.p
g)](im
g
s/4.p
g)

- **4\. 

t

tio
**: 

fi

 th
 

t

tio
 p

io
 fo
 

ch Vi
tu
l M
chi

 (VM). 

ch VM will h
v
 o

 o
 mo

 

cov

y poi
ts w


 i

ivi
u
l fil
s, 
pplic
tio
 o
j
ct o
 th
 th
 

ti

 VM c

 

 

cov



. 
 G



f
th

-F
th

-So
 (GFS) 

ckup 
ot
tio
 sch
m
 c

 

 us

.

[![](im
g
s/5-269x300.p
g)](im
g
s/5.p
g)

- **5\. Optio
s**: S
l
ct th
 optio
s fo
 th
 

ckup jo
:
    - **_
pp-
w


 mo

_**: Us
 this optio
 fo
 
pplic
tio
s th
t 

qui

 th
t th
 

t
 is co
sist

t such 
s Mic
osoft SQL 


 
xch

g
.
    - **_Ch

g
 t

cki
g_**: O
ly th
 
locks th
t 


 ch

g

 si
c
 th
 l
st 

ckup will 

 

ckup 

. This will i
c


s
 th
 

ckup sp


.
    - **_Sc



shot v

ific
tio
_**: 
ft

 th
 

ckup of 

ch VM it will 

 

cov



 (with th
 

two
k 
isco


ct

) 


 
 sc



shot will 

 m


 
ft

 th
 OS is st

t

. Th
 sc



shot will 

 i
clu


 i
 th
 
m
il 
otific
tio
 o
 i
 th
 jo
 

po
t.
    - _**
m
il 
otific
tio
s**_: Wh

 th
 jo
 compl
t
s th
 st
tus is s


 
y 
m
il.
    - **_T


spo
t Mo

_**: Hot 


, S

, L

 o
 
utom
tic c

 

 s
l
ct


    - **_



with th
ottli
g:_** With 



wi
th th
ottli
g you c

 co
t
ol th
 
mou
t of 



wi
th th
t is co
sum

 
y 

KIVO 

ckup 


 

plic
tio
.

[![](im
g
s/6-1-266x300.p
g)](im
g
s/6-1.p
g) [![](im
g
s/7-1-300x189.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/7-1.p
g) [![](im
g
s/8-1-291x300.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/8-1.p
g)

Th
 


 mo

 optio
s to co
figu

, 

f

 to th
 followi
g [li
k](https://h
lpc

t

.

kivo.com/
ispl
y/
H/

ckup+Jo
+Wiz


+fo
+VMw


%3
+Optio
s+St
p) fo
 
ll th
 optio
s to co
figu

.

I
 5 

sy wizz


 

s

 st
ps 
 

ckup jo
 is 

 co
figu


.




 **

po
ts**

Th


 


 s
v


l 

po
ti
g fu
ctio
s 
v
il

l
 such 
s:

- **L
st 
u
 

po
t.**  P
ovi

s th
 st
tus of th
 l
st 
u
 

ckup.
- **Poi
t-i
-tim
 

po
t.** P
ovi

s 

t
 o
 
 p

ticul

 jo
 
u
.
- **Jo
 histo
y 

po
t.** P
ovi

s 

t
 o
 jo
 
u
s th
t occu



 
u
i
g 
 sp
cifi

 tim
 p

io
.
- **P
ot
ctio
 cov


g
 

po
t.** Co
t
i
s i
fo
m
tio
 

out 
ll VMs 


 i
st

c
s p
ot
ct

 
y 

ckup 


/o
 

plic
tio
 jo
s, 
s w
ll 
s 

out 
ll u
p
ot
ct

 VMs 


 i
st

c
s.

Th
 "l
st 
u
" 

po
t is i
clu

s i
fo
m
tio
 

out th
 

ckup such 
s:

- Summ

y
- Vi
tu
l M
chi

s
- T

g
t Sto

g

- 
l

ms & 
otific
tio
s

This 

po
t c

 

 c


t

 m

u
lly o
 i
 th
 

ckup jo
 you c

 sp
cify th
 
m
il 




ss of o

 o
 mo

 

cipi

t(s) w


 th
 

po
t will 

 s


 to.

[![](im
g
s/

po
t-1-213x300.p
g)](im
g
s/

po
t-1.p
g)

Wh

 sc



shot v

ific
tio
 is us

, th
 sc



shot is 
lso i
clu


 i
 th
 

po
t.



 **

sto

 / 

cov

**

**
ppli

c
 

ckup**

Th
 co
figu

tio
 of th
 

KIVO 

ckup & 

plic
tio
 s

v

 /
ppli

c
 c

 

 s
cu


 
y usi
g th
 S
lf-

ckup f

tu

. Wh

 som
thi
g h
pp

 with th
 

KIVO 

ckup & 

plic
tio
 s

v

 th
 co
figu

tio
 c

 

 quickly 

sto


 o
 

oth

 s

v

.

[![](im
g
s/1-7-300x163.p
g)](im
g
s/1-7.p
g)


ft

 th
 fi
st 

ckup jo
 is fi
ish

 th


 
 multipl
 w
ys to 

cov

 VM 

t
. Th
 followi
g optio
s 


 
v
il

l
 to 

cov

 

t
 f
om th
 

ckups:

- **I

ivi
u
l fil
s**. You c

 

cov

 fil
s o
 fol


s 
i

ctly f
om comp

ss

 


 


uplic
t

 

posito
y.
- **Mic
osoft SQL S

v

 o
j
cts.** 



l
s 

owsi
g, s


chi
g, 


 

cov

i
g Mic
osoft SQL S

v

 o
j
cts.
- **Mic
osoft 
ctiv
 
i

cto
y o
j
cts. 
**


l
s 

owsi
g, s


chi
g, 


 

cov

i
g Mic
osoft 
ctiv
 
i

cto
y o
j
cts**.**
- **Mic
osoft 
xch

g
 o
j
cts**. 



l
s 

owsi
g, s


chi
g, 


 

cov

i
g Mic
osoft 
xch

g
 
m
ils.
- **
xpo
t 

ckups**. This is c
ll

 "**C
oss-Pl
tfo
m 

cov

y"** 


 will 

 h


l

 i
 th
 

xt p


g

ph.
- **Fl
sh VM 
oot**. 



l
s to 
u
 VMw


 


 Hyp

-V VMs 
i

ctly f
om 

posito
y without th
 



 to 

cov

 th
 VMs fi
st.
- **VM 

cov

y f
om 

ckup**. Full VM 

cov

y. Wh

 you 

cov

 
 VM, 
 

w VM is c


t

 


 th
 "ol
" VM is 

t
i


.

[![](im
g
s/2-4-264x300.p
g)](im
g
s/2-4.p
g)

I t
st

 s
v


l 

cov

 optio
s:

- **I

ivi
u
l fil
s.** I

ivi
u
l fil
s p

 VM c

 

 

sto


. Th
 fil
s c

 

 

cov



 o
 
 s

v

 (fo
 
x
mpl
 o
 th
 s
m
 loc
tio
 
s 

l
t

), 
ow
lo



 to th
 

ows

 o
 
m
il

. I t
st

 to 

cov

 two Pow

Sh
ll fil
s f
om 
 VM 


 s
l
ct

 th
 
ow
lo

 to 

ows

 optio
. Th
 fil
s 

cov

y is p

fo
m

 i
 s
co

s.

[![](im
g
s/2-7-300x178.p
g)](im
g
s/2-7.p
g) [![](im
g
s/3-3-300x155.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/3-3.p
g)

- **VM 

cov

y f
om 

ckup**. With this optio
 o

 o
 mo

 full VMs 


 

cov



.  Th
 o
igi

l VM will 

 

t
i


 so th
 

cov

i
g VM will 
ot ov

w
it
 th
 o
igi

l VM.  Th
 

cov

i
g VM 

m
 will 
pp


 "-

cov



" i
 th
 


. Th
 

cov

y is f
st.

[![](im
g
s/1-5-300x178.p
g)](im
g
s/1-5.p
g)[![](im
g
s/2-8-300x182.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/2-8.p
g) [![](im
g
s/4-1-300x149.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/4-1.p
g)

- **VM Fl
sh 
oot.** With th
 VM Fl
sh 
oot optio
 it's possi
l
 to 
oot VMs 
i

ctly f
om th
 comp

ss

 


 


uplic
t

 

posito
y without 

cov

i
g th
 VMs fi
st. This s
v
s tim
 


 c

 

 us

 fo
 
x
mpl
 fo
 t
sti
g softw


 up

t
s. VM Fl
sh 
oot us
s iSCSI t
ch
ology to co


ct VM 
isks sto


 i
 th
 

ckup to 
 t

g
t to th
 
SXi host. I
 this t
st I 

cov



 two VMs i
 isol
t

 

two
k 


 p

fo
m

 
 softw


 up

t
 fo
 t
sti
g. Th
 ch

g
s 


 
ot w
itt

 to th
 

cov

y poi
t th
t i'm usi
g. Wh

 i'm fi
ish

 with t
sti
g i c

 
isc


 th
 VMs with 
 si
gl
 click so th
t 
ll th
 ch

g
s 


 lost.

[![](im
g
s/1-8-300x191.p
g)](im
g
s/1-8.p
g) [![](im
g
s/2-9-300x191.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/2-9.p
g) [![](im
g
s/3-4-300x192.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/3-4.p
g) [![](im
g
s/4-3-300x192.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/4-3.p
g)

- **C
oss-Pl
tfo
m 

cov

y.** C
oss-Pl
tfo
m 

cov

y 
llows 
xpo
ti
g vi
tu
l 
isks to oth

 fo
m
ts such 
s:
    - VM
Ks fo
 VMw



    - VH
 fo
 Hyp

-V
    - V
HX fo
 Hyp

-V

This 
llows you to 

cov

 VMs i
 
iff



t 

vi
o
m

ts (VMw


 to Hyp

-V 


 Hyp

-V to VMw


). I
 this t
stI 
xpo
t

 
 VMw


 Vi
tu
l M
chi

 with two VM
K 
isks to VH
X 
isks with th
 

ckup 
xpo
t Wiz


. Th
 "
xpo
t 

ckups" wizz


 is us

 


 
y s
l
cti
g th
 VM 


 

cov

y poi
t, 
isks 


 optio
s to st

t th
 
xpo
t jo
.

[![](im
g
s/1-4-268x300.p
g)](im
g
s/1-4.p
g) [![](im
g
s/3-2-267x300.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/3-2.p
g) [![](im
g
s/2-5-269x300.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2018/08/2-5.p
g)

Wh

 th
 
xpo
t compl
t

, I c


t

 
 

w VM i
 Hyp

-V M


g

 


 poi
t

 to th
 

sto


 V
HX 
isks. Th

 i w
s 

l
 to st

t 
 Hyp

-V VM with th
 
xpo
t

 
isks 
tt
ch

. C
oss-Pl
tfo
m 

cov

y c

 

 us

 fo
 

cov

 VM 
isks f
om 

tw


 hyp

viso
 such 
s VMw


 vSph


 to Hyp

-V 


 to VMw


 Wo
kst
tio
 


 Vi
tu
l
ox.

[![](im
g
s/1-6-300x226.p
g)](im
g
s/1-6.p
g)

I
 this p

t of th
 

KIVO 

ckup & 

plic
tio
 

vi
w I highlight

 th
 

ckup 


 

cov

y f

tu

s. It w
s 
 pl

su

 to t
st th
 

ckup 


 

cov

y f

tu

s 

c
us
 th
y w


 

sy, quick 


 th
y wo
k

 out of th
 
ox without 

y t
ou
l
shooti
g skills 





. I
 th
 

xt 

vi
w I will highlight th
 

plic
tio
 f

tu

.






