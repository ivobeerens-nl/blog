---
titl
: "T
st

 SMS P
SSCO

 multi-f
cto
 
uth

tic
tio
 with VMw


 Ho
izo
 Vi
w"


t
: "2015-04-14T06:42:11.000Z"
c
t
go
i
s: 
  - "

vi
ws"
  - "VMw


-vi
w"
t
gs: 
  - "

vi
ws-2"
  - "VMw


-ho
izo
-vi
w"

utho
: Ivo 





s
---

- Cit
ix W

 I
t

f
c
 P
ot
ctio

- 


IUS P
ot
ctio

- Clou
 
pplic
tio
 P
ot
ctio

- IIS W

 Sit
 P
ot
ctio

- IS
/TMG W

 Sit
 P
ot
ctio

- Wi

ows Logo
 P
ot
ctio

- S
cu

 

vic
 P
ovisio
i
g (fo
 
ctiv
Sy
c 

vic
s)

I
 this 

vi
w w
 t
st how-to i
t
g

t
 SMS P
SSCO

 with th
 l
t
st v

sio
 of VMw


 Ho
izo
 Vi
w usi
g 


IUS 
uth

tic
tio
.



 **Wh
t is SMS P
SSCO

**

U
lik
 t


itio

l h


w


-tok

 

s

 solutio
s, SMS P
SSCO

 wo
ks without 
ist
i
utio
 of 

y h


w


-tok

s. 
s 
 

sult, th
 logistic ov

h


 i
volv

 is mi
im
l 


 
oll-out is much f
st

. O
 th
 mo
il
 pho

 is 
o softw


 i
st
ll
tio
 





. Just 
xt

ct th
 c
ll pho

 
um


 f
om th
 

.

SMS P
SSCO

 s


s 
 O

-Tim
-P
ssco

 (OTP) to th
 us

 mo
il
 pho

. SMS P
SSCO

 looks 
t multipl
 f
cto
s such 
s tim
, g
o-loc
tio
, 


 typ
 of logi
 syst
m 

i
g 
cc
ss

.

SMS P
SSCO

 off

s 
 Multi-F
cto
 
uth

tic
tio
 (MF
) solutio
 th
t 


s 

 
xt

 s
cu
ity l
y

 to th
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t. VMw


 Ho
izo
 Vi
w h
s suppo
t fo
 


UIS 
uth

tic
tio
.



 **L

 

vi
o
m

t**

I
 th
 l

 

vi
o
m

t th
 followi
g compo


ts 


 i
st
ll

:

[![SMS P
ssco

](im
g
s/SMS-P
ssco

-747x1024.jpg)](im
g
s/SMS-P
ssco

.jpg)

1. Ho
izo
 Vi
w Cli

ts (PCoIP, 

P 


 HTML)
2. Ho
izo
 Vi
w S
cu
ity S

v


3. Ho
izo
 Vi
w Co


ctio
 S

v

 
xt



l
4. Ho
izo
 Vi
w Co


ctio
 S

v

 i
t



l
5. Mic
osoft SQL S

v


6. Ho
izo
 Vi
w Compos


7. vC

t

 S

v


8. 
ctiv
 
i

cto
y 
om
i
 Co
t
oll


9. SMS P
SSCO

 v

sio
 with 

two
k Policy S

v

 (
PS) 
ol
 i
st
ll



Fo
 th
 
xt



l co


ctio
 to th
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t 
 Multi-F
cto
 
uth

tic
tio
 (MF
) is co
figu


 
y usi
g SMS P
SSCO

. Th
 i
t



l Ho
izo
 Vi
w us

s 
o
't us
 SMS P
SSCO

 to co


ct.

Th
 followi
g softw


 v

sio
s 


 us

:

- Wi

ows S

v

 2012 
2 
ctiv
 
i

cto
y (

)
- Wi

ows S

v

 2008 
2 fo
 th
 SMS P
SSCO

 


 
PS softw


 
ol

- VMw


 vSph


 6
- VMw


 Ho
izo
 Vi
