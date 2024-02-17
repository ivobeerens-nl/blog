---
titl
: "VMwo
l
 
u
op
 2013&


sh;Th
 Softw


-

fi


 

t
 C

t

 (S

C) 

c
p"


t
: "2013-10-20T20:31:37.000Z"
c
t
go
i
s: 
  - "s

c"
  - "vmwo
l
"
t
gs: 
  - "s

c"
  - "vmwo
l
"

utho
: Ivo 





s
---

[![foto](im
g
s/foto_thum
.jpg "foto")](im
g
s/foto.jpg)

It’s 
ll 

out 

liv

i
g IT 
s 
 S

vic
.   IT 
s 
 S

vic
s giv
s th
 followi
g 

sw

s:

- O
-

m


 
cc
ss to 

y 

vic
;
- Cost t


sp



cy;
- 

y clou
, 

y pl
tfo
m;
- P
og

mm

l
 


 
utom
t

 i
f

st
uctu

.

To 

liv

 IT 
s 
 S

vic
 VMw


 h
s fo
 th
 comi
g y


(s) th
 followi
g focus 



s:

- **Softw


-

fi


 

t
 C

t

 (S

C)**
- **


 Us

 Computi
g (
UC)**
- **vClou
 Hy

i
 S

vic
s (vCHS)**

I
 this 
log post I 
ig 


p

 i
 th
  Softw


-

fi


 

t
 C

t

 (S

C). I
 th
 

xt 
log posts I will cov

 th
 oth

 focus 



s.




 Softw


-

fi


 

t
 C

t

 (S

C)

Th
 S

C is 

out vi
tu
liz
tio
 
c
oss th
 

ti

 

t
 C

t

. Th
 Softw


-

fi


 

t
 C

t

 co
sist of th
 followi
g compo


ts:

- **Comput
**
- **

two
k**
- **Sto

g
**
- **M


g
m

t**

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




 Comput


Th
 comput
 l
y

 is 
uilt o
 th
 

w vSph


 5.5 pl
tfo
m.  Som
 imp
ov
m

ts of th
 vSph


 5.5 pl
tfo
m 


:

- 
SXi host sc
l

ility imp
ov
m

ts (2x i
c


s
 with 
SXi 5.1) such 
s 320 Logic
l CPUs, 16 
UM
 
o

s 


 4 T
 of 

M.
- W

 Cli

t imp
ov
m

ts such 
s 

tt

 p

fo
m

c
, OS X suppo
t 


 


g 


 

op fu
ctio

lity.
- Si
gl
 Sig
-O
 (SSO) imp
ov
m

ts.
- vC

t

 S

v

 
ppli

c
 (vCS
) 
ow 



y fo
 p
o
uctio
 

vi
o
m

ts
- vSph


 Fl
sh 



 C
ch
. 
cc
l


t
 



 IOs of VMs 
y usi
g loc
l fl
sh sto

g

- Suppo
t fo
 62 T
 VM
K. 
FS 


 v

M
- 
pplic
tio
 High 
v
il

ility (
pp H
).  
pp H
 p
ot
cts 
pps 
u

i
g i
si

 th
 VMs  such 
s MS SQL 


 IIS.

vSph


 Fl
sh 



 C
ch
 


 
pplic
tio
 High 
v
il

ility (
pp H
) will 

qui

 
 vSph


 

t

p
is
 Plus lic

s
. Fo
 mo

 i
fo
m
tio
 o
 th
 

w 


 imp
ov

 f

tu

s, s

 th
 “Wh
t’s 

w i
 VMw


 vSph


 5.5 Pl
tfo
m” P
F. [Li
k](http://www.VMw


.com/fil
s/p
f/vSph


/VMw


-vSph


-Pl
tfo
m-Wh
ts-

w.p
f)




 

two
k

Fo
 th
 

two
k i
 th
 S

C VMw


 


ou
c

 th
 G




l 
v
il

ility (G
) of 
SX.  VMw


 
cqui


 
ici
i
  


 








 it to 
