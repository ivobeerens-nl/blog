---
titl
: "C


t
 
 Wi

ows 11 VM i
 Hyp

-V with P
ck

"


t
: "2023-08-31T06:00:39.000Z"
c
t
go
i
s: 
  - "hyp

-v"
  - "p
ck

"
  - "wi

ows-11"
t
gs: 
  - "hyp

-v-2"
  - "p
ck

"
  - "wi

ows11"

utho
: Ivo 





s
---

So I 

ci


 to t
st P
ck

 with Hyp

-V 


 Wi

ows 11 


 c


t
 
 
log post 

out it.



 So wh
t 


 th
 p



quisit
s?

- M
k
 su

 th
 Hyp

-V 
ol
 is 



l

 i
 Wi

ows 10/11
- 
ow
lo

 th
 Wi

ows 11 ISO 


 s
v
 th
 ISO to th
 followi
g loc
tio
: c:
iso 

 
x
mpl
 of 
ow
lo

i
g 


 c


ti
g 
 Wi

ows 10/11 ISO c

 

 fou

 h


: https://www.ivo





s.
l/2021/05/19/quick-tip-
ow
lo

-th
-l
t
st-wi

ows-10-iso-fil
/
- I
st
ll th
 Wi

ows 
ss
ssm

t 


 

ploym

t Kit (32-
it v

sio
). https://l



.mic
osoft.com/

-us/wi

ows-h


w


/g
t-st

t

/

k-i
st
ll

ow
lo

-th
-

k-fo
-wi

ows-11-v

sio
-22h2
- 


 th
 followi
g loc
tio
 th
 th
 syst
m p
th v

i

l
: C:
P
og

m Fil
s (x86)
Wi

ows Kits
10

ss
ssm

t 


 

ploym

t Kit


ploym

t Tools
x86
Osc
img

Wh

 th
 p



quisit
s 


 m
t you c

 go fu
th

 with th
 

st. To m
k
 it 

sy I c


t

 
 Pow

Sh
ll sc
ipt c
ll

 **\_1.
uil
.ps1** ([li
k](https://githu
.com/i





s/p
ck

/
lo
/m
i
/hyp

-v/wi

ows11/_1.
uil
.ps1)) th
t 
o
s 
ll th
 wo
k fo
 you.

