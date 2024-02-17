---
titl
: "C


t
 
 
oot

l
 VMw


 
SXi 5 US
 stick i
 Wi

ows 


 p

fo
m 
 sc
ipt

 i
st
ll
tio
"


t
: "2011-09-17T16:42:10.000Z"
c
t
go
i
s: 
  - "
sxi"
  - "kickst

t"
  - "us
"
t
gs: 
  - "
sxi-2"
  - "ks"
  - "us
"

utho
: Ivo 





s
---





 St
p 1



 su

 

movi
g 
ll p

titio
s 


 fo
m
t 
 F
T32 p

titio
 o
 th
 US
 stick 
y usi
g th
 followi
g comm


:

Op

 th
 comm


 p
ompt 


 

t

 th
 followi
g comm


s:


iskp

t (m
k
 su

 you 
u
 
iskp

t 
s 

mi
ist

to
) 
list 
isk (list th
 
isk i
 you
 syst
m i
clu
i
g th
 US
) 
s
l
ct 
isk US
 
um


 
cl


 
c


t
 p

titio
 p
im

y 

ctiv
 
fo
m
t fs=f
t32 quick

ssig


xit





 St
p 2


ow
lo

 th
 Wi

ows Li
uxLiv
 US
 c


to
 utility [h


](http://www.li
uxliv
us
.com/).





 St
p 3

St

t th
 Lili US
 c


to
 utility.

 

[![im
g
](im
g
s/im
g
_thum
10.p
g "im
g
")](im
g
s/im
g
11.p
g)

Follow th
 st
ps 1,2,4 


 click 5 to c


t
 th
 US
 stick. W
it till th
 US
 c


tio
 p
oc
ss is fi
ish

. So 
ow you h
v
 
 
oot

l
 
SXi stick. You c

 stop h


 if you you w

t to i
st
ll 
SXi with m

u
l i
st
ll
tio
 st
ps. 





 St
p 4



it th
 
OOT.CFG fil
 i
 th
 
oot of th
 US
 stick 


 


 **ks=us
** 

tw


 /
.
00 


 --- /us

opts.gz mo
ul
s

Th
 
OOT.CFG shoul
 look lik
 this:


ootst
t
=0 
titl
=Lo

i
g 
SXi i
st
ll

 
k



l=/t
oot.
00 
k



lopt=
u
w

s
l 
mo
ul
s=/
.
00 ks=us
 --- /us

opts.gz --- /k.
00 --- /
.
00 --- /
t
-p
t
.v00 --- /
t
-p
t
.v01 --- /
t
-p
t
.v02 --- /
t
-p
t
.v03 --- /
t
-p
t
.v04 --- /
t
-p
t
.v05 --- /
t
-p
t
.v06 --- /
t
-p
t
.v07 --- /
lock-cc.v00 --- /
hci-
hc.v00 --- /s.v00 --- /w

s
li
.i00 --- /im
-ql
4.v00 --- /ipmi-ipm.v00 --- /ipmi-ipm.v01 --- /ipmi-ipm.v02 --- /misc-c
i.v00 --- /misc-

i.v00 --- /

t-

2
.v00 --- /

t-

x2.v00 --- /

t-

x2.v01 --- /

t-c
ic.v00 --- /

t-
100.v00 --- /

t-
100.v01 --- /

t-

ic.v00 --- /

t-fo
c.v00 --- /

t-ig
.v00 --- /

t-ixg
.v00 --- /

t-
x-
.v00 --- /

t-
816.v00 --- /

t-
816.v01 --- /

t-s2io.v00 --- /

t-sky2.v00 --- /

t-tg3.v00 --- /ohci-us
.v00 --- /s
t
-
hc.v00 --- /s
t
-
t
.v00 --- /s
t
-s
t.v00 --- /s
t
-s
t.v01 --- /s
t
-s
t.v02 --- /s
t
-s
t.v03 --- /scsi-

c.v00 --- /scsi-

p.v00 --- /scsi-
ic.v00 --- /scsi-

x.v00 --- /scsi-f
i.v00 --- /scsi-hps.v00 --- /scsi-ips.v00 --- /scsi-lpf.v00 --- /scsi-m
g.v00 --- /scsi-m
g.v01 --- /scsi-m
g.v02 --- /scsi-mpt.v00 --- /scsi-mpt.v01 --- /scsi-mpt.v02 --- /scsi-ql
.v00 --- /scsi-ql
.v01 --- /uhci-us
.v00 --- /tools.t00 --- /img

.tgz --- /imgp
yl
.tgz 

uil
= 
up

t

=0

 





 St
p 5

C


t
 
 Kickst

t co
figu

tio
 fil
 fo
 th
 sc
ipt

 i
st
ll
tio
 i
 th
 
oot of th
 US
 stick. H


 is 

 
x
mpl
:


S
mpl
 kickst

t sc
ipt

 i
st
ll
tio

vm
cc
pt
ul


ootpw VMw@


i
st
ll --fi
st
isk --ov

w
it
vmfs


two
k --
ootp
oto=st
tic --ip=192.168.250.21 --g
t
w
y=192.168.250.1 --

m
s

v

=192.168.250.6 --

tm
sk=255.255.255.0 --host

m
=
sxi5-01.





s.loc
l --

vic
=vm
ic0 --


vmpo
tg
oup=0



oot

%fi
st
oot --i
t

p

t

=
usy
ox

 



m
 loc
l 

t
sto

 

m

vim-cm
 hostsvc/

t
sto

/



m
 

t
sto

1 "$(host

m
 -s)-loc
l-sto

g
-1"

 

S 

m
s

sxcli syst
m host

m
 s
t --fq

=
sxi5-01.





s.loc
l

sxcli 

two
k ip 

s s


ch 


 --
om
i
=





s.loc
l

 

S s

v

 




ss
s

sxcli 

two
k ip 

s s

v

 


 --s

v

=192.168.250.6

sxcli 

two
k ip 

s s

v

 


 --s

v

=192.168.250.1

 SSH 


 
SXi sh
ll
vim-cm
 hostsvc/



l
\_ssh
vim-cm
 hostsvc/st

t\_ssh
vim-cm
 hostsvc/



l
\_
sx\_sh
ll
vim-cm
 hostsvc/st

t\_
sx\_sh
ll

Fo
 

iti
g 


 c


ti
g th
 
oot.cfg 


 ks.cfg fil
 i
 Wi

ows I us
 [
ot
p

++](http://
ot
p

-plus-plus.o
g/) so 
O hi



 c


i
g
 

tu

s 


 i
 th
 fil
s. 


 th
 US
 stick c


tio
 i
 



y.



 

sy w
y to t
st th
 
SXi 5 US
 stick 


 th
 sc
ipt

 i
st
ll
tio
  is usi
g VMw


 Wo
kst
tio
. S

 my post “
oot f
om US
 i
 VMw


 Wo
kst
tio
” fou

 [h


](https://www.ivo





s.
l/2009/10/16/
oot-f
om-us
-i
-VMw


-wo
kst
tio
/).

 

Willi
m L
m’s 
log h
s 


l goo
 i
fo
m
tio
 

out Kickst

t sc
ipts fou

 [h


](http://www.vi
tu
llygh
tto.com/2011/07/
utom
ti
g-
sxi-5x-kickst

t-tips.html).