w 6.1
- SMS P
SSCO

 7.2

I
st


 of usi
g 
 GSM mo

m, 
 W

 S

vic
 SMS 
isp
tchi
g s

vic
 is us

 fo
 s


i
g m
ss
g
s. 
 GSM mo

m is highly p

f




 i
 
 p
o
uctio
 

vi
o
m

t.



 **I
st
ll
tio
 


 co
figu

tio
 M


g
m

t**




 **I
st
ll
tio
 of SMS P
SSCO

**

SMS P
SSCO

 is i
st
ll

 o
 
 Mic
osoft 32-o
 64-
it Wi

ows Op


ti
g Syst
m.. Th
 co

 compo


ts of SMS P
SSCO

 


:

- **

t


s
 S

vic
**. Th
 

t


s
 sto

s th
 SMS P
SSCO

 co
figu

tio
 


 us

 

t
.
- **T


smitt

 s

vic
**. This s

vic
 is 

spo
si
l
 fo
 
isp
tchi
g m
ss
g
s 


 v
li

tio
 of SMS P
SSCO

 logo
s. H


l
s lo

 

l

ci
g 


 f
ilov

 

tw


 
ll GSM mo

ms
- **Lo

 

l

ci
g s

vic
**. S

vic
 

spo
si
l
 fo
 lo

 

l

ci
g 


 f
ilov

.
- **W

 

mi
ist

tio
 I
t

f
c
**. W

 sit
 fo
 m
i
t
i
i
g us

 


 co
figu

tio
 

t


Th
s
 co

 compo


ts c

 

 
ist
i
ut

 ov

 o

 of mo

 s

v

s to p
ovi

 


u



cy 


 lo

 
ist
i
utio
 fo
 

t

p
is
 24x7 uptim
 

m


s.  I
 th
 l

 s
tup 
ll th
 co

 compo


ts 


 i
st
ll

 o
 
 si
gl
 s

v

.


s 
uth

tic
tio
 Cli

t 


ius p
ot
ctio
 is s
l
ct

 
u
i
g th
 i
st
ll
tio
.

**

two
k Policy S

v

 (
PS)**

O
 th
 SMS P
SSCO

 s

v

 th
 

two
k Policy S

v

 (
PS) 
ol
 is i
st
ll

 fo
 


IUS 
uth

tic
tio
.




 **Co
figu

tio
**

**W

 

mi
ist

tio
 I
t

f
c
 (W
I)**

Th
 W

 

mi
ist

tio
 I
t

f
c
 (W
I) is 
v
il

l
 f
om th
 w

 

ows

 o
 po
t 2000. F
om th
 W
I th
 co
figu

tio
 of SMS P
SSCO

 is 
o

.

F
om th
 W
I w
 



 to 
o th
 followi
g m
i
 st
ps:

1. Co
figu

 

 i
t
g

tio
 


 th
 m
ss
gi
g i
f

st
uctu

 us

 i
 th
 G




l s
tti
gs
2. Co
figu

 th
 Us

 I
t
g

tio
 Policy (UIP)
3. Co
figu

 Us

 G
oup Polici
s
4. Co
figu

 t


smissio
 i
f

st
uctu

 fo
 c


ti
g 
 
isp
tchi
g 

tity




 **St
p 1. G




l S
tti
gs**

I
 th
 g




l s
tti
gs t

 

 i
t
g

tio
 i
 si
gl
 sy
c mo

 is 



l

. With si
gl
 sy
c mo

 us

s 


 impo
t

 f
om 
 si
gl
 us

 g
oup.

[![

 i
t
g

tio
](im
g
s/

-i
t
g

tio
-300x147.p
g)](im
g
s/

-i
t
g

tio
.p
g)

I
 th
 glo

liz
tio
 optio
s th
 m
ss
gi
g i
f

st
uctu

 us

. Th
 followi
g m
ss
g
s i
f

st
uctu

s c

 

 us

 i
 SMS P
SSCO

:

- SMS OTP
- 
-m
il OTP
- Voic
 c
