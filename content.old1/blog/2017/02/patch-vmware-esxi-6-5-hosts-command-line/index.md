---
titl
: "P
tch VMw


 
SXi hosts 
y comm


 li

"


t
: "2017-02-15T20:08:18.000Z"
c
t
go
i
s: 
  - "VMw


"
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

H


 is 
 quick ov

vi
w of how to p
tch 

 
SXi 6.x  o
 7.x host to th
 l
t
st p
tch o
 v

sio
 (f
om 
SXi 6 to 7 fo
 
x
mpl
).

**St
p 1**. 
ow
lo

 th
 l
t
st p
tch 
u

l
 f
om th
 VMw


 W

 sit
, [li
k](https://www.VMw


.com/p
tchmg
/fi

P
tch
y

l

s


m
.po
t
l). VMw


 
SXi p
tch
s 


 cumul
tiv
!  

ch p
tch 
u

l
 (.zip 

chiv
) i
clu

s 
ll th
 up

t
s f
om p
io
 p
tch
s.

[![](im
g
s/1-300x111.p
g)](im
g
s/1.p
g)

**St
p 2**. Uplo

 th
 p
tch 
u

l
 (zip) to 
 (c

t

l) 

t
sto

 with th
 vSph


 Cli

t (p
io
 vSph


 6.5), vSph


 W

 Cli

t, 
SXi host cli

t.

[![](im
g
s/3-300x127.p
g)](im
g
s/3.p
g)

**St
p 3**. 



l
 SSH

I
 th
 vSph


 W

 cli

t st

t th
 SSH s

vic
 


 m
k
 
 SSH s
ssio
 to th
 
SXi host

[![](im
g
s/4-300x131.p
g)](im
g
s/4.p
g)

**St
p 4.** Put th
 host i
 m
i
t



c
 mo



\[co

 l

gu
g
="Pow

Sh
ll"\] vim-cm
 hostsvc/m
i
t



c
\_mo

\_

t

 \[/co

\]

**St
p 5**. I
st
ll th
 p
tch 
u

l


Usi
g 
sxcli with th
 i
st
ll m
tho
 h
s th
 possi
ility of ov

w
iti
g 
xisti
g 

iv

s. If you 


 usi
g thi

-p

ty 
SXi im
g
s, VMw


 

comm


s usi
g th
 **up

t
** m
tho
 to p

v

t 

 u

oot

l
 st
t
. Th
 followi
g comm


 will i
st
ll th
 p
tch 
u


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
 up

t
 -
 /vmfs/volum
s/

t
sto

/p
tch
u

l
.zip \[/co

\]

Fo
 
x
mpl
 i
st
ll HP
 
SXi 6 Up

t
 3:

\[co

 l

gu
g
="Pow

Sh
ll"\] 
sxcli softw


 vi
 up

t
 -
 /vmfs/volum
s/VMFS01/VMw


-
SXi-6.0.0-Up

t
3-5050593-HP
-600.9.7.0.17-F

2017-

pot.zip \[/co

\]


ft

 th
 p
tch 
u

l
 is i
st
ll

 ch
ck th
 m
ss
g
. It must s
y "Th
 up

t
 compl
t

 succ
ssfully, 
ut th
 syst
m 



s to 

 


oot

 fo
 ch

g
s to 

 
ff
ctiv
."

[![](im
g
s/2-300x117.p
g)](im
g
s/2.p
g)

**St
p 6**. 


oot th
 host  
y 

t

i
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


oot \[/co

\]

**St
p 7**. M
k
 
 SSH s
ssio
 to th
 
SXi host 


 
xit m
i
t



c
 mo



\[co

 l

gu
g
="Pow

Sh
ll"\] vim-cm
 hostsvc/m
i
t



c
\_mo

\_
xit \[/co

\]






