---
titl
: "VMw


 
SXi 

p




cy 


o
 wh

 t
yi
g to up

t
"


t
: "2019-01-09T10:17:31.000Z"
t
gs: 
  - "up

t
-2"
  - "VMw


"

utho
: Ivo 





s
---

> \[

p




cy


o
\] VI
 VMw


\_
oot


k\_
sx-

s
\_6.7.0-1.28.10302608 

qui

s 
sx-up

t
 << 6.7.0-1.29, 
ut th
 

qui

m

t c


ot 

 s
tisfi

 withi
 th
 Im
g
P
ofil
. VI
 VMw


\_
oot


k\_
sx-

s
\_6.7.0-1.28.10302608 

qui

s 
sx-up

t
 >= 6.7.0-1.28, 
ut th
 

qui

m

t c


ot 

 s
tisfi

 withi
 th
 Im
g
P
ofil
. Pl

s
 

f

 to th
 log fil
 fo
 mo

 

t
ils.

[![](im
g
s/fout-1024x61.p
g)](im
g
s/fout.p
g)

Wh

 s


chi
g 

ou

 it looks lik
 th


 


 mo

 p
opl
 who 
xp

i

ci
g this p
o
l
m ([li
k](https://commu
ity.spic
wo
ks.com/topic/2170328-VMw


-

p



cy-


o
-10302608)) wh

 t
yi
g to up

t
 to 6.7U1. Usi
g th
s
 st
ps I w
s 

l
 to up

t
 th
 
SXi 6.7 host f
om 
uil
 9484548 to th
 l
t
st v

sio
 (10764712) :

- SSH to th
 
SXi host
- Put th
 
SXi host i
 M
i
t



c
 Mo




sxcli syst
m m
i
t



c
Mo

 s
t --



l
 t
u


- Op

 th
 
SXi fi

w
ll fo
 HTTP t

ffic. Th
 
SXi host must h
v
 i
t



t 
cc
ss.


sxcli 

two
k fi

w
ll 
ul
s
t s
t -
 t
u
 -
 httpCli

t

- Fi

 th
 l
t
st 
SXi 

l

s
 

m
 i
 th
 VMw


 
uil
 
um


s ov

vi
w, [li
k](https://k
.VMw


.com/s/

ticl
/2143832?l

g=

_US). Wh

 w
iti
g this 
log post th
 l
t
st 

l

s
 

m
/p
tch is "
SXi670-201811001" which h
s 
uil
 
um


 10764712.

[![](im
g
s/v

sio
s-300x62.p
g)](im
g
s/v

sio
s.p
g)

- Th
 VMw


 p
tch 

pot co
t
i
s 
 hug
 list of 
uil
s, to m
k
 it 

si

 filt

 


 fi

 th
 
ight p
ofil
 usi
g th
 followi
g comm


:


sxcli softw


 sou
c
s p
ofil
 list -
 https://hostup

t
.VMw


.com/softw


/VUM/P
O
UCTIO
/m
i
/vmw-

pot-i


x.xml | g

p 
SXi-6.7.0-201811

- This 

sults i
 two p
ofil
s:


SXi-6.7.0-20181104001-
o-tools VMw


, I
c. P

t


Suppo
t

 2018-11-08T08:39:18 2018-11-08T08:39:18

SXi-6.7.0-20181104001-st





 VMw


, I
c. P

t


Suppo
t

 2018-11-08T08:39:18 2018-11-08T08:39:18

- Up

t
 th
 host 
y 


i
g th
 "
SXi-6.7.0-20181104001-st





" p
ofil
 


 poi
t to to th
 VMw


 p
tch 

pot usi
g this comm


:


sxcli softw


 p
ofil
 up

t
 -p 
SXi-6.7.0-20181104001-st





 -
 https://hostup

t
.VMw


.com/softw


/VUM/P
O
UCTIO
/m
i
/vmw-

pot-i


x.xml

- Ch
ck if th
 up

t
 compl
t

 succ
ssfully

[![](im
g
s/up

t
h


m
tig-300x108.p
g)](im
g
s/up

t
h


m
tig.p
g)

- 
is

l
 th
 HTTP cli

t i
 th
 
SXi fi

w
ll


sxcli 

two
k fi

w
ll 
ul
s
t s
t -
 f
ls
 -
 httpCli

t

- 


oot th
 
SXi hosts




oot

- Wh

 th
 
SXi hosts is 


oot

 
xit m
i
t



c
 mo

 
y usi
g SSH

vim-cm
 hostsvc/m
i
t



c
\_mo

\_
xit

- Ch
ck th
 up

t
 compl
t

 succ
ssfully

VMw


 -v

Wh

 
ll th
 st
ps 


 succ
ssfully th
 
uil
 v

sio
 of VMw


 
SXi 6.7.0 is 10764712.






