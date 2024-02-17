---
titl
: "I
st
ll Hom
 
ssist

t o
 
SXi-

M"


t
: "2020-10-26T20:01:53.000Z"
c
t
go
i
s: 
  - "
sxi-

m"
t
gs: 
  - "

m"
  - "
sxi-

m"
  - "pi"

utho
: Ivo 





s
---

I
 this 
x
mpl
, I i
st
ll th
 followi
g compo


ts:

- U
u
tu fo
 

M
- VMw


 Tools
- 
ock


- Hom
 
ssist

t i
 
 
ock

 co
t
i


.



 P

-

quisit
s

1. 
ow
lo

 `U
u
tu 20.04.1-liv
-s

v

-

m64.iso`, [Li
k](http://c
im
g
.u
u
tu.com/u
u
tu/

l

s
s/20.04/

l

s
/u
u
tu-20.04.1-liv
-s

v

-

m64.iso)
2. M
k
 
 co


ctio
 to th
 vC

t

 S

v

 : `https://<vc

t

 s

v

>/ui` o
 th
 loc
l 
SXi s

v

 https://<
sx-s

v

>
3. Uplo

 th
 U
u
tu ISO to 
 

t
sto





 Hom
 
ssist

t VM C


tio


C


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

- 
ight click Host S
l
ct C


t
/

gist

 VM

[![](im
g
s/1-300x150.jpg)](im
g
s/1.jpg)

- **Vi
tu
l M
chi

 

m
**: Hom

ssst

t-001
- **S
l
ct 
 comput
 

sou
c
**: s
l
ct 

 
SXi s

v


- **S
l
ct sto

g
**: <S
l
ct th
 

t
sto

>
- **S
l
ct comp
ti
ility**: 
SXi 7.0 


 l
t


- **S
l
ct 
 gu
st OS**:
    - **Gu
st OS F
mily**: Li
ux
    - **Gu
st OS V

sio
**: U
u
tu Li
ux (64-
it)
- Customiz
 h


w


:
    - **CPUs**: 2
    - **M
mo
y:** 2048 M

    - **H


 
isk 1:** 30 G

    - **

two
k 


pt

 1:** S
l
ct th
 po
t g
oup
        - **


pt

 typ
:** 
1000

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


ct 
t Pow

 O
:** ch
ck


    - **Vi

o C


:** 

f
ult s
tti
gs
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




 U
u
tu I
st
ll
tio


- **S
l
ct**: I
st
ll U
u
tu S

v



[![](im
g
s/2-300x157.p
g)](im
g
s/2.p
g)

- **L

gu
g
:** 

glish
- **S
l
ct:** I
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

