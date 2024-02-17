---
titl
: "
ow
lo

 th
 l
t
st H
shico
p T



fo
m, P
ck

, 


 V
ult 
its"


t
: "2023-09-22T07:22:37.000Z"

utho
: Ivo 





s
---

\[co

 l

gu
g
="Pow

Sh
ll"\] <
 .

SC
IPTIO
 Fu
ctio
 to 
ow
lo

 


 
xt

ct th
 l
t
st P
ck

, T



fo
m 


 V
ult v

sio
 f
om H
shico
p .
OT
S 
utho
: Ivo 





s .
OT
S Sit
: www.ivo





s.
l .
OT
S V

sio
: 1.0 .
OT
S Ch

g

: S
pt
m


 10, 2023 .
OT
S 


so
: C


tio
 
>






l
 TLS 1.2 \[

t.S

vic
Poi
tM


g

\]::S
cu
ityP
otocol = \[

t.S
cu
ityP
otocolTyp
\]::Tls12 
Sp


 up th
 I
vok
-W



qu
st comm


 $P
og

ssP

f



c
 = 'Sil

tlyCo
ti
u
'


V

i

l
s $t
mp\_fol


 = "c:
i
st
ll
" 
T
mp 
ow
lo

 loc
tio
 $h
shico
p\_

sti

tio
 = "c:
i
st
ll
h
shico
p
" 
P
th fo
 sto
i
g th
 H
shico
p 
i


i
s


Ch
ck if th
 t
mp fol


 
xists If(!(t
st-p
th -P
thTyp
 co
t
i


 $h
shico
p\_

sti

tio
 )) { 

w-It
m -It
mTyp
 
i

cto
y -P
th $h
shico
p\_

sti

tio
 }


Jump to th
 
ow
lo

 fol


 S
t-Loc
tio
 $h
shico
p\_

sti

tio


Fu
ctio
 
ow
lo

-H
shico
p { p


m ( \[st
i
g\]$p
o
uct, \[st
i
g\]$u
l ) t
y { W
it
-Host "............ 
ow
lo

 $p
o
uct f
om H
shico
p ............" -Fo

g
ou

Colo
 G



 $u
ls = I
vok
-W



qu
st -U
i $u
l| S
l
ct-O
j
ct -
xp


 li
ks | Wh


-O
j
ct h

f -m
tch "//

l

s
s
.h
shico
p
.com/$p
o
uct/

.\*/$p
o
uct\_.\*\_wi

ows\_
m
64
.zip$" | S
l
ct-O
j
ct -
xp


 h

f $fil


m
 = $u
ls | Split-P
th -L

f $
ow
lo

 = $t
mp\_fol


 + $fil


m
 

ow
lo

 H
shico
p 
its I
vok
-W



qu
st $u
ls -outfil
 $
ow
lo

 

xp


 

chiv
 W
it
-Host "............ 
xp


 $p
o
uct 

chiv
 to 
i


y ............" -Fo

g
ou

Colo
 Y
llow 
xp


-

chiv
 $
ow
lo

 -

sti

tio
P
th $h
shico
p\_

sti

tio
 -Fo
c
 W
it
-Host "............ 

mov
 $p
o
uct 

chiv
 
ow
lo

............" -Fo

g
ou

Colo
 
lu
 


mov
 
ow
lo

 

mov
-It
m $
ow
lo

 } c
tch { W
it
-Host "

 


o
 occu



 whil
 
ow
lo

i
g o
 
xt

cti
g $p
o
uct" -Fo

g
ou

Colo
 


 th
ow $\_.
xc
ptio
.M
ss
g
 } }



ow
lo

 P
ck

, V
ult, 


 T



fo
m $p
o
ucts = @{ 'p
ck

' = 'https://

v
lop

.h
shico
p.com/p
ck

/
ow
lo

s' 'v
ult' = 'https://

v
lop

.h
shico
p.com/v
ult/
ow
lo

s' 't



fo
m' = 'https://

v
lop

.h
shico
p.com/t



fo
m/
ow
lo

s' }

fo


ch ($p
o
uct i
 $p
o
ucts.G
t

um


to
()) { 
ow
lo

-H
shico
p -p
o
uct $p
o
uct.

m
 -u
l $p
o
uct.V
lu
 }






 th
 H
shico
p 
i


y fol


 to th
 syst
m 

vi
o
m

t v

i

l
 p
th W
it
-Host "............ 


 fol


 to p
th ............" -Fo

g
ou

Colo
 G



 \[

vi
o
m

t\]::S
t

vi
o
m

tV

i

l
("P
TH", $

v:P
TH + ";" + $h
shico
p\_

sti

tio
, \[

vi
o
m

tV

i

l
T

g
t\]::Us

) W
it
-Host "Pl

s
 

st

t you
 Pow

Sh
ll s
ssio
 fo
 th
 ch

g
s to t
k
 
ff
ct." -Fo

g
ou

Colo
 Y
llow \[/co

\]

**Li

 15**: Ch

g
 th
 t
mp fol


 fo
 sto
i
g th
 
ow
lo



 

chiv
 fil
s **Li

 16:** Ch

g
 th
 fol


 p
th fo
 sto
i
g th
 H
shico
p 
i


i
s fo
 T



fo
m, P
ck

, 


 V
ult **Li

 19-22:** Ch
ck if th
 fol


 fo
 sto
i
g th
 H
shico
p 
i


i
s fo
 T



fo
m, P
ck

, 


 V
ult 
xists. If 
ot it will 

 c


t

 **Li

 24-50**: Fu
ctio
 th
t 
ow
lo

s 


 
xt

cts th
 

chiv
 fil
s fo
 T



fo
m, P
ck

, 


 V
ult **Li

 52-61**: 
u
 th
 fu
ctio
 to 
ow
lo

 


 
xt

ct th
 H
shico
p T



fo
m, P
ck

, 


 V
ult **Li

 63-66**: 


s th
 fol


 of th
 H
shico
p 
i


i
s to th
 p
th 

vi
o
m

t v

i

l


Th
 l
t
st v

sio
 of this sc
ipt c

 

 fou

 o
 my GitHu
 p
g
, [Li
k.](https://githu
.com/i





s/Pow

Sh
ll/
lo
/m
st

/H
shico
p-
ow
lo

s.ps1)






