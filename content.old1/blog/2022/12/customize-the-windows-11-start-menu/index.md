---
titl
: "Customiz
 th
 Wi

ows 11 St

t M

u"


t
: "2022-12-13T07:37:53.000Z"
c
t
go
i
s: 
  - "wi

ows-11"
t
gs: 
  - "st

t-m

u"
  - "wi

ows-11"

utho
: Ivo 





s
---

[![](im
g
s/2st

tm

u-300x144.jpg)](im
g
s/2st

tm

u.jpg)

 

Th


 


 m

y 

vi
o
m

ts (such 
s V
I 


 
zu

 Vi
tu
l 

sktop(
V
) th
t 
o
't us
 

 M
M p
ovi


 to m


g
 th
i
 Wi

ows 11 wo
ksp
c
 

vi
o
m

t. I
 this 
log post, I will highlight how to m


g
 th
 St

t M

u with 

tiv
 tools such 
s 
ctiv
 
i

cto
y 


 G
oup Polici
s.

I will c


t
 s
v


l 
log posts 

out how to customiz
 th
 Wi

ows 11 St

t M

u, co
figu

 th
 t
sk


, 

mov
 u
w

t

 

sktop ico
s 


 

mov
 
lo
tw


 


 
pps.

- **Customiz
 th
 Wi

ows 11 St

t M

u (this 
log post)**
- **Customiz
 th
 Wi

ows 11 

sktop ico
s**
- **Customiz
 th
 T
sk


 ico
s**
- **

mov
 
lo
tw


 f
om th
 St

t M

u**

I
 this 
log post, I will highlight how to customiz
 th
 Wi

ows 11 St

t M

u with 

tiv
 
ctiv
 
i

cto
y G
oup Polici
s.

I
 Wi

ows 10 you c

 
xpo
t 


 impo
t th
 St

t M

u l
yout. With th
 "
xpo
t-St

tL
yout" Pow

Sh
ll comm


, th
 St

t M

u is 
xpo
t

 to 

 XML fil
. With 
 G
oup Policy, you 

f

 to th
 custom XML fil
.

I
 Wi

ows 11, th
 St

t M

u is 
xpo
t

 to 
 JSO
 fil
. Th
 comm


 is lik
 this:


xpo
t-St

tL
yout -P
th "C:
L
youts
L
youtMo
ific
tio
.JSO
"

Th


 is 
o G
oup Policy (Wi

ows 11 22H2) to impo
t 
 St

t M

u JSO
 fil
. Th
 G
oup Policy o
ly wo
ks with 

 XML fil
.

Th


 is 
 wo
k

ou

. I
 Wi

ows 11 th
 St

t M

u is sto


 i
 
 si
gl
 

c
ypt

 fil
 i
 th
 followi
g fol


 loc
tio
:

%Loc
l
pp

t
%
P
ck
g
s
Mic
osoft.Wi

ows.St

tM

u
xp

i

c
Host\_cw5
1h2txy
wy
Loc
lSt
t


I
 this fol


, th


 is 
 **_st

t.
i
_** o
 **_st

t2.
i
_** (

p


i
g o
 th
 Wi

ows 11 v

sio
) fil
. This fil
 is th
 Wi

ows 11 St

t M

u th
t c

 

 copi

.

Th
s
 st
ps will copy th
 mo
ifi

 St

t M

u to 
 c

t

l loc
tio
 


 wh

 th
 


poi
t st

ts th
 mo
ifi

 St

t M

u will 

 copi

 to th
 

f
ult us

 p
ofil
. Wh

 

w us

s logs i
, th
y will g
t th
 customiz

 St

t M

u.

- Pi
/u
pi
 


 o
g

iz
 th
 
pps i
 th
 St

t M

u th
 w
y you w

t.

[![](im
g
s/3_u
pi
-300x145.jpg)](im
g
s/3_u
pi
.jpg) [![](im
g
s/4_st

tm

u-300x145.jpg)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2022/12/4_st

tm

u.jpg)

- Copy th
 st

t2.
i
 fil
 i
 f
om th
 _**%Loc
l
pp

t
%
P
ck
g
s
Mic
osoft.Wi

ows.St

tM

u
xp

i

c
Host\_cw5
1h2txy
wy
Loc
lSt
t
**_ fol


 to 
 c

t

l loc
tio
 (fo
 
x
mpl
 i
 
 fol


 i
 th
 

tlogo
 sh


 of th
 
om
i
 co
t
oll

 (fo
 
x
mpl
 

l

.loc
l


tlogo

w11).
- C


t
 
 cm
 fil
 c
ll

 w11st

tm

u.cm
 with th
 followi
g co
t
xt:

copy "

l

.loc
l


tlogo

w11
st

t2.
i
" "C:
Us

s


f
ult

pp

t

Loc
l
P
ck
g
s
Mic
osoft.Wi

ows.St

tM

u
xp

i

c
Host\_cw5
1h2txy
wy
Loc
lSt
t
" /Y

- Op

 G
oup Policy M


g
m

t co
sol

- C


t
 
 GPO Comput

 Co
figu

tio
 - Sc
ipts (St

tup/Shut
ow
) - St

tup - Sc
ipts 


 

ows
 to th
 cm
 sc
ipt fil
 i
 th
 

tlogo
 sh


 (fo
 
x
mpl
 

l

.loc
l


tlogo

w11
w11st

tm

u.cm
)

[![](im
g
s/5_GPO-300x128.jpg)](im
g
s/5_GPO.jpg)


ll us

s who log i
 with 
 

w p
ofil
 will g
t th
 customiz

 Wi

ows 11 St

t M

u.

Mo

 i
fo
m
tio
 c

 

 fou

 i
 th
 followi
g 

ticl
, [li
k](https://l



.mic
osoft.com/

-us/wi

ows/co
figu

tio
/customiz
-st

t-m

u-l
yout-wi

ows-11).






