---
titl
: "VMw


 
SXi6 P
sswo

 Policy"


t
: "2015-10-07T10:08:48.000Z"
c
t
go
i
s: 
  - "
sxi"
  - "VMw


"
t
gs: 
  - "
sxi-2"
  - "VMw


"

utho
: Ivo 





s
---

- P
sswo

s must co
t
i
 ch


ct

s f
om 
t l

st th


 ch


ct

 cl
ss
s.
- P
sswo

s co
t
i
i
g ch


ct

s f
om th


 ch


ct

 cl
ss
s must 

 
t l

st s
v

 ch


ct

s lo
g.
- P
sswo

s co
t
i
i
g ch


ct

s f
om 
ll fou
 ch


ct

 cl
ss
s must 

 
t l

st s
v

 ch


ct

s lo
g.



 upp

c
s
 ch


ct

 th
t 

gi
s 
 p
sswo

 
o
s 
ot cou
t tow


 th
 
um


 of ch


ct

 cl
ss
s us

. 
 
um


 th
t 


s 
 p
sswo

 
o
s 
ot cou
t tow


 th
 
um


 of ch


ct

 cl
ss
s us

.

Fo
 L

 

vi
o
m

ts I ch

g
 f

qu

tly th
 p
sswo

 policy  i
 th
 
SXi 5 

f
ult, 

c
us
 it is possi
l
 to g




t
 p
sswo

s th
t 


 

si

 to 

m
m


. Th
 
SXi 5 

f
ult p
sswo

 policy h
s th
 followi
g 

qui

m

ts:

- P
sswo

s co
t
i
i
g ch


ct

s f
om o

 o
 two ch


ct

 cl
ss
s must 

 
t l

st 
ight ch


ct

s lo
g.
- P
sswo

s co
t
i
i
g ch


ct

s f
om th


 ch


ct

 cl
ss
s must 

 
t l

st s
v

 ch


ct

s lo
g.
- P
sswo

s co
t
i
i
g ch


ct

s f
om 
ll fou
 ch


ct

 cl
ss
s must 

 
t l

st six ch


ct

s lo
g.

Th
 

f
ult co
figu

tio
 is fo
 
SXi 5 


 
SXi 6 


:

- **
SXi 5**: 

t
y=3 mi
=8,8,8,7,6
- **
SXi 6**: 

t
y=3 mi
=
is

l

,
is

l

,
is

l

,7,7

This m


s fo
 th
 
SXi 5 p
sswo

 policy:

**

t
y**\=3 mi
=**
0**,**
1**,**
2**,**
3**,**
4**

**

t
y**\=3: 
 us

 is 
llow

 3 
tt
mpts to 

t

 
 suffici

t p
sswo

. **
0**\=8: P
sswo

s co
t
i
i
g ch


ct

s f
om o

 ch


ct

 cl
ss must 

 
t l

st 
ight ch


ct

s lo
g. Fo
 
x
mpl
: VMw




 **
1**\=8: P
sswo

s co
t
i
i
g ch


ct

s f
om two ch


ct

 cl
ss
s must 

 
t l

st 
ight ch


ct

s lo
g. Fo
 
x
mpl
: VMw


12 **
2**\=8: P
ssph

s
s must co
t
i
 wo

s th
t 


 

ch 
t l

st 
ight ch


ct

s lo
g. Fo
 
x
mpl
: VMw




 **
3**\=7: P
sswo

s co
t
i
i
g ch


ct

s f
om 
ll th


 ch


ct

 cl
ss
s must 

 
t l

st s
v

 ch


ct

s lo
g. Fo
 
x
mpl
: VMw


12 **
4**\=6: P
sswo

s co
t
i
i
g ch


ct

s f
om 
ll fou
 ch


ct

 cl
ss
s must 

 
t l

st six ch


ct

s lo
g. Fo
 
x
mpl
: VMw


1!

Th
 wo

 "
is

l

" c

 

 us

 to 
ot us
 sp
cific p
sswo

 compl
xity. Th
 p
sswo

 policy c

 

 ch

g

 i
 th
 vSph


 (W

) Cli

t 

v

c

 syst
m s
tti
gs (s

 sc



shot). 
o 

iti
g of P
M co
fig fil
s o
 th
 
SXi host is 

qui


 

ymo

.

[![vSph


 cli

t](im
g
s/vSph


-cli

t-300x180.p
g)](im
g
s/vSph


-cli

t.p
g)

To ch

g
 th
 p
sswo

 policy o
 multipl
 
SXi hosts, Pow

CLI c

 

 us

. H


's 

 
x
mpl
 to ch

g
 th
 P
sswo

 Policy to th
 
SXi 5 p
sswo

 policy 

f
ult:

\[co

 l

gu
g
="Pow

Sh
ll"\] 
 S
t th
 
SXi P
sswo

 Policy 
y usi
g Pow

CLI fo
 
v

y 
SXi host 
 

f
ult P
sswo

 Policy 
SXi 6 = 

t
y=3 mi
=
is

l

, 
is

l

, 
is

l

, 7, 7 
 

f
ult P
sswo

 Policy 
SXi 5 = 

t
y=3 mi
=8,8,8,7,6 
 L
st up

t

 
y: Ivo 





s Octo


 4, 2015 $P
sswo

Policy = "

t
y=3 mi
=8,8,8,7,6" $VMHosts = G
t-VMHost | Wh


 { $\_.Co


ctio
St
t
 -
q "Co


ct

" } fo


ch ($VMHost i
 $VMHosts) { $VMHosts | G
t-

v

c

S
tti
g -

m
 “S
cu
ity.P
sswo

Qu
lityCo
t
ol" | S
t-

v

c

S
tti
g -V
lu
 $P
sswo

Policy -Co
fi
m:$f
ls
 } \[/co

\]






