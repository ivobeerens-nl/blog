---
titl
: "Post ch
cks 
ft

 upg


i
g to VMw


 vSph


 4.1"


t
: "2010-12-17T12:09:09.000Z"
c
t
go
i
s: 
  - "upg



"
  - "vSph


"
t
gs: 
  - "upg



"
  - "vpsh


"

utho
: Ivo 





s
---

Wh

 


i
g 
xisti
g VMw


 
SX s

v

s (fo
 
x
mpl
 3.5) to th
 VMw


 vC

t

 4.1 s

v

, 
ll th
 VMs got 
 m
mo
y limit.

[![2010-12-10 12h39_01](im
g
s/2010-12-10-12h39_01_thum
.jpg "2010-12-10 12h39_01")](im
g
s/2010-12-10-12h39_01.jpg)

To 

s
t th
 m
mo
y limits to u
limit

 fo
 
ll VMs, us
 th
 followi
g Pow

CLI sc
ipt:

Co


ct-VIS

v

 s

v



m
 G
t-VM | G
t-VM

sou
c
Co
figu

tio
 | Wh


-O
j
ct {$\_.M
mLimitM
 -

 ‘-1‘} | S
t-VM

sou
c
Co
figu

tio
 -M
mLimitM
 $
ull 




 VMw


 
SX 
ICs 
s fix




l



y m

tio


 


li

 i
 th
 “[Ch

g
 
IC sp


 


 
upl
x s
tti
g to 
UTO i
 
SX4 usi
g Pow

CLI”](https://www.ivo





s.
l/?p=537) 
logpost. Th
 VMw


 
SX i
st
ll
tio
 s
t 
y 

f
ult 

ch 
IC i
 th
 VMw


 hosts to fix

. To ch

g
 
v

y 
IC f
om fix

 to 
uto 

goti
t
  us
 th
 followi
g Pow

CLI sc
ipt

Co


ct-VIS

v

 s

v



m
 G
t-VMHost

two
k


pt

 | S
t-VMHost

two
k


pt

 –
uto

goti
t





 
ctiv
 
i

cto
y W

 S

vic
s w


i
gs i
 th
 vC

t

 s

v

 
v

t log

Th
 followi
g w


i
g is floo
i
g th
 vC

t

 
v

t log:

> 
ctiv
 
i

cto
y W

 S

vic
s 

cou
t



 

 


o
 whil
 



i
g th
 s
tti
gs fo
 th
 sp
cifi

 
ctiv
 
i

cto
y Lightw
ight 
i

cto
y S

vic
s i
st

c
.  
ctiv
 
i

cto
y W

 S

vic
s will 

t
y this op


tio
 p

io
ic
lly.  I
 th
 m


 tim
, this i
st

c
 will 

 ig
o


.
> 
> I
st

c
 

m
: 


M\_VMw


VCMS
S
> 
> 
v

tI
: 1209

Th
 Po
t SSL v
lu
 is c


t

 
s 
 

G\_SZ i
st


 of 
 

G\_
WO

. To solv
 this w


i
g op

 th
 Wi

ows 

gist
y 

ito
 (

g

t32) 


 

ows
 to:

- HKLM
Syst
m
Cu



tCo
t
olS
t
S

vic
s
VMw


VCMS
S
P


m
t



- 

l
t
 th
 “Po
t SSL” v
lu


- C


t
 
 

w ““Po
t SSL” v
lu
  
s 

G\_
WO

 


 giv
 it th
 

t
 636.

- 

st

t th
 

M i
st

c







