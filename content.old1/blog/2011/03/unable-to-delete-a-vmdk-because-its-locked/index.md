---
titl
: "U


l
 to 

l
t
 
 VM
K 

c
us
 it&
squo;s lock

"


t
: "2011-03-30T10:16:11.000Z"
c
t
go
i
s: 
  - "VMw


"
  - "vSph


"
t
gs: 
  - "VMw


"
  - "vpsh


"

utho
: Ivo 





s
---

I fou

 th
 VMw


 K
 

ticl
  “[Vi
tu
l m
chi

 
o
s 
ot pow

 o
 

c
us
 of lock

 fil
s”](http://k
.VMw


.com/s
lfs

vic
/mic
osit
s/s


ch.
o?l

gu
g
=

_US&cm
=
ispl
yKC&
xt



lI
=10051)

This K
 

ticl
 

sc
i

s how to fi

 th
 VMw


 
SX host th
t hol
s th
 lock.

To i


tify th
 VMw


 
SX s

v

 th
t hol
s th
 lock, us

 th
 followi
g comm


:

> vmkfstools -
 /vmfs/volum
s/<LU
/<

m
 s

v

.VM
K>

This comm


 

po
ts i
 th
 vmk



l.log th
 M
C 




ss of th
 
SX s

v

 th
t hol
s th
 lock. Look i
 th
 vmk



l.log 
y usi
g th
 followi
g comm


:

> t
il /v

/log/vmk



l log

Th
 vmk



l.log output:

> M

 29 15:43:07 s

v

 vmk



l: 7:03:34:25.713 cpu9:4223)FS3: 142: <ST

T                                                                                                                                                              s

v

-fl
t.vm
k>  
> M

 29 15:43:07 s

v

 vmk



l: 7:03:34:25.713 cpu9:4223)Lock \[typ
 10c00                                                                                                                                                             001 offs
t 31932416 v 142, h
 offs
t 3272704  
> M

 29 15:43:07 s

v

 vmk



l: g

 99305, mo

 1, ow


 4
39
32
-
f56720                                                                                                                                                            9-7754-**0025
3
1
4c8** mtim
 3227617\]

Th
 
ol
 t
xt is th
 M
C 




ss of th
 VMw


 
SX s

v

 th
t hol
s th
 lock. 
ow w
 



 to fi

 th
 VMw


 
SX s

v

 th
t m
tch
s th
 M
C 




ss. Th
 followi
g Pow

CLI sc
ipt 
ispl
ys 
ll M
C 




ss of 
ll VMw


 
SX s

v

s 


 
ispl
ys this i
 
 g
i
vi
w.

<t

l
 styl
="
o



-coll
ps
: s
p


t
" 
o



="0" c
llsp
ci
g="0" c
llp


i
g="5"><t
o
y><t
><t
 styl
="
o



-
ottom-styl
: 
o

; p


i
g-
ottom: 5px; 
o



-l
ft-styl
: 
o

; p


i
g-l
ft: 5px; p


i
g-
ight: 5px; 
o



-top-styl
: 
o

; 
o



-
ight-styl
: 
o

; p


i
g-top: 5px" v
lig
="top"><
iv styl
="p


i
g-
ottom: 5px; p


i
g-l
ft: 5px; p


i
g-
ight: 5px; fo
t-f
mily: ; 

ckg
ou

: 
c
c
c
; fo
t-siz
: ; p


i
g-top: 5px"><fo
t colo
="
000000"><fo
t f
c
="Co
sol
s"><fo
t styl
="fo
t-siz
: 10pt">001</fo
t></fo
t><

></fo
t></
iv></t
><t
 styl
="
o



-
ottom-styl
: 
o

; p


i
g-
ottom: 5px; 
o



-l
ft-styl
: 
o

; p


i
g-l
ft: 5px; p


i
g-
ight: 5px; 
o



-top-styl
: 
o

; 
o



-
ight-styl
: 
o

; p


i
g-top: 5px" v
lig
="top" 
ow

p="
ow

p"><
iv styl
="p


i
g-
ottom: 5px; p


i
g-l
ft: 5px; p


i
g-
ight: 5px; fo
t-f
mily: ; 

ckg
ou

: 
fcfcfc; fo
t-siz
: ; p


i
g-top: 5px"><fo
t f
c
="Co
sol
s"><sp

 styl
="colo
: "><fo
t styl
="fo
t-siz
: 10pt" colo
="
000000">Co


ct-vis

v

 vC

t

s

v

</fo
t></sp

></fo
t></
iv><
iv styl
="p


i
g-
ottom: 5px; p


i
g-l
ft: 5px; p


i
g-
ight: 5px; fo
t-f
mily: ; 

ckg
ou

: 
fcfcfc; fo
t-siz
: ; p


i
g-top: 5px"><fo
t f
c
="Co
sol
s"><fo
t colo
="
000000"><sp

 styl
="colo
: "><fo
t styl
="fo
t-siz
: 10pt">G
t-vmhost

two
k


pt

</fo
t></sp

><fo
t styl
="fo
t-siz
: 10pt"><sp

 styl
="colo
: ">&

sp;</sp

><sp

 styl
="colo
: ">|</sp

><sp

 styl
="colo
: ">&

sp;</sp

><sp

 styl
="colo
: ">S
l
ct</sp

><sp

 styl
="colo
: ">&

sp;</sp

><sp

 styl
="colo
: ">vmhost</sp

><sp

 styl
="colo
: ">,</sp

><sp

 styl
="colo
: ">m
c</sp

><sp

 styl
="colo
: ">&

sp;</sp

><sp

 styl
="colo
: ">|</sp

><sp

 styl
="colo
: ">&

sp;</sp

><sp

 styl
="colo
: ">Out-G
i
Vi
w</sp

></fo
t></fo
t></fo
t></
iv></t
></t
></t
o
y></t

l
>

With 
 g
i
vi
w it is possi
l
 to filt

 

sily. 


 th
 l
st p

t of th
 M
C 




ss (i
clu
i
g th
 : ) 


 th
 co


spo

i
g VMw


 
SX s

v

 is 
ispl
y

:

[![2011-03-29 16h20_42](im
g
s/2011-03-29-16h20_42_thum
.jpg "2011-03-29 16h20_42")](im
g
s/2011-03-29-16h20_42.jpg)

O
 th
 VMw


 s

v

 th
t hol
s th
 lock 

st

t th
 M


g
m

t 
g

ts 
y usi
g th
 followi
g comm


:

> s

vic
 mgmt-VMw


 

st

t

Th
 lock 
is
pp




 


 I w
s 

l
 to 

mov
 th
 VM
K fil
.






