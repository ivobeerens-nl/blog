---
titl
: "C


t
 
 Sit
-to-Sit
 VP
 to Mic
osoft 
zu

"


t
: "2021-11-08T12:35:25.000Z"
c
t
go
i
s: 
  - "
zu

"
t
gs: 
  - "
zu

-vp
-g
t
w
y"
  - "

g
-
out

"
  - "loc
l-

two
k-g
t
w
y"
  - "s2s"
  - "u
iquiti"
  - "v

t"
  - "vp
"
cov

Im
g
: "
zu

-1.p
g"

utho
: Ivo 





s
---

I
 this 
x
mpl
, I c


t
 
 Sit
-to-Sit
 VP
 

tw


 my o
-p

mis
s 

two
k 


 
zu

. F
om my o
-p

mis
s 

two
k, I'm 

l
 to co


ct to th
 spok
 

two
k wh


 my 
om
i
 Co
t
oll

 

si

s.

**

qui

m

ts**

- C


t
 
 

two
k topology 


wi
g. This m
k
s it 

si

 to s
t up 


 t
ou
l
shoot.

[![](im
g
s/
zu

-1-300x201.p
g)](im
g
s/
zu

-1.p
g)

- Ch
ck if you h
v
 
 comp
ti
l
 VP
 

vic
. Mo

 i
fo
m
tio
: [

out VP
 

vic
s fo
 co


ctio
s - 
zu

 VP
 G
t
w
y | Mic
osoft 
ocs](https://
ocs.mic
osoft.com/

-us/
zu

/vp
-g
t
w
y/vp
-g
t
w
y-

out-vp
-

vic
s)
- I
st
ll th
 
z Pow

Sh
ll mo
ul
. 
ll th
 st
ps 


 
o

 i
 Pow

Sh
ll.  [I
st
ll th
 
zu

 
z Pow

Sh
ll mo
ul
 | Mic
osoft 
ocs](https://
ocs.mic
osoft.com/

-us/Pow

Sh
ll/
zu

/i
st
ll-
z-ps?vi
w=
zps-6.6.0)

**Th
 m
i
 st
ps 


**

- **St
p 1**: Co
figu

 th
 
zu

 VP
 g
t
w
y
- **St
p 2**: Co
figu

 th
 U
iquiti 

g
 
out

.
- **St
p 3**: C


t
 th
 

two
k p


i
gs
- **St
p 4**: Op

 th
 fi

w
ll o
 th
 VMs




 St
p 1: Co
figu
i
g th
 
zu

 VP
 G
t
w
y

Fi
st, w
 

gi
 i
 
zu

 
y co
figu
i
g th
 VP
 G
t
w
y. Mic
osoft h
s 
 goo
 

ticl
 th
t 

sc
i

s th
 p
oc
ss th
t c

 

 fou

 [h


](https://
ocs.mic
osoft.com/

-us/
zu

/vp
-g
t
w
y/vp
-g
t
w
y-c


t
-sit
-to-sit
-
m-Pow

Sh
ll). I us
 Pow

Sh
ll to co
figu

 th
 VP
 g
t
w
y co
figu

tio
.

- Fill i
 th
 v

i

l
s with th
 co


ct v
lu
s of you
 

vi
o
m

t

\[co

 l

gu
g
="Pow

Sh
ll"\] 
 V

i

l
s $
g\_vp
 = "VP
-
G" $v

t

m
 = "VP
-V

T" $loc
tio
 = "W
st
u
op
" $




sssp
c
hu
 = "10.2.0.0/16" $su


t

m
 = "F
o
t


" $su


t = "10.2.0.0/24" $g
t
w
ysu


t = "10.2.255.0/27" $pu
lic\_ip\_o
p

m = "31.151.12.226" $
llow
\_o
p

m\_

two
ks1 = "192.168.249.0/24" $
llow
\_o
p

m\_

two
ks2 = "192.168.13.0/24" $g
t
w
y

m
 = "VP
-GW" $vp
typ
 = "
out


s

" 
 https://
ocs.mic
osoft.com/

-us/
zu

/vp
-g
t
w
y/vp
-g
t
w
y-

out-vp
-g
t
w
y-s
tti
gs
gwsku $sku = "

sic" $g
t
w
yTyp
 = "Vp
" $co


ctio


m
 = "VP
-V

tToO
P

m" $vp
pip\_
zu

 = "VP
-
ZU

-PIP" $vp
co


ctio
 = "VP
-IPS
C-S2S" $sh



k
y = "!Thisis
S
c

t!" \[/co

\]

- Co


ct to 
zu



