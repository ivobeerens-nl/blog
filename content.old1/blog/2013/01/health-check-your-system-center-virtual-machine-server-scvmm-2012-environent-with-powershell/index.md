---
titl
: "H

lth Ch
ck you
 Syst
m C

t

 Vi
tu
l M
chi

 S

v

 (SCVMM) 2012 

vi
o


t with Pow

Sh
ll"


t
: "2013-01-28T10:07:16.000Z"
c
t
go
i
s: 
  - "hyp

-v"
  - "Pow

Sh
ll"
  - "scvmm"
t
gs: 
  - "hyp

-v-2"
  - "Pow

Sh
ll"
  - "scvmm"

utho
: Ivo 





s
---

I 
u
 th
 Pow

Sh
ll sc
ipt  f
om 

oth

 Wi

ows S

v

 2012 host. To m
k
 this wo
k m
k
 su

 th
 Hyp

-V m


g

 


 th
 VMM Co
sol
 is i
st
ll

 o
 th
 s

v

. Th
 VMM co
sol
 c

 

 i
st
ll

 f
om th
 Mic
osoft Syst
m C

t

 2012 Vi
tu
l M
chi

 M


g

 ISO.

Th
 output is 
ispl
y

 o
 th
 sc



 


 
xpo
t

 to 
 HTML fil
. Th
 followi
g i
fo
m
tio
 is g




t

:

**Host i
fo
m
tio
:**

Clust

 it 

lo
gs, host 

m
, CPU cou
t, co

 cou
t, CPU sp


, CPU mo

l, m
mo
y, op


ti
g Syst
m, 


 VM hostg
oup

**VM i
fo
m
tio
:**

VM 

m
, comput

 

m
, host th
 VM is o
, CPU cou
t, CPU typ
, m
mo
y, if 
y

mic M
mo
y is 



l

, Op


ti
g Syst
m, If i
t
g

tio
 tools 


 i
st
ll

, i
t
g

tio
 tool v

sio
, VM st
tus, 

plic
tio
 St
tus 


 VM loc
tio


**VM s

pshot i
fo
m
tio
:**

VM 

m
, 

m
 of th
 s

pshot, 

sc
iptio
, tim
 




 


 mo
ifi

 tim


H


 is 

 
x
mpl
 how th
 output looks lik
:

[![im
g
](im
g
s/im
g
_thum
8.p
g "im
g
")](im
g
s/im
g
8.p
g)

Th
 o
ly p


m
t

 th
t 



s to 

 ch

g

 is th
 **$Fil
** v

i

l
 th
t sp
cify th
 loc
tio
 w


 th
 HTML fil
 is sto


.

**Pow

Sh
ll sc
ipt:**

<

.SY
OPSIS Syst
m C

t

 Vi
tu
l M
chi

 M


g

 H

lthch
ck .V

SIO
 1.0 .

SC
IPTIO
 G




t
s 
 HTML H

lthch
ck 

po
t .
OT
S 
utho
(s): Ivo 





s .
X
MPL
 PS\> ./scvmmhc.ps1 
> \
 Impo
t mo
ul
s Impo
t-Mo
ul
 -

m
 "Hyp

-v" Impo
t-Mo
ul
 -

m
 "Vi
tu
lM
chi

M


g

" 
V

i

l
s $

t
 \= G
t-

t
 $

t
fil
 \= ( g
t-

t
 ).ToSt
i
g('yyyy-MM-

-hhmmss') $Fil
 \= 

w-It
m -typ
 fil
 "
:
T
mp
H

ltch
ck\_$

t
fil
.html" 
Co


ct to th
 SCVMM s

v

 Cl


 $VMM

m
 \= 



-Host "

t

 Syst
m C

t

 Vi
tu
l M
chi

 S

v

 

m
 to ch
ck" W
it
-Host "VMM 

m
 is $VMM

m
" -Fo

G
ou

 


 G
t-VMMS

v

 -Comput



m
 $VMM

m
 
HTML

 


 T
xt to th
 HTML fil
  Fu
ctio
 C


t
-HTMLT

l

 { p


m(\[



y\]$



y) $


HTML \= $



y | Co
v

tTo-Html $


HTML\[-1\] \= $


HTML\[-1\].ToSt
i
g().

pl
c
('</
o
y></html>',"") 

tu

 $


HTML\[5..2000\]
    } $output \= @() $output += '<html><h


></h


><
o
y>' $output += '<styl
\>t

l
{
o



-styl
:soli
;
o



-wi
th:1px;fo
t-siz
:8pt;

ckg
ou

-colo
:
ccc;wi
th:100%;}th{t
xt-
lig
:l
ft;}t
{

ckg
ou

-colo
:
fff;wi
th:20%;
o



-styl
:so li
;
o



-wi
th:1px;}
o
y{fo
t-f
mily:v





;fo
t-siz
:12pt;}h1{fo
t-siz
:12pt;}h2{fo
t-siz
:10pt;}</styl
\>' $output += '<h1>Hyp

-V h

lth ch
ck</h1>' $output += '<h1>V

si
 1.0</h1>' $output += '<h2>

t
 


 tim
</h2>',$

t
 \
 Hosts $HVHosts \= G
t-VMHost | S
l
ct HostClust

,

m
,Physic
lCPUCou
t,Co

sP

CPU,P
oc
sso
M

uf
ctu


,CPUSp


,CPUMo

l,@{
\="M
mo
y(G
)";
\={\[m
th\]::
ou

((($\_.Tot
lM
mo
y)/1G
),3)}},Op


ti
gSyst
m,



l
Liv
Mig

tio
,VMHostG
oup $output += '<p>' $output += '<h1>Hosts</h1>' $output += '<p>' $output += C


t
-HTMLT

l
 $HVHosts $output += '</p>' \
 VM $VMs \= G
t-VM | S
l
ct 

m
,Comput



m
,Host

m
,CPUCou
t,CpuTyp
,M
mo
y
ssig


M
,
y

micM
mo
y



l

,Op


ti
gSyst
m,H
sVM


itio
s,VM


itio
,Vi
tu
lM
chi

St
t
,St
tus,

plic
tio
St
tus,Loc
tio
 $output += '<p>' $output += '<h1>VMs</h1>' $output += '<p>' $output += C


t
-HTMLT

l
 $VMs $output += '</p>' \
 S

pshots $VMS

ps \= G
t-VM | G
t-VMCh
ckpoi
t | S
l
ct VM,

m
,

sc
iptio
,




Tim
,Mo
ifi

Tim
 $output += '<p>' $output += '<h1>S

pshots</h1>' $output += '<p>' $output += C


t
-HTMLT

l
 $VMS

ps $output += '</p>' \
 


 $output += '</
o
y></html>' $output | Out-Fil
 $fil
 -Fo
c
 \
 Op

 th
 HTML fil
 ii $fil


Th
 sc
ipt c

 

 

sily 
xt




 with oth

 ch
cks, fo
 
x
mpl
 

 
-m
il optio
. If you h
v
 oth

 


itio
s l
t m
 k
ow so th
 sc
ipt c

 

 
xt




.






