---
titl
: "Tips fo
 I
st
lli
g Up

t
 
ollup 4 fo
 Syst
m C

t

 2012 
2 Vi
tu
l M
chi

 M


g

"


t
: "2014-10-30T08:58:22.000Z"

utho
: Ivo 





s
---

- 


 H
t 

t

p
is
 Li
ux 7 (64 
it)
- O

cl
 Li
ux 7 (64 
it)
- C

tOS Li
ux 7 (64 
it)

H


 


 som
 tips fo
 i
st
lli
g Up

t
 
ollup (U
) 4 fo
 Syst
m C

t

 2012 
2 Vi
tu
l M
chi

 M


g

:

- I
st
ll th
 VMM S

v

 


 

mi
ist

to
 Co
sol
 p
ck
g
 
y usi
g Mic
osoft Up

t
, WSUS o
 m

u
l 
ow
lo



[![u
4](im
g
s/u
4-1024x283.p
g)](im
g
s/u
4.p
g)

- 
ft

 th
 up

t
 of U
4 th
 SCVMM host must 

 


oot


- 

fo

 Up

t
 
ollup 4, you h

 to 
u
 

 SQL sc
ipt 
ft

 you i
st
ll

 

 up

t
 p
ck
g
 to m
k
 su

 Up

t
 
ollups fu
ctio
 co


ctly. 
s of Up

t
 
ollup 4, this st
p is 
O lo
g

 

qui



- Up

t
 th
 VMM 
g

ts of 
ll th
 SCVMM compo


ts such 
s Hyp

-V hosts, VMM S

v

, Li



y 


 WSUS s

v

. Th
 SCVMM U
4 
g

t v

sio
 is: **3.2.7768.0**
- Th
 Syst
m C

t

 Vi
tu
l M
chi

 M


g

 
HCP S

v

 (x64) compo


t must 

 m

u
lly up

t

 o
 
ll VMM Hyp

-V hosts. To up

t
 th
 
g

t, fi
st u
i
st
ll th
 ol
 v

sio
 
y 
u

i
g th
 followi
g comm


 f
om 

 
l
v
t

 Pow

Sh
ll Comm


 P
ompt:

\[co

 l

gu
g
="Pow

Sh
ll"\] (G
t-WmiO
j
ct -Cl
ss Wi
32\_P
o
uct -Filt

 '

m
 = "Mic
osoft Syst
m C

t

 Vi
tu
l M
chi

 M


g

 
HCP S

v

 (x64)"' -Comput



m
 . ).U
i
st
ll() \[/co

\]

- Copy th
 
HCP
xt
.msi f
om SCVMM s

v

 (

f
ult i
st
ll

 i
 C:
P
og

m Fil
s
Mic
osoft Syst
m C

t

 2012 
2
Vi
tu
l M
chi

 M


g


Sw
xt
) to th
 Hyp

-V host 


 
x
cut
 th
 MSI. 
o 

st

t of th
 Hyp

-V host i
 






- Ch
ck if th
 v

sio
 of th
 
HCP S

v

 compo


t. Th
 v

sio
 must m
tch 3.2.7768.0. Us
 th
 followi
g Pow

Sh
ll comm


:

\[co

 l

gu
g
="Pow

Sh
ll"\] G
t-WmiO
j
ct -Cl
ss wi
32\_p
o
uct -Filt

 '

m
 = "Mic
osoft Syst
m C

t

 Vi
tu
l M
chi

 M


g

 
HCP S

v

 (x64)"' \[/co

\]

[![
hcpcli

t](im
g
s/
hcpcli

t.p
g)](im
g
s/
hcpcli

t.p
g)

- Up

t
 th
 U
4 Syst
m C

t

 Vi
tu
l M
chi

 M


g

 Co
sol
 o
 
ll s

v

s fo
 
x
mpl
 th
 SCVMM 

mi
 wo
kst
tio
s 


 Cit
ix 

liv

y Co
t
oll

s

Mo

 i
fo
m
tio
 c

 

 fou

 [h


](http://suppo
t2.mic
osoft.com/k
/2992024).






