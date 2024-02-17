---
titl
: "Th
 mo
il
 S

C 


 
UC l

 

vi
o
m

t"


t
: "2016-06-23T09:46:03.000Z"
c
t
go
i
s: 
  - "
uc"
  - "hom
-l

"
  - "ss
c"
t
gs: 
  - "
uc"
  - "hom
-l

"
  - "l

"
  - "s

c"

utho
: Ivo 





s
---

Th
 p
st moths I'v
 got 
sk

 wh
t compo


ts w
 us

 to 
uil
 this l

 

vi
o
m

t. So h


 is 

 quick ov

vi
w. Th
 

vi
o
m

t logic
lly looks lik
 th
 pictu

 

low:

[![

mo 

vi
o
m

t](im
g
s/

mo-

vi
o
m

t-300x284.jpg)](im
g
s/

mo-

vi
o
m

t.jpg)

This 

vi
o
m

t co
t
i
s th


 physic
l hosts with VMw


 
SXi i
st
ll

 


 o

 switch. O

 
SXi host fu
ctio
 
s m


g
m

t host. O
 this m


g
m

t host th
 followi
g softw


 
its 


 i
st
ll

:

- vSph


 6
- VS

 Wit

ss
- 
SX M


g


- Fo
tig
t
 VMX
- v


liz
 compo


ts
- Th
 


 Us

 Computi
g st
ck such 
s Ho
izo
 Vi
w, 
pp Volum
s, Us

 

vi
o
m

t M


g

 


 I


tity M


g


- V


m

Th
 oth

 2 
SXi hosts fu
ctio
 
s 

mo clust

. O
 this 2-
o

 clust

 th
 followi
g softw


 
its 


 i
st
ll

:

- vSph


 6
- Vi
tu
l S

 (VS

) 
ll Fl
sh (
F) co
figu

tio

- 
SX i
t
g

tio

- Wi

ows 10l
- Wi

ows S

v

 2012 
2


 l
ptop is us

 to co


ct to th
 l

 

vi
o
m

t.

**Wh
t compo


t 


 us

?** 

Som
 highlights of this l

 


:

- 4U 

ckmou
t flightc
s

- Mi
i-ITX moth


o



- I
t
l X
o
 
-1541 si
gl
 sock
t Syst
m-o
-Chip 8 co

 p
oc
sso

- 2 x 10 G

 
th



t 


pt

s
- O
ly SS
 is us


- IPMI po
t

**C
s
**

Th
 c
s
 is 
 
o
ust custom m


 19" 4U 

ckmou
t flightc
s
 with 
 

mov

l
 f
o
t 


 

ck. It h
s two wh

ls so you c

 c


y it 

sily 

ou

. This c
s
 co
t
i
s 3 s

v

s 


 o

 switch.H


 is 
 pictu

 of th
 c
s
 i
clu
i
g 
ll
 th
 hosts 


 th
 switch.

[![IMG_0622](im
g
s/IMG_0622-300x225.jpg)](im
g
s/IMG_0622.jpg)[![I


li
g Flightc
s
](im
g
s/I


li
g-Flightc
s
-1-300x265.jpg)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2016/05/I


li
g-Flightc
s
-1.jpg)

**Hosts**

Th
 flightc
s
 co
t
i
s th


 Sup

Mic
o SYS-5018
-F
4T 1U 

ckmou
t hosts with th
 followi
g h


w


 sp
cific
tio
s:

- **Ch
ssis**: Sup

Mic
o 19" 1U with 
 200W Gol
 l
v
l pow

 supply. Optimiz

 fo
 Mi
i-ITX (Sup

Ch
ssis SC505-203
)
- **Moth


o


**: Sup

 X10S
V-8C-TL
4F Mi
i-ITX 
o



- **P
oc
sso
**: 1 x I
t
l X
o
 
-1541 si
gl
 sock
t Syst
m-o
-Chip. This p
oc
sso
 co