ll OTP
- W

 s

vic
 SMS OTP
- Tok

 OTP
- P

so

l p
ssco

 OTP

Th
 SMS OTP is th
 most s
cu

 optio
 to us
 


 highly p

f



l
. I
 ou
 l

 

vi
o
m

t w
 us
 W

 s

vic
 SMS OTP 
s m
ss
gi
g i
f

st
uctu

. 
 3

 p

ty w

 s

vic
 is us

 fo
 SMS 
isp
tchi
g.

[![g




l s
tti
gs - w

 s

vic
](im
g
s/g




l-s
tti
gs-w

-s

vic
-300x148.p
g)](im
g
s/g




l-s
tti
gs-w

-s

vic
.p
g)




 **St
p 2. Us

 I
t
g

tio
 Policy (UIP)**

Us

 I
t
g

tio
 Polici
s 


 us

 to co
figu

 how us

s i
 th
 SMS P
SSCO

 

t


s
 


 sy
ch
o
iz

 with us

s f
om o

 o
 mo

 
ctiv
 
i

cto
y sto

s.

[![UIP](im
g
s/UIP-300x147.p
g)](im
g
s/UIP.p
g)

Wh

 



li
g 

 i
t
g

tio
, us

s 


 sy
c

 wh

 

lo
gi
g to 
 sp
cifi

 g
oup o
 
tt
i
ut
. Fo
 
x
mpl
 th
 mo
il
 
tt
i
ut
 is us

 to 

t
i
v
 

 us

s. O
ly us

s with th
 pho

 
um


 fill

 i
 


 sy
c

 to SMS P
SSCO

.

[![impo
t](im
g
s/impo
t-300x96.p
g)](im
g
s/impo
t.p
g)




 **St
p 3. Us

 G
oup Polici
s (UGP)**

Us

 G
oup Polici
s (UGP) 


 us

 fo
 m


gi
g us

s. 
v

y us

s is 
ssig


 to 
 UGP 


 
utom
tic
lly i
h

its th
 s
tti
gs sp
cifi

 
y this policy. Fo
 
x
mpl
 th
 

mi
ist

to
 coul
 ch

g
 typ
 of p
ssco

 
isp
tchi
g, SMS typ
 (Fl
sh/
o
m
l) o
 S
lf S

vic
 Sit
 p

missio
s i
 th
 UGP. 
 UGP m


g
 us

 s
tti
gs o
 
 g
oup 

sis o
 o
 i

ivi
u
l 

sis 
y ov


i
i
g th
 UGP .

W
 ch

g

 th
 

f
ult UGP fo
 th
 
isp
tch typ
 to “S


 p
ssco

s 
y w

 s

vic
s SMS”.

[![

sic](im
g
s/

sic-300x146.p
g)](im
g
s/

sic.p
g)




 **St
p 4. t


smissio
 i
f

st
uctu

 fo
 c


ti
g 
 
isp
tchi
g 

tity**

I
 ou
 l

 

vi
o
m

t w
 
o
’t h
v
 
 GSM mo

m fo
 s


 SMS m
ss
g
s, so w
 us

 


 co
figu

 
 W

 S

vic
 
isp
tch

 s

vic
 fo
 s


i
g i
 SMS m
ss
g
s.

[![st
p 4 
isp
tch

](im
g
s/st
p-4-
isp
tch

-300x147.p
g)](im
g
s/st
p-4-
isp
tch

.p
g)


ft

 th
s
 fou
 m
i
 co
figu

tio
 st
ps w
 c

 t
st if th
 SMS m
ss
g
 is s

t to th
 us

 mo
il
 pho

 
y s
l
cti
g th
 t
st 
utto
 


 choos
 fo
 th
 W

 S

vic
 
isp
tch

 optio
. 
 t
st SMS m
ss
g
 is s

t to th
 us

s mo
il
 pho

. If th
 SMS m
ss
g
 


iv
s o
 th
 mo
il
 pho

 th
 co
figu

tio
 is 



y fo
 th
 

xt st
p.

