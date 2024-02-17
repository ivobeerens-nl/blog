---

utho
: Ivo 





s
titl
: "How-to 
xt


 th
 VM
K 


 th
 Wi

ows 
isk"


t
: "2008-08-08T13:36:29.000Z"
c
t
go
i
s: 
  - "VMw


 VM T
ou
l
shooti
g"
t
gs: 
  - "VMw


"
  - "VM"
  - "T
ou
l
shooti
g"
u
l: /2008/08/08/
xt


-vm
k-
isk-


-th
-wi

ows-
isk/
---

I s

 
 lot of 

vi
o
m

ts wh


 th
 Vi
tu
l M
chi

 (VM) 
isk sp
c
 must 

 
xt




.

P
io
 
SX 3.5 th
 w
y to 
xt


 
 V
MK w
s to us
 th
 vmkfstools comm


 with th
 -X p


m
t

 f
om th
 VMw


 
SX s

v

 co
sol
. With th
 comi
g of 
SX 3.5 it is possi
l
 to 
xt


 th
 VM
K fil
 wh

 th
 VM w
s shut
ow
. 
ow  with VMw


 
SX 3.5 Up

t
 2 it is possi
l
 to o
li

 (hot) 
xt


 th
 VM
K fil
.

I
 th
 Vi
tu
l I
f

st
uctu

 Cli

t (VIC) go to th
 VM 


 

it th
 s
tti
gs, click o
 th
 
isk th


 is 
 p
op

ty 

w Siz
 (figu

 1).

[![im
g
](im
g
s/im
g
-thum
.p
g)](im
g
s/im
g
.p
g)

Figu

 1. Th
 VM 
isk 
xt


 fu
ctio


Th
 fi
st st
p is to s

 if th


 is 

ough f


 sp
c
 o
 th
 LU
 (

t
sto

). You c

 ch
ck th
 
isk sp
c
 (


ltim
) 
y usi
g th
 comm


 v
f -h o
 th
 
SX s

v

 co
sol
 o
 i
 
 SSH s
ssio
. K

p i
 mi

 to h
v
 
 
v


g
 of 10% f


 o
 th
 LU
 fo
 s

pshots 


 sw
p fil
s 
tc. 

If th
 
isk sp
c
 o
 th
 LU
 is ok
y you c

 
xt


 th
 
isk. I
 this 
x
mpl
 w
 
xt


 th
 16G
 
isk to 20G
.

[![im
g
](im
g
s/im
g
-thum
1.p
g)](im
g
s/im
g
1.p
g)

Figu

 2. Th
 VM 
isk 
xt


 fu
ctio


Wh

 th
 VM
K is 
xt




 th
 
isk sp
c
 must 

 




 to th
 Wi

ows volum
.  I
 th
 Wi

ows 
isk m


g

 wh

 usi
g VMw


 
SX 3.5 Up

t
 2,  us
 th
 "

sc

 
isks" fu
ctio
 to 
iscov

 th
 

w 




 sp
c
 wh

 you us
 th
 hot 
xt


 fu
ctio
. Th
 

w 




 sp
c
 is s


 
s U

lloc
t



[![im
g
](im
g
s/im
g
-thum
2.p
g)](im
g
s/im
g
2.p
g)

Figu

 3. Wi

ows 
isk m


g



To 
xt


 th
 volum
 
y usi
g 
iskp

t us
 th
 followi
g comm


s:

- St

t - 
u
 - typ
 
iskp

t
- typ
 list volum

- typ
 s
l
ct volum
 1
- typ
 
xt


 Wh

 t
yi
g to 
xt


 th
 C p

titio
 with 
iskp

t you got th
 followi
g m
ss
g
 "Th
 volum
 you h
v
 s
l
ct

 m
y 
ot 

 
xt




"

[![im
g
](im
g
s/im
g
-thum
3.p
g)](im
g
s/im
g
3.p
g)

Figu

 4. 
iskp

t tool

It is 
ot possi
l
 to 
xt


 th
 syst
m- 


 
ootvolum
 
y usi
g th
 
iskp

