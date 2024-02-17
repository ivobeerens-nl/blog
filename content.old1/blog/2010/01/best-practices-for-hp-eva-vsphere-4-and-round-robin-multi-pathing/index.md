---
titl
: "

st p

ctic
s fo
 HP 
V
, vSph


 4 


 
ou

 
o
i
 multi-p
thi
g"


t
: "2010-01-19T10:47:58.000Z"
c
t
go
i
s: 
  - "

st-p

ctic
s"
  - "hp-
v
"
  - "multi-p
thi
g"
  - "
ou

-
o
i
"
  - "vSph


"
t
gs: 
  - "hp-
v
"
  - "multi-p
thi
g"
  - "
ou

-
o
i
"

utho
: Ivo 





s
---

Th
 VMw


 vSph


 


 th
 HP 
V
 4x00, 6x00 


 8x00 s

i
s 


 
LU
 compli

t. 
LU
 compli

t m


s i
 simpl
 wo

s th
t it is 
ot 





 to m

u
lly i


tify p

f




 I/O p
ths 

tw


 VMw


 
SX hosts 


 th
 sto

g
 co
t
oll

s.

Wh

 you c


t
 
 

w V
isk o
 th
 HP 
V
 th
 LU
 is s
t 

f
ult s
t to 
o P

f



c
. Th
 
o P

f



c
 policy m


s th
 followi
g:
- Co
t
oll

 ow


ship is 
o
-

t

mi
istic. Th
 u
it ow


ship is 
lt



t

 

tw


 co
t
oll

s 
u
i
g i
iti
l p

s

t
tio
 o
 wh

 co
t
oll

s 


 

st

t


    
- O
 co
t
oll

 f
ilov

 (ow
i
g co
t
oll

 f
ils), th
 u
its 


 ow


 
y th
 su
vivi
g co
t
oll


    
- O
 co
t
oll

 f
il

ck (p

vious ow
i
g co
t
oll

 

tu

s), th
 u
its 

m
i
 o
 th
 su
vivi
g co
t
oll

. 
o f
il

ck occu
s u
l
ss 
xplicitly t
igg



.
    

To g
t 
 goo
 
ist
i
utio
 

tw


 th
 co
t
oll

s th
 followi
g V
isk polici
s c

 

 us

:

<t

l
 
o



="0" c
llsp
ci
g="0" c
llp


i
g="2" wi
th="400"><t
o
y><t
><t
 v
lig
="top" wi
th="200"><p 
lig
="l
ft"><st
o
g><sp

 styl
="colo
: 
000000"><fo
t siz
="2">&

sp;</fo
t></sp

></st
o
g><sp

 styl
="colo
: 
000000"><fo
t siz
="2"><st
o
g>P
th 
-F
ilov

/f
il

ck</st
o
g></fo
t></sp

></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– 
t p

s

t
tio
, th
 u
its 


 

ought o
li

 to co
t
oll

 
</fo
t></sp

></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– O
 co
t
oll

 f
ilov

, th
 u
its 


 ow


 
y th
 su
vivi
g co
t
oll

 (
)</fo
t></sp

></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– O
 co
t
oll

 f
il

ck, th
 u
its 


 

ought o
li

 o
 co
t
oll

 
 implicitly.</fo
t></sp

></p></t
><t
 v
lig
="top" wi
th="200"><p 
lig
="l
ft"><sp

 styl
="colo
: 
000000"><fo
t siz
="2">&

sp;</fo
t></sp

><st
o
g><sp

 styl
="colo
: 
000000"><fo
t siz
="2">P
th 
-F
ilov

/f
il

ck</fo
t></sp

></st
o
g></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– 
t p

s

t
tio
, th
 u
its 


 

ought o
li

 to co
t
oll

 
</fo
t></sp

></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– O
 co
t
oll

 f
ilov

, th
 u
its 


 ow


 
y su
vivi
g co
t
oll

 (
)</fo
t></sp

></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– O
 co
t
oll

 f
il

ck, th
 u
its 


 

ought o
li

 o
 co
t
oll

 
 implicitly.</fo
t></sp

></p></t
></t
></t
o
y></t

l
>

O
 th
 HP 
V
 h
lf of th
 V
isks 


 s
t o
 p
th 
-F
ilov

/f
il

ck 


 th
 oth

 h
lf  of th
 V
isks 


 s
t to 
-F
ilov

/f
il

ck, so th
t th
y 
lt



t
 

tw


 co
t
oll

 
 


 
. This c

 

 
o

 f
om th
 HP 
V
 comm


 vi
w.  
ow th
 v
isk 


 
ist
i
ut

 

tw


 th
 two co
t
oll

s w
 c

 go to th
 vSph


 co
figu

tio
. O
 
v

y vSph


 host p

fo
m 

 

sc

 o
 


oot.

