---
titl
: "Thi
gs to k
ow 

fo

 impl
m

ti
g VMw


 

t
 

cov

y (v

) 2.0"


t
: "2011-09-06T11:02:45.000Z"
c
t
go
i
s: 
  - "v

"
  - "VMw


-

t
-

cov

y"
t
gs: 
  - "v

"
  - "VMw


-

t
-

cov

y"

utho
: Ivo 





s
---

> - VMw


 

t
 

cov

y 2.0 is 
ow 
 fully 64-
it vi
tu
l 
ppli

c
.
> 
> - 
m
il 

po
ts. VMw


 

t
 

cov

y 2.0 m
k
s it possi
l
 to g




t
 


 
m
il 

po
ts, i
 
 fully 
utom
t

 f
shio
, to 

 

mi
ist

to
 followi
g th
 compl
tio
 of 
 

ckup.
> 
> - 

tt

 


uplic
tio
 P

fo
m

c

> 
> - Jo
 Susp

sio
. VMw


 

t
 

cov

y 



l
s us

s to susp


 i

ivi
u
l jo
s f
om co
ti
ui
g to 
u
 
y 
ight-clicki
g o
 th
 

ckup jo
 


 s
l
cti
g “Susp


 Futu

 T
sks.”
> 
> - 

v

c

 Optio
s such 
s Ch

g
 th
 
um


 of 

ys 

tw


 
utom
t

 i
t
g
ity ch
cks, Sp
cify th
 

y of th
 w

k o
 which th
 
utom
t

 i
t
g
ity ch
ck is 
u
 


 
xclu

 o
 i
clu

 

ckup of sw
p p

titio
s o
 p
g
 

t
.
> 
> - Wi

ows p
g
fil
 


 Li
ux sw
p p

titio
s 


 
utom
tic
lly 
xclu


 f
om 

ckup 
y 

f
ult.
> 
> - If th
 m
i
t



c
 wi

ow clos
s 

fo

 

 i
t
g
ity ch
ck o
 

cl
im op


tio
 is compl
t

, th
 

t
sto

 is 
ot lock

 
s it w
s i
 p
io
 

l

s
s. This 



l
s 

ckups to co
ti
u
 wo
ki
g 
v

 if m
i
t



c
 is 
ot compl
t

. If, how
v

, 

m
g

 

sto

 poi
ts 


 

t
ct

, th
 


uplic
tio
 

t
sto

 will 

 lock

 u
til th
 

m
g

 

sto

 poi
ts 


 

l
t

.
> 
> - Issu
s 

solv

 fou

 i
 v

 1.2.1:
> 
> • CIFS t

g
t h


li
g 


 

sili

c
 • I
c

m

t
l 

M 

ckup • 

ckups f
ili
g with “
ot 

ough 
isk sp
c
” 


o
s • 

ckups f
ili
g with “
isk full” 


o
 

spit
 f


 sp
c
 

i
g 
v
il

l


 




 

fo

 impl
m

ti
g v

 2.0 co
si


 th
 followi
g thi
gs:

- VMw


 

t
 

cov

y is 
v
il

l
 i
 th
 followi
g vSph


 5 

itio
s: 
ss

ti
ls plus, St





, 

t

p
is
 


 

t

p
is
 Plus.

- It is possi
l
 to full 
is
st

 

cov

y 
v

 wh

 th


 is
’t 

y vC

t

 s

v

 
v
il

l
 fo
 
x
mpl
 

c
us
 it w
s i
st
ll

 
s VM. Follow th
s
 st
ps:

> - Co


ct 
i

ctly to 
 
SXi s

v

 with th
 vSph


 cli

t
> 
> - I
st
ll th
 VMw


 

t
 

cov

y 
ppli

c

> 
> - I
st
ll th
 VMw


 

t
 

cov

y cli

t
> 
> - Co


ct to th
 VM
K, 
FS o
 CIFS sh


 us

 
s 


uplic
tio
 sto

(s)
> 
> - M
ss
g
 
pp


s to impo
t th
 “ol
” co
figu

