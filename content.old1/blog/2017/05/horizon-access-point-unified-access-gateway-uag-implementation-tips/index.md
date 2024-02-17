---
titl
: "Ho
izo
 
cc
ss Poi
t / U
ifi

 
cc
ss G
t
w
y (U
G) impl
m

t
tio
 tips"


t
: "2017-05-16T06:26:13.000Z"
c
t
go
i
s: 
  - "ho
izo
"
  - "VMw


"
t
gs: 
  - "VMw


-ho
izo
"

utho
: Ivo 





s
---

- Th
 U
ifi

 
cc
ss G
t
w
y (U
G) p
ovi

s s
cu

 
cc
ss to th
 followi
g 

vi
o
m

ts:
    - VMw


 Ho
izo
 

sktops 


 
pplic
tio
s
    - VMw


 I


tity M


g


    - VMw


 
i
W
tch o
 VMw


 Wo
ksp
c
 O

 p

-
pp tu


ls 


 tu


l p
oxy
    - VMw


 Co
t

t G
t
w
y s

vic
 to 
llow VMw


 Co
t

t Lock

 
cc
ss to i
t



l fil
 sh


s 


 Mic
osoft Sh


Poi
t

[![](im
g
s/i
logsch

m-300x279.jpg)](im
g
s/i
logsch

m.jpg)

- I
 v

sio
 2.9 
cc
ss Poi
t is 



m

 to U
ifi

 
cc
ss G
t
w
y (U
G)
- U
G is i
clu


 i
 th
 Ho
izo
 st





, 

v

c

 


 

t

p
is
 lic

s

- Th
 us
 c
s
s list

 

ov
 c

 

 mix

 o
 th
 s
m
 U
G o
 s
p


t

 o
 multipl
 U
Gs
- U
G 2.9 suppo
ts Ho
izo
 6.2.3, 6.2.4 


 7.1.0
- U
G i
clu

s som
 imp
ov
m

ts (such 
s 
l
st 
xt

m
) th
t 


 
ot 
v
il

l
 i
 th
 Ho
izo
 S
cu
ity S

v


- U
G is 

ploy

 i
 th
 
MZ 


 

pl
c
s th
 Ho
izo
 S
cu
ity S

v

 (Wi

ows 

s

)
- U
G is p
ck
g

 
s 

 OVF.  It's 
 h






 Li
ux 
ppli

c
 

s

 o
 SUS
 

t

p
is
 Li
ux. So th


 
o 



 fo
 Wi

ows OS
s i
 th
 
MZ which imp
ov
s s
cu
ity!
- H


w


 sp
cific
tio
s fo
 th
 U
G 


:
    - 2 vCPU
    - 4 G
 m
mo
y
    - 20 G
 h



isk
    - 1,2 o
 3 

two
k 


pt

s
- C


t
 

 IP pool 

fo

 

ployi
g th
 U
G
- 

low is 

 ov

vi
w of th
 VMw


 U
G fi

w
ll po
ts co
figu

tio
:

[![](im
g
s/
cc
ss-Poi
t-fi

w
ll-po
ts-1-300x278.jpg)](im
g
s/
cc
ss-Poi
t-fi

w
ll-po
ts-1.jpg)

Th
 
ocum

t
tio
 

out th
 th
 fi

w
ll po
ts c

 

 fou

 [h


](http://pu
s.VMw


.com/
cc
sspoi
t-29/i


x.jsp?topic=%2Fcom.VMw


.
cc
ss-poi
t-29-

ploy-co
fig.
oc%2FGUI
-F197

60-3
0C-41
F-8
3
-C99CC

6
06
.html).

(**\*1**) Wh

 usi
g 
l
st 
xt

m
 ov

 po
t 443, po
t 8443 is 
ot 







- Th
 

mi
ist

tio
 us

 i
t

f
c
 (UI) c

 

 us

 to s
t up 


 m


g
 th
 U
