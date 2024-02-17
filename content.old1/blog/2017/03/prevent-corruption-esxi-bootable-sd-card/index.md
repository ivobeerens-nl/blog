---
titl
: "P

v

t co

uptio
 of th
 
SXi 
oot

l
 S
 c


"


t
: "2017-03-14T14:55:14.000Z"
c
t
go
i
s: 
  - "
sxi"
t
gs: 
  - "
sxi-2"
  - "VMw


"

utho
: Ivo 





s
---

To 
ctiv
t
 this f

tu

 th
 followi
g 

v

c

 s
tti
gs must 

 ch

g

 o
 

ch 
SXi host:

- S
t th
 

v

c

 Tools

m
isk optio
 to 1 
y usi
g this comm


:
    
    \[co

 l

gu
g
="t
xt"\]
sxcli syst
m s
tti
gs 

v

c

 s
t -o /Us

V

s/Tools

m
isk -i 1 \[/co

\]
    
- 
ft

 ch

gi
g th
 s
tti
g 


oot th
 host.

I c


t

 
 simpl
 Pow

CLI sc
ipt th
t s
ts th
 

v

c

 s
tti
g \`tools

m
isk\` v
lu
 to '1' o
 
ll th
 
SXi hosts.

\[co

 l

gu
g
="Pow

Sh
ll"\] <
 
utho
 : Ivo 





s 
log : www.ivo





s.
l Twitt

 : @i





s P

-

quisit
 : 
SXi 6.0 U3 S
t : S
t Us

V

s.Tools

m
isk to th
 v
lu
 1 
>

G
t-Mo
ul
 -List
v
il

l
 VMw


\* | Impo
t-Mo
ul
 Co


ct-VIS

v

 Fo


ch ($vmhost i
 G
t-VMHost | wh


 {$\_.Co


ctio
St
t
 -
q "Co


ct

"}) { W
it
-Host "Host: $($vmhost.

m
)" -Fo

g
ou

Colo
 G



 G
t-

v

c

S
tti
g -

tity $vmhost -

m
 Us

V

s.Tools

m
isk | S
t-

v

c

S
tti
g -V
lu
 ‘1’ -Co
fi
m:$f
ls
 } \[/co

\]


ft

 
u

i
g this sc
ipt 
ll th
 
SXi hosts must 

 


oot

. **Mo

 i
fo
m
tio
**: VMw


 K
: High f

qu

cy of 



 op


tio
s o
 VMw


 Tools im
g
 m
y c
us
 S
 c


 co

uptio
 (2149257), [Li
k](https://k
.VMw


.com/s
lfs

vic
/mic
osit
s/s


ch.
o?cm
=
ispl
yKC&
ocTyp
=kc&
xt



lI
=2149257&slic
I
=1&
ocTyp
I
=
T_K
_1_1&
i
logI
=355414078&st
t
I
=1%200%20355416185)






