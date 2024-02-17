---
titl
: "VMw


 
SX Post i
st
ll
tio
 co
figu

tio
 vi
 Pow

CLI"


t
: "2010-02-10T14:36:55.000Z"
c
t
go
i
s: 
  - "pow

cli"
  - "Pow

Sh
ll"
t
gs: 
  - "co
figu

tio
"
  - "post-co
fig"
  - "pow

cli"
  - "Pow

Sh
ll"

utho
: Ivo 





s
---

- - Co


ct to VMw


 
SX s

v


    
- - S
t th
 SC m
mo
y to 800M

    
- - C


t
s vSwitch2 


 


 vm
ic2 


 vm
ic3
    
- - 


 s
v


l Po
tG
oups 


 VL

s to vSwitch2
    
- - 

mov
 

f
ult Po
tG
oup VM 

two
k
    
- - C


t
s 
 VMk



l VMotio
 po
t with IP 




ss, su


tm
sk 


 VL


    
- - 


 vm
ic0 


 vm
ic1 to vSwitch0, s
t fo
 th
 VMotio
 po
t vm
ic1 
ctiv
 


 vm
ic0 st



y 


 fo
 th
 S

vic
 Co
sol
 po
t vm
ic0 
ctiv
 


 vm
ic1 st



y
    
- - Co
figu

 
TP s

v

s 


 op

 th
 fi

w
ll
    
- - S
ts 

v

c

 s
tti
gs 
isk.Us


vic


s
t to 0 


 
isk.Us
LU


s
t  to 1
    
- - S
ts h
 Qlogic H

 qu
u
 

pth 


 th
 
isk.Sch


um

qOutst


ig to 64
    
- - 



l
 VMhost St

tup 


 stop
    

H


’s th
 listi
g of th
 sc
ipt:  


 Titl
: VMw


 
SX4 Post co
fig 
  

 Fil


m
:    
sx4postco
fig.sp1 
   

 C


t

 
y: Ivo 





s 
   

 

t
: F


u

y 2010 
   

 V

sio
: 1.0 
  

 W

sit
: www.ivo





s.
l 
   

 
-m
il: ivo\[
T\]ivo





s.
l 
   
  

 V

i

l
s 
  

 vC

t

 

m
 


 po
t 
  
$vcs

v

 \= "vc01"  
$po
tvc \= "443"  

S

vic
 Co
sol
 m
mo
y 
  
$SCM
mo
y \= 800  

 

f
ult Po
tG
oup 
  
$

f
ultPG \= G
t-Vi
tu
lPo
tg
oup -

m
 'VM 

two
k'  

 VMotio
 IP, su


tm
sk 


 VL

  
$VMotio
IP \= “172.16.1.50“  
$VMotio
Su


t = “255.255.0.0“  
$VMotio
VL

 ="3"  
\
 H

 Qu
u
 

pth 
  
$H

qu
u

pth = 64  
\
 vSwitch 

m
s 
  
$Switch1 ="vSwitch0"  
$Switch2 ="vSwitch2"  
  
Co


ct-VIS

v

 $vcs

v

 -Us

 
oot -P
sswo

 i
o
tk
ow -po
t $po
tvc  
  
\
 S
t SC m
mo
y to 800M
 
  
G
t-VMHost | G
t-Vi
w | %{(G
t-Vi
w -I
 $\_.Co
figM


g

.M
mo
yM


g

).

co
figu

S

vic
Co
sol


s

v
tio
($SCM
mo
y\*1m
)}  
  
\
 C


t
 vSwitch1 


 


 vm
ic2 


 vm
ic3 
  


w-Vi
tu
lSwitch -

m
 $Switch2 -
ic vm
ic2,vm
ic3  
  
\
 


 Po
tG
oups 


 VL

s  to th
 vSwitch2 
  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

999 M


g
m

t" -VL

I
 999  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

100 S

v

s" -VL

I
 100  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

99 Cli

ts S

-
" -VL

I
 99  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

98 Cli

ts S

-
" -VL

I
 98  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

33 S
cu

 L

" -VL

I
 33  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

32 
MZ3" -VL

I
 32  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

31 
MZ1" -VL

I
 31  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

30 
MZ0" -VL

I
 30  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

7 VOiP" -VL

I
 7  
g
t-vmhost | G
t-Vi
tu
lSwitch -

m
 $Switch2 | 

w-Vi
tu
lPo
tG
oup -

m
"VL

1 

f
ult"\
 

mov
 

f
ult Po
t G
oup 
ft

 