ifi

 
cc
ss G
t
w
y 

vi
o
m

t. To 
cc
ss to th
 m


g
m

t i
t

f
c
 go to: **_https://ip




ss:9443/

mi
_**
- Upg


i
g U
G is 
ot suppo
t

. I
st
ll 
 

w 
ppli

c
. It's highly 

comm


 to c


t
 
 Pow

Sh
ll sc
ipt fo
 th
 

ploym

t th
t c

 

 us

 
v

ytim
 wh

 i
st
lli
gi
g 
 

w U
G.
- Wh

 

ployi
g U
G usi
g Pow

Sh
ll, 
ow
lo

 th
 l
t
st 

ploym

t sc
ipts, [li
k](https://commu
iti
s.VMw


.com/
ocs/
OC-30835)
- Th
 followi
g c

tific
t
s c

 

 us

:
    - Si
gl
-S

v

 

m
 C

tific
t

    - Su
j
ct 
lt



tiv
 

m
 (S

)
    - Wil
c


 C

tific
t

- Co
v

t th
 c

tific
t
 i
to P
M-fo
m
t fil
s fo
 th
 c

tific
t
 ch
i
 


 th
 p
iv
t
 k
y, th

 co
v

t th
 .p
m fil
s to 
 o

-li

 fo
m
t th
t i
clu

s 
m





 

wli

 ch


ct

s
- If you
 c

tific
t
 is i
 PKCS
12 (.p12 o
 .pfx) fo
m
t, o
 
ft

 th
 c

tific
t
 is co
v

t

 to PKCS
12 fo
m
t, us
 Op

ssl to co
v

t th
 c

tific
t
 to .p
m fil
s
- Th


 is 
O 



 to p
i
 Ho
izo
 Co


ctio
 S

v

s with 
cc
ss Poi
t o
 U
G. U
ch
ck th
 
ox
s i
 th
 Co


ctio
 S

v

:

[![](im
g
s/Co


ctio
-s
tti
gs-300x215.jpg)](im
g
s/Co


ctio
-s
tti
gs.jpg)

- 

fo

 co
figu
i
g 


ius 
uth

tic
tio
, fi
st t
st if PCoIP 


 
l
st 
cc
ss wo
ks:
    - T
st 
 

tiv
 Ho
izo
 Cli

t usi
g PCoIP. T
st 
 

tiv
 Ho
izo
 Cli

t usi
g 
l
st. T
st th
 HTML 
cc
ss Cli

t (which 
lso us
s 
l
st)
- Som
 

ows

s h
v
 p
o
l
ms with Cli

t HTML 
cc
ss ([li
k](https://commu
iti
s.VMw


.com/th



/553631)). To solv
 this p
o
l
m ch

g
 th
 ch
cko
igi
 p
op

ty.
    - O
 

ch Ho
izo
 Co


ctio
 S

v


    - 


 
 li

 i
 th
 "lock

.p
op

ti
s" fil
 (C:
P
og

m Fil
s
VMw



VMw


 Vi
w
S

v


sslg
t
w
y
co
f)
    - ch
ckO
igi
=f
ls

    - S
v

    - 

st

t th
 VMw


 Ho
izo
 Vi
w Co


ctio
 S

v

 s

vic
.

**Pow

Sh
ll 
x
mpl
**

I p

f

 th
 c


t
 
 Pow

Sh
ll sc
ipt fo
 th
 

ploym

t of th
 U
G. This sc
ipt 

ploys 
 si
gl
 U
G with 
 si
gl
 
IC 


 p
ovi

 s
cu

 
cc
ss to th
 Ho
izo
 Vi
w 

vi
o
m

t. Th
 c

tific
t
 will 

 g




t

 
utom
tic
lly 


 is s
lf-sig


 (i
 p
o
uctio
 

vi
o
m

ts us
 

 sig


 c

tific
t
).

Wh

 

-

ployi
g 

 U