t 
uilt-i
 comm


 (fo
 MS Vist
, Wi

ows 7 


 Wi

ows 2008 


 high

 you c

 
xt


 th
 volum
 
y usi
g 
iskp

t). Fo
 MS Wi

ows XP 


 MS Wi

ows 2003 th


 


 oth

 optio
s you c

 us
:
- 


 th
 syst
m- 


 
oot
isk volum
 to th
 oth

 Vi
tu
l
 M
chi

 (VM) 
s 
isk.  St

t th
 oth

 VM 


 us
 th
 
iskp

t comm


 to 
xt


 this 
isk o
 us
 

 3
 p

ty p

titio
 tool.
- Us
 th
 comm


 li

 tool f
om 

ll c
ll

 [
xtp

t](http://suppo
t.

ll.com/suppo
t/
ow
lo

s/
ow
lo

.
spx?c=us&cs=19&l=

&s=
hs&

l

s
i
=
64398&fo
m
tc
t=2&fil
i
=83929). Us
g
:  
xp

t \[

iv
\] \[siz
to
xt


\] 
- Us
 th
 Gp

t

 tool. You c

 
ow
lo

 th
 ISO fil
 f
om [h


](http://gp

t

.sou
c
fo
g
.

t/). Wh

 th
 
ow
lo

 compl
t
s uplo

 th
 ISO fil
 to you
 sto

g
 


 
tt
ch 


 co


ct th
 ISO th
 to th
 VM.

- ![im
g
](im
g
s/im
g
-thum
4.p
g)

Figu

 5. Co


ct th
 ISO fil
 to th
 VM

St

t th
 VM, th
 ISO g
ts st

t



[![im
g
](im
g
s/im
g
-thum
5.p
g)](im
g
s/im
g
5.p
g)

Figu

 6. St

t th
 Gp

t

 tool

- P

ss 

t



[![im
g
](im
g
s/im
g
-thum
6.p
g)](im
g
s/im
g
6.p
g)

Figu

 7. K
ym
p choic


- P

ss OK

[![im
g
](im
g
s/im
g
-thum
7.p
g)](im
g
s/im
g
7.p
g)

Figu

 8. K
y
o


 l
yout

- S
l
ct you
 k
y
o


 l
yout

[![im
g
](im
g
s/im
g
-thum
8.p
g)](im
g
s/im
g
8.p
g)

Figu

 10. X-wi

ows g

phic
l w


i
g

- P

ss 

t



[![im
g
](im
g
s/im
g
-thum
9.p
g)](im
g
s/im
g
9.p
g)

Figu

 11. GP

t

 P

itio
 tool

- Th
 p

titio
 l
yout is 
ispl
y

. S
l
ct th
 
isk th
 
xt


 


 p

ss 

siz
/Mov


[![im
g
](im
g
s/im
g
-thum
10.p
g)](im
g
s/im
g
10.p
g)

Figu

 12. P

titio
 

siz
 wi

ow

- 

t

 th
 

w siz
 o
 


g th
 


 th
 th
 
ight 


 p

ss th
 

siz
/ Mov
 
utto


[![im
g
](im
g
s/im
g
-thum
11.p
g)](im
g
s/im
g
11.p
g)

Figu

 13. P

titio
 

siz


- Click th
 
pply 
utto


[![im
g
](im
g
s/im
g
-thum
12.p
g)](im
g
s/im
g
12.p
g)

Figu

 14. P

titio
 

siz
 w


i
g

- P

ss 
pply

[![im
g
](im
g
s/im
g
-thum
13.p
g)](im
g
s/im
g
13.p
g)

Figu

 15. P

titio
 

siz
 p
oc
ss

- If th
 
xt


i
g p
oc
ss compl
t
s 


 is succ
ssfully, 


oot th
 syst
m 


 
isco


ct th
 ISO f
om th
 VM 


 

st

t th
 VM.

[![im
g
](im
g
s/im
g
-thum
14.p
g)](im
g
s/im
g
14.p
g)

Figu

 16. Wi

ows 
isk M


g



- 
ft

 th
 


oot, op

 th
 Wi

ows 
isk m


g

 


 you s

 th
 

w sp
c
 is 




 to th
 volum
.






