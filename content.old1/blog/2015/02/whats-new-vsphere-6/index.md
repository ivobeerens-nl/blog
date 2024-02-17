---
titl
: "Wh
t's 

w i
 vSph


 6?"


t
: "2015-02-02T21:05:24.000Z"
c
t
go
i
s: 
  - "vSph


6"
t
gs: 
  - "VMw


"
  - "vSph


6"

utho
: Ivo 





s
---

**Sc
l

ility**

- vSph


 Clust

s: Up to 64 
o

s 


 6000 VMs
- Hosts: 480 physic
l CPUs, 12 T
 

M, 64 T
 

t
sto

s, 1000 VMs  


 32 s

i
l po
ts. vGPU 
vi
i
 suppo
t
- VMs: Up to 128 vCPUs 


 4 T
 v

M

[![m
ximums](im
g
s/m
ximums-300x171.p
g)](im
g
s/m
ximums.p
g)

**vC

t

 S

v

**

- Pl
tfo
m S

vic
s Co
t
oll

 (PSC)**.** Th
 Pl
tfo
m S

vic
s Co
t
oll

 (PSC) co
t
i
s commo
 I
f

st
uctu

 S

vic
s such 
s:
    - Si
gl
 Sig
-O

    - Lic

si
g
    - C

tific
t
 
utho
ity
    - C

tific
t
 Sto


    - S

vic
 (P
o
uct) 

gist

tio

    - Oth

 futu

 s

vic
s
    - PSC is 
 c

t

l p

t th
t is us

 fo
 
x
mpl
 
y vCou
 Suit
 p

ts such 
s vC

t

, v


liz
 Op


tio
s, 
tc.). Fo
 most 

vi
o
m

ts (8 o
 l
ss vC

t

 S

v

s) 
 vC

t

 S

v

 with 1 
m





 PSC is suffici

t.
- 

h

c

 Li
k Mo

 (
LM). 

h

c

 Li
k Mo

 (
LM) will suppo
t Wi

ows 


 vCS
 

ploym

ts 


 

qui

 
 Pl
tfo
m S

vic
s Co
t
oll

 (PSC).
- Mic
osoft Clust

i
g suppo
t fo
 vC

t

 S

v

. vC

t

 S

v

 6.0 will suppo
t th
 clust

i
g of th
 vC

t

 S

v

 i
 


itio
 to th
 

ck


 

t


s
.
- vC

t

 S

v

 
ppi

c
 (vCS
):
    - ISO fil
 th
t co
t
i
s 
 gui


 i
st
ll


    - 
m





 vPostg

s 

t


s
. 
s 
xt



l 

t


s
 O

cl
 is suppo
t

.
    - 

h

c

 Li
k

 mo

 suppo
t
    - V
P suppo
t fo
 

ckup 


 

cov

y of th
 vCS

    - Mo

 i
fo
m
tio
 c

 

 fou

 i
 this 
log post, [li
k](https://www.ivo





s.
l/2015/02/02/wh
ts-

w-vSph


-6-vc

t

-s

v

-
ppli

c
-vcs
/)

 **Sto

g
**

- Sto

g
 I/O Co
t
ol (SIOC).  P

 VM sto

g
 

s

v
tio

- 
FS 4.1 with K




os suppo
t. 
FS cli

t suppo
t fo
 
FS 4.1
- Vi
tu
l Volum
s (VVols) 


 Sto

g
 Policy-

s

 M


g
m

t. 



l
s VM-
w


 sto

g
. VVOl is off



 
y sto

g
 v


o
s such 
s 

t
pp, 

ll, Pu

Sto

g
, 
MC, 
im
l
sto

g
, I
M 


 Ti
t
i
- Vi
tu
l S

 (VS

) 6 co
t
i
s th
 followi
g imp
ov
m

ts:
    - Sc
l

ility imp
ov
m

ts such 
s:
    - [![vs

](im
g
s/vs

-300x149.p
g)](im
g
s/vs

.p
g)
    - 

w O
-
isk fo
m
t fo
 high

 p

fo
m

c
, 
ffici

t 


 sc
