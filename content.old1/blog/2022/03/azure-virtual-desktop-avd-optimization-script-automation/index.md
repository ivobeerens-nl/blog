---
titl
: "Optimiz
 th
 
zu

 Vi
tu
l 

sktop (
V
) gol


 im
g
 
utom
tic
lly"


t
: "2022-03-25T11:01:55.000Z"
c
t
go
i
s: 
  - "
v
"
  - "
zu

-vi
tu
l-

sktop"
t
gs: 
  - "
v
"
  - "
zu

-vi
tu
l-

sktop"

utho
: Ivo 





s
---

- - U
iv

s
l Wi

ows Pl
tfo
m (UWP) 
pp cl


up
    - Optio

l F

tu

s cl


up
    - Loc
l policy s
tti
gs
    - Syst
m s

vic
s
    - Sch

ul

 t
sks
    - 
pply Wi

ows (


 oth

) up

t
s
    - 
utom
tic Wi

ows t

c
s
    - Wi

ows 

f




 optimiz
tio

    - Cli

t 

two
k p

fo
m

c
 tu
i
g 
y 

gist
y s
tti
gs
    - 


itio

l s
tti
gs f
om th
 "Wi

ows 

st
ict

 T

ffic Limit

 Fu
ctio

lity 

s
li

" gui


c
.
    - 
isk cl


up

Optimizi
g th
 
V
 Gol


 Im
g
 will imp
ov
 th
 Us

 
xp

i

c
, so it is highly 

comm




 to us
 it. V


o
s such 
s VMw


 (VMw


 OS Optimiz
tio
 Tool) 


 Cit
ix (Cit
ix Optimiz

 Tool) us
 th
i
 ow
 tools fo
 optimizi
g th
i
 Gol


 Im
g
s.

To optimiz
 

 
V
 im
g
 you must 
o som
 thi
gs m

u
lly 

fo

 you 
u
 th
 Vi
tu
l 

sktop Optimiz
tio
 Tool (V
OT). I c


t

 
 Pow

Sh
ll sc
ipt th
t 
ow
lo

s th
 l
t
st V
OT 


 optimiz
s th
 
V
 im
g
 
utom
tic
lly.

Th
 Pow

Sh
ll sc
ipt 

low 
o
s th
 followi
g:

- C


t
 
 fol


 o
 th
 
V
  VM c
ll

 c:
optimiz

- 
ow
lo

 th
 l
t
st Vi
tu
l 

sktop Optimiz
tio
 Tool
- 
xp


 th
 Vi
tu
l 

sktop Optimiz
tio
 Tool  zip fil
 to th
 c:
optimiz
 fol



- 

mov
 th
 V
OT 

chiv
 fil

- 
ow
lo

 
 mo
ifi

 
ppp
ck
g
s.jso
 fil
. Th
 

f
ult 
ppp
ck
g
s.jso
 fil
 will 



l
 
ll th
 
PPX p
ck
g
s.
- Copy th
 
ppp
ck
g
s.jso
 fil
 to th
 co
figu

tio
 fol


 fo
 

ch 
uil

- U

lock 
ll th
 
ow
lo



 fil
s
- 
x
cut
 th
 Vi
tu
l 

sktop Optimiz
tio
 Tool
- 

mov
 th
 c:
optimiz
 fol



- 


oot th
 
V
 host

