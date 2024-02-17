---
titl
: "



l
 


 
is

l
 

mot
 T
ch Suppo
t mo

 (SSH)"


t
: "2011-11-11T09:58:48.000Z"
c
t
go
i
s: 
  - "pow

cli"
  - "vpsh


"
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

> 

mot
 T
ch Suppo
t Mo

 (SSH) fo
 th
 host … h
s 



 



l



[![im
g
](im
g
s/im
g
_thum
1.p
g "im
g
")](im
g
s/im
g
20.p
g)

Wh

 th
 w


i
g 
pp


s som
 

mi
s g
t 
 littl
 


vous. Si
c
 VMw


 
SXi 4.1 Up

t
 2 


 VMw


 
SXi 5 th
 w


i
g c

 

 supp

ss

.

Wh

 st

ti
g th
 

mot
 T
ch Suppo
t (TSM) s

vic
 it is possi
l
 to SSH to th
 
SXi host.

Th
 followi
g sc
ipt c

 st

t o
 stop th
 

mot
 T
ch Suppo
t mo

 


 supp

ss th
 w


i
gs o
 th
 VMw


 
SXi hosts.

<

.SY
OPSIS
  



l
 o
 
is

l
 TSM 
.V

SIO

 1.0
.

SC
IPTIO

  TSM-SSH 

mot
 T
ch Suppo
t (SSH) 
.
OT
S
  
utho
(s): Ivo 





s 
.
X
MPL

  PS> ./tsm.ps1

>




-PSS

pi
 VMw


.Vim
utom
tio
.co

 -


o

ctio
 Sil

tlyCo
ti
u



 VMw


 Vi
tu
lC

t

 s

v

 

m
 
$VCs

v

 = 



-host "

t

 you
 vC

t

 s

v

"
$Us



m
= 



-host "

t

 th
 us



m
"
$P
sswo

 = 



-host "

t

 p
sswo

"


 Co


ct to th
 vC

t

 s

v

 
Co


ct-VIS

v

 $VCs

v

 -Us

 $Us



m
 -P
sswo

 $P
sswo

 -po
t 443
 

 M

u
W
it
-Host "Choos
 St

t o
 to stop th
 

mot
 T
ch Suppo
t (SSH)s

vic
"
W
it
-Host " 1. St

t 

mot
 T
ch Suppo
t (SSH)"
W
it
-Host " 2. Stop 

mot
 T
ch Suppo
t (SSH)"
$

spo
s
 = 



-Host "S
l
ct 1 o
 2"

if ($

spo
s
 -
q 1){

St

t
g
t-vmhost | S
t-VMHost

v

c

Co
figu

tio
 -

m
 "Us

V

s.Supp

ssSh
llW


i
g" -V
lu
 1
g
t-vmhost | G
t-VMHostS

vic
 | Wh


 {$\_.k
y -
q "TSM-SSH"} | St

t-VMHostS

vic
 
}

if ($

spo
s
 -
q 2){

Stop
g
t-vmhost | G
t-VMHostS

vic
 | Wh


 {$\_.k
y -
q "TSM-SSH"} | Stop-VMHostS

vic
 -Co
fi
m:$f
ls

g
t-vmhost | S
t-VMHost

v

c

Co
figu

tio
 -

m
 "Us

V

s.Supp

ssSh
llW


i
g" -V
lu
 0 
}