l

l
 high p

fo
m

c
 s

pshots 


 clo

s.
    - 
ll fl
sh suppo
t
    - Us

ility imp
ov
m

ts i
 W

 Cli

t such 
s:
        - Sto

g
 co
sumptio
 i
fo
m
tio

        - 

sy
c st
tus i
fo
m
tio

    - F
ilu

 
om
i
s. 
llow g
oupi
g of hosts i
to 
iff



t logic
l f
ilu

 zo

s. This 

su

s 

plic
s f
om 
 VM 


 
ot p
ovisio


 o
to th
 s
m
 logic
l f
ilu

 zo

. F
ilu

 
om
i
s 


 
o m
t
o/st

tch

 clust

s! F
ilu

 
om
i
s is 
lso k
ow
 
s 

ck 
w




ss.
    - 
isks s

vic


ility. M
p th
 loc
tio
 of 
 m
g

tic o
 fl
sh 

vic
 f
om th
 W

 Cli

t o
 f
ilu

s, SS
, loc
l 
tc.
    - VS

 is sol
 
s s
p


t
 p
o
uct 


 
ot i
clu


 i
 th
 lic

s
!

**
v
il

ility**

- 64 
o

 clust

 suppo
t 


 6000 VMs
- VMw


 VM Compo


t P
ot
ctio
 (VMCP)
- vMotio
 
c
oss vC

t

 S

v

s.
- vMotio
 
c
oss vi
tu
l (
ist
i
ut

) switch
s
    - 
o 



 of sh



 vMotio
 is 






- Lo
g-
ist

c
 vMotio
 up to 100ms 
TTs
    - 



fits: P

m



t mig

tio
s 

tw


 

t
 c

t

s
    - 
is
st

 
voi


c
 (

)
    - S
M/

 t
sti
g
    - Multi-sit
 lo

 

l

ci
g
- F
ult Tol



c
 (FT) i
c


s
 suppo
t fo
 1, 2 


 4 vCPU VMs
- I
t
g

tio
 with vClou
 
i
 (

plic
tio
 


 

ckup)
- vSph


 

plic
tio
. 5 mi
s i
c

m

ts (5.5 w
s 15 mi
ut
s) 


 2000k 

plic
t

 VMs p

 vC

t


- 
pp H
. Suppo
t fo
 mo

 
usi

ss c
itic
l 
pplic
tio
s

**

two
k**

- 

two
k I/O Co
t
ol (
IOC)**.** P

 VM 


 
ist
i
ut

 Switch 



wi
th 

s

v
tio


**M


g
m

t**

- vSph


 W

 Cli

t 

h

c
m

ts such 
s 

tt

 p

fo
m

c
 


 t
ggi
g imp
ov
m

ts. Th
 W

 Cli

t still us
s fl
sh!

[![2015-02-02_16h41_00](im
g
s/2015-02-02_16h41_00-1024x587.p
g)](im
g
s/2015-02-02_16h41_00.p
g)

- Th
 vSph


 Cli

t C
 is still 
v
il

l
 i
 this 

l

s
. 
o 

w f

tu

s 


 i
 this 

l

s
. H


w


 v

sio
s 9 to 11 f

tu

s 


 



-o
ly o
 u

v
il

l
 i
 th
 vSph


 Cli

t C
.
- Multi-Sit
 Co
t

t Li



y. Sto

s 


 sy
c VMs, T
mpl
t
s, OVFs, ISOs 


 sc
ipts f
om o

 c

t

l loc
tio
 


 sy
c th
 co
t

t 
c
oss oth

 vC

t

 S

v

s (sit
s)
- vSph


 6 h
s suppo
t fo
 H


w


 V

sio
 11. M
i
 imp
ov
m

ts of H


w


 V

sio
 11 


:
    - M
ximum vi

o m
mo
y up to 2 G
 (512 M
 i
 H


w


 V

sio
  10)
    - PCI p
sst
ough 16 

vic
s (6 i
 H


w


 V

sio
  10)
    - 32 s

i
l po
ts (4 i
 i
 H


w


 V

sio
  10)