SX. 
SX is 
ll 

out 

two
k vi
tu
liz
tio
. Th
 
SX 

two
k is c


t

 i
 softw


 
ut look lik
 physic
l 

two
ks.  It’s 
ot o
ly fo
 
SXi 
ut fo
 

y hyp

viso
. 
SX wo
ks with th
 
xisti
g 

two
k i
f

st
uctu

. C
p

iliti
s 


:

- Switchi
g L2
- 
outi
g L3
- Fi

w
ll
- Lo

 

l

c


- VP

- Suppo
t fo
 p

t


 
co-syst
m 


itio
s


SX giv
s you th
 fl
xi
ility 
o 

ploy 
 multi ti

 

two
k with softw


. You 


 

l
 to s
v
, 

l
t
, 

sto

 


 mov
 it, just lik
 you 
o fo
 VMs.  I
t


st

 custom

s shoul
 co
t
ct th
i
 VMw


 

p

s

t
tiv
 who c

 put th
m i
 touch 
i

ctly with 
 VMw


 
SX sp
ci
list. Mo

 i
fo
m
tio
 

out 
SX c

 

 fou

 h


 [li
k](http://www.VMw


.com/p
o
ucts/
sx/
2609166141001).




 Sto

g


VMw


 h
s th
 followi
g 


ou
c
m

ts m


 o
 Softw


-

fi


 Sto

g
:

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

**Vi
tu
l S

 (VS

)**

VS

 
gg

g
t
s 
ll th
 loc
l sto

g
 (spi

i
g 
isk) i
 th
 clust

 


 c


t
s 
 sh



 sto

g
 



y. With th
 us
 of fl
sh 
isks, 



 


 w
it
s c

 

 
cc
l


t

.  Wh

 

 
SXi host is offli

 th
 

t
 is still 
v
il

l
 o
 

oth

 
o

. It is fully comp
ti
l
 with High 
v
il

ility (H
) , 

S, vMotio
 


 SvMotio
. VS

 will p
o


ly G
 i
 H1 2014 


 will suppo
ts up to 16 
o

s. Th
 mi
imum of 3 
SXi 
o

s is 





. It c

 

 sc
l

-out 
y 


i
g 
xt

 
o

s. 
 us
 c
s
 of VS

 is VMw


 Ho
izo
 Vi
w V
I 

vi
o
m

ts.

Mo

 i
fo
m
tio
 s

 th
 “Wh
t’s 

w i
 VMw


 Vi
tu
l S

 (vS

)”  [Li
k](http://www.VMw


.com/fil
s/p
f/p
o
ucts/vs

/VMw


_Vi
tu
l_S

_Wh
ts_

w.p
f).

T
y th
 Pu
lic 

t
 of VS

? Li
k 

**Vi
tu
l Volum
s (VVOL)**

With VVOL 
xisti
g S

/

S syst
ms 

com
 VM-
w


.  Op


ti
g such 
s s

pshots, 

plic
tio
, c
chi
g, 

c
yptio
 


 

-
uplic
tio
  c

 

 
o

 
t VM l
v
l. VVOL must 

 suppo
t

 
y th
 sto

g
 h


w


. VVOl is 
v
il

l
 
s T
ch
ic
l P

vi
w 
y sto

g
 p

t


s.

**vSph


 Fl
sh 



 C
ch
 (vF
C)**

vF
C 
cc
l


t
s 



 IOs of VMs 
y usi
g loc
l fl
sh sto

g
. It is 
v
il

l
 i
 vSph


 5.5.

**Vi
sto**

Vi
sto is 
 softw


-o
ly solutio
 to 

liv

 p


ict

l
 p

fo
m

c
 i
 
xisti
g S

 syst
ms. It 

liv

s high p

fo
m

t VM-c

t
ic 

t
 s

vic
s.

