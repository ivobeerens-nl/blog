---
titl
: "C


t
 
 c

t

l VMw


 Tools 

posito
y"


t
: "2021-07-08T07:01:42.000Z"
t
gs: 
  - "pow

cli"
  - "VMw


"

utho
: Ivo 





s
---



qui

m

ts:

- VMw


 
SXi 6.7 Up

t
 1 o
 l
t


- Pow

CLI i
st
ll



H


 


 th
 st
ps to c


t
 
 c

t

l VMw


 Tools 

posito
y:

- C


t
 
 fol


 st
uctu

 o
 
 c

t

l 

t
sto

 (
ll VMw


 
SXi hosts h
v
 
cc
ss to this 

t
sto

)  i
 th
 clust

. Fo
 
x
mpl
:
    - O
 th
 
fs01 

t
sto

 is c


t

 
 fol


 c
ll

 "**vmwtools**", u



 th
t fol


, I c


t

 

oth

 fol


 c
ll

 "**11.3.0-18090558**"
- 
ow
lo

 th
 l
t
st VMw


 Tools v

sio
, [li
k](https://www.VMw


.com/go/tools)
- 
xt

ct th
 VMw


 Tools ZIP fil
. Two fol


s 


 
xt

ct

:
    - floppi
s
    - vmtools
- Uplo

 th
 two fol


s to th
 fol


 st
uctu

 c


t

. I
 this 
x
mpl
 I us

: /vmfs/volum
s/vmwtools/11.3.0-18090558

[![](im
g
s/1-300x158.jpg)](im
g
s/1.jpg)

- Ch

g
 th
 followi
g v

i

l
s so it m
tch
s th
 vSph


 

vi
o
m

t:
    - $clust


    - $

t
sto


- Th
 Pow

CLI sc
ipt 

low will poi
t 
ll th
 VMw


 
SXi hosts i
 
 clust

 to th
 c

t

l VMw


 Tools 

posito
y loc
tio
.
- 
x
cut
 this sc
ipt

\[co

 l

gu
g
="Pow

Sh
ll"\] 
 Impo
t Pow

CLI mo
ul
 Impo
t-Mo
ul
 VMw


.Pow

CLI

\
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

 th
 vC

t

 s

v

 

m
"

\
 Co


ct to th
 vC

t

 s

v

 Co


ct-VIS

v

 -s

v

 $VCs

v



$clust

 = 'CL-MG
T' $hosts = G
t-Clust

 -

m
 $clust

 | G
t-VMHost $

t
sto

 = '/vmfs/volum
s/
fs01/vmwtools/11.3.0-18090558/'

\
 
ispl
y cu



t VMw


 Loc
tio
 $hosts | G
t-

v

c

S
tti
g -

m
 "Us

V

s.P
o
uctLock

Loc
tio
" | S
l
ct-O
j
ct 

tity,V
lu


\
 Ch

g
 VMw


 Tools loc
tio
 G
t-clust

 -

m
 $clust

 | G
t-VMhost | %{$\_.
xt

sio


t
.Up

t
P
o
uctLock

Loc
tio
($

t
sto

)}

\
 
ispl
y cu



t VMw


 Loc
tio
 $hosts | G
t-

v

c

S
tti
g -

m
 "Us

V

s.P
o
uctLock

Loc
tio
" | S
l
ct-O
j
ct 

tity,V
lu


\
 
isco


ct vC

t

 
isco


ct-VIs

v

 -s

v

 \* -Co
fi
m:$f
ls


\[/co

\]

Th
 

f
ult loc
tio
 of th
 VMw


 Tools is: **/lock

/p
ck
g
s/vmtools

po/**

- S
l
ct 
 Wi

ows VM i
 th
 vSph


 clust

. 
 m
ss
g
 is 
ispl
y

 th
t th


 is 
 

w

 v

sio
 of VMw


 Tools 
v
il

l
.
- S
l
ct Upg



 VMw


 Tools (It is possi
l
 th
t th
 VM is 
utom
tic
lly 


oot

 wh

 choosi
g fo
 

 
utom
tic Upg



).

[![](im
g
s/2-300x146.jpg)](im
g
s/2.jpg)[![](im
g
s/3-300x272.jpg)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2021/07/3.jpg)

- 
ft

 th
 i
st
ll
tio
, ch
ck if VMTools is 
u

i
g 


 if th
 v

sio
 is cu



t.

[![](im
g
s/4-300x141.jpg)](im
g
s/4.jpg)

C


ti
g 
 c

t

l VMw


 Tools 

posito
y is 

 

sy st
p th
t is v

y us
ful to st
y up to 

t
 with th
 l
t
st VMw


 Tools v

sio
s fo
 th
 Vi
tu
l M
chi

s.

Th
 VMw


 Pow

CLI sc
ipt list

 

ov
 c

 

 fou

 o
 my GitHu
 

posito
y, [li
k](https://githu
.com/i





s/Pow

CLI/
lo
/m
st

/s
t-loc-vmwtools.ps1).






