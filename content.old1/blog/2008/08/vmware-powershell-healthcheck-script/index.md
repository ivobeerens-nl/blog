---

utho
: Ivo 





s
titl
: "VMw


 Pow

Sh
ll H

lthch
ck sc
ipt"


t
: "2008-08-28T12:57:27.000Z"
c
t
go
i
s: 
  - "VMw


"
t
gs: 
  - "VMw


"
  - Pow

Sh
ll
  - 
utom
tio

u
l: /2008/08/28/VMw


-Pow

Sh
ll-h

lthch
ck-sc
ipt/
---

H

lthch
ck is 
 Pow

Sh
ll sc
ipt th
t 

po
ts i
fo
m
tio
 lik
 **s

pshots**, **VMw


 tools v

sio
**, **

t
sto

 sp
c
, C

OM 


/o
 floppy 

iv
s co


ct

** 
tc. to HTML 


 
-m
il th
 output to 
 p

so
 o
 
ist
i
utio
 list.

**


so
 fo
 c


ti
g this sc
ipt:**


s VMw


 Co
sult

t I s

 
 lot of commo
 p
o
l
ms i
 VMw


 

vi
o
m

ts lik
:
- S

pshots 


 



l

 


 fo
got
- 

t
sto

s 


 
lmost full (fo
 
x
mpl
 if s

pshots 


 



l

)
- VMw


 tools v

sio
s 


 
iff



t
- C

OM 


 floppy 

iv
s 


 still mou
t

 to th
 VM
- Vi
tu
l M
chi

s h
v
 CPU 


 M
mo
y limits o
 

s

v
tio
s (VMs 


 sw
ppi
g)
- I
 th
 VM, th
 VMw


 Tools tim
sy
c optio
 is 
ot 



l



I
 th
 Vi
tu
l I
f

st
uctu

 Cli

t (VIC) it is 
ifficult to s

 this so
t of i
fo
m
tio
. 
y c


ti
g 
 Pow

Sh
ll sc
ipt,  I c

 
o 
 quick i
v

to
y.  I
 
 lot of VMw


 

vi
o
m

ts I c


t

 
 sch

ul

 t
sks, so th
 sc
ipt 
u
s o
c
 
 w

k 


 s

t to HTML 

ppo
t to th
 

mi
ist

to
.

**Wh
t 
o
s th
 sc
ipt:**

I w
ot
 
 Pow

Sh
ll sc
ipt with H
LP f
om th
 VMT
 commu
ity th
t m
k
s 
 HTML fil
 


 s

t th
 output 
y 
-m
il to 
 p

so
 o
 
ist
i
utio
 list. Th
 H

lthch
ck sc
ipt 
o
s th
 followi
g ch
cks:
- VMw


 
SX h


w



- VMw


 
SX v

sio
s
- VMw


 Vi
tu
lC

t

 v

sio
s
- 
ctiv
 s

pshots
- C

OM 


 Floppy 

iv
(s) mou
t

 to th
 VM
- 

t
sto

 i
fo
m
tio
 lik
 c
p
city, f


 sp
c
 


 th
 p

c

t
g
 f


 sp
c

- Vi
tu
lM
chi

 (VM) i
fo
m
tio
 lik
 VMw


 tools v

sio
, CPU, M
mo
y 

s

v
tio
s 


 limits 
tc.
- O
 wh
t VMs VMw


 Tools tim
sy
c is 
ot 



l



**

qui

m

ts:**

Th
 followi
g softw


 must 

 i
st
ll

:
- Mic
osoft Pow

Sh
ll 5.1
- VMw


 I
f

stuctu

 (VI) toolkit fo
 Wi

ows 1.0 [http://www.VMw


.com/
ow
lo

/s
k/](http://www.VMw


.com/
ow
lo

/s
k/)
- S
t th
 
x
cutio
Policy i
 Wi

ows Pow

Sh
ll to 

mot
Sig


 
y usi
g th
 followi
g comm


:
**s
t-
x
cutio
Policy 

mot
Sig


**

**I
st
ll
tio
:**
- U
zip th
 H

lthch
ck.zip sc
ipt to 
 
i

cto
y o
 th
 VC s

v

 fo
 
x
mpl
.
- Wh

 th
 ZIP if u
p
ck

 th


 


 two fil
s:
- H

lthch
ck.ps1, this is th
 Pow

Sh
ll sc
ipt
- Styl
.CSS, co
t
ols th
 HTML l
yout

**Co
figu

tio
:**

- 

it th
 Pow

Sh
ll.ps1 fil
, 

it th
 followi
g v

i

l
s:
```Pow

Sh
ll
$vcs

v

="loc
lhost"


t

 th
 VC s

v

, if you 
x
cut
 th
 sc
ipt o
 th
 VC s

v

 you c

 us
 th
 loc
lhost 

m

$fil
loc
tio
="
:
t
mp
H

lthch
ck.htm" Sp
cify th
 loc
tio
 wh


 to sto

 th
 HTML output
$



l
m
il="y
s" 



l
 (y
s) o
 
is

l
 (
o) to s

t th
 sc
ipt 
y 
-m
il
$smtpS

v

 = "m
il.ivo





s.
l" Sp
cify th
 SMTP s

v

 i
 you
 

two
k
$m
ilf
om = "VMw


 H

ltch
ck <[Pow

Sh
ll@ivo





s.
l](m
ilto:Pow

Sh
ll@ivo





s.
l)\>" Sp
cify th
 f
om fi
l

$m
ilto = [ivo@ivo





s.
l](m
ilto:ivo@ivo





s.
l)
Sp
cify th
 




ss wh


 th
 
-m
il to s

t  to
```

**Us
g
:**

M

u
lly 
u
 th
 H

lthch
ck.ps1 sc
ipt":

1. Op

 Pow

Sh
ll

2. 

ows
 to th
 
i

cto
y wh


 th
 H

lthch
ck.ps1 sc
ipt 

si

s

3. 

t

 th
 comm


:
```Pow

Sh
ll
./H

lthch
ck.ps1
```
To c


t
 
 sch

ul
 t
sk i
 fo
 
x
mpl
 Wi

ows 2003 us
 th
 followi
g sy
t
x i
 th
 
u
 p
op

ty: Pow

Sh
ll -comm


 "& 'p
th\H

lthch
ck.ps1' 

it th
 p
th
```Pow

Sh
ll
Pow

Sh
ll -comm


 "& 'p
th\H

lthch
ck.ps1'
```


it th
 p
th .

**Futu

:**

- List O
ph



 VM
K's
- 


 p

fo
m

c
 i
fo
m
tio
 lik
 VM us
g

- Ch
ck tim
sy
c o
 th
 VMw


 hosts

H
ppy t
sti
g :-)


ow
lo

 Li
k: H

lthch
ck sc
ipt

Th
 sc
ipt is post

 o
 th
 VMw


 Pow

Sh
ll co
t
st fo
um, [li
k](http://commu
iti
s.VMw


.com/m
ss
g
/1036432)

Som
 sc



shots of th
 HTML output:

[![1JPG](im
g
s/1jpg-thum
.jpg)](im
g
s/1jpg.jpg)

 [![2](im
g
s/2-thum
.jpg)](im
g
s/2.jpg)

[![3](im
g
s/3-thum
.jpg)](im
g
s/3.jpg)