\[co

 l

gu
g
="Pow

Sh
ll"\] <
 .SY
OPSIS Vi
tu
l 

sktop Optim
liz
tio
 Tool (V
OT) .

SC
IPTIO
 
ow
lo

 th
 Vi
tu
l 

sktop Optim
liz
tio
 Tool (V
OT), c


t
s 
 fol


 c
ll

 optimiz
 


 
u
s V
OT tool. Th
 V
OT tool 

t

mi

s OS v

sio
 
t 
u
-tim
 .
OT
S V

sio
: 1.0 
utho
: Ivo 





s i
fo@ivo





s.
l C


tio
 

t
: 25-02-2022 Pl
ttfo
m: 
zu

 VI
tu
l 

sktop (
V
) Ch

g
log: 25-05-2022 1.0 - I
iti
l sc
ipt 

v
lopm

t .COMPO


T

.LI
K .
x
mpl
 Sc
ipt 



s to 

 
u
 with Pow

Sh
ll 
l
v
t

 
>

\
 V

i

l
s $v


os
P

f



c
 = 'Co
ti
u
' $v
ot = 'https://githu
.com/Th
-Vi
tu
l-

sktop-T

m/Vi
tu
l-

sktop-Optimiz
tio
-Tool/

chiv
/

fs/h


s/m
i
.zip' $
ppp
ck
g
s = 'https://

w.githu
us

co
t

t.com/i





s/
V
/m
i
/v
ot/Co
figFil
s/
ppxP
ck
g
s.jso
' $v
ot\_loc
tio
 = 'c:
Optimiz
' $v
ot\_loc
tio
\_zip = 'c:
Optimiz

v
ot.zip' $
ppp
ck
g
s\_loc
tio
 = 'C:
Optimiz


ppxP
ck
g
s.jso
'

\
 



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

\
 Cl


 sc



 Cl




\
 C


t
 Fol


 $ch
ck
i
 = T
st-P
th -P
th $v
ot\_loc
tio
 if ($ch
ck
i
 -
q $f
ls
){ W
it
-V


os
 "C


ti
g '$v
ot\_loc
tio
' fol


" 

w-It
m -P
th 'c:
' -

m
 'Optimiz
' -It
mTyp
 '
i

cto
y' | Out-
ull } 
ls
 { W
it
-V


os
 "Fol


 '$v
ot\_loc
tio
' 
l



y 
xists." }

\
 
ow
lo

 V
OT W
it
-V


os
 "
owmlo

 V
OT" I
vok
-W



qu
st -U
i $v
ot -OutFil
 $v
ot\_loc
tio
\_zip

\
 
xp


 

chiv
 W
it
-V


os
 "
xp


 

chiv
" 
xp


-

chiv
 $v
ot\_loc
tio
\_zip -

sti

tio
P
th $v
ot\_loc
tio
 -V


os
 -Fo
c


\
 

mov
 

chiv
 W
it
-V


os
 "

mov
 

chiv
" 

mov
-It
m $v
ot\_loc
tio
\_zip

\
 
ow
lo

 
ppP
ck
g
s W
it
-V


os
 "
owmlo

 
ppp
ck
g
s.jso
 
PPX fil
" I
vok
-W



qu
st -U
i $
ppp
ck
g
s -OutFil
 $
ppp
ck
g
s\_loc
tio


\
 Copy th
 
ppP
ck
g
 fil
 to 
ll v

sio
s W
it
-V


os
 "Copy 
ppp
ck
g
s.jso
 to 
ll co
figu

tio
fil
s fol


s" Copy-It
m $
ppp
ck
g
s\_loc
tio
 -

sti

tio
 'C:
Optimiz

Vi
tu
l-

sktop-Optimiz
tio
-Tool-m
i

1909
Co
figu

tio
Fil
s

ppxP
ck
g
s.jso
' Copy-It
m $
ppp
ck
g
s\_loc
tio
 -

sti

tio
 'C:
Optimiz

Vi
tu
l-

sktop-Optimiz
tio
-Tool-m
i

2004
Co
figu

tio
Fil
s

ppxP
ck
g
s.jso
' Copy-It
m $
ppp
ck
g
s\_loc
tio
 -

sti

tio
 'C:
Optimiz

Vi
tu
l-

sktop-Optimiz
tio
-Tool-m
i

2009
Co
figu

tio
Fil
s

ppxP
ck
g
s.jso
'

\
 U

lock 
ll fil
s W
it
-V


os
 "U

lock 
ll fil
s" 
i
 $v
ot\_loc
tio
 -

cu
s
 | U

lock-Fil


\
 Ch

g
 fol


 to V
OT W
it
-V


os
 "Ch

g
 fol


 to V
OT loc
tio
" $v
ot\_fol


 = $v
ot\_loc
tio
 + '
Vi
tu
l-

sktop-Optimiz
tio
-Tool-m
i
' c
 $v
ot\_fol




W
it
-V


os
 "
u
 V
OT" S
t-
x
cutio
Policy -
x
cutio
Policy 

mot
Sig


 -Scop
 P
oc
ss -Fo
c
 .
Wi

ows\_V
OT.ps1 -V


os
 -
cc
pt
UL


\
 Sl

p 5 s
co

s sl

p 5

\
 

mov
 fol


 W
it
-V


os
 "

mov
 Optimiz
 fol


" c
 
 

mov
-It
m $v
ot\_loc
tio
 -

cu
s
 -Fo
c


\
 

st

t 
V
 Gol


 im
g
 

st

t-Comput

 -Fo
c
 \[/co

\]

You c

 us
 this sc
ipt i
 you
 
V
 Gol


 Im
g
 
uil
i
g p
oc
ss. Th
 Vi
tu
l 

sktop Optimiz
tio
 Tool (V
OT) ch

g
s 
 lot of s
tti
gs so 

 su

 to t
st you
 im
g
 v

y c


fully. Th
 sc
ipt c

 

 fou

 o
 my GitHu
, [li
k](https://githu
.com/i





s/
V
/t


/m
i
/v
ot).