f
ult i
st
ll
tio
 
  


mov
-Vi
tu
lPo
tG
oup -Vi
tu
lPo
tG
oup $

f
ultPG -Co
fi
m:$f
ls
  
  
\
 C


t
s 
 VMk



l po
t VMotio
 o
 vSwitch0 
  


w-VMHost

two
k


pt

 -Po
tG
oup “VMotio
“ -Vi
tu
lSwitch $Switch1 -IP $VMotio
IP -Su


tM
sk $VMotio
Su


t -VMotio




l

:$t
u
  
  
\
 S
t VL

 of th
 VMotio
 VMk



l 
  
$VMotio
PG = G
t-Vi
tu
lPo
tg
oup -

m
 'VMotio
'  
S
t-Vi
tu
lPo
tG
oup -Vi
tu
lPo
tG
oup $VMotio
PG -Vl

I
 $VMotio
VL

  
  
\
 


 vm
ic0 


 vm
ic1 to vSwitch0 
  
$vs = g
t-vi
tu
lswitch -

m
 $Switch0  
S
t-Vi
tu
lSwitch -Vi
tu
lSwitch $vs -
ic vm
ic0,vm
ic1  
  
\
 S
t VMotio
 vm
ic1 
ctiv
 vm
ic0 st



y 
  
g
t-vi
tu
lpo
tg
oup -

m
 VMotio
 | G
t-
icT

mi
gPolicy | S
t-
icT

mi
gPolicy -M
k

ic
ctiv
 vm
ic1  
g
t-vi
tu
lpo
tg
oup -

m
 VMotio
 | G
t-
icT

mi
gPolicy | S
t-
icT

mi
gPolicy -M
k

icSt



y vm
ic0  
  
\
 S
t S

vic
 Co
sol
 vm
ic0 
ctiv
, vm
ic1 st



y 
  
g
t-vi
tu
lpo
tg
oup -

m
 'S

vic
 Co
sol
' | G
t-
icT

mi
gPolicy | S
t-
icT

mi
gPolicy -M
k

ic
ctiv
 vm
ic0  
g
t-vi
tu
lpo
tg
oup -

m
 'S

vic
 Co
sol
' | G
t-
icT

mi
gPolicy | S
t-
icT

mi
gPolicy -M
k

icSt



y vm
ic1  
  
\
 Co
figu

s 
TP, 


 
TP s

v

s, st

ts 
TP 


 op

 th
 fi

w
ll po
t 
  



-VmHost
tpS

v

 -
tpS

v

 "0.VMw


.pool.
tp.o
g"


-VmHost
tpS

v

 -
tpS

v

 "1.VMw


.pool.
tp.o
g"


-VmHost
tpS

v

 -
tpS

v

 "2.VMw


.pool.
tp.o
g"G
t-vmhostfi

w
ll
xc
ptio
 "
TP Cli

t" | S
t-VMHostFi

w
ll
xc
ptio
 -



l

:$t
u
  
  
\
 

v

c

 s
tti
gs i
st
ll

 
  
S
t-VMHost

v

c

Co
figu

tio
 -

m
"
isk.Us


vic


s
t" -V
lu
 0  
S
t-VMHost

v

c

Co
figu

tio
 -

m
"
isk.Us
Lu


s
t" -V
lu
 1  
  
\
 S
t th
 qu
u


pth fo
 th
 Qlogic H

 


 Sch


um

qOutst


i
g s
tti
g 
  
G
t-VMhostMo
ul
 "ql
2xxx" | S
t-VMHostMo
ul
 -Optio
s"ql2xm
xq

pth\=$H

qu
u

pth"  
S
t-VMHost

v

c

Co
figu

tio
 -

m
"
isk.Sch


um

qOutst


i
g" -V
lu
 $H

qu
u

pth  
  
\
 



l
 VMHostSt

tup 
  
$VMst

t = G
t-VMHostSt

tPolicy  
S
t-VMHostSt

tPolicy -VMHostSt

tPolicy $VMst

t -



l

:$t
u
 -St

t

l
y 60 -Stop

l
y 60 -Stop
ctio
 Gu
stShut
ow
  
  
\
 
isco


ct 
  

isco


ct-vis

v

 -co
fi
m:$f
ls


It’s 

sy to 

just th
 s
tti
gs fo
 you
 



. This shows th
 st


gth to us
 th
 Pow

CLI fo
 
oi
g 
utom
tio
 i
 VMw


. If you h
v
 sugg
stio
s pl

s
 l
t m
 k
ow.

\[


v

tic

l\]