t
i
s 8 co

s with 16 th



s (hyp

t



i
g)
- **M
mo
y**: 4x 


4 
IMM sock
ts (m
ximum 128 G
, 4 x 32G
 


4 
CC  m
mo
y)
- **L

**: 2 x 10G

 


 2 x 1 G

 


 1 x IPMI L

 po
t
- **
xp

sio
 slots**: 1 x PCI
 3.0 x16 slot 


 
 M.2 PCI
 3.0 x4
- **Vi

o**: 
sp


 
ST2400
- **US
**: 2x US
 3.0 


 4x US
 2.0

_M


g
m

t host_

- **M
mo
y**: 4 x 32G
 = 128 G

- **SS
**: 2 x S
msu
g PM863 MZ-7LM1T9
 - SS
 

t

p
is
 - 1.92 T
 - i
t


 - 2.5" - S
T
 6G

- **
isk**: S

g
t
 

t

p
is
 6 T
 
isk (fo
 

ckup)
- **US
 Stick:** S


isk Ult

 Fit US
3 16 G
 (fo
 
ooti
g 
SXi)

_

mo hosts_ 



ch host co
t
i
s th
 followi
g h


w


:

- **M
mo
y**: 2 x 16G
 = 32 G
 p

 s

v


- **SS
**: 1 x I
t
l P3500 SS
 1.2 T
 PCI
 3.0 x4 (
VM
) 


 S
msu
g 950 P
o V-



 M.2 PCI-
 SS
 512G

- **US
 Stick:** S


isk Ult

 Fit US
3 16 G
 (fo
 
ooti
g 
SXi)

_Switch_

- **Switch**: 

tg


 P
oS
f
 Plus XS708
 8 x 10 G
ps +SFP slot

_C

l
s_

- 6 x UTP C
T6 0.50 cm c

l
s
- 1 x UTP C
T6 5m
- 1 x UTP C
T6 10m

 

[![P
oc
sso
](im
g
s/P
oc
sso
-300x130.p
g)](im
g
s/P
oc
sso
.p
g) [![host](im
g
s/host-300x140.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2016/06/host.p
g)

Th
 two I
t
l X552/X557-
T 
ICs 


 
ot 

cog
iz

 
y 
SXi 6.5 


 low

 v

sio
s 
y 

f
ult. To 



l
 th
 I
t
l X552/x557 2 x 10G

 
ICs 
ow
lo

 th
 I
t
l 

iv

 o
 th
 VMw


 w

sit
 ([li
k](https://www.VMw


.com/

sou
c
s/comp
ti
ility/

t
il.php?

vic
C
t
go
y=io&p
o
ucti
=39968&

vic
C
t
go
y=io&

t
ils=1&p

t


=46&

l

s
s=274&k
ywo

=10G
&p
g
=1&
ispl
y_i
t

v
l=10&so
tColum
=P

t


&so
tO



=
sc)). 
xt

ct th
 ZIP fil
 


 i
st
ll th
 offli

 
u

l
 
y usi
g th
 followi
g comm


:

\[co

 l

gu
g
="Pow

Sh
ll"\] 
sxcli softw


 vi
 i
st
ll -
 /vmfs/volum
s/

t
sto

/

iv

/ixg

-4.4.1-2159203-offli

\_
u

l
-3848596.zip \[/co

\]

[![](im
g
s/t
st-300x100.p
g)](im
g
s/t
st.p
g)

With this mo
il
 SS
C l

 

vi
o
m

t w
 

chiv

 th
 followi
g 



fits:

- Mo
il
 


 

sy to c


y 

ou


- Fl
xi
ility to i
st
ll th
 l
t
st VMw


 S

C 


 3
 p

ty softw



- 
o 

p




cy
- 

ough ho
s
pow


- Low 
ois
 


 pow

 co
sumptio

- 

mot
 
cc
ssi
l
 f
om ou
 

t
c

t


- IPMI 


 KVM suppo
t






