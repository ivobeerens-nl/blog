---
titl
: "vC

t

 S

v

 
ppli

c
 (vCS
) 
utom
t

/u

tt




 

ploym

t"


t
: "2018-08-20T09:54:28.000Z"
t
gs: 
  - "vcs
"
  - "VMw


"

utho
: Ivo 





s
---

**P



quisit
s:**

- This 
x
mpl
 is 

s

 o
 
 Wi

ows Op


ti
g Syst
m. Usi
g 
 Li
ux o
 M
C OS is 
lso possi
l
 
ut 
ot highlight

 i
 this 
log.
- M
k
 su

 th
 FQ

 of th
 vCS
 is 

solv

l
 
y 
 

S s

v

 


 ch
ck if 

v

s
 lookup wo
ks.

**St
ps to p

fo
m:**

- 
ow
lo

 th
 vC

t

 S

v

 
ppi

c
 (VCS
) ISO (v

sio
 6.5 o
 6.7)
- Mou
t th
 ISO
- Th
 CLI i
st
ll

 fo
 Wi

ows 

qui

s 
 Mic
osoft Visu
l C++ 


ist
i
ut

l
 v

sio
 14.0. This 

qui

m

t c

 

 ch
ck

 with th
 followi
g comm


:

```
\vcs
-cli-i
st
ll

\wi
32\ch
ck_wi

ows_vc_


ist.

t
```

- 

vig
t
 to th
 JSO
 t
mpl
t
s. Th
 vCS
 ISO co
t
i
s t
mpl
t
 JSO
 fil
s th
t c

 

 us

 fo
 

ployi
g th
 vCS
. Th
 t
mpl
t
s c

 

 fou

 o
 th
 ISO i
 th
 followi
g m
p:

```
 \vcs
-cli-i
st
ll

\t
mpl
t
s\i
st
ll
```

Th
 typ
s of t
mpl
t
s 


 
v
l

l
:

```
           
m





_vCS
_o
_*.jso
: Pl
tfo
m S

vic
s Co
t
oll

 (PSC) 


 vCS

                                     tog
th

 o
 o

 syst
m
            PSC_o
_*.jso
:           O
ly 
 PSC
            vCS
_o
_*.jso
:          O
ly 
 vCS

            *_o
_
SXi.jso
:          I
st
ll o
to th
 
SXi host sp
cifi

 i
 th
 JSO

                                     fil

            *_o
_VC.jso
:            I
st
ll o
to 
 host m


g

 
y th
 vC

t


                                     i
st

c
 sp
cifi

 i
 th
 JSO
 fil

```

- 

it 
 t
mpl
t
 "**
m





\_vCS
\_o
\_
SXi.jso
**" o
 **us
 th
 
x
mpl
 

low** with you'

 f
vo
it
 

ito
 (I us
 
ot
p

 ++) 


 s
v
 it to 
 w
it

l
 loc
tio
 (i
 th
 CLI sy
t
x you 



 to poi
t to this mo
ifi

 JSO
 fil
). Th
 t
mpl
t
 co
t
i
s th
 mi
im
l p


m
t

s 





 to 

ploy th
 
m





 vCS
. Th
 vCS
 will 

ploy

 
s ti
y (2 vCPU, 10 G
 m
mo
y, 300 G
 sto

g
). 

 ov

vi
w of 
ll p


m
t

s th
t c

 

 us

 


 fou

 h


, [li
k](https://
ocs.VMw


.com/

/VMw


-vSph


/6.7/com.VMw


.vc

t

.i
st
ll.
oc/GUI
-457


1F-
08
-4
64-8506-8
3F
84
0446.html).


x
mpl
 JSO
 fil
 to 

ploy 

 
m





 vC

t

 S

v

 
ppli

c
 with th
 PSC 


 vC

t

 compo


ts:

