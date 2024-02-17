---

utho
: Ivo 





s
c
t
go
i
s:
- P
ck




t
: "2024-01-15T18:19:53Z"
gui
: https://www.ivo





s.
l/?p=9202
i
: 9202
ss
_ol
_cou
ts:
- 
:5:{s:7:"twitt

";i:0;s:9:"pi
t


st";i:0;s:7:"f
sh


";i:0;s:6:"



it";i:0;s:6:"tum
l
";
;}
ss
_tot
l_cou
ts:
- "0"
t
gs:
- Im
g

- P
ck


titl
: P
ck

 - Us
 th
 SSH commu
ic
to
 fo
 Wi

ows im
g
s
u
l: /2024/01/15/p
ck

-us
-th
-ssh-commu
ic
to
-fo
-wi

ows-im
g
s/
y

pp_m
t
:
- 
:1:{s:27:"y

pp_
ispl
y_fo
_this_post";i:1;}
---

P
ck

 commu
ic
to
s 


 us

 to uplo

 fil
s 


 
x
cut
 sc
ipts wh

 c


ti
g im
g
s. Th
 two most commo
 commu
ic
to
s 


:

- ssh – 

 SSH co


ctio
 will 

 
st

lish

 to th
 m
chi

. This commu
ic
to
 is us

 
y Li
ux
- wi

m – 
 Wi

M co


ctio
 will 

 
st

lish

. This commu
ic
to
 is us

 
y Wi

ows.

Op

SSH is 
v
il

l
 
s 

 Optio

l F

tu

 i
 Wi

ows 10 (v

sio
 1809 


 high

), Wi

ows 11, Wi

ows S

v

 2019, 


 Wi

ows S

v

 2022. Op

SSH us
s th
 SSH p
otocol (po
t TCP 22) which 

c
ypts 
ll t

ffic 

tw


 cli

t 


 s

v

.

To co
figu

 th
 SSH commu
ic
to
 fo
 c


ti
g Wi

ows im
g
s, follow th
 st
ps 

low.

**P



quisit
s**

Th
 followi
g p



quisit
s 


 





:

- 
 

vic
 
u

i
g 
t l

st Wi

ows S

v

 2019 o
 Wi

ows 10 (
uil
 1809).
- Pow

Sh
ll 5.1 o
 l
t

.
- 

 
ccou
t th
t is 
 m
m


 of th
 
uilt-i
 

mi
ist

to
s g
oup.

**St
p 1: 



l
 SSH i
 th
 Wi

ows im
g
**

C


t
 
 Pow

Sh
ll to i
st
ll th
 Op

SSH cli

t 


 s

v

 i
 th
 Wi

ows im
g
. Op

SSH 



l
s th
 SSH p
otocol. This sc
ipt is 
x
cut

 
u
i
g th
 p
ovisio
i
g of th
 Wi

ows im
g
 i
 th
 
utou

tt


.xml fil
.

sc
ipt 

m
: **



l
-ssh.ps1**

```Pow

Sh
ll  

 I
st
ll th
 Op

SSH Cli

t



-Wi

owsC
p

ility -O
li

 -

m
 Op

SSH.Cli

t~~~~0.0.1.0
 

 I
st
ll th
 Op

SSH S

v





-Wi

owsC
p

ility -O
li

 -

m
 Op

SSH.S

v

~~~~0.0.1.0
 

 St

t th
 ssh
 s

vic

St

t-S

vic
 ssh

 

 St

t th
 SSH s

vic
 
utom
tic 
t st

tup
S
t-S

vic
 -

m
 ssh
 -St

tupTyp
 '
utom
tic'
 

 Co
fi
m th
 Fi

w
ll 
ul
 is co
figu


. It shoul
 

 c


t

 
utom
tic
lly 
y s
tup. 
u
 th
 followi
g to v

ify
if (!(G
t-

tFi

w
ll
ul
 -

m
 "Op

SSH-S

v

-I
-TCP" -


o

ctio
 Sil

tlyCo
ti
u
 | S
l
ct-O
j
ct 

m
, 



l

)) {
  W
it
-Output "Fi

w
ll 
ul
 'Op

SSH-S

v

-I
-TCP' 
o
s 
ot 
xist, c


ti
g it..."
  

w-

tFi

w
ll
ul
 -

m
 'Op

SSH-S

v

-I
-TCP' -
ispl
y

m
 'Op

SSH S

v

 (ssh
)' -



l

 T
u
 -
i

ctio
 I

ou

 -P
otocol TCP -
ctio
 
llow -Loc
lPo
t 22
} 
ls
 {
  W
it
-Output "Fi

w
ll 
ul
 'Op

SSH-S

v

-I
-TCP' h
s 



 c


t

 


 
xists."
}
```

This sc
ipt is s
v

 i
 th
 sc
ipts fol


 i
 th
 P
ck

 fol


 


 mou
t

 
s 
 floppy 

iv
.

**St
p 2: 


 th
 sc
ipt i
 th
 
utou

tt


.xml**




 th
 sc
ipt c


t

 i
 st
p 1 i
 th
 Fi
stLogo
Comm


s s
ctio
 (**li

s 19-23**) of th
 
utou

tt


.xml.

```xml  
<Fi
stLogo
Comm


s>
   <Sy
ch
o
ousComm


 wcm:
ctio
="


">
      <Comm


Li

>%Syst
m
oot%\syst
m32\Wi

owsPow

Sh
ll\v1.0\Pow

Sh
ll.
x
 -Comm


 "S
t-
x
cutio
Policy -
x
cutio
Policy 

mot
Sig


 -Fo
c
"</Comm


Li

>
      <

sc
iptio
>S
t 
x
cutio
 Policy 64-
it</

sc
iptio
>
      <O



>1</O



>
      <

qui

sUs

I
put>t
u
</

qui

sUs

I
put>
   </Sy
ch
o
ousComm


>
   <Sy
ch
o
ousComm


 wcm:
ctio
="


">
      <Comm


Li

>%Syst
m
oot%\syst
m32\Wi

owsPow

Sh
ll\v1.0\Pow

Sh
ll.
x
 -Comm


 "S
t-
x
cutio
Policy -
x
cutio
Policy 

mot
Sig


 -Fo
c
"</Comm


Li

>
      <

sc
iptio
>S
t 
x
cutio
 Policy 32-
it</

sc
iptio
>
      <O



>2</O



>
      <

qui

sUs

I
put>t
u
</

qui

sUs

I
put>
   </Sy
ch
o
ousComm


>
   <Sy
ch
o
ousComm


 wcm:
ctio
="


">
      <Comm


Li

>
:\vmtools.cm
</Comm


Li

>
      <O



>3</O



>
      <

sc
iptio
>I
st
ll VMw


 Tools</

sc
iptio
>
   </Sy
ch
o
ousComm


>
   <Sy
ch
o
ousComm


 wcm:
ctio
="


">
      <Comm


Li

>%Syst
m
oot%\syst
m32\Wi

owsPow

Sh
ll\v1.0\Pow

Sh
ll.
x
 -Fil
 
:\



l
-ssh.ps1</Comm


Li

>
      <O



>4</O



>
      <

sc
iptio
>



l
 SSH</

sc
iptio
>
   </Sy
ch
o
ousComm


>
</Fi
stLogo
Comm


s>
```

**St
p 3: 


 th
 SSH commu
ic
to
 to th
 P
ck

 co
fig**

I
 th
 P
ck

 HCL co
fig fil
 


 th
 SSH commu
ic
to
. H


 is 

 
x
mpl
:

```sh
ll
sou
c
 "vSph


-iso" "wi
10t
st" {
floppy_fil
s = ["${p
th.
oot}/sc
ipts/"]
 
 // SSH
commu
ic
to
 = "ssh"
ssh_us



m
 = loc
l.SSHUs

 



 you
 ow
 SSH us



m

ssh_p
sswo

 = loc
l.SSHP
ss 



 you
 ow
 SSH p
sswo


ssh_tim
out = "2h"
ssh_cl


_
utho
iz

_k
ys = "t
u
"
}
```


u
i
g th
 

ploym

t of th
 im
g
, you s

 wh

 th
 commu
ic
to
 co


cts usi
g SSH to th
 im
g
.
![p
ck

](im
g
s/2-1024x644.p
g)

If you us
 P
ck

 fo
 c


ti
g Wi

ows 


 Li
ux im
g
s, o
ly 1 fi

w
ll po
t (TCP 22) 



s to 

 op



 wh

 usi
g th
 SSH commu
ic
to
.