glish US (v

i

t (US)
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
 `

s160` is th
 
th



t 
IC of th
 VM. S
l
ct th
 IPv4 m
tho
: 
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

k you 


 
 
ot usi
g 
 p
oxy s

v


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
    - _You
 

m
_: <you
 

m
>
    - _You
 s

v

’s 

m
_: <s

v

 

m
>
    - _Pick 
 us



m
_: <us



m
>
    - _Choos
 
 p
sswo

_: <p
sswo

>
    - _Co
fi
m 
 p
sswo

_: <p
sswo

>
- **SSH S
tup**: I
st
ll th
 Op

SSH s

v


    - Impo
t SSH i


tity: 
o

[![](im
g
s/SSH-300x227.p
g)](im
g
s/SSH.p
g)

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

[![](im
g
s/I
st
ll-300x224.p
g)](im
g
s/I
st
ll.p
g)

- O
c
 th
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


ft

 th
 i
st
ll
tio
 of th
 U
u
tu OS, p

fo
m th
 followi
g post co
figu

tio
 
ctio
s:

- I
 
 co
sol
 s
ssio
, fi

 th
 IP 




ss with th
 `ip -
` comm


. VMw


 Tools is 
ot i
st
ll

 y
t, so th
 IP 




ss is 
ot visi
l
 i
 VM p
op

ti
s.
- Co


ct to th
 U
u
tu usi
g 

 SSH s
ssio
 with Putty fo
 
x
mpl

- I
st
ll th
 l
t
st U
u
tu up

t
s 


 upg



s

```
su
o 
pt up

t
 && su
o 
pt upg



 -y
su
o 


oot
```



 **Op

 VMw


 Tools i
st
ll
tio
**

I
 th
 SSH s
ssio
 i
st
ll p
ck
g
 

p




ci
s 


 clo

 th
 op

 git 

posito
y.

```
su
o -i

pt i
st
ll -y 
utom
k
-1.15 pkg-co
fig li
tool li
msp
ck-

v li
gli
2.0-

v li
p
m0g-

v li
ssl-

v li
xml2-

v li
xmls
c1-

v li
x11-

v li
x
xt-

v li
xi



m
-

v li
xi-

v li
x





-

v li
x




-

v li
gtk2.0-

v li
gtk-3-

v li
gtkmm-3.0-

v
git clo

 https://githu
.com/VMw


/op

-vm-tools.git
c
 op

-vm-tools/op

-vm-tools/

uto

co
f -i
./co
figu


m
k

m
k
 i
st
ll
l
co
fig
```


uil
 


 i
st
ll th
 Op

 VMw


 Tools

```

uto

co
f -i 
./co
figu


m
k

m
k
 i
st
ll
l
co
fig
```

c


t
 
 `vmtools
.s

vic
` fil


```
c
t > /
tc/syst
m
/syst
m/vmtools
.s

vic
 << 
OF
[U
it]


sc
iptio
=


sc
iptio
=Op

 VM Tools

ft

=

ft

=

two
k-o
li

.t

g
t
[S

vic
]

x
cSt

t=

x
cSt

t=/us
/loc
l/
i
/vmtools



st

t=
lw
ys


st

tS
c=1s
c
[I
st
ll]
W

t


y=multi-us

.t

g
t

OF
```





l
 th
 VMw


 Tools 


mo
 
t st

tup

```
syst
mctl 



l
 vmtools
.s

vic

syst
mctl st

t vmtools
.s

vic

```

Ch
ck if th
 VMw


 tools 


 
u

i
g

```
syst
mctl st
tus vmtools
.s

vic

```



 [![](im
g
s/VMw


ToolsCh
ck-300x47.p
g)](im
g
s/VMw


ToolsCh
ck.p
g)



 
ock

 i
st
ll
tio


I
 th
 SSH s
ssio
 
u
 th
 followi
g comm


s:

```

pt i
st
ll softw


-p
op

ti
s-commo
 -y

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
```



 Hom
 
ssist

t i
st
ll
tio


I
 th
 SSH s
ssio
 
u
 th
 followi
g comm


:

```
cu
l -sL "https://

w.githu
us

co
t

t.com/hom
-
ssist

t/sup

vis

-i
st
ll

/m
st

/i
st
ll

.sh" | 

sh -s -- -m 

sp



ypi4
```

<t

l
 styl
="
o



-coll
ps
: coll
ps
; wi
th: 100%;"><t
o
y><t
><t
 styl
="wi
th: 50%;"><
 h

f="im
g
s/H
1-1.p
g"><img cl
ss="
lig
c

t

 siz
-m

ium wp-im
g
-7761" s
c="im
g
s/H
1-1-300x91.p
g" 
lt="" wi
th="300" h
ight="91"></
></t
><t
 styl
="wi
th: 50%;"><
 h

f="https://www.ivo





s.
l/wp-co
t

t/uplo

s/2020/10/h
2.p
g"><img cl
ss="
lig
c

t

 siz
-m

ium wp-im
g
-7762" s
c="im
g
s/h
2-300x87.p
g" 
lt="" wi
th="300" h
ight="87"></
></t
></t
></t
o
y></t

l
>


ft

 th
 i
st
ll
tio
, it t
k
s 

out 1 mi
ut
 fo
 
ll th
 7 
ock

 H
 co
t
i


s 


 up. You c

 ch
ck this 
y usi
g th
 `
ock

 -ps` comm


.

<t

l
 styl
="
o



-coll
ps
: coll
ps
; wi
th: 100%;"><t
o
y><t
><t
 styl
="wi
th: 50%;"><
 h

f="im
g
s/H
-w

.p
g"><img cl
ss="
lig
c

t

 siz
-m

ium wp-im
g
-7763" s
c="im
g
s/H
-w

-300x178.p
g" 
lt="" wi
th="300" h
ight="178"></
></t
><t
 styl
="wi
th: 50%;"><
 h

f="https://www.ivo





s.
l/wp-co
t

t/uplo

s/2020/10/H
-w

1.p
g"><img cl
ss="
lig
c

t

 siz
-m

ium wp-im
g
-7764" s
c="im
g
s/H
-w

1-300x130.p
g" 
lt="" wi
th="300" h
ight="130"></
></t
></t
></t
o
y></t

l
>

Wh

 th
 
ock

 co
t
i


s 


 up, you c

 m
k
 
 w

 

ows

 co


ctio
 to:

`http://<ip 




ss:8123>`

Th


 will 

 
 "P

p

i
g Hom
 
ssist

t" p
g
 fo
 som
 mi
ut
s. O
c
 compl
t

 you'

 



y to c


t
 
 us

 of 

sto

 
 s

pshot of you'

 
xisti
g co
figu

tio
. 
ft

 this, you c

 st

t with you
 hom
 
utom
tio
 p
oj
cts.






