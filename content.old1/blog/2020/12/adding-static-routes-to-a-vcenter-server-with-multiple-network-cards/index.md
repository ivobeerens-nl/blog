---
titl
: "


i
g 
 st
tic 
out
 to 
 vC

t

 S

v

 with multipl
 

two
k I
t

f
c
 C


s (
ICs)"


t
: "2020-12-15T13:22:57.000Z"
c
t
go
i
s: 
  - "vc

t

-s

v

"
t
gs: 
  - "vc

t

-s

v

"
  - "VMw


"
cov

Im
g
: "ov

vi
w.p
g"

utho
: Ivo 





s
---

[![](im
g
s/ov

vi
w-300x207.p
g)](im
g
s/ov

vi
w.p
g)

Th


 must 

 
 st
tic 
out
 to th
 Ho
izo
 su


t 

c
us
 th
 Ho
izo
 Co


ctio
 S

v

s 


 VMw


 
pp Volum
s i
t
g

t
 with th
 vC

t

 S

v

.

H


 


 th
 st
ps outli


 to c


t
 such 

 

vi
o
m

t:

- Th
 fi
st thi
g 
ft

 

ployi
g 
 

w vC

t

 S

v

 is 


i
g 

 
xt

 
IC (**VMX

T3**). Th
 st
ps 


 
xpl
i


 i
 th
 followi
g 

ticl
: [K
2147155](https://k
.VMw


.com/s/

ticl
/2147155)
- 


 th
 
IC to th
 co


ct i
t



l Po
tG
oup
- Op

 th
 V
MI i
t

f
c
 (**https://<IP\_




ss>:5480**) of th
 vC

t

 S

v

 


 


 th
 IP co
figu

tio
 of 
th1 (
IC1).

[![](im
g
s/1-300x163.p
g)](im
g
s/1.p
g)

- 



l
 SSH i
 th
 V
MI i
t

f
c
 (**
cc
ss - 

it - 



l
 SSH logi
**)
- M
k
 

 SSH s
ssio
 to vC

t

 S

v

 


 log i
 with 
oot 


 th
 co


ct p
sswo


- 

t

 "sh
ll" to l
u
ch th
 

SH sh
ll
- 

ows
 to th
 followi
g loc
tio
:

```
c
 /
tc/syst
m
/

two
k
```

- Th


 


 two fil
s 
v
il

l
 (**10-
th0.

two
k** 


 **10-
th1.

two
k**). Th
 **10-
th0.

two
k** 

p

s

ts 
th0 


 looks lik
:

> ```
> [M
tch]
> 

m
=
th0
> 
> [

two
k]
> G
t
w
y=10.2.145.249
> 




ss=10.2.145.202/24
> 
HCP=
o
> 
> [
HCP]
> Us


S=f
ls

> ```

- Th
 **10-
th1.

two
k** fil
 

p

s

ts 
th1 


 looks lik
 this.

> ```
> [M
tch]
> 

m
=
th1
> [

two
k]
> 




ss=192.168.0.102/24
> 
HCP=
o
> [
HCP]
> Us


S=f
ls

> ```

- 


 
 st
tic 
out
 
y 


i
g th
 \[
out
\] s
ctio
 of this fil
.

> ```
> [M
tch]
> 

m
=
th1
> [

two
k]
> 




ss=192.168.0.102/24
> 
HCP=
o
> [
HCP]
> Us


S=f
ls

> 
> [
out
]
> G
t
w
y=192.168.0.1
> 

sti

tio
=10.21.9.0/24
> ```

- 

st

t th
 

two
k s

vic
s

```
syst
mctl 

st

t syst
m
-

two
k
.s

vic

```

- Ch
ck if th
 
out
 is 




 with th
 **
out
 -
** comm


:

> ```
> 
oot@vc

01 [ /
tc/syst
m
/

two
k ]
 
out
 -

> K



l IP 
outi
g t

l

> 

sti

tio
 G
t
w
y G

m
sk Fl
gs M
t
ic 

f Us
 If
c

> 0.0.0.0 10.2.145.249 0.0.0.0 UG 0 0 0 
th0
> 10.2.145.0 0.0.0.0 255.255.255.0 U 0 0 0 
th0
> 10.21.9.0 192.168.0.1 255.255.255.0 UG 0 0 0 
th1
> 192.168.0.0 0.0.0.0 255.255.255.0 U 0 0 0 
th1
> ```

- T
st with th
 pi
g comm


 f
om th
 vC

t

 S

v

 if you c

 


ch th
 Ho
izo
 i
f

 compo


ts i
 th
 su


t.