tio
:
> 
> [![im
g
](im
g
s/im
g
_thum
7.p
g "im
g
")](im
g
s/im
g
7.p
g)
> 
> - S
l
ct “y
s” to impo
t th
 “ol
” co
figu

tio

> 
> - 
ow th
 co
figu

tio
 is 

ck, you 


 



y to 

sto

 
ll th
 VMs
> 
>  

- 

ch 

ckup 
ppli

c
 c

 p
ot
ct 
 tot
l of 100 Vi
tu
l M
chi

s. If you w

t mo

 VMs to 

ckup 


 

 
xt

 

ckup 
ppli

c
.

- 

ch i
st

c
 of vC

t

 S

v

 c

 suppo
t up to t

 

t
 

cov

y 

ckup 
ppli

c
s.

- suppo
t 


uplic
tio
 sto

s th
t 


 up to o

 t



yt
 i
 siz
 


 

ch 

ckup 
ppli

c
 is limit

 to usi
g two 


uplic
tio
 sto

s p

 
ppli

c
 ( 1 T
 o
 VM
Ks 


 

Ms 


 500 G
 o
 CIFS 

two
k sh


s).

- v

 

qui

s 

 

solut
 mi
imum of 10 G
 of f


 sp
c
 p

 sto

 fo
 i


xi
g 


 

sto

 poi
t p
oc
ssi
g. 
u
 to this s
iz
 th
 sto

s 
ot sm
ll

 
s 50 G
.

- Fo
 i
iti
l s
tup s
iz
 th
 


uplic
tio
 sto

 sp
c
 
qu
l to th
 
mou
t of us

 
isk sp
c
 o
 
ll th
 VMs 

i
g p
ot
ct

.

- Us
 VM
K’s 
s 


uplic
tio
 sto

 us
 thick p
ovisio
i
g 

g

 z

o

 fo
 th
 

st p

fo
m

c
.

- Pl
c
 th
 


uplic
tio
 sto

(s) o
 sto

g
 

vic
 o
 

oth

 loc
tio
.

- Usi
g CIFS sh


s 
s 


uplic
tio
 sto

 
voi
 sto

s o
 s

v

s with multipl
 
ol
s o
/


 s

vic
s 


 i
 
 VM.

- CIFS sh


s with p
sswo

s limit

 to 64 ch


ct

s o
 l
ss. CIFS sh


 p
sswo

s must co
fo
m to th
 L
ti
 1(ISO 8859-1) st





. 
ou
l
-
yt
 ch


ct

s 


 
ot suppo
t

.

- 
FS is o
ly suppo
t

 
s 
 


uplic
tio
 sto

 fo
m
t if th
 sh


 is p

s

t

 
y 

 
SX/
SXi S

v

 


 th
 VM
K is 
ssig


 to th
 

t
 

cov

y 
ppli

c
.

- 
ll th
 v

 
ppli

c
s 


 m


g

 s
p


t
ly.

- H


w


 v

sio
 7 of high

 is 





 fo
 usi
g Ch

g

 
lock T

ci
g (C
T). Upg



 th
 h


w


 v

sio
 4 VMs.

- Wi

ows p
g
fil
s (p
g
fil
.sys) fil
 


 th
 Li
ux sw
p p

titio
 is 
ot 

ck

 up.

- VMw


 

t
 

cov

y us
s Mic
osoft Wi

ows Volum
 Sh

ow Copy S

vic
 (VSS) qui
sci
g ( poi
t-i
-tim
 copi
s).

- H


’s 

 ov

vi
w of th
 Gu
st Op


ti
g Syst
ms 


 th
 qui
sci
g m
tho
:

[![im
g
](im
g
s/im
g
_thum
8.p
g "im
g
")](im
g
s/im
g
9.p
g)

- 
pplic
tio
 co
sist

t qui
sci
g of Wi

ows 2008 vi
tu
l m
chi

s is o
ly 
v
il

l
 wh

 thos
 vi
tu
l m
chi

s 


 c


t

 i
 vSph


 4.1 


 l
t

. Vi
tu
l m
chi

s c


t

 i
 vSph


 4.0 c

 

 up

t

 to 



l
 
pplic
tio
 co
sist

t qui
sci
g, 
s 

sc
i


 i
 



l
 Wi

ows 2008 Vi
tu
l M
chi

 
pplic
tio
 Co
sist

t Qui
sci
g.

- 

c
us
 

t
 

cov

y us
s VSS, 

t
 

cov

y c

 c


t
 s

pshots whil
 

su
i
g 
pplic
tio
 co
sist

cy. This m


s th
t 
pplic
tio
s w
it
 to 
isk 

y impo
t

t 

t
 th
t is cu



tly i
 m
mo
y, m
ki
g su

 th
t 
 l
t

 

sto

 of th
t vi
tu
l m
chi

 c

 

sto

 th
 
pplic
tio
 

ck i
to 
 co
sist

t st
t
.

-  
 m
ximum of 8 vi
tu
l m
chi

s c

 

 

ck

 up simult


ously. 

f
ult o
ly 14 SCSI 
isks c

 

 hot-




. Fo
 
x
mpl
 wh

 

ckup 8 VMs with th


 
isks, th
 hot-


 c

 o
ly hot-


 14 
isks, th
 oth

 
isks 


 

ck

 up ov

 th
 

two
k. 


 

 
xt

 
ummy 
isk (1M
) fo
 
v

y SCSI 


pt

 i
 th
 v

 
ppli

c
 co
figu

tio
 so th
t th
 hot-


 h
s 

ough 
oom.

 

- v

 
o
s 
ot suppo
t:

> - 

cki
g up vi
tu
l m
chi

s th
t 


 p
ot
ct

 
y VMw


 F
ult Tol



c
,-
> 
> - 

cki
g up vi
tu
l m
chi

s with 3

 p

ty multi-p
thi
g 



l

 wh


 sh



 SCSI 
us
s 


 i
 us

> 
> - 

w 

vic
 m
pp

 (

M) 
isks i
 physic
l comp
ti
ility mo

 i
 vi
tu
l m
chi

s to 

 

ck

 up
> 
> - Multipl
 

ckup 
ppli

c
s o
 
 si
gl
 host
> 
> - 

ckup of vi
tu
l m
chi

 
isks th
t 


 m

k

 
s I


p




t
> 
> - 

ckup of Sto

g
 Vi
tu
l 
ppli

c
s (SV
s)
> 
>  

**-** v

 is i
t

t fo
 SM
 custom

. Wh

 usi
g mo

 th

 o

 v

 
ppli

c
 it’s 
ifficult to m


g
. If you w

t mo

 
o
ust  solutio
 look 3
 p

ty softw


 fo
 
x
mpl
 
t V


m 

ckup 


 

cov

y o
 T
il


 VM 
xplo


.

 

 




 **Mo

 i
fo
m
tio
 o
 VMw


 

t
 

cov

y 2.0**:

- [Wh
t’s 

w i
 VMw


 

t
 

cov

y 2.0](http://www.VMw


.com/fil
s/p
f/t
chp
p

/Wh
ts-

w-VMw


-

t
-

cov

y-20-T
ch
ic
l-Whit
p
p

.p
f)