I
 VMw


 vSph


 th
 Most 

c

tly Us

 (M
U) 


 
ou

 
o
i
 (

) multi-p
thi
g polici
s 


 
LU
 compli

t. 
ou

 
o
i
 lo

 

l

ci
g is 
ow offici
lly suppo
t

.  Th
s
 multi-p
th polici
s h
v
 th
 followi
g ch


ct

istics:

<t

l
 
o



="0" c
llsp
ci
g="0" c
llp


i
g="2" wi
th="400"><t
o
y><t
><t
 v
lig
="top" wi
th="200"><sp

 styl
="fo
t-siz
: x-sm
ll"><sp

 styl
="fo
t-siz
: x-sm
ll"><fo
t siz
="2"><st
o
g><sp

 styl
="colo
: 
000000">M
U:</sp

></st
o
g></fo
t><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– Will giv
 p

f



c
 to 

 optim
l p
th to th
 LU
</fo
t></sp

></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– Wh

 
ll optim
l p
ths 


 u

v
il

l
, it will us
 
 
o
-optim
l p
th</fo
t></sp

></p><p><sp

 styl
="fo
t-siz
: sm
ll"><sp

 styl
="fo
t-siz
: sm
ll">&

sp;</sp

></sp

><sp

 styl
="fo
t-siz
: x-sm
ll"><sp

 styl
="fo
t-siz
: x-sm
ll"><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– Wh

 

 optim
l p
th 

com
s 
v
il

l
, it will f
ilov

 to th
 optim
l</fo
t></sp

></sp

></sp

></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2">– 
lthough 

ch 
SX s

v

 m
y us
 
 
iff



t po
t th
ough th
 optim
l co
t
oll

 to th
 LU
, o
ly 
 si
gl
 co
t
oll

 po
t is us

 fo
 LU
 
cc
ss p

 
SX s

v

</fo
t></sp

></p><p><fo
t siz
="2"></fo
t></p><p><fo
t siz
="2"></fo
t></p></sp

></sp

></t
><t
 v
lig
="top" wi
th="200"><p><sp

 styl
="colo
: 
000000; fo
t-siz
: x-sm
ll"><fo
t siz
="2">&

sp;<st
o
g>
ou

 
o
i
:</st
o
g></fo
t></sp

></p><p><sp

 styl
="colo
: 
000000; fo
t-siz
: x-sm
ll"></sp

><sp

 styl
="colo
: 
000000; fo
t-siz
: x-sm
ll"><fo
t siz
="2">– Will qu
u
 I/O to LU
s o
 
ll po
ts of th
 ow
i
g co
t
oll

s i
 
 
ou

 
o
i
 f
shio
 p
ovi
i
g i
st

t 



wi
th imp
ov
m

t</fo
t></sp

></p><p><sp

 styl
="colo
: 
000000; fo
t-siz
: x-sm
ll"><fo
t siz
="2">– Will co
ti
u
 qu
ui
g I/O i
 
 
ou

 
o
i
 f
shio
 to optim
l co
t
oll

 po
ts u
til 
o

 


 
v
il

l
 


 will f
ilov

 to th
 
o
-optim
l p
ths</fo
t></sp

></p><p><sp

 styl
="colo
: 
000000; fo
t-siz
: x-sm
ll"><fo
t siz
="2">– O
c
 

 optim
l p
th 

tu

s it will f
il

ck to it</fo
t></sp

></p><p><sp

 styl
="colo
: 
000000"><fo
t siz
="2"><sp

 styl
="fo
t-siz
: x-sm
ll">– <fo
t siz
="2">C

 

 co
figu


 to 
ou

 
o
i
 I/O to 
ll co
t
oll

 po
ts fo
 
 LU
 
y ig
o
i
g optim
l p
th p

f



c
. (M
y 

 suit

l
 fo
 
 w
it
 i
t

siv
 

vi
o
m

t 
u
 to i
c


s

 co
t
oll

 po
t 



wi
th)</fo
t></sp

></fo
t></sp

></p></t
></t
></t
o
y></t

l
>

Th
 fix

 multi-p
th policy is 
ot 
LU
 compli

t 


 th


fo

 
ot 

comm


 to us
.

I
 vSph


 4 th


 is 

w multi-p
thi
g f

m
wo
k. Th


 


 th


 co

 compo


ts:

- 

tiv
 Multi-p
thi
g Plugi
 (
MP), h


l
s th
 multi-p
thi
g co
figu

tio
, commu
ic
t
s with th
 S
TP 


 PSP to i



tify p
th f
ilu

 co

itio
s.

- Sto

g
 



y Typ
 Plugi
 (S
TP), h


l
s sp
cific op


tio
s such 
s 

vic
 
iscov

y, 


o
 co

s 


 f
ilov

.

- P
th S
l
ctio
 Plugi
 (PSP), h


