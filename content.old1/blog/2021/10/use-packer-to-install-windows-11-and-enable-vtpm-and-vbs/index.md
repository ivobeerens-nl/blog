---
titl
: "Us
 P
ck

 to i
st
ll Wi

ows 11 


 



l
 vTPM 


 V
S"


t
: "2021-10-22T07:30:08.000Z"
c
t
go
i
s: 
  - "wi

ows-11"
t
gs: 
  - "hcl"
  - "p
ck

"
  - "tpm"
  - "v
s"
  - "wi

ows-11"

utho
: Ivo 





s
---

**Up

t
: J

u

y 27, 2022**: P
ck

 with th
 VMw


 vSph


 plugi
 ((V1.0.3) h
s 
ow suppo
t fo
 


i
g 
 vTPM 

vic
. Mo

 i
fo
m
tio
 c

 

 fou

 h


: [li
k](https://www.ivo





s.
l/2022/01/27/p
ck

-h
s-
ow-vi
tu
l-tpm-vtpm-

vic
-suppo
t/).

You c

 i
st
ll Wi

ows 11 usi
g 
 

gist
y h
ck ([li
k](https://www.ivo





s.
l/2021/10/06/i
st
ll-wi

ows-11-
s-vm-i
-VMw


-vSph


-wo
kst
tio
-without-tpm-2-0/)) to 
yp
ss th
 TPM ch
ck:

\[co

 l

gu
g
="Pow

Sh
ll"\] 

g 


 "HKLM
SYST
M
S
tup
L

Co
fig" /f /v 
yp
ssS
cu


ootCh
ck /t 

G\_
WO

 /
 1 \[/co

\]

vCommu
ity m
m


 Si


y L


 f
om v
UC


ict w
ot
 
 
ic
 
log 

out usi
g P
ck

 to i
st
ll Wi

ows 11 usi
g this 

gist
y h
ck ([li
k](https://v
uc


ict.com/
log/
iff



c
s-i
-c


ti
g-wi

ows-10-


-wi

ows-11-im
g
s-o
-VMw


-vSph


-with-p
ck

/)). Wh

 usi
g this h
ck, it 
o
s
't 



l
 vTPM o
 V
S.

[![](im
g
s/TPM
ot



l

-300x226.jpg)](im
g
s/TPM
ot



l

.jpg) [![](im
g
s/V
S
ot



l

-300x165.jpg)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2021/10/V
S
ot



l

.jpg)

Fo
 L

 

vi
o
m

ts, this is 
o issu
 
ut fo
 p
o
uctio
, 

vi
o
m

ts you w

t to h
v
 
 vTPM 



l

 


 
v

 Vi
tu
liz
tio
-

s

 S
cu
ity (V
S) 

p


i
g o
 th
 s
cu
ity 

qui

m

ts.




 **So wh
t 


 TPM 


 V
S**?

> _TPM_
> 
> T
ust

 Pl
tfo
m Mo
ul
 (TPM) t
ch
ology is 

sig


 to p
ovi

 h


w


-

s

, s
cu
ity-

l
t

 fu
ctio
s. 
 TPM chip is 
 s
cu

 c
ypto-p
oc
sso
 th
t h
lps you with 
ctio
s such 
s g




ti
g, sto
i
g, 


 limiti
g th
 us
 of c
yptog

phic k
ys.
> 
> _V
S_
> 
> Vi
tu
liz
tio
-

s

 s
cu
ity, o
 V
S, us
s h


w


 vi
tu
liz
tio
 f

tu

s to c


t
 


 isol
t
 
 s
cu

 

gio
 of m
mo
y f
om th
 
o
m
l op


ti
g syst
m. Wi

ows c

 us
 this "vi
tu
l s
cu

 mo

" to host 
 
um


 of s
cu
ity solutio
s, p
ovi
i
g th
m with g


tly i
c


s

 p
ot
ctio
 f
om vul




iliti
s i
 th
 op


ti
g syst
m, 


 p

v

ti
g th
 us
 of m
licious 
xploits which 
tt
mpt to 

f

t p
ot
ctio
s.
> 
> [sou
c
 li
k](https://
ocs.mic
osoft.com/

-us/wi

ows-h


w


/

sig
/

vic
-
xp

i

c
s/o
m-v
s)


ft

 th
 Wi

ows 11 i
st
ll
tio
 with P
ck

, it is possi
l
 to 


 
 vTPM 


 
v

 



l
 Vi
tu
liz
tio
-

s

 S
cu
ity (V
S)  
y usi
g VMw


 Pow

CLI.




 **

qui

m

ts**

- Us
 vC

t

 S

v

 syst
m v

sio
s 6.7 o
 l
t


- 


 
 K
y P
ovi


 ([li
k](https://www.ivo





s.
l/2021/10/07/i
st
ll-wi

ows-11-o
-VMw


-vSph


-with-
-vi
tu
l-tpm/))
- I
st
ll Pow

CLI 
y usi
g th
 followi
g comm


 i
 Pow

Sh
ll:
    - \[co

 l

gu
g
="Pow

Sh
ll"\]I
st
ll-Mo
ul
 VMw


.Pow

CLI -Scop
 Cu



tUs

\[/co

\]
        
- Th
 Wi

ows 11 VM must 

 pow



 off
- Us
 VM h


w


 v

sio
 14 o
 high


- 
o
't c


t
 
 s

pshot with P
ck

 (c


t
\_s

pshot = f
ls
)




 **Pow

CLI Sc
ipt**

Th
 followi
g Pow

CLI sc
ipt c

 

 
x
cut

 
ft

 th
 P
ck

 Wi

ows 11 

ploym

t. This sc
ipt 


s vTPM, 



l
s V
S suppo
t, 


 c


t
s 
 s

pshot.

- Ch

g
 th
 v

i

l
s fo
 you
 

vi
o
m

t.

\[co

 l

gu
g
="Pow

Sh
ll"\]

\
 Impo
t Pow

CLI Impo
t-Mo
ul
 VMw


.Pow

CLI

\
 V

i

l
s $vc

t



m
 = "vc

t



m
" $VMT
mp

m
 = "VM

m
" $s

p

m
 = "v0.1" $s

p

sc
iptio
 = "P
ck

 

ploy
m

t with vTPM 


 V
S 



l

"

\
 Co


ct to vC

t

 S

v

 Co


ct-VIS

v

 -S

v

 $vc

t



m


\
 


 vTPM W
it
-Host 'S
t vTPM' 

w-VTpm -VM $VMT
mp

m


\
 



l
 Vi
tu
liz
tio
 

s

 S
cu
ity (V
S) W
it
-Host '



l
 V
S' $vm = G
t-VM $VMT
mp

m
 $sp
c = 

w-O
j
ct VMw


.Vim.Vi
tu
lM
chi

Co
figSp
c $sp
c.Fi
mw


 = \[VMw


.Vim.Gu
stOs

sc
ipto
Fi
mw


Typ
\]::
fi $sp
c.

st

HV



l

 = $t
u
 $
oot = 

w-O
j
ct VMw


.Vim.Vi
tu
lM
chi


ootOptio
s $
oot.
fiS
cu


oot



l

 = $t
u
 $sp
c.
ootOptio
s = $
oot $fl
gs = 

w-O
j
ct VMw


.Vim.Vi
tu
lM
chi

Fl
gI
fo $fl
gs.V
s



l

 = $t
u
 $fl
gs.Vvt




l

 = $t
u
 $sp
c.fl
gs = $fl
gs $vm.
xt

sio


t
.

co
figVM($sp
c)

\
 C


t
 S

pshot W
it
-Host 'C


t
 s

pshot' -Fo

g
ou

Colo
 g



 G
t-VM -

m
 $VMT
mp

m
 | 

w-S

pshot -

m
 $s

p

m
 -

sc
iptio
 $s

p

sc
iptio
 
 
isco


ct vC

t

 S

v

 
isco


ct-VIS

v

 -S

v

 \* -Co
fi
m:$f
ls
 \[/co

\]

- Wh

 th
 sc
ipt is fi
ish

, vTPM 


 V
S suppo
t is 





- St

t th
 VM
- Ch
ck if 
 TPM is 
ispl
y

 i
 

vic
 M


g

 


 with th
 TPM.MSC comm




[![](im
g
s/TPM

vic
M


g

-300x225.jpg)](im
g
s/TPM

vic
M


g

.jpg) [![](im
g
s/vTPM



l

-300x219.jpg)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2021/10/vTPM



l

.jpg)

- Usi
g Pow

Sh
ll th
 comm


 "G
t-TPM" c

 ch
ck th
 p

s

c
 of th
 TPM

[![](im
g
s/G
t-TPM-300x157.jpg)](im
g
s/G
t-TPM.jpg)

- - Fo
 



li
g V
S (**\*1**) go to "

vic
 s
cu
ity" i
 Wi

ows 11, s
l
ct "Co

 isol
tio
 

t
ils" 


 **



l
** "M
mo
y I
t
g
ity"
        - - 



li
g V
S c

 
lso 

 
o

 
y usi
g th
 followi
g 

gist
y s
tti
gs

\[co

 l

gu
g
="Pow

Sh
ll"\] 

g 


 "HKLM
SYST
M
Cu



tCo
t
olS
t
Co
t
ol


vic
Gu


" /v "



l
Vi
tu
liz
tio


s

S
cu
ity" /t 

G\_
WO

 /
 1 /f 

g 


 "HKLM
SYST
M
Cu



tCo
t
olS
t
Co
t
ol


vic
Gu


" /v "

qui

Pl
tfo
mS
cu
ityF

tu

s" /t 

G\_
WO

 /
 1 /f 

g 


 "HKLM
SYST
M
Cu



tCo
t
olS
t
Co
t
ol


vic
Gu


" /v "Lock

" /t 

G\_
WO

 /
 0 /f 

g 


 "HKLM
SYST
M
Cu



tCo
t
olS
t
Co
t
ol


vic
Gu



Sc



ios
Hyp

viso


fo
c

Co

I
t
g
ity" /v "



l

" /t 

G\_
WO

 /
 1 /f 

g 


 "HKLM
SYST
M
Cu



tCo
t
olS
t
Co
t
ol


vic
Gu



Sc



ios
Hyp

viso


fo
c

Co

I
t
g
ity" /v "Lock

" \[/co

\]

Mo

 i
fo: [Li
k](https://
ocs.mic
osoft.com/

-us/wi

ows/s
cu
ity/th


t-p
ot
ctio
/

vic
-gu


/



l
-vi
tu
liz
tio
-

s

-p
ot
ctio
-of-co

-i
t
g
ity)

(**\*1**) 


i
g V
S i
 Wi

ows 11 c

 h
v
 
 p

fo
m

c
 imp
ct o
 th
 VM

- 


oot th
 VM

[![](im
g
s/0V
S-300x234.jpg)](im
g
s/0V
S.jpg) [![](im
g
s/V
S-1-300x169.jpg)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2021/10/V
S-1.jpg)

- Wh

 th
 VM is 

st

t

 
u
 "msi
fo32"
- Sc
oll 
ow
 


 ch
ck if "Vi
tu
liz
tio
-

s

 S
cu
ity" is **
u

i
g**

[![](im
g
s/0MSi
fo32-300x169.jpg)](im
g
s/0MSi
fo32.jpg)




i
g th
 Pow

CLI sc
ipt 
ft

 th
 P
ck

 

ploym

t will 



l
 vTPM 


 V
S fo
 th
 Wi

ows 11 VM. I hop
 th
 vTPM 


 V
S optio
s will 

 




 soo
 i
 P
ck

 so w
 us
 th
 HCL co
fig fil
 without th
 



 fo
 

 
xt

 Pow

CLI sc
ipt.