\[co

 l

gu
g
="xml"\] { "\_\_v

sio
": "2.13.0", "\_\_comm

ts": "S
mpl
 t
mpl
t
 to 

ploy 
 vC

t

 S

v

 
ppli

c
 with 

 
m





 Pl
tfo
m S

vic
s Co
t
oll

 o
 

 
SXi host.", "

w\_vcs
": { "
sxi": { "host

m
": "192.168.11.10", "us



m
": "
oot", "p
sswo

": "VMw




01!", "

ploym

t\_

two
k": "vl

13-s
v", "

t
sto

": "SS
-M2-01" }, "
ppli

c
": { "\_\_comm

ts": \[ "You must p
ovi

 th
 '

ploym

t\_optio
' k
y with 
 v
lu
, which will 
ff
ct th
 VCS
's co
figu

tio
 p


m
t

s, such 
s th
 VCS
's 
um


 of vCPUs, th
 m
mo
y siz
, th
 sto

g
 siz
, 


 th
 m
ximum 
um


s of 
SXi hosts 


 VMs which c

 

 m


g

. Fo
 
 list of 
cc
pt

l
 v
lu
s, 
u
 th
 suppo
t

 

ploym

t siz
s h
lp, i.
. vcs
-

ploy --suppo
t

-

ploym

t-siz
s" \], "thi
\_
isk\_mo

": t
u
, "

ploym

t\_optio
": "ti
y", "

m
": "vcs
03.l

.loc
l" }, "

two
k": { "ip\_f
mily": "ipv4", "mo

": "st
tic", "ip": "192.168.13.13", "

s\_s

v

s": \[ "192.168.13.101" \], "p

fix": "24", "g
t
w
y": "192.168.13.254", "syst
m\_

m
": "vcs
03.l

.loc
l" }, "os": { "p
sswo

": "VMw


01!", "
tp\_s

v

s": "pool.
tp.o
g", "ssh\_



l
": t
u
 }, "sso": { "p
sswo

": "VMw


01!", "
om
i
\_

m
": "vSph


.loc
l" } }, "c
ip": { "

sc
iptio
": { "\_\_comm

ts": \[ "++++VMw


 Custom

 
xp

i

c
 Imp
ov
m

t P
og

m (C
IP)++++", "VMw


's Custom

 
xp

i

c
 Imp
ov
m

t P
og

m (C
IP) ", "p
ovi

s VMw


 with i
fo
m
tio
 th
t 



l
s VMw


 to ", "imp
ov
 its p
o
ucts 


 s

vic
s, to fix p
o
l
ms, ", "


 to 

vis
 you o
 how 

st to 

ploy 


 us
 ou
 ", "p
o
ucts. 
s p

t of C
IP, VMw


 coll
cts t
ch
ic
l ", "i
fo
m
tio
 

out you
 o
g

iz
tio
's us
 of VMw


 ", "p
o
ucts 


 s

vic
s o
 
 

gul

 

sis i
 
ssoci
tio
 ", "with you
 o
g

iz
tio
's VMw


 lic

s
 k
y(s). This ", "i
fo
m
tio
 
o
s 
ot p

so

lly i


tify 

y i

ivi
u
l. ", "", "


itio

l i
fo
m
tio
 

g


i
g th
 

t
 coll
ct

 ", "th
ough C
IP 


 th
 pu
pos
s fo
 which it is us

 
y ", "VMw


 is s
t fo
th i
 th
 T
ust &
mp;
mp;
mp; 
ssu


c
 C

t

 
t ", "http://www.VMw


.com/t
ustVMw


/c
ip.html . If you ", "p

f

 
ot to p

ticip
t
 i
 VMw


's C
IP fo
 this ", "p
o
uct, you shoul
 
is

l
 C
IP 
y s
tti
g ", "'c
ip\_



l

': f
ls
. You m
y joi
 o
 l

v
 VMw


's ", "C
IP fo
 this p
o
uct 
t 

y tim
. Pl

s
 co
fi
m you
 ", "
ck
owl

g
m

t 
y p
ssi
g i
 th
 p


m
t

 ", "--
ck
owl

g
-c
ip i
 th
 comm


 li

.", "++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++" \] }, "s
tti
gs": { "c
ip\_



l

": t
u
 } } }

\[/co

\]

Th
 fi
st 

ploym

ts f
il

 wh

 usi
g th
 FQ

 
SXi host

m
 i
 th
 JSO
 fil
, with th
 followi
g 


o
:

OVF Tool: T


sf

 F
il



OVF Tool: 


o
: F
il

 to s


 http 

t




ploym

t f
il

. OVF Tool 

tu

 


o
 co

: 1

[![](im
g
s/1-9-300x194.p
g)](im
g
s/1-9.p
g)

I ch
ck

 th
 logs 
ut 
i

't fi

 

y clu
. Th
 FQ

 of th
 
SXi host w
s 

volv

l
 
y 

S 
ut 
ft

 ch

gi
g th
 
SXi FQ

 to th
 IP 




ss of th
 
SXi  host i
 th
 JSO
 fil
 th
 

ploym

t fi
ish

 without 


o
s.

- P

fo
m 
 t
mpl
t
 JSO
 v

ific
tio
 without i
st
lli
g:

```
vcs
-

ploy i
st
ll --
cc
pt-
ul
 --v

ify-t
mpl
t
-o
ly <JSO
 fil
 p
th>
```

- P

fo
m th
 
ctu
lly 

ploym

t

```
vcs
-

ploy.
x
 i
st
ll --
cc
pt-
ul
 --
ck
owl

g
-c
ip --t

s
 --
o-ssl-c

tific
t
-v

ific
tio
 <JSO
 fil
 p
th>
```

Wh

 th
 u

tt




 

ploym

t fi
ish

, 

 
m





 vC

t

 S

v

 
ppli

c
 with th
 Pl
tfo
m S

vic
 Co
t
oll

 (PSC) 


 vC

t

 S

v

 
ol
 is 



y to 
um
l
.

I c


t

 
 GitHu
 

posito
y fo
 th
 

ploym

t 


 p


m
t

s, [li
k](https://githu
.com/i





s/VCS
).

VMw


 
ocum

t
tio
 

out th
 CLI 

ploym

t c

 

 fou

 h


, [li
k](https://
ocs.VMw


.com/

/VMw


-vSph


/6.7/com.VMw


.vc

t

.i
st
ll.
oc/GUI
-C17
FF44-22

-41F4-
85
-19
7
995
144.html).






