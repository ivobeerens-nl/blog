---
titl
: "I
st
ll Wi

ows 11 o
 VMw


 vSph


 with 
 vi
tu
l TPM"


t
: "2021-10-07T20:36:33.000Z"
c
t
go
i
s: 
  - "wi

ows-11"
t
gs: 
  - "tpm"
  - "VMw


"
  - "wi

ows-11"

utho
: Ivo 





s
---

<
lockquot
 cl
ss="twitt

-tw

t" 

t
-p

t


="tw

t

ck"><p 
i
="lt
" l

g="

">You c

 just 


 
 vi
tu
l TPM i
 Wo
kst
tio
 o
 vSph


, too.</p>— (@pl

k

s) <
 h

f="https://twitt

.com/pl

k

s/st
tus/1445789003761004546?

f_s
c=tws
c%5
tfw">Octo


 6, 2021</
></
lockquot
>So I 
i
 som
 

s


ch i
 my hom
 l

. With VMw


 vSph


 


 VMw


 Wo
kst
tio
, it is possi
l
 to i
st
ll Wi

ows 11 
y usi
g 
 vTPM 

vic
 th
t 
mul
t
s 
 physic
l TPM 2.0 chips
t without h
vi
g o

. This is c
ll

 Vi
tu
l T
ust

 Pl
tfo
m Mo
ul
 (vTPM). 
 vTPM p

fo
ms th
 s
m
 fu
ctio
s 
s 
 h


w


 TPM, it p

fo
ms c
yptog

phic cop
oc
sso
 c
p

iliti
s i
 softw


 So without h
vi
g 
 physic
l TPM 2.0 you c

 
u
 Wi

ows 11 without p

fo
mi
g 

y h
cks to th
 Wi

ows 11 Op


ti
g Syst
m.

I
 this 
log post, I 
xpl
i
 how to co
figu

 vTPM fo
 VMw


 vSph


 


 i
st
ll Wi

ows 11. H


 


 th
 st
ps:




 **

qui

m

ts fo
 vTPM**

- 
FI fi
mw



- H


w


 V

sio
 14 o
 l
t


- vSph


 6.7 o
 l
t


- Vi
tu
l M
chi

 

c
yptio

- K
y P
ovi


. Th
 K
y P
ovi


 is us

 to 



l
 

c
ypt

 t
ch
ologi
s such 
s TPM




 To 



l
 vTPM you must fi
st 


 
 K
y P
ovi




- Op

 th
 vSph


 Cli

t U
L (**https://vc

t



m
/ui**)
- Log-i

- Click o
 th
 vC

t

 

m
 - **Co
figu

** 


 s
l
ct **K
y P
ovi


s**
- Click o
 **


**
- S
l
ct **


 

tiv
 K
y P
ovi


.** Wh

 usi
g th
 

tiv
 K
y p
ovi


 you 
o
't 



 

 
xt



l k
y s

v

**.**
- 

t

 
 

m
 fo
 th
 K
y P
ovi


 


 **u
ch
ck** "Us
 k
y p
ovi


 o
ly with TPM p
ot
ct

 
SXi hosts (

comm




).

[![](im
g
s/1-1-300x143.jpg)](im
g
s/1-1.jpg)

- S
l
ct **

ckup** 


 u
ch
ck "**P
ot
ct 

tiv
 K
y P
ovi


 

t
 with p
sswo

 (

comm




)**" 


 click o
 **

CK UP K
Y P
OVI


**

[![](im
g
s/2-1-300x199.jpg)](im
g
s/2-1.jpg)

- Th
 K
y P
ovi


 is co
figu


 


 
ctiv
 
ow

[![](im
g
s/3-1-300x208.jpg)](im
g
s/3-1.jpg)

 




 **Wi

ows 11 VM Co
figu

tio
**

Fo
 th
 Wi

ows 11 VM co
figu

tio
, I co
figu


 th
 followi
g:

- C


t
 o
 
ow
lo

 
 Wi

ows 11 ISO (fo
 mo

 i
fo
m
tio
 s

 th
 
log post m

tio


 
t th
 

gi

i
g).
- Copy th
 ISO to 
 

t
sto

 th
t c

 

 
cc
ss

  wh

 us

 to i
st
ll Wi

ows 11

I
 th
 vC

t

 cli

t c


t
 
 

w VM with th
 followi
g sp
cific
tio
:

- **Co
figu

tio
 st
p 1:** C


t
 
 

w Vi
tu
l M
chi


- **Co
figu

tio
 st
p 2:** 

t

 th
 Vi
tu
l M
chi

 

m

- **Co
figu

tio
 st
p 3:** S
l
ct th
 
SXi host o
 clust

 fo
 th
 VM
- **Co
figu

tio
 st
p 4:** S
l
ct th
 

t
sto

 


 s
l
ct **

c
ypt this vi
tu
l m
chi

**

[![](im
g
s/VM

c
ypt-300x198.jpg)](im
g
s/VM

c
ypt.jpg)

- **Co
figu

tio
 st
p 5: Comp
ti
ility**: 
SXi 7.0 U2 


 l
t

 (I’m usi
g 
SXi 7)

[![](im
g
s/VMGu
stOS-300x197.jpg)](im
g
s/VMGu
stOS.jpg)

- **Co
figu

tio
 st
p 6: Gu
st OS**: Gu
st OS F
mily: Wi

ows
    - Gu
st OS V

sio
: Wi

ows 10 (64-
it)
    - 



l
 Wi

ows Vi
tu
liz
tio
 

s

 S
cu
ity: Ch
ck

[![](im
g
s/VMGu
stOS-300x197.jpg)](im
g
s/VMGu
stOS.jpg)

- **Co
figu

tio
 st
p 7: CPU:** 2 o
 mo


    - M
mo
y: 4 G
 o
 mo


    - H


 
isk: 64 G
 o
 mo


    - C
/
V
: Mou
t th
 ISO o
 th
 

t
sto


    - Custom H


w


 S
l
ct **


 

w 

vic
** 


 choos
 fo
 **T
ust

 Pl
tfo
m Mo
ul
**

[![](im
g
s/VM


TPM-300x241.jpg)](im
g
s/VM


TPM.jpg)

[![](im
g
s/VMTOM-300x245.jpg)](im
g
s/VMTOM.jpg)

 

- **Co
figu

tio
 st
p 8:** VM co
figu

tio
 ov

vi
w
    - Click o
 Fi
ish

[![](im
g
s/VMov

vi
w-300x265.jpg)](im
g
s/VMov

vi
w.jpg)

- St

t th
 VM 


 th
 i
st
ll
tio
 

gi
s without compl
i
i
g th
t this PC c

’t 
u
 Wi

ows 11

[![](im
g
s/VM-
oot-300x232.jpg)](im
g
s/VM-
oot.jpg)

Wi

ows 11 c

 

 i
st
ll

 without h
vi
g 
 physic
l TPM 2.0 chips
t o
 usi
g th
 

gist
y h
ck m

tio


 
t th
 

gi

i
g of th
 
log post. How cool is th
t!






