---
titl
: "C


t
 Wi

ows VMs i
 
zu

 with T



fo
m"


t
: "2023-03-27T17:42:30.000Z"
c
t
go
i
s: 
  - "
zu

"
  - "t



fo
m"
t
gs: 
  - "
zu

"
  - "t



fo
m"

utho
: Ivo 





s
---

I
 this 
x
mpl
, 

 
zu

 VM is c


t

 usi
g 
xisti
g 
zu

 

sou
c
s (

sou
c
 G
oup, V

t, 


 Su


t) with th
 followi
g s
tti
gs:

- 
 Wi

ows S

v

 2022 o
 Wi

ows 11 22H2 

t

p
is
 multi-s
ssio
 VM with th
 optio
s t
ust

 l
u
ch, s
cu

 
oot, 


 vTPM 



l


- Th
 VM h
s 
 pu
lic 


 p
iv
t
 IP 




ss o
 o
ly 
 p
iv
t
 IP 




ss
- Wh

 

fi
i
g 
 pu
lic IP 




ss, 
 

two
k S
cu
ity G
oup (
SG) is c


t

 with 

 

P 
ul
 th
t o
ly 
llows th
 
xt



l IP 




ss
- 
 Custom Sc
ipt 
xt

sio
 th
t 
ow
lo

s 


 
x
cut
s 
 Pow

Sh
ll sc
ipt
- 
utom
tic
lly Shut
ow
 th
 VM 
t 
 giv

 tim



ft

 th
 t
st compl
t
s, th
 VM is 

st
oy

 
y T



fo
m. Wh

 c


ti
g im
g
s (gol


 im
g
s) I us
 oth

 tools such 
s H
shico
p P
ck

 fo
 
x
mpl
.



 Fil
 st
uctu



I
 th
 T



fo
m fil
 st
uctu

, th
 followi
g fil
s 


 c


t

:

**t



fo
m.tfv

s -** Th
 v
lu
s of th
 v

i

l
s 


 

fi


 i
 this fil
. This is th
 o
ly fil
 th
t's 





 to 

 mo
ifi

. **v

i

l
s.tf -** Co
t
i
s 
ll th
 

fi


 v

i

l
s. **p
ovi


.tf -** Co
t
i
s th
 
zu

 Clou
 p
ovi


 T



fo
m commu
ic
t
s with. **m
i
.tf -** This is th
 m
i
 co
figu

tio
 fil
 fo
 c


ti
g th
 VM

I
 

 
xisti
g 

vi
o
m

t, w
 
l



y h
v
 

sou
c
s th
t 


 
ot m


g

 
y T



fo
m 
s p

t of th
 

ploym

t. I
 th
 **t



fo
m.tfv

s** fil
 w
 c

 

fi

 th
 

m
s of th
 
xisti
g 

sou
c
s th
 VM is goi
g to us
 such 
s:

- 

sou
c
 G
oup
- 

gio

- Th
 V

T
- Th
 Su


t



 t



fo
m.tfv

s

I
 th
 **t



fo
m.tfv

s**, 
ll th
 v
lu
s of th
 v

i

l
s 


 

fi


. I us
 comm

ts (si
gl
 li

) 


 comm

t 
locks with th
 followi
g sy
t
x:

