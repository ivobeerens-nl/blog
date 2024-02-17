---
titl
: "vMotio
 

tw


 two vC

t

 S

v

s with 
iff



t SSO 
om
i
s"


t
: "2017-10-11T07:15:22.000Z"
t
gs: 
  - "pow

cli"
  - "vSph


"

utho
: Ivo 





s
---



fo

 st

ti
g th
 followi
g 

qui

m

ts must 

 m
t:

- VMw


 vSph


 6.0 


 l
t

 fo
 th
 sou
c
 


 

sti

tio
 

vi
o
m

t
- Pow

CLI 6.5 


 l
t


- vSph


 

t

p
is
 Plus lic

s
 p

 
SXi host
- 

 
ctiv
 co


ctio
 to th
 sou
c
 


 

sti

tio
  vC

t

 S

v



I c


t

 
 simpl
 sc
ipt to vMotio
 th
 VMs 

tw


 th
 two SSO 
om
i
s. S

 th
 mo

 i
fo
m
tio
 s
ctio
 fo
 mo

 

v

c

 Pow

CLI sc
ipts f
om fo
 
x
mpl
 Willi
m L
m 


 
om
i
 

ck

.

I
 th
 sc
ipt th
 followi
g v

i

l
s must 

 

fi


:

- Sou
c
 vC

t

 S

v

, us



m
 


 p
sswo


- 

sti

tio
 vC

t

 S

v

, us



m
 


 p
sswo


- VM 

m
 will 

 mov


- 

sti

tio
 vSwitch
- 

sti

tio
 Po
tg
oup
- 

sti

tio
 

t
sto



O
ly VMs with o

 
IC 


 suppo
t



Pow

CLI 
x
mpl
 sc
ipt

\[co

 l

gu
g
="Pow

Sh
ll"\] Impo
t-Mo
ul
 VMw


.Pow

CLI 
V

i

l
s $sou
c
VC = 'sou
c
vc' $sou
c
VCUs



m
 = '

mi
ist

to
@vSph


.loc
l' $sou
c
VCP
sswo

= 'p
sswo

!' $

stVC = '

sti

tio
vc' $

stVCUs



m
 = '

mi
ist

to
@vSph


.loc
l' $

stVCP
sswo

= 'p
sswo

' $

st
SXi = '

sti

tio

sxi' $vm

m
 = 'vm

m
' $Switch

m
 = '

sti

tio
switch' $

two
k

m
 = '

sti

tio
vl

' $

t
sto



m
 = '

sti

tio


t
sto

' 
 Co


ct to th
 vC

t

 S

v

s $sou
c
VCCo

 = Co


ct-VIS

v

 -S

v

 $sou
c
VC -us

 $sou
c
VCUs



m
 -p
sswo

 $sou
c
VCP
sswo

 $

stVCCo

 = Co


ct-VIS

v

 -S

v

 $

stVC -us

 $

stVCUs



m
 -p
sswo

 $

stVCP
sswo

 $vm = G
t-VM $vm

m
 -S

v

 $sou
c
VCCo

 $

two
k


pt

 = G
t-

two
k


pt

 -VM $vm -S

v

 $sou
c
VCCo

 $

sti

tio
 = G
t-VMHost -

m
 $

st
SXi -S

v

 $

stVCCo

 $

sti

tio
Po
tG
oup = G
t-Vi
tu
lPo
tG
oup -Vi
tu
lSwitch $Switch

m
 -

m
 $

two
k

m
 -VMHost $

sti

tio
 $

sti

tio


t
sto

 = G
t-

t
sto

 -

m
 $

t
sto



m
 -S

v

 $

stVCCo

 Mov
-VM -VM $vm -

sti

tio
 $

sti

tio
 -

two
k


pt

 $

two
k


pt

 -Po
tG
oup $

sti

tio
Po
tG
oup -

t
sto

 $

sti

tio


t
sto

 \[/co

\]

With this sc
ipt I mig

t

 
 coupl
 of VMs 

tw


 to vSph


 6.5 

vi
o
m

t with 
iff



t SSO 
om
i
s without 

y 
ow
tim
.

Mo

 i
fo
m
tio
:

- Pow

CLI 
log o
 th
 Mov
-VM cm
l
t, [li
k](https://
logs.VMw


.com/Pow

CLI/2017/01/spotlight-mov
-vm-cm
l
t.html)
- Willi
m L
m, 
utom
tio
 C
oss vC

t

 vMotio
, [li
k](http://www.vi
tu
llygh
tto.com/2016/05/
utom
ti
g-c
oss-vc

t

-vmotio
-xvc-vmotio
-

tw


-th
-s
m
-
iff



t-sso-
om
i
.html)
- 
om
i
 

ck

 C
oss vMotio
 sc
ipt f
om, [li
k](https://githu
.com/clou
m

i
c/C
oss-SSO_vMotio
)






