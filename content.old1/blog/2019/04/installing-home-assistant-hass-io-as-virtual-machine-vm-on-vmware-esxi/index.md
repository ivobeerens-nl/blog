---
titl
: "I
st
ll Hom
 
ssist

t H
ss.io 
s Vi
tu
l M
chi

 (VM) o
 VMw


 
SXi"


t
: "2019-04-03T11:10:17.000Z"
c
t
go
i
s: 
  - "
sxi"
  - "h
ss-io"
  - "hom
-
ssist

t"
t
gs: 
  - "
sxi-2"
  - "hom
-
ssist

t"

utho
: Ivo 





s
---

**Up

t
: Ju

 2021:** U
u
tu is 
ot suppo
t

 

ymo

 
s Op


ti
g Syst
m fo
 Hom
 
ssist

t. S

 my 
log post 

out i
st
lli
g th
 


i

 fo
 Hom
 
ssist

t fo
 mo

 i
fo
m
tio
.

https://www.ivo





s.
l/2021/06/21/
u
-hom
-
ssist

t-sup

vis

-
s-vi
tu
l-m
chi

-vm-o
-VMw


-
sxi/

 

Oth

 

v

t
g
s of 
u

i
g H
ss.io 
s VM o
 VMw


 
SXi 


 fo
 
x
mpl
:

- Th
 

sp



y PI h
s limit

 h


w


 

sou
c
s 


 c

 

 
 p

fo
m

c
 
ottl


ck wh

 usi
g mo

 


 mo

 s

so
s 


 i
st
lli
g H
ss.io 


-o
s. 
 hom
 l

 s

v

 off

s mo

 CPU pow

, m
mo
y 


 sto

g
 p

fo
m

c
.
- S

pshot fu
ctio

lity. Quickly m
k
 
 Vi
tu
l M
chi

 s

pshot 

fo

 upg


i
g th
 


-o
s o
 H
ss.io its
lf. Wh

 som
thi
g w

t w
o
g 
u
i
g th
 upg



, simply 

v

t th
 s

pshot 


 
v

ythi
g wo
ks 
g
i
 withi
 s
co

s.
- Th
 i
st
ll
tio
 of H
ss.io i
 
 U
u
tu VM o
 
SXi is simpl
.
- US
 sticks lik
 Z-W
v
 o
 Zig


2MQTT c

 

 
tt
ch

 to th
 H
ss.io VM usi
g 
SXi US
 p
ss-th
ough.

H


 


 th
 st
ps outli


 how-to i
st
ll 

 U
u
tu VM 


 i
st
ll H
ss.io.



 Co
figu

 th
 Vi
tu
l M
chi

 h


w


 sp
cific
tio
s

- 
ow
lo

 U
u
tu 18.04.2 LTS (Lo
g-T

m Suppo
t), [li
k.](https://www.u
u
tu.com/
ow
lo

/s

v

)
- M
k
 
 co


ctio
 to th
 
SXi host: https://<ip-




ss>/ui
- Uplo

 th
 U
u
tu ISO to 
 

t
sto


- C


t
 
 

w vi
tu
l m
chi

 with th
 followi
g sp
cific
tio
s:
    - **

m
:** H
-01
    - **Comp
ti
ility:** 
SXi 6.7 vi
tu
l m
chi


    - **Gu
st OS f
mily:** Li
ux
    - **Gu
st OS v

sio
:** U
u
tu Li
ux (64-
it)
    - **Sto

g
:** 

t
sto

 with 30 G
 f


 sp
c

    - **CPUs**: 2
    - **M
mo
y:** 2048 M

    - **H


 
isk 1:** 30 G

        - **
isk P
ovisio
i
g:** Thi
 p
ovisio



    - **SCSI Co
t
oll

 0:** VMw


 P


vi
tu
l
    - **US
 co
t
oll

 1:** US
 2.0 o
 3.0 

p


i
g o
 th
 
SXi h


w



    - **

two
k 


pt

 1:** S
l
ct th
 po
tg
oup
        - **


pt

 typ
:** VMX

T 3
    - **C
/
V
 

iv
 1:** 

t
sto

 ISO fil

        - 

ows
 to th
 U
u
tu ISO
        - **Co


ct:** ch
ck


    - **Vi

o C


:** 

f
ult s
tti
gs