[![sms t
st](im
g
s/sms-t
st-300x147.p
g)](im
g
s/sms-t
st.p
g)

Wh

 th
 fou
 m
i
 st
ps 


 p

fo
m

 it is possi
l
 to p

fo
m som
 optio

l 


itio

l st
ps such 
s:

- 

just th
 p
ssco

 policy to 

fl
ct to th
 o
g

iz
tio
 policy. Fo
 
x
mpl
 

just th
 mi
im
l p
ssco

 l

gth, compositio
 of th
 p
ssco

, lif
tim
 


 m
ss
g
 compositio
 fo
 th
 SMS m
ss
g
 th
t is s

t to th
 mo
il
 pho

.
- C


t
 
uth

tic
tio
 polici
s 


 lockout p

io
s s
tti
gs
- 



l
 G
o IP 


 IP histo
y lookup to i


tify wh


 i
 th
 wo
l
 you
 us

s 


 loggi
g-i
.
- Co
figu

 

t
 


 tim
 

st
ictio
s
- Co
figu

 th
 S
lf S

vic
 W

 Sit
. Th
 S
lf-s

vic
 w

 sit
 is fo
 m
i
t
i
i
g th
 us

s 
ccou
t s
tti
gs 


 P
sswo

 

s
ts.




 **

two
k Policy S

v

 (
PS)**

O
 th
 

two
k Policy S

v

 
 


IUS Cli

t p
ofil
 is c


t

. Th
 


IUS p
ofil
 poi
ts to th
 VMw


 Ho
izo
 Vi
w Co


ctio
 S

v

 (3) th
t is co
figu


 fo
 th
 
xt



l us

s. I
 this Cli

t p
ofil
 w
 

t

 th
 followi
g i
fo
m
tio
:

- F
i


ly 

m
.
- 

S o
 IP 




ss of th
 Co


ctio
 s

v

.
- M

u
lly 
ssig


 
 sh



 s
c

t th
t will 

 us

 fo
 th
 


IUS co


ctio
 

tw


 th
 
PS 


 Co


ctio
 S

v

.

[![
PS](im
g
s/
PS-300x178.p
g)](im
g
s/
PS.p
g)




 **VMw


 Ho
izo
 Vi
w 
xt



l Co


ctio
 S

v

 co
figu

tio
**

O
 th
 Ho
izo
 Vi
w Co


ctio
 S

v

 (3) fo
 th
 
xt



l 
cc
ss w
 co
figu

 2-f
cto
 
uth

tic
tio
 fo
 

mot
 
uth

tic
tio
 
i
l-I
 Us

 S

vic
 (


IUS). O
 th
 VMw


 Ho
izo
 Vi
w Co


ctio
 S

v

 w
 c


t
 
 


UIS p
ofil
 usi
g th
 followi
g s
tti
gs:

