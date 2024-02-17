---
titl
: "W
ys to p
tch you
 VMw


 
SX(i) hosts"


t
: "2010-03-11T11:02:34.000Z"
c
t
go
i
s: 
  - "
sxup

t
"
  - "p
tch"
  - "up

t
"
  - "vum"
t
gs: 
  - "p
tch"

utho
: Ivo 





s
---

**VUM** c

 

 us

 to 
utom
t

 p
tch you
 compl
t
 

vi
o
m

t without us

 i
t

v

tio
. 
SX(i) host 


 
utom
tic
lly pl
c

 i
 m
i
t



c
 mo

 


 VM’s 


 mig

t

 to oth

 VMw


 
SX(i) host usi
g VMotio
 


 

S t
ch
iqu
s, th
 host is p
tch

, 


oot

 


 
xiti
g m
i
t



c
 mo

.  VUM is us

 o
 

t

p
is
 

vi
o
m

ts.

**vSph


 Host Up

t
 Utility** c

 

 us

 to p
tch o
ly VMw


 
SXi (
ot 
SX) hosts. 
o
m
lly this utility is us

 i
 sm
ll 
SXi 

vi
o
m

ts without VUM, VMotio
 


 

S.

<t

l
 
o



="0" c
llsp
ci
g="0" c
llp


i
g="2" wi
th="586"><t
o
y><t
><t
 v
lig
="top" wi
th="273"><p 
lig
="c

t

"><
 h

f="im
g
s/im
g
12.p
g"><img styl
="
o



-
ight-wi
th: 0px; 
ispl
y: i
li

; 
o



-top-wi
th: 0px; 
o



-
ottom-wi
th: 0px; 
o



-l
ft-wi
th: 0px" titl
="im
g
" 
o



="0" 
lt="im
g
" s
c="im
g
s/im
g
12_thum
.p
g" wi
th="292" h
ight="178"></
>&

sp;<

>&

sp;<

><

><

><

><

><

></p></t
><t
 v
lig
="top" wi
th="311"><
 h

f="https://www.ivo





s.
l/wp-co
t

t/uplo

s/2010/03/im
g
8.p
g"><img styl
="
o



-
ight-wi
th: 0px; 
ispl
y: 
lock; flo
t: 
o

; 
o



-top-wi
th: 0px; 
o



-
ottom-wi
th: 0px; m

gi
-l
ft: 
uto; 
o



-l
ft-wi
th: 0px; m

gi
-
ight: 
uto" titl
="im
g
" 
o



="0" 
lt="im
g
" s
c="im
g
s/im
g
8_thum
.p
g" wi
th="253" h
ight="265"></
></t
></t
><t
><t
 v
lig
="top" wi
th="273">VUM utility</t
><t
 v
lig
="top" wi
th="311">vSph


 Host Up

t
 Utility<fo
t colo
="
3672
1"></fo
t></t
></t
></t
o
y></t

l
>

**
SXup

t
** comm


, this comm


 li

 utility (i
 th
 s

vic
 co
sol
) c

 

 us

 to p
tch you
 st



lo

 VMw


 
SX host, fo
 
x
mpl
 th
 vSph


 
ss

ti
ls 

itio
. This sm
ll 
usi

ss v

sio
 com
s with fo
 
x
mpl
 VMw


 
SX, vC

t

 


 VMw


 Up

t
 M


g

. 
ut wh

 you
 vC

t

 s

v

 is i
st
ll

 vi
tu
lly 
s VM you 


 
ot 

l
 to t


sf

 th
 VM to 

oth

 host 

c
us
 th


 is 
o VMotio
 i
 th
 lic

s
. 
ll th
 VMs must 

 shut
ow
 i
clu
i
g th
 vC

t

 VM to put th
 host i
 m
i
t



c
 mo

. So you c

’t us
 VMw


 Up

t
 M


g

. 
ow you 



 th
 
sxup

t
 comm


.  H


 


 th
 st
ps fo
 usi
g th
 
SXup

t
 comm


:

- Th
 fi
st thi
g is to 
ow
lo

 th
 p
tch 
u

l
s. 
 
u

l
 co
t
i
s 
 m
t


t
 zip which 

fi

s th
 
ull
ti
s 
v
il

l
 fo
 i
st
ll
tio
. This is 
 g


t imp
ov
m

t to 


li

 v

sio
s of VMw


 
SX. It’s possi
l
 to s
l
ct 
ll p
tch 
u

l
s 


 
ow
lo

 th
m 
t o
c
. Th
 p
tch 
u

l
s c

 

 fou

 [h


](https://www.VMw


.com/mysuppo
t/
ow
lo

/).

[![im
g
](im
g
s/im
g
_thum
2.p
g "im
g
")](im
g
s/im
g
2.p
g)

- Uplo

 th
 p
tch 
u

l
s o
 th
 VMw


 
SX VMFS  o
 
FS p

titio
 (oth

 optio
s such 
s HTTP 

posito
y 


 
lso possi
l
). This c

 

 
o

 
y usi
g th
 

t
sto

 

ows

 i
 th
 vC

t

 cli

t.

 [![im
g
](im
g
s/im
g
4_thum
.p
g "im
g
")](im
g
s/im
g
4.p
g)

- Shut
ow
 
ll VMs o
 th
 VMw


 
SX host to p
tch usi
g th
 .vSph


 cli

t o
 th
 VMw


-cm
 comm


.
- Put th
 host i
 m
i
t



c
 mo

 usi
g th
 vSph


 cli

t o
 th
 followi
g comm


:

vimsh -
 -
 /hostsvc/m
i
t



c
\_mo

\_

t



- Ch
ck th
 i
t
g
ity of th
 p
tch 
u

l
 with th
 
sxup

t
 –ch
ck –
u

l
 comm


. 
o this fo
 
ll p
tch 
u

l
s.
- I
st
ll th
 p
tch usi
g th
 
sxup

t
 up

t
 –
u

l
 comm


. I
st
ll 
ll p
tch 
u

l
s 

gi

i
g with th
 ol

st p
tch 
u

l
.
- 
xit m
i
t



c
 mo

 
y usi
g th
 vSph


 cli

t of th
 followi
g comm


:

vimsh -
 -
 /hostsvc/m
i
t



c
\_mo

\_
xit

- 


oot th
 hosts vSph


 cli

t of th
 followi
g comm


:

shut
ow
 –
 
ow

H


’s 
 s
mpl
 sc
ipt:

vimsh -
 -
 /hostsvc/m
i
t



c
\_mo

\_

t



sxup

t
 ch
ck --
u

l
 
SX400-200906001.zip

sxup

t
 up

t
 --
u

l
 
SX400-200906001.zip

sxup

t
 ch
ck --
u

l
 
SX400-200907001.zip

sxup

t
 up

t
 --
u

l
 
SX400-200907001.zip

sxup

t
 ch
ck --
u

l
 
SX400-200909001.zip

sxup

t
 up

t
 --
u

l
 
SX400-200909001.zip

sxup

t
 ch
ck --
u

l
 
SX-4.0.0-up

t
01
.zip

sxup

t
 up

t
 --
u

l
 
SX-4.0.0-up

t
01
.zip

sxup

t
 ch
ck --
u

l
 
SX400-200912001.zip

sxup

t
 up

t
 --
u

l
 
SX400-200912001.zip

sxup

t
 ch
ck --
u

l
 
SX400-201002001.zip

sxup

t
 up

t
 --
u

l
 
SX400-201002001.zip
vimsh -
 -
 /hostsvc/m
i
t



c
\_mo

\_
xit
shut
ow
 -
 
ow

\[


v

tic

l\]