[![](im
g
s/1-300x201.p
g)](im
g
s/1.p
g) [![](im
g
s/2-300x202.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2019/04/2.p
g)

- 

xt
- Fi
ish
- Pow

 o
 th
 VM
- Op

 
 co
sol
 s
ssio


Th
 VM h
s 
 p


vi
tu
liz

 SCSI co
t
oll

 (PVSCSI) 


 Vi
tu
l 
IC (VMX

T3)



 I
st
ll U
u
tu o
 
SXi

- **L

gu
g
:** 

glish
- **S
l
ct:** I
st
ll U
u
tu S

v


- **Choos
 you
 p

f




 l

gu
g
:** 

glish
- **K
y
o


 co
figu

tio
:** S
l
ct th
 l
yout 


 v

i

t: 

glish US (
- **I
st
ll
tio
**: I
st
ll U
u
tu
- **

two
ki
g co


ctio
s**: Th
 VMX

T3 
IC of th
 VM is 
ispl
y

. S
l
ct fo
 th
 IPv4 m
tho
 
HCP o
 
 m

u
l fix

 IP 




ss
- **Co
figu

 p
oxy**: l

v
 this 
l

k
- **U
u
tu mi

o
**: Us
 th
 mi

o
 




ss sugg
st


- **Fil
syst
m s
tup**: Us
 

 

ti

 
isk
    - Choos
 th
 
isk to i
st
ll to: /

v/s

 30.00G
    - Fil
syst
m summ

y: 
o


    - Co
fi
m 

st
uctiv
 
ctio
. 


 you su

 you w

t to co
ti
u
: Co
ti
u


[![](im
g
s/fil
syst
m-summ

y-300x226.p
g)](im
g
s/fil
syst
m-summ

y.p
g)

- **P
ofil
 s
tup**: Fill i
 th
 followi
g fi
l
s (

m
m


 th
 us



m
 


 p
sswo

)
    - You
 

m
:
    - You
 s

v

's 

m
:
    - Pick 
 us



m
:
    - Choos
 
 p
sswo

:
    - Co
fi
m 
 p
sswo

:
- **SSH S
tup**: I
st
ll Op

SSH s

v


    - Impo
t SSH i


tity: 
o
- **F

tu


 S

v

 S

ps**: S
l
ct 
o


- Th
 i
st
ll
tio
 of U
u
tu 

gi
s
- Th
 i
st
ll
tio
 is compl
t
! 


oot th
 syst
m

[![](im
g
s/compl
t

-300x234.p
g)](im
g
s/compl
t

.p
g)

- 

mov
 th
 
tt
ch

 U
u
tu ISO f
om th
 VM 


 p

ss **

t

**
- 
ft

 th
 


oot it's tim
 to i
st
ll H
ss.io i
 th
 VM

Th
 Op

 VM Tools is 
l



y i
st
ll

  
y 

f
ult so th


 
o 



 to i
st
ll this p
ck
g
.



 I
st
ll H
ss.io

- 

c
us
 w
 i
st
ll

 Op

SSH w
 


 usi
g 
 SSH s
ssio
 fo
 th
 H
ss.io co
figu

tio
.
- Co


ct to th
 IP 




ss of thj
 U
u
tu VM usi
g SSH (i'm usi
g putty) fo
 th
 co


ctio
.
- P
ck
g
s 

qui

m

ts ([li
k](https://www.hom
-
ssist

t.io/h
ssio/i
st
ll
tio
/)) fo
 H
ss.io:
    - 
pp

mo
-utils
    - 
pt-t


spo
t-https
    - 
v
hi-


mo

    - c
-c

tific
t
s
    - cu
l
    - 

us
    - jq
    - 

two
k-m


g


    - soc
t
    - softw


-p
op

ti
s-commo
 (
l



y i
st
ll

 i
 U
u
tu 18.04)
    - 
s 
ock

 p
ck
g
 
ock

-C
 must 

 i
st
ll

.
-  Us
 th
 followi
g comm


s to i
st
ll 
ll th
 

qui


 p
ck
g
s 


 i
st
ll H
ss.io

```
su
o -i



-
pt-

posito
y u
iv

s


pt-g
t up

t


pt-g
t i
st
ll -y 
pp

mo
-utils 
pt-t


spo
t-https 
v
hi-


mo
 c
-c

tific
t
s cu
l 

us jq 

two
k-m


g

 soc
t
cu
l -fsSL g
t.
ock

.com | sh
cu
l -sL https://

w.githu
us

co
t

t.com/hom
-
ssist

t/h
ssio-i
st
ll

/m
st

/h
ssio_i
st
ll.sh | 

sh -s
```

- 
ft

 th
 i
st
ll
tio
 ch
ck if th


 


 two co
t
i


s 
u

i
g usi
g th
 followi
g comm


:

```

oot@h
-01:~
 
ock

 ps
CO
T
I


 I
 IM
G
 COMM


 C


T

 ST
TUS PO
TS 

M
S
8

f326c0c
7 hom

ssist

t/q
mux86-64-hom

ssist

t "/
i
/

t
y.sh pytho…" 

out 
 mi
ut
 
go Up 

out 
 mi
ut
 hom

ssist

t
47945
4f
0f4 hom

ssist

t/
m
64-h
ssio-sup

viso
 "pytho
3 -m h
ssio" 2 mi
ut
s 
go Up 2 mi
ut
s h
ssio_sup

viso


oot@h
-01:~

```

- Co


ct to H
ss.io: http://<IP 




ss>:8123

[![](im
g
s/H
i
i-300x161.p
g)](im
g
s/H
i
i.p
g)

Hom
 
ssist

t H
ss.io is 
ow 
u

i
g 
s VM o
 VMw


 
SXi.






