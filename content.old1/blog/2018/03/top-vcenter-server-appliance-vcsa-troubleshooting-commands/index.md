---
titl
: "Top vC

t

 S

v

 
ppli

c
 (VCS
) t
ou
l
shooti
g comm


s"


t
: "2018-03-06T14:17:31.000Z"
c
t
go
i
s: 
  - "VMw


"
t
gs: 
  - "vcs
"

utho
: Ivo 





s
---

- 



l
 
cc
ss th
 

sh sh
ll:

\[co

 l

gu
g
="t
xt"\] sh
ll.s
t --



l

 t
u
 \[/co

\]

- P

m



tly co
figu

 th
 

f
ult Sh
ll to 

SH fo
 
oot:

\[co

 l

gu
g
="t
xt"\] chsh -s /
i
/

sh 
oot \[/co

\]

- Log loc
tio
 of th
 VCS
:

\[co

 l

gu
g
="t
xt"\] /v

/log/VMw


/vSph


-cli

t/logs/ \[/co

\]

- VCS
 s

vic
 m


g
m

t:

\[co

 l

gu
g
="t
xt"\] Ch
ck st
tus s

vic
-co
t
ol --st
tus --
ll List s

vic
s s

vic
-co
t
ol --list Stop 
ll s

vic
s s

vic
-co
t
ol --stop --
ll St

t 
ll s

vic
s s

vic
-co
t
ol --st

t --
ll \[/co

\]

- Joi
 th
 

 
om
i
 f
om PSC:

\[co

 l

gu
g
="t
xt"\] /opt/lik
wis
/
i
/
om
i
joi
-cli joi
 
om
i
.
l 

us

 p
sswo

 \[/co

\]


ft

 th
 

 
om
i
 joi
 


oot th
 
ppli

c


- Ch
ck th
 

 
om
i
 joi
 st
tus:

\[co

 l

gu
g
="t
xt"\] /opt/lik
wis
/
i
/
om
i
joi
-cli qu

y \[/co

\]

- L

v
 

 
om
i
 joi
:

\[co

 l

gu
g
="t
xt"\] /opt/lik
wis
/
i
/
om
i
joi
-cli l

v
 \[/co

\]


ft

 th
 

 
om
i
 l

v
 


oot th
 
ppli

c


- C

tific
t
 M


g

 loc
tio
:

\[co

 l

gu
g
="t
xt"\] /us
/li
/VMw


-vmc
/
i
/c

tific
t
-m


g

 \[/co

\]

- T
st po
t co


ctivity f
om th
 VCS
:

\[co

 l

gu
g
="t
xt"\] cu
l -v t
l

t://t

g
t ip 




ss:po
t 
x
mpl
: cu
l –v t
l

t://mypsc.
om
i
.loc
l:443 \[/co

\]

- I


tity which PSC th
 VCS
 is poi
ti
g to:

\[co

 l

gu
g
="t
xt"\] /us
/li
/VMw


-vm
f
/
i
/vm
f
-cli g
t-ls-loc
tio
 --s

v

-

m
 loc
lhost \[/co

\]

- 

poi
t th
 VCS
 to 

oth

 PSC:

\[co

 l

gu
g
="t
xt"\] cmsso-util 

poi
t --

poi
t-psc "PSC01" \[/co

\]

- Ch
ck th
 PSC 

plic
tio
 p

t


:

\[co

 l

gu
g
="t
xt"\] /us
/li
/VMw


-vm
i
/
i
/v
c

p

mi
 -f showp

t


s -h loc
lhost -u 

mi
ist

to
 -w p
sswo

 \[/co

\]

- Ch
ck th
 PSC 

plic
tio
 st
tus:

\[co

 l

gu
g
="t
xt"\] /us
/li
/VMw


-vm
i
/
i
/v
c

p

mi
 -f showp

t


st
tus -h loc
lhost -u 

mi
ist

to
 -w p
sswo

 \[/co

\]

Output:

\[co

 l

gu
g
="t
xt"\] P

t


: psc02 Host 
v
il

l
: Y
s St
tus 
v
il

l
: Y
s My l
st ch

g
 
um


: 4274 P

t


 h
s s


 my ch

g
 
um


: 4274 P

t


 is 0 ch

g
s 

hi

. \[/co

\]

- V
C 

mi
 tool t
st L

P 


 fo
c
 

plic
tio


\[co

 l

gu
g
="t
xt"\] /us
/li
/VMw


-vm
i
/
i
/v
c

mi
tool \[/co

\]






