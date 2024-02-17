---
titl
: "Ch
ck fo
 
uplic
t
 M
C 




ss pools i
 you
 Hyp

-V 

vi
o
m

t"


t
: "2014-01-13T14:27:18.000Z"
c
t
go
i
s: 
  - "hyp

-v"
t
gs: 
  - "hyp

-v-2"

utho
: Ivo 





s
---

[![im
g
[16]](im
g
s/im
g
16_thum
.p
g "im
g
[16]")](im
g
s/im
g
16.p
g)

Th
 M
C 




ss pool is g




t

 
s follows:

- Th
 fi
st th


 oct
ts 


 Mic
osoft's I


 o
g

iz
tio

lly U
iqu
 I


tifi

, 00:15:5
 (which is commo
 o
 
ll Hyp

-V hosts)
- Th
 

xt two oct
ts 


 


iv

 f
om th
 l
st two oct
ts of th
 s

v

's IP 




ss
- Th
 l
st oct
t is 
utom
tic
lly g




t

 f
om th
 


g
 0x0 - 0xFF. This giv
s 256 M
C 




ss
s


s you c

 s

 th
 M
C 




ss pool c


tio
 

p


s o
 th
 IP 




ss us

 
u
i
g th
 i
st
ll
tio
 of th
 Hyp

-V 
ol
. I
 this 
x
mpl
 (sc



shot 

ov
) th
 IP 




ss w
s xxx.xxx.250.108 
u
i
g th
 Hyp

-V 
ol
 i
st
ll
tio
. This IP 




ss w
s 
ssig


 
y 
 
HCP s

v

 with 
 sho
t l

s
 tim
. 
ft

 



li
g th
 Hyp

-V 
ol
 
 st
tic IP 




ss w
s 
ssig


. This 
o
s 
ot ch

g
 

 M
C 




ss pool 

ymo

.

Wh

 i
st
lli
g th
 Hyp

-V 
ol
 o
  

oth

 s

v

, th
 s

v

 

c
iv

 th
 s
m
 IP 




ss. This 

sults i
 th
 s
m
 M
C 




ss pool o
 
oth s

v

s which m


s th
t VMs g
ts 
uplic
t
 M
C 




ss
s.

To ch
ck th
 M
C 




ss pool of 
ll th
 Hyp

-V s

v

s, I c


t
 
 Pow

Sh
ll list

 

low. Ch

g
 th
 Comput



m
 


 –C




ti
ls p


m
t

s.

Sc
ipt:

$S
ssio
 = 

w-PSS
ssio
 -Comput



m
 's

v

1, 's

v

2' –C




ti
l 
om
i


ccou
t

m
 
i
vok
-comm


 –S
ssio
 $s
ssio
 -sc
ipt
lock {G
t-VMHost | s
l
ct Comput



m
, M
c




ssMi
imum, M
c




ssM
ximum} | ft

[![im
g
](im
g
s/im
g
_thum
.p
g "im
g
")](im
g
s/im
g
.p
g)

Ch

g
 th
 M
C 




ss pool us
 th
 followi
g comm


:

S
t-VMHost –M
c




ssMi
imum –M
c




ssM
ximum 


x
mpl
:

S
t-VMHost -M
c




ssMi
imum 00155
020600 -M
c




ssM
ximum 00155
0206FF