[![im
g
](im
g
s/im
g
_thum
5.p
g "im
g
")](im
g
s/im
g
5.p
g)

Vi
sto sits o
 

ch host 


 p

s

ts 
 vi
tu
l sto

g
 
ppli

c
 (VS
) to th
 VMs o
 th
 host.  Th
 VMs s

 Vi
sto 
s 
 

w sto

g
 mou
t poi
t, which m


s Vi
sto is i
 th
 I/O p
th fo
 th
 VMs.  Vi
sto offlo

s th
 I/O f
om th
 Hyp

viso
 i
 
 mo

 
ffici

t m




.   Vi
sto will p

fo
m 
 s
t of 
ctio
s o
 th
 



om I/O so it is s
qu

ti
liz

 


 s

t to th
 
lock sto

g
 l
y

 i
 o



ly, logic
l 
locks. Fu
th

 it c

 
o high p

fo
m

c
 s

pshots 


 clo

s of VMs o
 VM
Ks. Vi
sto is 
ow 
v
il

l
.

**vSph


 

t
 P
ot
ctio
 

v

c

 (V
P
)**

VMw


 vSph


 

t
 P
ot
ctio
 5.5 

v

c

 (V
P
) is 
ow 
v
il

l
. It’s 
 

ckup 


 

cov

y solutio
 

s

 o
 
MC 
v
m

.  V

sio
 5.5 h
s 

w f

tu

s such 
s 

ckup 

t
 

plic
tio
, i
t
g

tio
 with 
MC 

t
 
om
i
, 
utom
tic 

ckup v

ific
tio
.  Th
 sm
ll

 
oth

 VMw


 vSph


 

t
 P
ot
ctio
 (V
P) is i
clu


 i
 vSph


 
ss

ti
ls Plus 

 high

 
ut h
s 
 lot of limits such 
s 2 T
 

ckup sto

 


 100 VMs p

 
ppli

c
.  With V
P
 VMw


 will comp
t
 
g
i
st oth

 vi
tu
liz
tio
 

ckup 


 

cov

y solutio
s such 
s  V


m 

ckup & 

cov

y 


 PH
 Vi
tu
l.




 M


g
m

t

O
 th
 Clou
 M


g
m

t l
y

 th
 followi
g p
o
ucts 


 


ou
c

:

[![im
g
](im
g
s/im
g
_thum
6.p
g "im
g
")](im
g
s/im
g
6.p
g)

**vClou
 
utom
tio
 C

t

 (vC
C) 6.0**. 

VMw


 
cqui


 th
 comp

y “
y

micOps” l
st y


 


 








 it 
s vC
C. vC
C is 
ll 

out 
utom
ti
g, 
uil
i
g, 

ployi
g 


 m


gi
g 
pplic
tio
 c
t
logs. 

<t

l
 c
llsp
ci
g="0" c
llp


i
g="2" wi
th="400" 
o



="0"><t
o
y><t
><t
 v
lig
="top" wi
th="200"><
 h

f="im
g
s/im
g
7.p
g"><img titl
="im
g
" styl
="
o



-l
ft-wi
th: 0px; 
o



-
ight-wi
th: 0px; 

ckg
ou

-im
g
: 
o

; 
o



-
ottom-wi
th: 0px; p


i
g-top: 0px; p


i
g-l
ft: 0px; 
ispl
y: i
li

; p


i
g-
ight: 0px; 
o



-top-wi
th: 0px" 
o



="0" 
lt="im
g
" s
c="im
g
s/im
g
_thum
7.p
g" wi
th="230" h
ight="133"></
></t
><t
 v
lig
="top" wi
th="200"><
 h

f="https://www.ivo





s.
l/wp-co
t

t/uplo

s/2013/10/im
g
8.p
g"><img titl
="im
g
" styl
="
o



-l
ft-wi
th: 0px; 
o



-
ight-wi
th: 0px; 

ckg
ou

-im
g
: 
o

; 
o



-
ottom-wi
th: 0px; p


i
g-top: 0px; p


i
g-l
ft: 0px; m

gi
: 0px; 
ispl
y: i
li

; p


i
g-
ight: 0px; 
o



-top-wi
th: 0px" 
o



="0" 
lt="im
g
" s
c="im
g
s/im
g
_thum
8.p
g" wi
th="327" h
ight="328"></
></t
></t
></t
o
y></t

l
>


y usi
g s
lf-s

vic
 c
t
logs us

s 

qu
st 


 m


g
 multi-v


o
, multi clou
 
pplic
tio
s.  Th


 


 th


 v

sio
s of vC
C 
v
il

l
: st





, 

v

c

 


 

t

p
is
. 

Fo
 mo

 i
fo
m
tio
 w
tch th
 vClou
 
utom
tio
 C

t

 Ov

vi
w vi

o, [li
k](http://www.VMw


.com/p
o
ucts/vclou
-
utom
tio
-c

t

/
2431280120001).

**VMw


 vC

t

 Op


tio
s M


g
m

t Suit
 5.8**

Th
 

w v

sio
 of th
 vC

t

 Op


tio
s M


g
m

t Suit
 c

 mo
ito
 h
t

og


ous 

vi
o
m

ts.

[![im
g
](im
g
s/im
g
_thum
9.p
g "im
g
")](im
g
s/im
g
9.p
g)

Som
 
x
mpl
s of 

w c
p

iliti
s 


:

- Sto

g
 


lytics such 
s Out Of Th
 
ox (OOT
) 

sh
o


s, physic
l sto

g
 


 H

, f


ic 


 



y visi
ility
- Hyp

-V suppo
t. 
 

sh
o


 with Top 25 (CPU, m
mo
y, 

two
ki
g 


 
isk, IOPS), 

t
sto

 c
p
city 


 p

fo
m

c
 


 lo

 h

tm
ps 
y usi
g SCOM o
 Hyp

ic
- OOT
 

sh
o


 fo
 Mic
osoft SQL 


 
xch

g
 


 suppo
t fo
 Mic
osoft Clust

i
g
- 
m
zo
 
WS suppo
t.



 ov

vi
w of th
 

w 5.8 c
p

iliti
s c

 

 fou

 h


. [Li
k](http://
logs.VMw


.com/m


g
m

t/2013/10/


ou
ci
g-VMw


-vc

t

-op


tio
s-m


g
m

t-suit
-5-8.html)

**VMw


 vC

t

 Log i
sight**

VMw


 vC

t

 Log i
sight 

liv

s 
utom
t

 log m


g
m

t th
ough 
gg

g
tio
, 


lytics 


 s


ch, 



li
g op


tio

l i
t
llig

c
 


 

t

p
is
-wi

 visi
ility i
 
y

mic hy

i
 clou
 

vi
o
m

ts.  VMw


 vC

t

 Log I
sight is th
 VMw


 

sw

 to 
 p
o
uct lik
 [Splu
k](http://www.splu
k.com/).  vC

t

 Log I
sight 1.5 is 


ou
c

.

VMwo
l
 2013 
tt




s 


 p

t


s c

 g
t 5  f


 lic

s
s fo
 VMw


 vC

t

 Log I
sight. [Li
k](http://i
fo.VMw


.com/co
t

t/23713_VMwo
l
_LogI
sight?s
c=&xyz=&ci
=)

**VMw


 IT 
usi

ss M


g
m

t Suit
 (IT
M)**

Th
 VMw


 IT 
usi

ss M


g
m

t Suit
 p
ovi

s t


sp



cy 


 co
t
ol ov

 th
 costs 


 qu
lity of IT s

vic
s, 



li
g CIOs to 
lig
 IT with 
usi

ss p
io
iti
s.  With th
 IT 
usi

ss M


g
m

t (IT
M) optio
 you c

 fo
 
x
mpl
 you c

 comp


 th
 cost clou
 s

vic
 p
ovi


s.

![](im
g
s/
log_IT
M2.p
g)

Th
s
 compo


ts 


 p
o
ucts will fo
m th
 S

C.