l
s th
 

st 
v
il

l
 p
th, th


 


 th


 polici
s fix

, M
U 


 
ou

 
o
i
.

PSP 


 s
t p

 LU
, m


i
g th
t it is possi
l
 to h
v
 som
 LU
s us
 M
U 


 oth

 us
 
ou

 
o
i
 policy. 

st p

ctic
 f
om HP is to ch

g
 to PSP f
om M
U to 
ou

 
o
i
 w
 us
 th
 followi
g comm


 i
 th
 S

vic
 Co
sol
:


sxcli 
mp s
tp s
t

f
ultpsp --s
tp VMW\_S
TP\_
LU
 --psp VMW\_PSP\_





oth

 

st p

ctic
 is to s
t th
 IOPS (

f
ult th
 IOPS v
lu
 is 1000) with 
 v
lu
 of 1 (co
t
ols how m

y IOs 


 s

t 
ow
 
 giv

 p
th 

fo

 vSph


 st

ts to us
 th
 

xt p
th) fo
 
v

y LU
 
y usi
g th
 followi
g comm


:

fo
 i i
 \`ls /vmfs/

vic
s/
isks/ | g

p 


.600\` ; 


o 
sxcli 
mp 
ou


o
i
 s
tco
fig --typ
 "iops" --iops\=1 --

vic
 $i ;
o




ut th


 is 
 
ug wh

 


ooti
g th
 VMw


 
SX s

v

, th
 IOPS v
lu
 

v

t

 to 
 



om v
lu
. Mo

 i
fo
m
tio
 c

 

 fou

 o
 th
 [Vi
tu
l G

k](http://vi
tu
lg

k.typ
p

.com/vi
tu
l_g

k/2009/12/vSph


-4-
mp-

-ioop


tio
slimit-
ug-


-wo
k

ou

.html) 
log f
om Ch

 S
k
c. To ch
ck th
 IOPS v
lu
s o
 
ll LU
s us
 th
 followi
g comm


:

fo
 i i
 \`ls /vmfs/

vic
s/
isks/ | g

p 


.600\` ; 


o 
sxcli 
mp 
ou


o
i
 g
tco
fig --

vic
 $i ;
o



[![im
g
](im
g
s/im
g
4_thum
.p
g "im
g
")](im
g
s/im
g
4.p
g)

  
To solv
 this IOPS 
ug, 

it th
 /
tc/
c.loc
l fil
 o
 
v

y VMw


 
SX host 


 


 


 th
  IOPS=1 comm


. Th
 
c.loc
l fil
 
x
cut
 
ft

 
ll i
it sc
ipts 


 
x
cut

.

[](im
g
s/clip_im
g
0025.jpg)[![clip_im
g
002[5]](im
g
s/clip_im
g
0025_thum
1.jpg "clip_im
g
002[5]")](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2012/01/clip_im
g
00251.jpg)


ft

 


i
g th
 IOPS=1 comm


 

st

t th
 VMw


 
SX host 


 ch
ck th
 IOPS v
lu
s wh

 its 

ck o
li

.

[![clip_im
g
002[7]](im
g
s/clip_im
g
0027_thum
.jpg "clip_im
g
002[7]")](im
g
s/clip_im
g
0027.jpg)


ow you c

 ch
ck if th
 th
 
ou

 
o
i
 policy is 
ctiv
 


 th
 LU
s 


 sp



 ov

 th
 two co
t
oll

s.

<t

l
 
o



="0" c
llsp
ci
g="0" c
llp


i
g="2" wi
th="400"><t
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
s/clip_im
g
002.jpg"><sp

 styl
="colo
: 
000000"><img styl
="
o



-
ight-wi
th: 0px; 
ispl
y: i
li

; 
o



-top-wi
th: 0px; 
o



-
ottom-wi
th: 0px; 
o



-l
ft-wi
th: 0px" titl
="clip_im
g
002" 
o



="0" 
lt="clip_im
g
002" s
c="im
g
s/clip_im
g
002_thum
.jpg" wi
th="244" h
ight="179"></sp

></
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

s/2010/01/clip_im
g
0024.jpg"><sp

 styl
="colo
: 
000000"><img styl
="
o



-
ight-wi
th: 0px; 
ispl
y: i
li

; 
o



-top-wi
th: 0px; 
o



-
ottom-wi
th: 0px; 
o



-l
ft-wi
th: 0px" titl
="clip_im
g
002[4]" 
o



="0" 
lt="clip_im
g
002[4]" s
c="im
g
s/clip_im
g
0024_thum
.jpg" wi
th="244" h
ight="177"></sp

></
></t
></t
></t
o
y></t

l
>

H


 


 som
 g


t Pow

CLI o

-li


s c


t

 
y [Luc 

k

s](http://luc
.i
fo/). Th

ks fo
 c


ti
g so quickly th
s
 o

-li


s fo
 m
!

<t

l
 
o



="0" c
llsp
ci
g="0" c
llp


i
g="2" wi
th="645"><t
o
y><t
><t
 v
lig
="top" wi
th="643"><sp

 styl
="colo
: 
000000; fo
t-siz
: x-sm
ll"><fo
t siz
="2">S
t th
 multi-p
th policy to 
ou

 
o
i
 fo
 
ll hosts:</fo
t></sp

><
iv></
iv><

><
iv></
iv><

><
iv></
iv><p

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">G
t-VMHost</sp

><sp

 styl
="colo
: 
000000">|</sp

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">G
t-ScsiLu
</sp

><sp

 styl
="colo
: 
000000"> </sp

><sp

 styl
="fo
t-styl
: it
lic; colo
: 
5f9

0">-Lu
Typ
</sp

><sp

 styl
="colo
: 
000000"> </sp

><sp

 styl
="colo
: 
800000">"</sp

><sp

 styl
="colo
: 
800000">
isk</sp

><sp

 styl
="colo
: 
800000">"</sp

><sp

 styl
="colo
: 
000000">|</sp

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">wh


</sp

><sp

 styl
="colo
: 
000000"> {</sp

><sp

 styl
="colo
: 
800080">$_</sp

><sp

 styl
="colo
: 
000000">.Multip
thPolicy –</sp

><sp

 styl
="colo
: 
ff0000">

</sp

><sp

 styl
="colo
: 
000000"> </sp

></p

><
iv></
iv><p

><sp

 styl
="colo
: 
000000"></sp

><sp

 styl
="colo
: 
800000">"</sp

><sp

 styl
="colo
: 
800000">
ou


o
i
</sp

><sp

 styl
="colo
: 
800000">"</sp

><sp

 styl
="colo
: 
000000">}|</sp

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">S
t-ScsiLu
</sp

><sp

 styl
="colo
: 
000000"> </sp

><sp

 styl
="fo
t-styl
: it
lic; colo
: 
5f9

0">-Multip
thPolicy</sp

><sp

 styl
="colo
: 
000000"> </sp

><sp

 styl
="colo
: 
800000">"</sp

><sp

 styl
="colo
: 
800000">
ou


o
i
</sp

><sp

 styl
="colo
: 
800000">"</sp

><sp

 styl
="colo
: 
000000"> </sp

></p

><
iv></
iv><p><sp

 styl
="colo
: 
000000"><fo
t f
c
="

i
l">G
t th
 multi-p
th policy fo
 o

 host:</fo
t></sp

></p><
iv></
iv><p

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">G
t-VMHost</sp

><sp

 styl
="colo
: 
000000"> &lt;
SX

m
&gt; | </sp

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">G
t-ScsiLu
</sp

><sp

 styl
="colo
: 
000000"> | </sp

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">S
l
ct</sp

><sp

 styl
="colo
: 
000000"> C

o
ic
l

m
, </sp

><sp

 styl
="colo
: 
800000">MultiP
thPolicy</sp

></p

><
iv></
iv><p styl
="m

gi
: 0cm 0cm 0pt" cl
ss="Mso
o
m
l"><sp

 styl
="colo
: 
000000">&

sp;</sp

><sp

 styl
="colo
: 
000000"><fo
t f
c
="

i
l">G
t th
 multi-p
th policy fo
 
ll th
 hosts:</fo
t></sp

></p><
iv></
iv><p styl
="m

gi
: 0cm 0cm 0pt" cl
ss="Mso
o
m
l"><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
"></sp

></p><
iv></
iv><p

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">G
t-VMHost</sp

><sp

 styl
="colo
: 
000000"> | </sp

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">%</sp

><sp

 styl
="colo
: 
000000">{</sp

><sp

 styl
="colo
: 
800080">$_</sp

><sp

 styl
="colo
: 
000000">.

m
; </sp

><sp

 styl
="colo
: 
800080">$_</sp

><sp

 styl
="colo
: 
000000"> | </sp

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">G
t-ScsiLu
</sp

><sp

 styl
="colo
: 
000000"> | </sp

><sp

 styl
="colo
: 
5f9

0; fo
t-w
ight: 
ol
">S
l
ct</sp

><sp

 styl
="colo
: 
000000"> C

o
ic
l

m
, </sp

><sp

 styl
="colo
: 
800000">MultiP
thPolicy</sp

><sp

 styl
="colo
: 
000000">}</sp

></p

><
iv></
iv></t
></t
></t
o
y></t

l
>

\[








\]

sou
c
: Co
figu

tio
 

st p

ctic
s fo
 HP Sto

g
Wo
ks 

t

p
is
 Vi
tu
l 



y (
V
) f
mily 


 VMw


 vSph


 4






