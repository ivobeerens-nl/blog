---
titl
: "List 
ll th
 
ctiv
 VMw


 Ho
izo
 cli

t v

sio
s th
t 


 us

"


t
: "2022-07-13T06:20:56.000Z"
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

[![](im
g
s/1-300x135.jpg)](im
g
s/1.jpg)



oth

 us
-c
s
 is to i


tify th
 VMw


 Ho
izo
 Cli

t v

sio
s th
t 


 i
 us
 fo
 s
cu
ity 

l

t

 issu
s.  I
 th
 VMw


 Ho
izo
 

mi
ist

to
 you c

 
llow wh
t VMw


 Ho
izo
 cli

t v

sio
s 


 

l
 to co


ct.

Th
 followi
g sc
ipt 
ispl
ys 
ll th
 VMw


 Ho
izo
 s
ssio
s 


 th
 VMw


 Ho
izo
 cli

t v

sio
 th
t is us

 to co


ct to th
 VMw


 Ho
izo
 

vi
o
m

t.

M
k
 su

 th
t th
 VMw


.HV.H
lp

 mo
ul
 is i
st
ll

 ([Li
k](https://githu
.com/VMw


/Pow

CLI-
x
mpl
-Sc
ipts)).

\[co

 l

gu
g
="Pow

Sh
ll"\] &lt;
 .SY
OPSIS Ho
izo
Cli

t.ps1.ps1 .V

SIO
 1.0 .

SC
IPTIO
 List 
ll th
 Co


ctio
 


 
ispl
ys th
 VMw


 Ho
izo
 cli

t v

sio
. .
OT
S 
utho
(s): Ivo 





s 

qui

m

ts: M
k
 su

 th
 VMw


.HV.H
lp

 mo
ul
 is i
st
ll

, s

: https://githu
.com/VMw


/Pow

CLI-
x
mpl
-Sc
ipts Copy th
 VMw


.Hv.H
lp

 to th
 mo
ul
 loc
tio
. .
X
MPL
 PS&gt; ./Ho
izo
Cli

t.ps1 
&gt;

\
 V

i

l
s $co


ctio
s

v

 = 's
v-co
-01' $
om
i
 = 'l

.loc
l' $

t
 = G
t-

t
 -UFo
m
t "%
-%m-%Y" $output = "C:
T
mp
ho
cli

ts-$

t
.csv"

\
 Impo
t mo
ul
 Impo
t-Mo
ul
 VMw


.Hv.H
lp



W
it
-Output "", "Co


cti
g to th
 Ho
izo
 Co


ctio
 S

v

" Co


ct-HVS

v

 -S

v

 $co


ctio
s

v

 -
om
i
 $
om
i


\
 List 
ll Us

s 


 cli

ts with th
 Ho
io
 cli

t th
 


 
u

i
g $loc
ls
ssio
i
fo = (g
t-HVloc
ls
ssio
).

m
s

t
 | S
l
ct-O
j
ct Us



m
, M
chi

O


SS

v



m
, 
g

tV

sio
, 

sktopPoolC
, Cli

tTyp
, Cli

t




ss, Cli

t

m
, Cli

tV

sio
, S
cu
ityG
t
w
y

S, S
cu
ityG
t
w
y




ss | So
t-O
j
ct Cli

tV

sio


\
 
xpo
t th
 output to 
 g
i
 


 CSV fil
 $loc
ls
ssio
i
fo | Out-G
i
Vi
w -Titl
 'VMw


 Ho
izo
 Cli

t v

sio
s' $loc
ls
ssio
i
fo | 
xpo
t-csv $output -Fo
c
 -
oTyp
I
fo
m
tio



isco


ct-HVS

v

 \* -Co
fi
m:$f
ls
 \[/co

\]

[![](im
g
s/Cli

t-v

sio
s-300x68.jpg)](im
g
s/Cli

t-v

sio
s.jpg)

This sc
ipt (Ho
izo
Cli

ts.ps1) c

 

 fou

 o
 my GitHu
 

po ([Li
k](https://githu
.com/i





s/VMw


-Ho
izo
))