[![Co


ctio
 S

v

](im
g
s/Co


ctio
-S

v

-300x279.p
g)](im
g
s/Co


ctio
-S

v

.p
g) [![Vi
wCo


ctio
1](im
g
s/Vi
wCo


ctio
1-251x300.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2015/03/Vi
wCo


ctio
1.p
g)

I
 th
 p
im

y 
uth

tic
tio
 Host

m
/




ss th
 IP 




ss of th
 
PS s

v

. 
PS is i
st
ll

 o
 th
 SMS P
SSCO

 s

v

. Th
 s
m
 sh



 s
c

t is us

 f
om th
 
PS Cli

t co
figu

tio
.



 **Co


cti
g to th
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t**


xt



lly us

s co


ct to th
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t 
y usi
g th
 VMw


 Vi
w Cli

t 


 HTML 
cc
ss.




 **VMw


 Ho
izo
 Vi
w Cli

t**

Wh

 co


cti
g 
xt



lly to th
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t 
y usi
g th
 Ho
izo
 Vi
w Cli

t, th
 followi
g logi
 
ox 
pp


s i
 th
 Ho
izo
 Vi
w Cli

t:

[![VI
wcli

t](im
g
s/VI
wcli

t-300x173.p
g)](im
g
s/VI
wcli

t.p
g)


ft

 

t

i
g th
 

 us

 

m
 


 p
sswo

 c




ti
ls, 
 O

-Tim
-P
ssco

 (OTP) is s


 th
 us

 mo
il
 pho

.

[![Ipho

](im
g
s/Ipho

-169x300.p
g)](im
g
s/Ipho

.p
g)



t

i
g th
 OTP i
 th
 

xt Co

: fi
l
 


 you'

 
uth

tic
t

 to th
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t 


 you s

 you
 pool 

titl
m

ts.

[![

xt co

](im
g
s/

xt-co

-300x156.p
g)](im
g
s/

xt-co

.p
g)




 **HTML 
cc
ss**



oth

 optio
 is to co


ct to th
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t is 
y usi
g HTML 
cc
ss. This optio
 
o
s 
ot 

qui

 

y softw


 oth

 th

 
 suppo
t

 

ows

 such 
s I
, Ch
om
 o
 Fi

fox o
 th
 cli

t. HTML 
cc
ss us
s th
 
l
st p
otocol i
st


 of th
 PCoIP p
otocol.  Th
 logi
 st
ps 


 th
 s
m
 
s th
 Ho
izo
 Vi
w cli

t.

 **[![html5](im
g
s/html51-300x144.p
g)](im
g
s/html51.p
g) [![html5-1](im
g
s/html5-11-300x157.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2015/04/html5-11.p
g) [![html5-3](im
g
s/html5-31-300x160.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2015/04/html5-31.p
g)** 



 **Co
clusio
**

SMS P
SSCO

 is 
 multif
cto
 solutio
 th
t 


s 

 
xt

 s
cu
ity l
y

 to th
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t. SMS P
SSCO

 h
s th
 followi
g p
os:

- St

l
 


 fl
xi
l
 p
o
uct. W
 t
st

 SMS P
SSCO

 fo
 s
v


l mo
ths 


 it is 
 v

y st

l
 p
o
uct. W
 
xp

i

c

 
o c

sh
s o
 st


g
 thi
gs 
u
i
g ou
 t
sts.
- Simpl
 i
st
ll
tio
, co
figu

tio
 


 m
i
t
i
i
g
- C

 

 us

 i
 Sm
ll 


 Mi
siz
 
usi

ss (SM
) till l

g
 

t

p
is
 (24x7) 

vi
o
m

ts (sc
l

l
).
- 
o 
xt

 softw


 is 





 o
 th
 us

s mo
il
 pho


- 
o h


w


-tok

s 


 






- 

c
us
 


IUS 
uth

tic
tio
 is us

, it wo
ks with 

w v

sio
s of VMw


 Ho
izo
 Vi
w out of th
 
ox.

Fo
 SMS P
SSCO

 
 Wi

ows Op


ti
g Syst
m is 





. It woul
 

 g


t if i
 th
 futu

 

 
ppli

c
 v

sio
 c

 

 us

 wihout th
 



 of 
 Wi

ows Op


ti
g Syst
m.

Wh

 wo
ki
g with 
xt



l us

s th
t co


ct to you
 VMw


 Ho
izo
 Vi
w 

vi
o
m

t 

 
xt

 s
cu
ity l
y

 is 





 

si

s th
 st





 us



m
 


 p
sswo

.

SMS P
SSCO

 off

s th
t 
xt

 l
y

 of s
cu
ity 
y usi
g 2-f
cto
 o
 Multi-F
cto
 
uth

tic
tio
.




 **Mo

 i
fo
m
tio
**

W

t to t
y SMS P
SSCO

 liv
 o
 

qu
st 
 f


 30 

y t
i
l? Click th
 li
k. **v
xp

ts c

 o
t
i
 
 
F
 lic

s
** 
y s


i
g 

 
m
il to suppo
t@smsp
ssco

.com. P
ovi

 som
 
ocum

t
tio
 th
t p
ov
s you 


 
 v
xp

t.






