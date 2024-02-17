---
titl
: "Wh
t to k
ow 

out VMw


 Clou
 o
 
WS"


t
: "2017-10-02T09:55:17.000Z"
t
gs: 
  - "
ws"
  - "clou
"
  - "VMw


"

utho
: Ivo 





s
---

- VMw


 Clou
 o
 
WS is 
 clou
 s

vic
 th
t is fully co
figu


 


 will 

 p
ovisio


, op


t

 


 m
i
t
i


 
i

ctly 
y VMw


. VMw


 h


l
s 
ll p
tchi
g 


 up

t
s. 
s custom

 you m


g
 th
 VMs, 
ot th
 pl
tfo
m.

[![](im
g
s/1-300x161.jpg)](im
g
s/1.jpg)

- Th
 followi
g VMw


 p
o
ucts 


 i
clu


 i
 VMw


 Clou
 o
 
WS off

i
g (comput
, sto

g
 


 

two
ki
g):
    - vSph


 
SXi o
 


ic
t

 



-m
t
l h


w


 with suppo
t fo
 VMs 


 co
t
i


s
    - vC

t

 S

v

 fo
 m


g
m

t
    - vS

 
ll Fl
sh sto

g

    - 
SX fo
 sp


i
g o
-p

mis
s 


 Clou
, 

v

c

 

two
ki
g 


 s
cu
ity
    - v


liz
 p
o
ucts 


 
OT i
clu


 i
 this off

i
g 
ut c

 i
t
g

t


- I
 o



 fo
 th
 o
-
o


i
g p
oc
ss to compl
t
 succ
ssfully th


 is 
 st
ict 

qui

m

t th
t 
v

y o
g

iz
tio
 

 li
k

 to 

 
WS 
ccou
t. 

y s

vic
s co
sum

 withi
 
WS will 

 
ill

 th
ough this 
m
zo
 
ccou
t, whil
 S

C co
sumptio
 will 

 
ill

 th
ough VMw


.
- Th
 mi
im
l pu
ch
s
 is clust

 of 4 
SXi hosts. Th
 m
ximum clust

 siz
 is 16 hosts.
- It's 
 


ic
t

 pl
tfo
m th
t is 
ot sh



 with oth

 custom

s.
- You c

 


 


itio

l o
-

m


 hosts 


 
lso 

mov
 hosts o
-

m


 
ow
 to 4 
SXi hosts.
- 

ch 
SXi host is h
s:
    - 2 pCPU sock
ts, 18 co

s p

 sock
t = 36 co

s tot
l  


 72 with hyp

-t



i
g
    - 512 G
 

M
    - 14 T
 
VM
 

W c
p
city sto

g
 (

ou

 10 T
  of us

l
 sto

g
 p

 host). I
 
 4 
o

 clust

 21 T
 of us

l
 sto

g
 is 
v
il

l
 with FTT=1 (

I
=1) p
ot
ctio

    - Th
 vS

 

t
sto

 is co
figu


 
s 
 si
gl
 

t
sto


    - 10 G
ps+ (


)
- To 
xt


 sto

g
 you 



 to 


 
xt

 
SXi hosts
- Th
 followi
g VMw


 f

tu

s 


 



l

:
    - vSph


 H
,
    - vMotio
,
    - 

S
    - 
l
stic 

S
- Clust

 fu
ctio
s 


 co
figu


 
y VMw




[![](im
g
s/3-300x140.jpg)](im
g
s/3.jpg)

- It's possi
l
 to co


ct th
 o
-p

mis
s VMw


 

t
c

t

 with VMw


 Clou
 o
 
WS 
y usi
g fo
 
x
mpl
  
 L3 IPs
c VP
 


 



l
 Hy

i
 Li
k Mo

 (HLM) 

tw


 th
 two vC

t

 s

v

s fo
 si
gl
 p


 of gl
ss hy

i
 clou
 m


g
m

t.
- I
 th
 futu

 
 
m
zo
 
i

ct co


ct is suppo
t

 (1 G
ps o
 mo

)
- Th


 
o 



 fo
 
SX 


 vS

 i
 th
 o
-p

mis
s 

t
c

t

.
- Som
 us
 c
s
s 


:
    - 
is
st

 

cov

y (

) 


 

ckup.
    - T
st 


 

v
lopm

t
    - 
xt


 th
 o
-p

mis
s 

t
 c

t

s to th
 clou
 with 
 co
sist

t op


tio

l mo

l, 

t
i
i
g you
 f
mili

 VMw


 tools, polici
s 


 m


g
m

t.
    - 

w 
pplic
tio
 

v
lopm

t 


 t
st th
t 
cc
ss 

tiv
 
WS s

vic
s
    - 
u
st c
p
city
- O
 th
 mom

t th
 


 two co
sumptio
 mo

ls 
v
il

l
:
    - O
-

m


/hou
ly co
sumptio
 mo

l
    - 1 o
 3 y


s 

s

v

 mo

l.
    - Mo

 o
 p
ici
g c

 

 fou

 h


, [li
k](https://clou
.VMw


.com/vmc-
ws/p
ici
g)
- Th
 i
iti
l 

l

s
 h
s suppo
t fo
 col
 mig

tio
. C
oss clou
 vMotio
 will 

 
v
il

l
 i
 
 futu

 

l

s

- VMw


 Clou
 o
 
WS is 

s

 o
 op

 
PI's.
- Cu



tly VMw


 Clou
 o
 
WS is o
ly 
v
il

l
 i
 
WS US W
st (O

go
) 

gio
. Oth

 

gio
s will follow i
 2018.
- You c

 

i
g you
 ow
 lic

s
s 

c
us
 it's 
 


ic
t

 pl
tfo
m.

Mo

 i
fo
m
tio
:

- VMw


 Clou
 o
 
WS w

sit
, [li
k](https://clou
.VMw


.com/vmc-
ws)
- VMw


 Clou
 o
 
WS: Liv
 


 to 


 

mo, [li
k](https://www.youtu

.com/w
tch?v=JI_
UvgfX
g&f

tu

=youtu.

)
- VMw


 o
 
WS f
om 
 V


m p

sp
ctiv
, [li
k](https://vzill
.co.uk/vzill
-
log/VMw


-
ws-will-look-v


m-p

sp
ctiv
)
- VMw


 Clou
 o
 
WS p
ici
g v

sus o
-p

mis
s vSph


, [li
k](http://s


chs

v

vi
tu
liz
tio
.t
cht

g
t.com/tip/VMw


-Clou
-o
-
WS-p
ici
g-v

sus-o
-p

mis
s-vSph


)