\[co

 l

gu
g
="Pow

Sh
ll"\] 
 



l
 TLS 1.2 \[

t.S

vic
Poi
tM


g

\]::S
cu
ityP
otocol = \[

t.S
cu
ityP
otocolTyp
\]::Tls12 
 Sp


 up th
 i
vok
-w



qu
st comm


 $P
og

ssP

f



c
 = 'Sil

tlyCo
ti
u
'

\
 V

i

l
s $
ow
lo

fol


 = "C:
t
mp
" 
 P
ck

 loc
tio
 i
st
ll

 $wi
11\_
ow
lo

fol


 = "C:
T
mp
p
ck

-m
i

hyp

-v
wi

ows11
" $p
ck

\_co
fig = "wi

ows.jso
.pk
.hcl" 
P
ck

 co
fig fil
 $p
ck

\_v

i

l
 = "wi

ows.
uto.pk
v

s.hcl" 
 P
ck

 v

i

l
 fil
 $githu
 = "https://githu
.com/i





s/p
ck

/

chiv
/

fs/h


s/m
i
.zip" $p
o
uct = "p
ck

" $p
ck

\_u
i = "https://

v
lop

.h
shico
p.com/p
ck

/
ow
lo

s"

\
 Ch
ck if th
 t
mp fol


 
xist If(!(t
st-p
th -P
thTyp
 co
t
i


 $
ow
lo

fol


)) { 

w-It
m -It
mTyp
 
i

cto
y -P
th $
ow
lo

fol


 }

\
 Go to th
 P
ck

 
ow
lo

 fol


 S
t-Loc
tio
 $
ow
lo

fol




\
 
ow
lo

 Githu
 fil
s I
vok
-W



qu
st -U
i $githu
 -OutFil
 ${
ow
lo

fol


}p
ck

.zip 
xp


-

chiv
 ${
ow
lo

fol


}p
ck

.zip -

sti

tio
P
th $
ow
lo

fol


 -Fo
c


\
 

mov
 zip fil
 

mov
-It
m -P
th ${
ow
lo

fol


}p
ck

.zip

\
 
ow
lo

 th
 l
t
st v

sio
 of P
ck

 $p
cku
l = I
vok
-W



qu
st -U
i $p
ck

\_u
i| S
l
ct-O
j
ct -
xp


 li
ks | Wh


-O
j
ct h

f -m
tch "//

l

s
s
.h
shico
p
.com/$p
o
uct/

.\*/$p
o
uct\_.\*\_wi

ows\_
m
64
.zip$" | S
l
ct-O
j
ct -
xp


 h

f $p
ck
ow
 = $p
cku
l | Split-P
th -L

f $p
ck
ow
lo

 = $
ow
lo

fol


 + $p
ck
ow
 I
vok
-W



qu
st $p
cku
l -outfil
 $p
ck
ow
lo



\
 U
zip P
ck

 
xp


-

chiv
 $p
ck
ow
lo

 -

sti

tio
P
th $wi
11\_
ow
lo

fol


 -Fo
c
 
 

mov
 th
 P
ck

 ZIP fil
 

mov
-It
m $p
ck
ow
lo



\
 Go to th
 P
ck

 
ow
lo

 fol


 S
t-Loc
tio
 $wi
11\_
ow
lo

fol




\[/co

\]

- Li

 **7-13**: This is th
 v

i

l
 
lock. Ch

g
 if 






- Li

 **13-19**: H


 


 th
 v

i

l
s loc
t

. Ch

g
 if 






- Li

 **21-25**: Th
 sc
ipt c


t
s 
 c:
t
mp fol


 if it 
o
s 
ot 
xist
- Li

 **30-32**: 
ow
lo

s th
 GitHu
 fil
s fo
 c


ti
g 
 Wi

ows 11 VM
- Li

 **37-41:** 
ow
lo

s th
 l
t
st v

sio
 of P
ck




ft

 
u

i
g th
 **\_1.
uil
.ps1** sc
ipt it is tim
 to ch

g
 th
 v

i

l
s:

- G
t th
 h
sh of th
 ISO fil
 with th
 Pow

Sh
ll G
t-Fil
h
sh comm


 


 ch

g
 th
 v

i

l
 i
 th
 **wi

ows-
uto-pkv

s.hcl** fil

- Ch

g
 th
 oth

 v

i

l
s i
 th
 wi

ows-
uto-pkv

s.hcl such 
s **wi
\_iso** fo
 th
 
x
ct iso 

m

- 
u
 th
 followi
g **\_2.
u
\_p
ck

.ps1** sc
ipt

\[co

 l

gu
g
="Pow

Sh
ll"\] 
 Show P
ck

 V

sio
 .
p
ck

.
x
 -v

\
 
ow
lo

 P
ck

 plugi
s .
p
ck

.
x
 i
it "${$wi
11\_
ow
lo

fol


}${p
ck

\_co
fig}"

\
 P
ck

 Fo
m
t co
figu

tio
 fil
s (.pk
.hcl) 


 v

i

l
 fil
s (.pk
v

s.hcl) 


 up

t

. .
p
ck

.
x
 fmt -v

-fil
="${$wi
11\_
ow
lo

fol


}{$p
ck

\_v

i

l
}" "${$wi
11\_
ow
lo

fol


}${p
ck

\_co
fig}"

\
 P
ck

 v
li

t
 .
p
ck

.
x
 v
li

t
 .

\
 P
ck

 
uil
 .
p
ck

.
x
 
uil
 -fo
c
 -v

-fil
="${$wi
11\_
ow
lo

fol


}${p
ck

\_v

i

l
}" "${$wi
11\_
ow
lo

fol


}${p
ck

\_co
fig}" \[/co

\]

- Li

 **2**: Show th
 P
ck

 v

sio

- Li

 **5**: 
ow
lo

 P
ck

 plugi
s such 
s th
 hyp

-v 


 Wi

ows up

t
 plugi

- Li

 **8**: Fo
m
ts th
 co
fig 


 v

i

l
 HCL fil
 sy
t
x
- Li

 **11**: P

fo
ms 
 v
li

tio
 to m
k
 su

 th
 v

i

l
 


 co
fig fil
 


 ok
- Li

 **15**: St

ts P
ck

 to c


t
 
 Wi

ows 11 VM

![](im
g
s/i
st
ll-1024x854.p
g)

Th
 c


tio
 of 
 Wi

ows 11 VM st

ts. Wh

 th
 im
g
 is c


t

 it is sto


 


 



s to 

 impo
t

 i
 th
 Hyp

-V m


g

.

- St

t th
 Hyp

-V M


g


- S
l
ct Impo
t Vi
tu
l M
chi


- 

ows
 to th
 c


t

 im
g
 fol


 C:
T
mp
p
ck

-m
i

hyp

-v
wi

ows11
output-wi

ows11

- S
l
ct th
 VM
- 

gist

 th
 VM i
-pl
c

- St

t th
 VM

![](im
g
s/wi
11-1024x854.jpg)

O
 my l
ptop, I h
v
 i
 35 mi
ut
s 
 f

sh copy of Wi

ows 11 
u

i
g with th
 l
t
st up

t
s i
st
ll

 
u

i
g i
 Hyp

-V. How cool is th
t! Th
 sc
ipts c

 

 fou

 o
 my GitHu
 p
g
 ([li
k](https://githu
.com/i





s/p
ck

/t


/m
i
/hyp

-v/wi

ows11)). H
v
 fu
 c


ti
g Wi

ows 11 VMs.






