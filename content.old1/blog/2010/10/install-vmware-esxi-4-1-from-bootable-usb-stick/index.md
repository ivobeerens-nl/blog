---
titl
: "I
st
ll VMw


 
SXi 4.1 f
om 
oot

l
 US
 stick"


t
: "2010-10-25T08:00:00.000Z"
c
t
go
i
s: 
  - "
oot"
  - "
sxi"
  - "us
"
  - "vSph


"
t
gs: 
  - "
oot"
  - "
sxi-2"
  - "
sxi-4-1"
  - "us
"
  - "VMw


"
  - "vSph


"

utho
: Ivo 





s
---

**P

p


tio
:**

- 



 1G
 US
 m
mo
y stick o
 mo

.
- 
ow
lo

 th
 VMw


 
SXi 4.1 ISO 

m

 **VMw


-VMviso
-I
st
ll

-4.1.0-260247.x86\_64.iso** (I
 this 
x
mpl
 I us

 th
 VMw


 vSph


 Hyp

viso
 v

sio
).

**Up

t
: Th
 l
t
st v

sio
 of VMw


 
SXi is  4.1 Up

t
 1 (VMw


-VMviso
-I
st
ll

-4.1.0.up

t
1-348481.x86\_64.iso). It solv
s th
 “Tot
l 
um


 of s
cto
s” 
ug i
 VMw


 
SXi 4.1. It is 

comm


 to us
 this v

sio
 so th
 “mo
.tgz” wo
k

ou

 is
’t 





 

ymo

!**

- 
ow
lo

 Sysli
ux, c

 

 fou

 
y clicki
g o
 th
 followi
g [li
k](http://www.k



l.o
g/pu
/li
ux/utils/
oot/sysli
ux/). 
ow
lo

 th
 l
t
st Sysli
ux zip fil
 (wh

 w
iti
g this 

ticl
  sysli
ux-4.02.zip w
s th
 l
t
st).

**Up

t
: 
lso t
st

 Sysli
ux v

sio
 4.03.**

Stick th
 US
 stick o
 
  f


 US
 po
t o
 you
 comput

 
quipp

 with 
 Wi

ows OS. Fo
 this 
x
mpl
 I us

 Wi

ows7 
s Op


ti
g Syst
m. Cl


 th
 US
 stick 


 c


t
 
 p

titio
 o
 it 
y usi
g th
 followi
g comm


’s:

- Op

 th
 comm


 p
ompt 


 

t

 th
 followi
g comm


s:


iskp

t (m
k
 su

 you 
u
 
iskp

t 
s 

mi
ist

to
) 

list 
isk (list th
 
isk i
 you
 syst
m i
clu
i
g th
 US
) 

s
l
ct 
isk US
 
um


 

cl


 

c


t
 p

titio
 p
im

y 


ctiv
 

fo
m
t fs=f
t32 quick 


ssig
 


xit

To m
k
 th
 US
 stick 
oot

l
:

- 
xt

ct th
 Sysli
ux ZIP 


 

ows
 to th
 th
 
sysli
ux
wi
32 fol


,  
x
cut
 “**sysli
ux \[

iv
 l
tt

 US
 stick\]**”, 
x
mpl
 **sysli
ux f:**

- Mou
t th
 ISO  


 copy 
ll th
 co
t

t of th
 VMw


 
SXi 4.1 ISO to th
 US
 stick. Fo
 mou
ti
g th
 ISO, I us

 ‘


mo
 Tools Lit
’ tool.

- 



m
 th
 **isoli
ux.cfg** fil
 to **sysli
ux.cfg**

- 

it th
 sysli
ux.cfg 


 


 **ks=us
** 


 o
 th
 


 of th
 
pp


 li

 **--- mo
.tgz** (

w


 of th
 sp
c
 

tw


 **---** 


 th
 **mo
.tgz).**

**Up

t
: Wh

 usi
g VMw


 
SXi 4.1 Up

t
 1 th
 mo
.tgz li

 
o
s
’t 



 to 
pp


!**



f
ult m

u.c32

m

u titl
 VMw


 VMviso
 
oot M

u

tim
out 80

l


l 
SXi I
st
ll



m

u l


l ^
SXi I
st
ll



k



l m
oot.c32


pp


 vmk
oot.gz ks=us
 --- vmk



l.gz --- sys.vgz --- cim.vgz --- i

vi
o
.vgz --- i
st
ll.vgz --- mo
.tgz

l


l ^
oot f
om loc
l 
isk

m

u l


l ^
oot f
om loc
l 
isk

loc
l
oot 0x80

