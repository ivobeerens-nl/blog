---
titl
: "T
ou
l
shoot VMw


 Vi
w S
cu
ity S

v

 PCoIP po
t p
o
l
ms"


t
: "2013-07-26T11:21:57.000Z"
c
t
go
i
s: 
  - "pcoip-2"
  - "t
ou
l
shooti
g"
  - "VMw


-vi
w"
t
gs: 
  - "pcoip"
  - "t
ou
l
shooti
g"
  - "VMw


-vi
w"

utho
: Ivo 





s
---

> Th
 co


ctio
 to th
 

mot
 comput

 






Wh

 th
 us

s co


cts to th
 Vi
w 

sktop usi
g th
 L

 (without th
 S
cu
ity S

v

) 
v

ythi
g wo
k

 fi

. I susp
ct

 th
t 
 PCoIP po
t (4172 TCP 


 U
P) is 
lock

 

tw


 th
 S
cu
ity S

v

 


 

sktop pool o
 vic
 v

s
. 

To t
ou
l
shoot this p
o
l
m I us

 th
 tool “

tc
t”. With 

tc
t TCP 


 U
P po
ts c

 

 ch
ck

 (T
l

t c

 o
ly ch
ck TCP po
ts). So I us

 

tc
t  to ch
ck th
 TCP 


 U
P po
ts 

tw


 th
 S
cu
ity s

v

 


 Vi
w 

sktop (1) 


 th
 Vi
w 

sktop to th
 S
cu
ity S

v

(2).

[![im
g
](im
g
s/im
g
_thum
9.p
g "im
g
")](im
g
s/im
g
9.p
g)

H


 is 

 
x
mpl
 how to us
 

tc
t:

**O
 th
 Vi
w 

sktop  
u
 

tc
t  to list

 to U
P po
t 4172**:


c –l –u –p 4172

**O
 th
 s
cu
ity s

v

 
u
 

tc
t to co


ct to th
 Vi
w 

sktop o
 U
P po
t 4172**:


c –u ip




ss 4172

You c

 typ
 som
 t
xt 


 p

ss 

t

. Th
 t
xt typ

 i
 th
 sc



 must 

 
ispl
y

 o
 
oth si

s, If 
ot th
 po
t is 
lock

.

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
10.p
g)

So I 
iscov



 th
t th
 4172 U
P p
otocol f
om th
 Vi
w 

sktop pool to th
 S
cu
ity s

v

 w
s 
lock

 
y 
 fi

w
ll. 
ft

 op

i
g this po
t i
 th
 fi

w
lls th
 p
o
l
m w
s solv

.

Mo

 i
fo
m
tio
:  

tc
t fo
 Wi

ows c

 

 
ow
lo



 [h


](http://jo
c

to
.o
g/
log/

tc
t-fo
-wi

ows).