\[co

 l

gu
g
="Pow

Sh
ll"\] Si
gl
 li

 

gi
 with: // Multipl
 li

s: 

gi
s with: /\* 


 


s with \*/ \[/co

\]

Th
 comm

t 
locks 


 us

 fo
 
xclu
i
g multipl
 li

s f
om th
 T



fo
m fil
s.

**vm\_

m
 -** Th
 

m
 of th
 VM **vm\_
g -** 

 
xisti
g 

sou
c
 G
oup wh


 th
 VM 

sou
c
s will 

 c


t

 **v

t\_
g -** 

 
xisti
g V

t 

sou
c
 g
oup **v

t\_

m
 -** 

 
xisti
g V

t 

m
 **vm\_siz
 -** VM typ
 **vm\_us



m
 -** Loc
l 

mi
ist

to
 us



m
 **t
g\_

vi
o
m

t -** 

vi
o
m

t t
g

**Op


ti
g Syst
m**

Wi

ows S

v

 2022 


 Wi

ows 11 22H2 

t

p
is
 multi-s
ssio
 with t
ust

 l
u
ch, s
cu

 
oot, 


 vTPM 



l

 


 

fi


. S
l
ct o

 OS.

Wi

ows 11 22H2 

t

p
is
 Multi-S
ssio


\[co

 l

gu
g
="Pow

Sh
ll"\] off

 = "Wi

ows-11" pu
lish

 = "mic
osoftwi

ows

sktop" sku = "wi
11-22h2-
v
" \[/co

\]

Wi

ows S

v

 2022

\[co

 l

gu
g
="Pow

Sh
ll"\] off

 = "wi

owss

v

" pu
lish

 = "mic
osoftwi

owss

v

" sku = "2022-

t
c

t

-
zu

-

itio
" \[/co

\]

**vm\_sto

g
 -** Typ
 of sto

g
 us

 **vm\_tim
zo

 -** Which Tim
zo

 is us

 **fil
\_u
is -** Fil
 loc
tio
 of th
 Custom Sc
ipt 
xt

sio
 **vm\_shut
ow
 -** VM shut
ow
 tim


Ch

g
 th
 v
lu
s to you
 



s.



 P
iv
t
/Pu
lic IP 




ss

Wh

 

ployi
g  VMs it is 
ot 

comm




 to giv
 th
m 
 pu
lic IP 




ss 

c
us
 
v

yo

 c

 co


ct to th
 VM f
om outsi

 th
 

two
k.  
ut without 
 VP
 co


ctio
, you 



 
 pu
lic IP fo
 co


cti
g th
 VM 
y 

P fo
 
x
mpl
. Wh

 

ployi
g 
 VM with 
 pu
lic IP 




ss m
k
 su

 to c


t
 
 

two
k S
cu
ity G
oup (
SG) with 

 

P 
ul
 th
t o
ly 
llows th
 pu
lic IP 
cc
ss to th
 VM. Th
 cool thi
g is th
t th
 pu
lic IP is 
ot h


co


 i
 th
 sc
ipt. 
 s

vic
 c
ll

 https://
pi.ipify.o
g will g
t th
 pu
lic IP 




ss.

Pu
lic IP 




ss

[![](im
g
s/
sg-300x186.jpg)](im
g
s/
sg.jpg)

If you h
v
 
 VP
 co


ctio
 
 p
iv
t
 IP is suffici

t. Th
 followi
g li

s c

 

 
xclu


:

\[co

 l

gu
g
="Pow

Sh
ll"\] // 
ot 





 wh

 usi
g 
 VP
 o
 

stio
 pu
lic\_ip\_




ss\_i
 = 
zu


m\_pu
lic\_ip.pu
lic\_ip.i
 \[/co

\]

**


 th
 

P 
ul
:**

\[co

 l

gu
g
="Pow

Sh
ll"\] // 
ot 





 wh

 usi
g 
 VP
 o
 

stio
 // 
SG S
cu
ity 

P 
ul
(s) 

sou
c
 "
zu


m\_

two
k\_s
cu
ity\_
ul
" "vm-s
c-
ul
" { 
cc
ss = "
llow" 

sti

tio
\_




ss\_p

fix = "\*" 

sti

tio
\_po
t\_


g
 = "3389" 
i

ctio
 = "I

ou

" 

m
 = "

P" 

two
k\_s
cu
ity\_g
oup\_

m
 = 
zu


m\_

two
k\_s
cu
ity\_g
oup.vm-
sg.

m
 p
io
ity = 100 p
otocol = "Tcp" 

sou
c
\_g
oup\_

m
 = 

t
.
zu


m\_

sou
c
\_g
oup.vm-
g.

m
 sou
c
\_




ss\_p

fix
s = loc
l.
utho
iz

\_ip\_


g
s sou
c
\_po
t\_


g
 = "\*" 

p


s\_o
 = \[ 
zu


m\_

two
k\_s
cu
ity\_g
oup.vm-
sg, \] } \[/co

\]



 Custom Sc
ipt 
xt

sio


Th
 
zu


m\_vi
tu
l\_m
chi

\_
xt

sio
 

sou
c
, 
ow
lo

s 


 
u
 
 sc
ipt i
 th
 VM 
s 
 post-

ploym

t t
sk. 
s 
 loc
tio
, I us
 my ow
 GitHu
 

posito
y. I
 th
 

posito
y is 
 Pow

Sh
ll sc
ipt th
t p

fo
ms th
 followi
g post-

ploym

t t
sks:

- 
llow ICMP pi
g 

qu
sts to th
 VM
- S
t th
 Pow

 M


g
m

t p
ofil
 to "High P

fo
m

c
"
- C


t
 
 c:
t
mp fol



- S
t th
 OS l


l to Op


ti
gSyst
m
- I
st
ll th
 Chocol
t
y p
ck
g
 m


g


- I
st
ll Visu
l Stu
io Co


- I
st
ll 
ot
P

++



 
utom
tic
lly shut
ow


With th
 
zu


m\_

v\_t
st\_glo

l\_vm\_shut
ow
\_sch

ul
 

sou
c
, you c

 co
t
ol th
 shut
ow
 tim
 of th
 VM. This c

 

 us
ful if you w

t to stop (


lloc
t

) th
 VM to s
v
 costs. I
 th
 **t



fo
m.tfv

s** fil
, you s
t th
 **vm\_shut
ow
** v
lu
.



 C


t
 th
 VM

To 
u
 T



fo
m, 
x
cut
 st
p 1 till 3 fou

 h


: [li
k](https://githu
.com/i





s/T



fo
m/
lo
/m
i
/



M
.m
)

Fi
st, i
iti
liz
 t



fo
m which 
ow
lo

s th
 T



fo
m p
ovi


(s) 

fi


:

\[co

 l

gu
g
="Pow

Sh
ll"\] t



fo
m i
it \[/co

\]

Th
 p
sswo

 is 
ot h


co


 i
 th
 **t



fo
m.tfv

s** fil
. With th
 T



fo
m 
pply comm


 you c

 s
t th
 p
sswo

 fo
 th
 v

i

l
 "vm\_p
sswo

". Th
 
pply optio
 c


t
s 
 pl

 


 
x
cut
s this.  Th
 **--
uto-
pp
ov
** optio
 
o
s
't 
sk fo
 co
fi
m
tio
 to 
pply ch

g
s:

\[co

 l

gu
g
="Pow

Sh
ll"\] t



fo
m 
pply -v

 "vm\_p
sswo

=Thisis
Goo
P
sswo

!" --
uto-
pp
ov
 \[/co

\]


ft

 
 coupl
 of mi
ut
s, th
 VM is c


t

 


 th
 p
iv
t
 


 pu
lic IP 




ss
s 


 
ispl
y

 
s output v
lu
s.

![](im
g
s/T



fo
m-1024x534.jpg)



 

st
oyi
g th
 Wi

ows VM

Wh

 fi
ishi
g with t
sti
g th
  VM c

 

 

st
oy

 without 

st
oyi
g th
 
xisti
g 

sou
c
s such 
s:

- 

sou
c
 G
oup
- Th
 V

t
- Th
 Su


t

Th
 followi
g comm


 

st
oys th
 VM just c


t

:

\[co

 l

gu
g
="Pow

Sh
ll"\] t



fo
m 

st
oy -v

 "vm\_p
sswo

=Thisis
Goo
P
sswo

!" --
uto-
pp
ov
 \[/co

\]



 Co
clusio


This 
x
mpl
 shows o

 of th
 st


gths of T



fo
m. You o
ly 



 to ch

g
 
 si
gl
 fil
 (**t



fo
m.tfv

s**) o
c
 th
t i
clu

s th
 v
lu
s of th
 v

i

l
s. With 
 si
gl
 comm


, you c


t
 
 VM i
 
 coupl
 of mi
ut
s, 


 with 
 si
gl
 comm


, you 

st
oy th
 VM with 
ll th
 

sou
c
s you c


t

. V

y pow

ful!

Th
 GitHu
 

posito
y c

 

 fou

 h


: [Li
k](https://githu
.com/i





s/T



fo
m/t


/m
i
/

w-VM)