G with Pow

Sh
ll th


 is 
o 



 to m

u
lly 

mov
 th
 
ppli

c
. Wh

 th
 co
fig is th
 s
m
 th
 ol
 
ppli

c
 is 
utom
tic
lly 

mov

.



fo

 usi
g Pow

Sh
ll m
k
 su

 th
 followi
g 

qui

m

ts 


 m
t, [li
k](http://pu
s.VMw


.com/
cc
sspoi
t-29/i


x.jsp
com.VMw


.
cc
ss-poi
t-29-

ploy-co
fig.
oc/GUI
-3
409

7-C889-4F1
-8
60-896
78F0C3F2.html).

Pow

Sh
ll sc
ipt:

\[co

 l

gu
g
="Pow

Sh
ll"\]

\[G




l\] 
 
 U
G vi
tu
l 
ppli

c
 u
iqu
 

m
 (

tw


 1 


 32 ch


ct

s). 
 If 

m
 is 
ot sp
cifi

, th
 sc
ipt will p
ompt fo
 it. 




m
=U
G01

\
 
 Full p
th fil


m
 of th
 U
G .ov
 vi
tu
l m
chi

 im
g
 
 Th
 fil
 c

 

 o
t
i


 f
om VMw


 


sou
c
=C:
t
mp

uc-
cc
ss-poi
t-2.9.0.0-5202536\_OVF10.ov


\
 
 t

g
t 

f

s to th
 vC

t

 us



m
 


 




ss/host

m
 


 th
 
SXi host fo
 

ploym

t 
 

f

 to th
 ovftool 
ocum

t
tio
 fo
 i
fo
m
tio
 

out th
 t

g
t sy
t
x. 
 S

 https://www.VMw


.com/suppo
t/

v
lop

/ovf/ 
 P
SSWO

 i
 upp

 c
s
 

sults i
 
 p
sswo

 p
ompt 
u
i
g 

ploym

t so th
t p
sswo

s 
o 
ot 



 
 to sp
cifi

 i
 this .I
I fil
. 
 I
 this 
x
mpl
, th
 vC

t

 us



m
 is 

mi
ist

to
@vSph


.loc
l 
 th
 vC

t

 s

v

 is 192.168.0.21 (this c

 

 
 host

m
 o
 IP 




ss) 
 th
 
SXi host

m
 is 
sx1.myco.i
t (this c

 

 
 host

m
 o
 IP 




ss) 
 t

g
t=vi://

mi
ist

to
@vSph


.loc
l:P
SSWO

@192.168.250.30/
c-





s-01/host/mg
t

\
 
 vSph


 

t
sto

 

m
 



s=
FS-01

\
 
 vSph


 

two
k 

m
s. 
 vSph


 

two
k P
otocol P
ofil
 must 

 
ssoci
t

 with 
v

y 

f



c

 

two
k 

m
. This sp
cifi
s 
 

two
k s
tti
gs such 
s IPv4 su


t m
sk, g
t
w
y 
tc. 




tI
t



t=
mz-vl

100 

tM


g
m

t

two
k=
mz-vl

100 

t

ck




two
k=
mz-vl

100 

ploym

tOptio
=o


ic ip0=192.168.250.32 

tm
sk0=255.255.255.0 

s=192.168.250.2 
syslogU
l=syslog://s

v

.
x
mpl
.com:514

\
 
 S
tti
g ho
o
Ciph

O



 to t
u
 fo
c
s th
 TLS ciph

 o



 to 

 th
 o



 sp
cifi

 
y th
 s

v

. This c

 

 s
t o
 
 U
G 2.7.2 


 

w

 to fo
c
 th
 Fo
w


 S
c

cy ciph

s to 

 p

s

t

 fi
st to imp
ov
 s
cu
ity. 


ho
o
Ciph

O



=t
u


\[Ho
izo
\]

\
 
 p
oxy

sti

tio
U
l 

f

s to th
 

ck


 Co


ctio
 S

v

 to which this U
G 
ppli

c
 will co


ct. 
 It c

 
ith

 sp
cify th
 

m
 o
 IP 




ss of 

 i

ivi
u
l Co


ctio
 S

v

 o
 of 
 lo

 

l

c

 
li
s to co


ct 
 vi
 
 lo

 

l

c

 i
 f
o
t of multipl
 Co


ctio
 S

v

s. 


p
oxy

sti

tio
U
l=https://192.168.250.71

\
 
 p
oxy

sti

tio
U
lThum
p
i
ts o
ly 



s to 

 sp
cifi

 if th
 

ck


 Co


ctio
 S

v

s 
o 
ot h
v
 
 
 t
ust

 C
 sig


 SSL s

v

 c

tific
t
 i
st
ll

 (
.g. if it h
s th
 

f
ult s
lf-sig


 c

tific
t
 o
ly). 
 This is 
 comm
 s
p


t

 list of thum
p
i
ts i
 th
 fo
m
t show
 h


. 


p
oxy

sti

tio
U
lThum
p
i
ts=sh
1:‎f1 c2 
8 0
 3f 7
 87 
f 33 96 22 49 66 40 70 1
 11 74 9
 
1

tu


l
xt



lU
l=https://v
i.ivo





s.
l:443 
l
st
xt



lU
l=https://v
i.ivo





s.
l:443

\
 
 pcoip
xt



lU
l must co
t
i
 

 IPv4 




ss (
ot 
 

S 

m
) 


pcoip
xt



lU
l=31.151.8.45:4172

\[/co

\]

- _

m
_: Th
 

m
 of th
 U
ifi

 
cc
ss G
t
w
y (U
G)
- _sou
c
_: Th
 loc
tio
 of th
 OVF fil

- _t

g
t_: Sp
cifi
s th
 vC

t

 S

v

 i
fo
m
tio
 


 t

g
t 
SX host.
- _
s_: 

t
sto

 to 

ploy th
 U
G
- _vSph


 

two
k 

m
s_: This s
ctio
 co
t
i
s th
 

two
k s
tti
gs such 
s:
    - Po
tg
oup
    - IP 




ss
    - Su


tm
sk
    - 
mou
t of 
ICs
    - 

S s

v

(s)
- _ho
o
Ciph

O



_: This 
llows fo
w


 s
c

cy ciph

s to 

 p

s

t

 fi
st i
 th
 ciph

 list to imp
ov
 s
cu
ity.
- _p
oxy

sti

tio
U
l_: U
L 

p

s

ti
g th
 Ho
izo
 

ck


 s

v

 (i
t



l Co


ctio
 s

v

)
- _p
oxy

sti

tio
U
lThum
p
i
ts_: This co
t
i
s th
 thum
p
i
t of th
 Co


ctio
 S

v



![](im
g
s/Fi
g

p
i
t-229x300.jpg)

- _tu


l
xt



lU
l_: U
L us

 
y Ho
izo
 Cli

ts to co


ct th
 s
cu

 tu


l to this U
G 
ppli

c

- _
l
st
xt



lU
l_: U
L us

 
y HTML 
cc
ss Cli

ts to co


ct to this U
G 
ppli

c

- _pcoip
xt



lU
l_: U
L us

 
y Ho
izo
 Cli

ts to co


ct usi
g PCoIP to this U
G 
ppli

c
 (
xt



l IP 




ss)

[![](im
g
s/Pow

Sh
ll-300x179.jpg)](im
g
s/Pow

Sh
ll.jpg)

Wh

 th
 U
G 

ploym

t succ
ssfully 
x
cut
s oth

 co
figu

tio
 (UI o
 Pow

Sh
ll) optio
s c

 

 




 such 
s:

- T
ust

 c

tific
t
s
- 


ius 
uth

tic
tio

- I


tity M


g








