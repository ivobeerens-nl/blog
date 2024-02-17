---
titl
: "U


l
 to co


ct f
om th
 vSph


 Cli

t o
 Pow

CLI o
 Wi

ows XP o
 Wi

ows 2003 to 
 vC

t

 S

v

 5.5"


t
: "2013-11-15T07:54:34.000Z"
c
t
go
i
s: 
  - "vc

t

-2"
  - "vcs
"
  - "vSph


"
t
gs: 
  - "cli

t"
  - "vc

t

"
  - "vcs
"
  - "vSph


"

utho
: Ivo 





s
---

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

Pow

CLI 


o
:

[![im
g
](im
g
s/im
g
_thum
2.p
g "im
g
")](im
g
s/im
g
2.p
g)

I
 th
 

l

s
 
ot
s of vSph


 5.5 this is 
 k
ow
 issu
:

> vSph


 5.5 us
s th
 Op

 SSL li



y, which, fo
 s
cu
ity, is co
figu


 
y 

f
ult to 
cc
pt o
ly co


ctio
s th
t us
 st
o
g ciph

 suit
s. O
 Wi

ows XP o
 Wi

ows S

v

 2003, th
 vSph


 Cli

t 


 vSph


 Pow

CLI 
o 
ot us
 st
o
g ciph

 suit
s to co


ct with vC

t

 S

v

. Th
 


o
 
o m
tchi
g ciph

 suit
 is show
 o
 th
 s

v

 si

, 


 th
 h


sh
k
 f
ils o
 th
 vSph


 Cli

t o
 vSph


 Pow

CLI si

.

Th


 


 th


 wo
k

ou

s fo
 this:

- Usi
g Wi

ows hotfix
s o
 th
 Wi

ows XP / 2003 OS
- 

justi
g th
 vC

t

 S

v

 co
figu

tio

- 

justi
g th
 vC

t

 S

v

 
ppli

c
 (VCS
) co
figu

tio


I
 th
 followi
g st
ps I will  

just th
 vC

t

 S

v

 
ppli

c
 co
figu

tio
:

- Op

 
 SSH co


ctio
 to th
 VCS

- logi
 th
 
ppli

c
 (
y 

f
ult this is 
oot 


 with th
 p
ssswo

 VMw


)
- 

vig
t
 to th
 /
tc/VMw


-vpx 
i

cto
y
- 

it th
 vpx
.cfg fil
 with fo
 
x
mpl
 th
 VI 

ito
 (i = i
s

t)
- 


 th
 followi
g <ciph

List>
LL</ciph

List> 

tw


 th
 <ssl> s
ctio
 (s

 sc



shot 

low):

> <ssl>  
> ...  
> ...  
> </ssl>

[![im
g
](im
g
s/im
g
_thum
3.p
g "im
g
")](im
g
s/im
g
3.p
g)

- S
v
 th
 ch

g
s 


 quit th
 VI 

ito
  (wq!)
- 

st

t th
 vC

t

 S

v

 s

vic
 
y usi
g th
 followi
g comm


: “s

vic
 VMw


-vpx
 

st

t”  
    


ft

 th
 mo
ific
tio
 I w
s 

l
 to us
 th
 vSph


 Cli

t 


 Pow

CLI to co


ct to th
 vC

t

 S

v

 
ppli

c
.

[![im
g
](im
g
s/im
g
_thum
4.p
g "im
g
")](im
g
s/im
g
4.p
g)

Fo
 mo

 i
fo
m
tio
 s

 K
 

ticl
 2049143 fou

 h


, [li
k](http://k
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
=2049143)






