---
titl
: "Customiz
 th
 VMw


 
SXi 5 i
st
ll
tio
 m

i
 
y 


i
g th
 l
t
st p
tch
s usi
g Im
g
 
uil


"


t
: "2012-02-13T22:17:34.000Z"
c
t
go
i
s: 
  - "customiz
tio
"
  - "
sxi"
  - "im
g
-
uil


"
  - "VMw


"
t
gs: 
  - "customiz
tio
"
  - "
sxi-2"
  - "im
g
-
uil


"

utho
: Ivo 





s
---

I
 this 
log post 


 th
 st
ps outli


 o
 how-to c


t
 
 customiz

 VMw


 
SXi5 ISO with th
 l
t
st p
tch
s. 


i
g th
 l
t
st p
tch
s c

 

 us
ful 

c
us
 it co
t
i
s fo
 
x
mpl
 th
 up

t

 HP 
mul
x 

t-

2

t 

iv

 





 fo
 HP Fl
x-10 
SXi5 i
st
ll
tio
s.

Mo

 

iv

s c

 

 fou

 o
 th
 VMw


 
ow
lo

 sit
:

[![im
g
](im
g
s/im
g
_thum
11.p
g "im
g
")](im
g
s/im
g
13.p
g)

 





 P



qui

m

ts

1\. 
ow
lo

 


 i
st
ll Pow

CLI 5.x. Op

 Pow

CLI 


 s
t th
 

mot
 sig
i
g to 

mot
Sig


 
y usi
g th
 followi
g comm


:

**S
t-
x
cutio
Policy 

mot
Sig


**

2\. C


t
 
 fol


 st
uctu

 lik
 this:

> **<

iv
 l
tt

>:
Im
g

uil

SXi**

3\. 
ow
lo

 th
 VMw


 
SXi Offli

 
u

l
 f
om th
 VMw


 
ow
lo

 w

sit
 


 s
v
 th
 fil
 i
 **<

iv
l
tt

>:
Im
g

uil

SXi**

[![im
g
](im
g
s/im
g
_thum
4.p
g "im
g
")](im
g
s/im
g
4.p
g)

Th
 
SXi offli

 
u

l
 w
 us
 is 

m

 **
SXi500-201111001.zip**





 C


t
 
 customiz

 
SXi5 ISO

**1\. 


 th
 
SXi offli

 
u

l
 


 l
t
st p
tch
s to 

pots**




 th
 VMw


 
SXi offli

 
u

l
 


 th
 l
t
st p
tch
s us
 th
 **


-
sxSoftw




pot** comm


.  Fi
st 


 th
 offli

 
SXi 

pot 
y usi
g th
 followi
g comm


:

**


-
sxSoftw




pot F:
Im
g

uil

SXi

SXi500-201111001.zip**

 



tu

 
 list of 
ll th
 VMw


 I
st
ll
tio
 
u

l
 (VI
) o
j
cts, us
 th
 **G
t-
sxSoftw


P
ck
g
** comm


. This 
x
mpl
 list 
ll th
 softw


 p
ck
g
 (VI
) o
j
cts so
t

 o
 

l

s
 

t
:

**G
t-
sxSoftw


P
ck
g
 | s
l
ct 

m
,V

sio
,

l

s


t
 | so
t 

l

s


t
**

 




 th
 U
L of th
 p
tch 

pot (w
 us
 th
 VMw


 Up

t
 M


g

 U
L) usi
g th
 followi
g comm


:

**


-
sxSoftw




pot -

potU
l https://hostup

t
.VMw


.com/softw


/VUM/P
O
UCTIO
/m
i
/vmw-

pot-i


x.xml**

 

List th
 VMw


 I
st
ll
tio
 
u

l
 (VI
) o
j
cts 
g
i
 


 s

 th
 

w VI
s 




:

**G
t-
sxSoftw


P
ck
g
 | s
l
ct 

m
,V

sio
,

l

s


t
 | so
t 

l

s


t
**

 

<t

l
 
o



="0" wi
th="400" c
llsp
ci
g="0" c
llp


i
g="2"><t
o
y><t
><t
 v
lig
="top" wi
th="200"><
 h

f="im
g
s/im
g
5.p
g"><sp

 styl
="colo
: 
000000;"><img styl
="

ckg
ou

-im
g
: 
o

; m

gi
: 7px 0px; p


i
g-l
ft: 0px; p


i
g-
ight: 0px; 
ispl
y: i
li

; p


i
g-top: 0px; 
o



-wi
th: 0px;" titl
="im
g
" s
c="im
g
s/im
g
_thum
5.p
g" 
lt="im
g
" wi
th="250" h
ight="317" 
o



="0"></sp

></
></t
><t
 v
lig
="top" wi
th="200"><
 h

f="https://www.ivo





s.
l/wp-co
t

t/uplo

s/2012/02/im
g
7.p
g"><sp

 styl
="colo
: 
000000;"><img styl
="

ckg
ou

-im
g
: 
o

; m

gi
: 7px 0px; p


i
g-l
ft: 0px; p


i
g-
ight: 0px; 
ispl
y: i
li

; p


i
g-top: 0px; 
o



-wi
th: 0px;" titl
="im
g
" s
c="im
g
s/im
g
_thum
6.p
g" 
lt="im
g
" wi
th="233" h
ight="323" 
o



="0"></sp

></
></t
></t
><t
><t
 v
lig
="top" wi
th="200"><sp

 styl
="colo
: 
000000; fo
t-f
mily: 'Cou
i

 

w';"><st
o
g>output usi
g:</st
o
g></sp

><
iv></
iv>


-
sxSoftw




pot F:\Im
g

uil\
SXi\
SXi500-201111001.zip</t
><t
 v
lig
="top" wi
th="200"><sp

 styl
="fo
t-f
mily: 'Cou
i

 

w';"><st
o
g><sp

 styl
="colo
: 
000000;">output usi
g:</sp

></st
o
g></sp

><
iv></
iv><sp

 styl
="fo
t-siz
: sm
ll;">


-
sxSoftw




pot -

potU
l </sp

><
 h

f="https://hostup

t
.VMw


.com/softw


/VUM/P
O
UCTIO
/m
i
/vmw-

pot-i


x.xml"><sp

 styl
="colo
: 
000000; fo
t-f
mily: 'Cou
i

 

w'; fo
t-siz
: sm
ll;"><st
o
g>https://hostup

t
.VMw


.com/softw</st
o
g></sp

></
> <
 h

f="https://hostup

t
.VMw


.com/softw


/VUM/P
O
UCTIO
/m
i
/vmw-

pot-i


x.xml"><sp

 styl
="colo
: 
000000; fo
t-f
mily: 'Cou
i

 

w'; fo
t-siz
: sm
ll;"><st
o
g>


/VUM/P
O
UCTIO
/m
i
/vmw-

pot-i


x.xml</st
o
g></sp

></
></t
></t
></t
o
y></t

l
>

 

**2.** **Clo

 th
 
xisti
g im
g
 p
ofil
**


u
 th
 G
t-
sxIm
g
P
ofil
 cm
l
t to fi

 th
 

m
 of th
 p
ofil
 th
t you w

t to clo

.

**G
t-
sxIm
g
P
ofil
 | S
l
ct 

m
,C


tio
Tim
,
cc
pt

c
L
v
l | So
t C


tio
Tim
 | FT -
utoSiz
**

[![im
g
](im
g
s/im
g
_thum
7.p
g "im
g
")](im
g
s/im
g
8.p
g)

Clo

 th
 l
t
st im
g
 p
ofil
 usi
g this comm


:

**

w-
sxIm
g
P
ofil
 -Clo

P
ofil
 "
SXi-5.0.0-20111204001-st





" -

m
 "VMw


 
SXi5 custom" -V


o
 "





s"**

[![im
g
](im
g
s/im
g
_thum
8.p
g "im
g
")](im
g
s/im
g
9.p
g)

 

**3\. 
xpo
t th
 im
g
 p
ofil
 to ISO**


xpo
t 

 im
g
 p
ofil
 to 

 ISO im
g
 o
 
 ZIP fil
 of compo


t fil
s 


 fol


s. Th
 followi
g comm


 
xpo
t th
 im
g
 p
ofil
 to 

 ISO:

**
xpo
t-
sxIm
g
P
ofil
 -Im
g
P
ofil
 "VMw


 
SXi5 custom" –
xpo
tToIso -Fil
P
th F:
Im
g

uil

sxi5custom.iso**




 you 


 



y to 
oot f
om th
 

w i
st
ll
tio
 m

i
 

m

 **
sxi5custom.iso.** Ch
ck th
 followi
g compo


ts to s

 if th
 customiz
tio
 h
s th
 

si


 

sult:

- VMw


 
SXi 5 
oot M

u
- VMw


 
SXi 
uil

- Im
g
 P
ofil
 

m


 

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
11.p
g)

 

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
12.p
g)






