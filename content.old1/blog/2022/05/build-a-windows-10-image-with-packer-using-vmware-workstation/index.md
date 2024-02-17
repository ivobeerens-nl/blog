---
titl
: "
uil
 
 Wi

ows 10 im
g
 with P
ck

 usi
g VMw


 Wo
kst
tio
"


t
: "2022-05-31T20:04:33.000Z"
c
t
go
i
s: 
  - "i
c"
  - "p
ck

"
t
gs: 
  - "p
ck

"
  - "wi

ows"

utho
: Ivo 





s
---

With P
ck

, th
 VMw


-iso 
uil


 is us

 fo
 c


ti
g im
g
s with VMw


 Wo
kst
tio
/Fusio
.  I
 this 
x
mpl
 I c


t
 
 Wi

ows 10 im
g
 with th
 l
t
st VMw


 Tools i
st
ll

, th
 i
st
ll
tio
 of th
 
v

g



 mo
ul
, 


 
utom
tic
lly i
st
ll th
 l
t
st Wi

ows up

t
s.



 **P

-

quisit
s**

- Wi

ows 
 10 ISO fil
. You c

 us
 this [li
k](https://www.ivo





s.
l/2021/05/19/quick-tip-
ow
lo

-th
-l
t
st-wi

ows-10-iso-fil
/) fo
 
ow
lo

i
g th
 l
t
st Wi

ows 10 ISO fo
 
x
mpl

- I
st
ll VMw


 Wo
kst
tio
. I us
 VMw


 Wo
kst
tio
 P
o 16.x
- Th
 

wly c


t

 im
g
 must 

 

l
 to 
cc
ss th
 i
t



t fo
  
ow
lo

i
g th
 l
t
st VMw


 Tools v

sio

- 
u
i
g my fi
st 

ploym

t, th
 followi
g 
uil
 issu
 occu



 
uil
 "**Coul
 
ot 

t

mi

 

two
k m
ppi
gs f
om fil
s i
 th
 p
th: C:/P
og

m Fil
s (x86)/VMw


/VMw


 Wo
kst
tio
**". Coli
 W
stw
t

 of vG
m

.

t h
s 
logg

 

out 
 solutio
 th
t c

 

 fou

 h


, [li
k](https://www.vg
m

.

t/VMw


/P
ck

-Wo
kst
tio
-


o
/).
- Us
 

T i
 VMw


 Wo
kst
tio
.



 **St
ps**

- 
u
 th
 followi
g Pow

Sh
ll sc
ipt ([li
k](https://

w.githu
us

co
t

t.com/i





s/P
ck

/m
i
/wo
kst
tio
/wi

ows10/
ow
lo

.ps1)). This sc
ipt 
o
s th
 followi
g thi
gs:
    - C


t
 
 
ow
lo

 fol


 such 
s c:
P
ck

 (li

 6-17)
    - 
ow
lo

 th
 l
t
st P
ck

 v

sio
 


 u
zip th
 p
ck
g
 (li

 19-30)
    - 
ow
lo

 my Githu
 P
ck

 

posito
y to th
 loc
l 
ow
lo

 fol


 (li

 35-39)
    - C


t
 withi
 th
 
ow
lo

 fol


 th
 P
ck

 fol


 st
uctu

 (li

 41-45)