- C


t
 
 **ks.cfg** fil
 i
 th
 
oot f
om th
 U
S stick. Fo
 
x
mpl
:


ootpw VMw


01

i
st
ll us



utop

t --fi
st
isk --ov

w
it
vmfs




oot




two
k i
st
ll typ




two
k --
ootp
oto=st
tic --


vmpo
tg
oup=f
ls
 --

vic
=vm
ic0 --ip=192.168.1.10 --

tm
sk=255.255.255.0 --g
t
w
y=192.168.1.1  --

m
s

v

=192.168.1.1 --host

m
=
SXi-01.





s.loc
l


cc
pt
ul


%fi
st
oot --u
suppo
t

 --i
t

p

t

=
usy
ox

vim-cm
 hostsvc/

t
sto

/



m
 

t
sto

1 "$(host

m
 -s)-loc
l-sto

g
-1"

- Copy th
 sysli
ux-4.02
com32
m
oot
**m
oot.c32** fil
 th
 US
 stick (ov

w
it
 th
 ol
 fil
 o
 th
 US
 stick) 

- Copy th
 sysli
ux-4.02
com32
m

u
**m

u.c32** fil
 th
 US
 stick (ov

w
it
 th
 ol
 fil
 o
 th
 US
 stick)

Th
 
oot

l
 VMw


 
SXi 4.1 stick is 



y fo
 us
. Wh

 
ooti
g  th
 US
 stick th
 followi
g m
ss
g
 is 
ispl
y

 “**Tot
l 
um


 of s
cto
s 
ot 
 multipl
 of s
cto
s p

 t

ck! 


 mtools\_skip\_ch
ck=1 to you
 .mtools
c fil
 to skip this t
st**”.

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

**Up

t
: Wh

 usi
g VMw


 
SXi 4.1 Up

t
 1 this 
ug is fix

. You’

 



y to us
 th
 US
 stick!**

O
 th
 VMw


 commu
iti
s I fou

 th
 followi
g [post](http://commu
iti
s.VMw


.com/m
ss
g
/1621352). This post st
t
s 
 m

u
l solutio
 
y usi
g th
 followi
g comm


s:

- P

ss 
LT-F1

- Logi
 
y usi
g th
 
oot 
ccou
t with 
o p
sswo



- **
cho “mtools\_skip\_ch
ck=1”>.
mtools
c**

- 
LT+F2 


 

tu

 to th
 o
gi

l Co
sol
  wi

ow

- P

ss 

T

 o
 w
it to co
ti
u


To 
utom
t
 th
 

ov
 solutio
 



 th
 followi
g 
logpost “**VMw


 
SX 4.1 i
st
ll usi
g W
st


 
igit
l US
 H


 

iv
”** . 
y usi
g  this 
logpost I c


t

 
 mo
.tgz fil
 
y usi
g th
 followi
g comm


s f
om 
 full i
st
ll
tio
 of VMw


 
SXi 4.1:

- Logi
 th
 VMw


 
SXi 4.1 co
sol


- M
k
 
 
i

cto
y i
 th
 
oot fo
 
x
mpl
 mk
i
 t
mp

- c
 t
mp

- mk
i
 –p 
tc/VMw


/i
it/i
it.
/

- c
 
tc/VMw


/i
it/i
it.
/

- vi 47.mtoolsh
ck


cho "mtools\_skip\_ch
ck=1" >/.mtools
c



tu

 ${SUCC
SS}

- S
v
 th
 fi usi
g th
 comm


 **:wq** i
 VI

- c
 /t
mp

- t

 czvf mo
.tgz 
tc

- SCP th
 fil
 **mo
.tgz** fil
 to th
 US
 stick

Th
 mo
.tgz c

 
lso 
ow
lo



, so th
 

ov
 st
ps c

 

 skip

. O
 th
 


 of this 

ticl
 is 
 
ow
lo

 li
k fo
 th
 mo
.tgz.

Th
 mo
.tgz co
t
i
s 

 i
it sc
ipt which skips th
 mtools ch
ck. 
ow you’

 



y to 
oot you
 s

v

 with th
 US
 stick 


 you
 

l
 to i
st
ll  VMw


 
SXi 4.1. 





 [
ow
lo

 mo
.tgz](https://www.ivo





s.
l/wp-co
t

t/uplo

s/mo
.tgz)

**Up

t
 : Wh

 usi
g VMw


 
SXi 4.1 Up

t
 1 th


 is 
o 



 to 


 th
 mo
.tgz 

c
us
 this 
ug is fix

.**

\[








\]






