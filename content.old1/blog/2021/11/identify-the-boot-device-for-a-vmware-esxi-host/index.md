---
titl
: "I


tify th
 
oot 

vic
 fo
 
 VMw


 
SXi host"


t
: "2021-11-26T08:31:16.000Z"
c
t
go
i
s: 
  - "vSph


-7"
t
gs: 
  - "
oot"
  - "s
-c


"
  - "vSph


-7"
cov

Im
g
: "
oot

vic
.jpg"

utho
: Ivo 





s
---

Mov
 f
om S
 c


s 


 US
 

vic
s to loc
l p

sist

t 
isk(s) such 
s S
T
, S
S (i
clu
i
g S
T

OM), SS
 
isks 
s 
 
oot 

vic
 fo
 
x
mpl
. Th
 mi
imum 
isk siz
 is 32 G
, th
 

comm




 siz
 is 128 G
. 

oth

 optio
 is to us
 
oot f
om S

.

Mo

 i
fo
m
tio
 c

 

 fou

 h


 [li
k](https://k
.VMw


.com/s/

ticl
/85685).

Th
 g




l suppo
t p

io
 fo
 vSph


 6.7 will 


 o
 **Octo


 15, 2022.** So m
k
 su

 to upg



 

fo

 Octo


 15, 2022, to VMw


 vSph


 7.

To i


tify wh
t 
oot m

i
 (
o
s 
ot wo
k fo
 
oot f
om S

)  is us

 I c


t

 
 Pow

CLI sc
ipt th
t i


tifi
s th
 
oot 

vic
 fo
 
v

y VMw


 
SXi host i
 
 clust

. 
ft

 

t

i
g th
 vC

t

 S

v

 


 c




ti
ls it will list 
ll th
 clust

s 
v
il

l
 i
 th
 vC

t

 

vi
o
m

t, s
l
ct th
 clust

 


 th
 
oot 

vic
 p

 VMw


 
SXi host will 

 i


tifi

.

\[co

 l

gu
g
="Pow

Sh
ll"\] <
 .SY
OPSIS This sc
ipt list th
 
oot 

vic
 fo
 
v

y VMw


 
SXi host .

SC
IPTIO
 VMw


 is movi
g 
w
y f
om th
 suppo
t of S
 c


s 


 US
 

iv
s 
s 
oot m

i
. 
SXi 
oot co
figu

tio
 with o
ly S
 c


 o
 US
 

iv
, without 

y p

sist

t 

vic
, is 

p

c
t

 with vSph


 7 Up

t
 3. I
 futu

 vSph


 

l

s
s, it will 

 

 u
suppo
t

 co
figu

tio
. Mo

 i
fo
m
tio
: https://
logs.VMw


.com/vSph


/2021/09/
sxi-7-
oot-m

i
-co
si



tio
-VMw


-t
ch
ic
l-gui


c
.html .
OT
S V

sio
: 1.0 
utho
: Ivo 





s C


tio
 

t
: 2021 
ov
m


 Ch

g
: C


tio
 
>

\
 Impo
t th
 Pow

CLI mo
ul
 Impo
t-Mo
ul
 VMw


.Pow

CLI

\
 V

i

l
s $

t
fil
 = ( g
t-

t
 ).ToSt
i
g('yyyy-MM-

-hhmmss') $fil
 = 

w-It
m -typ
 fil
 "C:
T
mp

oot

vic
s$

t
fil
.csv" $vc

t

s

v

 = 



-Host "

t

 th
 vC

t

 s

v

 

m
"

\
 Co


ct to th
 vC

t

 S

v

 Co


ct-VIS

v

 $vc

t

s

v



$clust

 = G
t-Clust

 | Out-G
i
Vi
w -Titl
 "S
l
ct th
 clust

" -OutputMo

 Si
gl
 $
llhosts = $clust

 | G
t-VMHost | wh


 {$\_.Co


ctio
St
t
 -
q "Co


ct

"}

$

sult = @()

fo


ch ($
llhost i
 $
llhosts) { $
sxcli = G
t-
sxCli -V2 -VMHost $
llhost $

sult += $
sxcli.sto

g
.co

.

vic
.list.i
vok
() | Wh


 {$\_.Is
oot

vic
 -m
tch "t
u
"} | S
l
ct @{
="Clust

";
={$clust

.

m
}},@{
="VMhost";
={$
llhost.

m
}}, V


o
, Mo

l, Is
oot

vic
, IsLoc
l, IsS
S, IsSS
, IsUS
, 

vic
 }

\
 
ispl
y th
 output $

sult | FT

\
 
xpo
t th
 output to 
 CSV fil
 $

sult | 
xpo
t-Csv $fil
 -
oTyp
I
fo
m
tio
 -Fo
c


\
 
isco


ct th
 vC

t

 s

v

 s
ssio
 
isco


ct-VIs

v

 -Co
fi
m:$f
ls
 \[/co

\]

Th
 output will 

 
ispl
y

 o
 th
 sc



 


 s
v

 to 
 CSV fil
.

[![](im
g
s/
oot

vic
-300x45.jpg)](im
g
s/
oot

vic
.jpg)

This sc
ipt m
k
s it 

sy to i


tify th
 
oot 

vic
s of 
v

y VMw


 
SXi host i
 
 clust

.