\[co

 l

gu
g
="Pow

Sh
ll"\] 
 $


o

ctio
P

f



c
 = "Sil

tlyCo
ti
u
" 
 



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
 V

i

l
s $
ow
lo

fol


 = 'C:
p
ck


' $githu
 = 'https://githu
.com/i





s/P
ck

/

chiv
/

fs/h


s/m
i
.zip'

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
th $
ow
lo

fol


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
g '$
ow
lo

fol


' fol


" 

w-It
m -P
th $
ow
lo

fol


 -It
mTyp
 
i

cto
y | Out-
ull } 
ls
 { W
it
-V


os
 "Fol


 '$
ow
lo

fol


' 
l



y 
xists." }

\
 
ow
lo

 th
 l
t
st P
ck

 v

sio
 $p
o
uct='p
ck

' $p
cku
l = I
vok
-W



qu
st -U
i https://www.$p
o
uct.io/
ow
lo

s.html | S
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
 $w

cli

t = 

w-o
j
ct -Typ


m
 Syst
m.

t.W

Cli

t $w

cli

t.
ow
lo

Fil
($p
cku
l, $p
ck
ow
lo

)

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
th $
ow
lo

fol


 
 

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


 
 

mov
 th
 p
ck

.zip 

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
 C


t
 th
 fol


 st
uctu

 Mov
-It
m ${
ow
lo

fol


}P
ck

-m
i

wo
kst
tio

wi

ows10
s
tup -

sti

tio
 $
ow
lo

fol


 Mov
-It
m ${
ow
lo

fol


}P
ck

-m
i

wo
kst
tio

wi

ows10
\*.\* -

sti

tio
 $
ow
lo

fol


 
 

mov
 th
 Githu
 st
uctu

 

mov
-It
m -P
th ${
ow
lo

fol


}P
ck

-m
i
 -

cu
s
 -Co
fi
m:$f
ls
 -Fo
c
 \[/co

\]

- 

ows
 to th
 
ow
lo

 fol



- Op

 th
 "wi
10-st
-.
uto-pkv

s.hcl" fil
 


 

it th
 v

i

l
s fo
 you
 



s such 
s:
    - Li

 2: Th
 VM 

m

    - Li

 17: Th
 ISO loc
tio

    - Li

 19: Th
 ISO ch
cksum. Us
 th
 Pow

Sh
ll G
t-Fil
h
sh comm


 to g
t th
 ch
cksum of th
 ISO

\[co

 l

gu
g
="t
xt"\] // VM vm\_

m
 = "GI-W10-001" op


ti
g\_syst
m\_vm = "wi

ows9-64" vm\_fi
mw


 = "
ios" vm\_c

om\_typ
 = "i

" vm\_cpus = "2" vm\_co

s = "1" vm\_m
mo
y = "2048" vm\_
isk\_co
t
oll

\_typ
 = "
vm
" vm\_
isk\_siz
 = "32768" vm\_

two
k\_


pt

\_typ
 = "
1000
" // Us
 th
 

T 

two
k vm\_

two
k = "VM

t8" vm\_h


w


v

sio
 = "19"

// 

mov


l
 m

i
 wi
10\_iso = "c:/iso/

-us\_wi

ows\_10\_
usi

ss\_

itio
s\_v

sio
\_21h2\_x64\_
v
\_c
067768.iso" // I
 Pow

Sh
ll us
 th
 "g
t-fil
h
sh" comm


 to fi

 th
 ch
cksum of th
 ISO wi
10\_iso\_ch
cksum = "1323F
1
F0C
F
4
F23F
56
6538FF69

410

49969983F

3
F936
6C811C5" \[/co

\]

- Op

 th
 "
utou

tt


.xml" fil
 i
 th
 s
tup fol


 


 ch
ck 


 

it th
 followi
g li

s 
s 





:
    - L

gu
g
 


 k
y
o


 s
tti
gs
        
    - Li

 84: 

mi
ist

to
 P
sswo

 (must 

 th
 s
m
 
s th
 wi

m\_p
sswo

)
    - Li

 92: 
utologo
 P
sswo

 (must 

 th
 s
m
 
s th
 wi

m\_p
sswo

)
    - Li

 141: Th
 Comput



m


- 

it th
 
uil
.ps1 fil
 


 ch
ck th
 followi
g li

s:
    - Li

 2: P
ck

 fol


 loc
tio

    - Li

 14: Th
 wi

m\_p
sswo

 m
tch
s th
 

mi
ist

to
 p
sswo

 i
 th
 
utou

tt




.xml fil


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
ow
lo

fol


 = 'C:
p
ck


'

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
it "${
ow
lo

fol


}wi

ows.jso
.pk
.hcl"

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
="${
ow
lo

fol


}wi
10-st
.
uto.pk
v

s.hcl" -v

 "wi

m\_us



m
=

mi
ist

to
" -v

 "wi

m\_p
sswo

=Thisis
goo
P
sswo

!" "${
ow
lo

fol


}wi

ows.jso
.pk
.hcl" \[/co

\]

- 
x
cut
 th
 "
uil
.ps1" fil
 with Pow

Sh
ll to st

t th
 P
ck

 im
g
 
uil
 p
oc
ss.

[![](im
g
s/P
ck


u
-300x164.jpg)](im
g
s/P
ck


u
.jpg)

- 
ft

 
 whil
, th
 
uil
 p
oc
ss fi
ish
s 


 you h
v
 
 

w Wi

ows 10 im
g
 

ploy

 with P
ck

 i
 VMw


 Wo
kst
tio
.

[![](im
g
s/Wi

ows-300x225.jpg)](im
g
s/Wi

ows.jpg)