\[co

 l

gu
g
="Pow

Sh
ll"\] Co


ct-
z
ccou
t \[/co

\]

- C


t
 th
 
zu

 VP
 g
t
w
y

\[co

 l

gu
g
="Pow

Sh
ll"\] 
 C


t
 
zu

 

sou
c
 G
oup W
it
-Host "C


t
 
 

sou
c
 G
oup c
ll

 $
g\_vp
" -Fo

g
ou

Colo
 G



 

w-
z

sou
c
G
oup -

m
 $
g\_vp
 -Loc
tio
 $Loc
tio


\
 C


t
 

two
ks $su


t1 = 

w-
zVi
tu
l

two
kSu


tCo
fig -

m
 'G
t
w
ySu


t' -




ssP

fix $g
t
w
ysu


t $su


t2 = 

w-
zVi
tu
l

two
kSu


tCo
fig -

m
 $su


t

m
 -




ssP

fix $su


t

\
 C


t
 V

t $v

t = 

w-
zVi
tu
l

two
k -

m
 $v

t

m
 -

sou
c
G
oup

m
 $
g\_vp
 \` -Loc
tio
 $loc
tio
 -




ssP

fix $




sssp
c
hu
 -Su


t $su


t1,$su


t2 $v

t | S
t-
zVi
tu
l

two
k

\
 C


t
 
 loc
l 

two
k g
t
w
y 

w-
zLoc
l

two
kG
t
w
y -

m
 $co


ctio


m
 -

sou
c
G
oup

m
 $
g\_vp
 \` -Loc
tio
 $loc
tio
 -G
t
w
yIp




ss $pu
lic\_ip\_o
p

m -




ssP

fix $
llow
\_o
p

m\_

two
ks1,$
llow
\_o
p

m\_

two
ks2

\
 

qu
st 
 pu
lic IP 




ss $gwpip= 

w-
zPu
licIp




ss -

m
 $vp
pip\_
zu

 -

sou
c
G
oup

m
 $
g\_vp
 -Loc
tio
 $loc
tio
 -
lloc
tio
M
tho
 
y

mic

\
 C


t
 G
tw
y IP 




ssi
g $v

t = G
t-
zVi
tu
l

two
k -

m
 $v

t

m
 -

sou
c
G
oup

m
 $
g\_vp
 $su


t = G
t-
zVi
tu
l

two
kSu


tCo
fig -

m
 'G
t
w
ySu


t' -Vi
tu
l

two
k $v

t $gwipco
fig = 

w-
zVi
tu
l

two
kG
t
w
yIpCo
fig -

m
 gwipco
fig1 -Su


tI
 $su


t.I
 -Pu
licIp




ssI
 $gwpip.I


\
 C


t
 
 Sit
 to Sit
 VP
 g
t
w
y W
it
-Host "C


ti
g th
 VP
 g
t
w
y. This c

 t
k
 up to 45 mi
ut
s!" -Fo

g
ou

Colo
 G



 

w-
zVi
tu
l

two
kG
t
w
y -

m
 $g
t
w
y

m
 -

sou
c
G
oup

m
 $
g\_vp
 \` -Loc
tio
 $loc
tio
 -IpCo
figu

tio
s $gwipco
fig -G
t
w
yTyp
 $g
t
w
yTyp
 \` -Vp
Typ
 $vp
typ
 -G
t
w
ySku $sku

\
 Co
figu

 th
 VP
 Co


ctio
 co
figu

tio
 $g
t
w
y1 = G
t-
zVi
tu
l

two
kG
t
w
y -

m
 $g
t
w
y

m
 -

sou
c
G
oup

m
 $
g\_vp
 $loc
l = G
t-
zLoc
l

two
kG
t
w
y -

m
 $co


ctio


m
 -

sou
c
G
oup

m
 $
g\_vp




w-
zVi
tu
l

two
kG
t
w
yCo


ctio
 -

m
 $vp
co


ctio
 -

sou
c
G
oup

m
 $
g\_vp
 \` -Loc
tio
 $loc
tio
 -Vi
tu
l

two
kG
t
w
y1 $g
t
w
y1 -Loc
l

two
kG
t
w
y2 $loc
l \` -Co


ctio
Typ
 IPs
c -
outi
gW
ight 10 -Sh



K
y $sh



k
y \[/co

\]

- Wh

 
ll th
 p

ts 


 c


t

 you s

 th
 followi
g 

sou
c
s i
 th
 

sou
c
 g
oup.

[![](im
g
s/VP

G-300x177.jpg)](im
g
s/VP

G.jpg)

- Click o
 th
 "VP
-IPS
C-S2S" Co


ctio
 


 click o
 
ow
lo

 co
figu

tio
. Fo
 v

ious v


o
s such 
s Cisco, 
lli

 T
l
sis, Ju
ip

 


 U
iquiti th


 


 s
mpl
 co
figu

tio
 t
mpl
t
s 
v
il

l
. If th
 v


o
 is 
ot list

 you c

 choos
 
 g



ic s
mpl
 co
figu

tio
.

[![](im
g
s/VP
CO


ctio
-300x144.jpg)](im
g
s/VP
CO


ctio
.jpg)

- S
l
ct "
ow
lo

 co
figu

tio
" 


 th
 co
figu

tio
 will 

 
ow
lo



 
s t
xt fil
.



 St
p 2: Co
figu

 th
 U
iquiti 

g
 
out



- C


t
 
 SSH s
ssio
 to th
 

g
 
out

 


 log i

- S
t th
 
out

 i
 co
fig mo

 
y usi
g th
 followi
g comm




\[co

 l

gu
g
="t
xt"\] co
figu

 \[/co

\]

- Copy th
 
ow
lo



 s
mpl
 co
figu

tio
, st

ti
g f
om  th
 li

 th
t 

gi
s with "s
t vp
 ips
c 
uto-fi

w
ll-

t-
xclu

 



l
 " s
mpl
 co
figu

tio


\[co

 l

gu
g
="t
xt"\] s
t vp
 ips
c 
uto-fi

w
ll-

t-
xclu

 



l


s
t vp
 ips
c 
sp-g
oup FOO0 lif
tim
 3600 s
t vp
 ips
c 
sp-g
oup FOO0 pfs 
is

l
 s
t vp
 ips
c 
sp-g
oup FOO0 p
opos
l 1 

c
yptio
 

s256 s
t vp
 ips
c 
sp-g
oup FOO0 p
opos
l 1 h
sh sh
1

s
t vp
 ips
c ik
-g
oup FOO0 k
y-
xch

g
 ik
v2 s
t vp
 ips
c ik
-g
oup FOO0 lif
tim
 3600

s
t vp
 ips
c ik
-g
oup FOO0 p
opos
l 1 
h-g
oup 2 s
t vp
 ips
c ik
-g
oup FOO0 p
opos
l 1 

c
yptio
 

s256 s
t vp
 ips
c ik
-g
oup FOO0 p
opos
l 1 h
sh sh
1

s
t vp
 ips
c sit
-to-sit
 p


 51.124.215.67 
uth

tic
tio
 mo

 p

-sh



-s
c

t s
t vp
 ips
c sit
-to-sit
 p


 51.124.215.67 
uth

tic
tio
 p

-sh



-s
c

t !Thisis
S
c

t! s
t vp
 ips
c sit
-to-sit
 p


 51.124.215.67 co


ctio
-typ
 

spo

 s
t vp
 ips
c sit
-to-sit
 p


 51.124.215.67 

sc
iptio
 IPs
c
zu

 s
t vp
 ips
c sit
-to-sit
 p


 51.124.215.67 ik
-g
oup FOO0 s
t vp
 ips
c sit
-to-sit
 p


 51.124.215.67 loc
l-




ss 31.151.12.227

s
t vp
 ips
c sit
-to-sit
 p


 51.124.215.67 vti 
i

 vti0 s
t vp
 ips
c sit
-to-sit
 p


 51.124.215.67 vti 
sp-g
oup FOO0 s
t i
t

f
c
s vti vti0 s
t p
otocols st
tic i
t

f
c
-
out
 10.2.0.0/16 

xt-hop-i
t

f
c
 vti0

s
t fi

w
ll optio
s mss-cl
mp i
t

f
c
-typ
 vti s
t fi

w
ll optio
s mss-cl
mp mss 1350 s
t syst
m offlo

 ips
c 



l
 \[/co

\]

- I
 this 
x
mpl
, w
 
o
't us
 
y

mic 
outi
g p
otocols such 
s 
GP, so w
 must c


t
 st
tic 
out
s i
 th
 

g
 
out

 fo
 
ll th
 su


ts w
 w

t to co


ct to. I
 this 
x
mpl
, w
 co


ct th
 10.1.0.0/24 su


t i
 
zu

 f
om th
 o
-p

mis
s 

two
k. This su


t co
t
i
s th
 
om
i
 Co
t
oll

s. Th
 
outi
g go
s th
ough Vi
tu
l Tu


l I
t

f
c
 0 

fi


 i
 th
 

g
 
out

.

\[co

 l

gu
g
="t
xt"\] s
t p
otocols st
tic i
t

f
c
-
out
 10.1.0.0/24 

xt-hop-i
t

f
c
 vti0 \[/co

\]

- Commit 


 s
v
 th
 ch

g
s

\[co

 l

gu
g
="t
xt"\] commit ; s
v
 ; 
xit \[/co

\]

- Ch
ck if th
 tu


l is up. This c

 t
k
 
 whil


\[co

 l

gu
g
="t
xt"\] show vp
 ips
c s
 \[/co

\]

[![](im
g
s/

g
showvp
-300x49.jpg)](im
g
s/

g
showvp
.jpg)

- Th
 IPS
C tu


l must 

 **
ST

LISH

**



 St
p 3: C


t
 th
 

two
k p


i
gs

Co


cti
g th
 spok
 

two
k wh


 th
 
om
i
 Co
t
oll

 

si

s is 
ot possi
l
 

c
us
 

two
k p


i
g is 
ot co
figu


 y
t.

- Op

 th
 Pow

Sh
ll Wi

ow th
t is still 
uth

tic
t

 to 
zu


- Ch

g
 th
 v

i

l
s if 






- 
x
cut
 th
 Pow

Sh
ll sc
ipt

\[co

 l

gu
g
="Pow

Sh
ll"\] 
 V

i

l
s $
g\_vp
 = "VP
-
G" $
g\_
c = "vm-
c-
g" $p




m
vp
 = "p


-vp
-to-
c" $p




m

c = "p


-
c-to-vp
" $v

tvp


m
 = "VP
-V

T" $v

t
c

m
 = "vm-
c-
g-v

t"

$v

tvp
 = G
t-
zVi
tu
l

two
k -

m
 $v

tvp


m
 -

sou
c
G
oup

m
 $
g\_vp
 $v

t
c = G
t-
zVi
tu
l

two
k -

m
 $v

t
c

m
 -

sou
c
G
oup

m
 $
g\_
c

\
 Us
 this vi
tu
l 

two
k's g
t
w
y o
 
out
 S

v






-
zVi
tu
l

two
kP


i
g \` -

m
 $p




m
vp
 \` -Vi
tu
l

two
k $v

tvp
 \` -

mot
Vi
tu
l

two
kI
 $v

t
c.I
 -
llowG
t
w
yT


sit:$t
u
 


-
zVi
tu
l

two
kP


i
g \` -

m
 $v

t
c

m
 \` -Vi
tu
l

two
k $v

t
c \` -

mot
Vi
tu
l

two
kI
 $v

tvp
.I
 -Us


mot
G
t
w
ys:$t
u
 \[/co

\]

- Ch
ck th
 st
tus of th
 V

t p


i
g

\[co

 l

gu
g
="Pow

Sh
ll"\] G
t-
zVi
tu
l

two
kP


i
g -

sou
c
G
oup

m
 $
g\_vp
 \` -Vi
tu
l

two
k

m
 $v

tvp
.

m
 | Fo
m
t-T

l
 Vi
tu
l

two
k

m
, p


i
gSt
t


G
t-
zVi
tu
l

two
kP


i
g -

sou
c
G
oup

m
 $
g\_
c \` -Vi
tu
l

two
k

m
 $v

t
c.

m
 | Fo
m
t-T

l
 Vi
tu
l

two
k

m
, p


i
gSt
t
 \[/co

\]

- Fo
 
oth V

ts th
 p


i
gSt
t
 must 

 Co


ct



[![](im
g
s/ch
ckp


-300x68.jpg)](im
g
s/ch
ckp


.jpg)



 St
p 4: Op

 th
 fi

w
ll o
 th
 VMs

Th
 fi
st t
st I p

fo
m is 
 pi
g t
st.

- To pi
g 
 VM , ICMP i
 th
 Wi

ows fi

w
ll 



s to 

 op



. This c

 

 
o

 
y usi
g th
 followi
g Pow

Sh
ll comm


.

\[co

 l

gu
g
="Pow

Sh
ll"\] 

w-

tFi

w
ll
ul
 –
ispl
y

m
 "
llow ICMPv4-I
" –P
otocol ICMPv4 \[/co

\]


ft

 this ch

g
, you must 

 

l
 to pi
g (f
om th
 192.168.249.0/24 


 192.168.13.0/24 su


ts) to th
 10.1.0.0/24 su


t i
 
zu

 wh


 th
 
om
i
 Co
t
oll

 

si

s.



 W

p-up

Co
figu
i
g 
 Sit
-to-sit
 VP
 tu


l i
volv
s 
 lot of st
ps 
s you c

 s

 i
 this 
log post. I hop
 
y 



i
g this post it will giv
 g


t i
sight i
to how to s
t up 
 Sit
-to-Sit
 VP
 to 
zu

.






