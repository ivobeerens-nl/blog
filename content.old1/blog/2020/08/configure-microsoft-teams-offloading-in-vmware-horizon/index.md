---
titl
: "Co
figu

 Mic
osoft T

ms offlo

i
g i
 VMw


 Ho
izo
"


t
: "2020-08-25T06:41:58.000Z"
c
t
go
i
s: 
  - "VMw


"
t
gs: 
  - "ho
izo
"
  - "t

ms"
  - "VMw


"

utho
: Ivo 





s
---



 Wh
t is suppo
t



Th
 M

i
 Optimiz
tio
 fo
 Mic
osoft T

ms off

s th
 followi
g f

tu

s:

- 
cc
pti
g 


 m
ki
g 
u
io 


 vi

o c
lls
- Multip

ty 
u
io 


 vi

o co
f



ci
g
- T


sf

, fo
w


, mut
, hol
, 


 

sum
 
 c
ll
- PST
 c
lls vi
 
i
l p


- 

sktop sc



 sh

i
g
- Multi mo
ito
 sc



 sh

i
g 


 sc



 pick

 fo
 sc



 sh

i
g
- Volum
 co
t
ol f
om th
 

mot
 

sktop
- 
ctiv
 sp

k

 i


tific
tio




 Limit
tio
s

M

i
 Optimiz
tio
 fo
 Mic
osoft T

ms h
s th
 followi
g limit
tio
s:

[![](im
g
s/Limit
tio
s-300x148.p
g)](im
g
s/Limit
tio
s.p
g)

To 



l
 this f

tu

 you 



  to co
figu

 th
 followi
g s
tti
gs:

- I
st
ll Ho
izo
 2006 cli

t 


 



l
 m

i
 optimiz
tio
.
- Impo
t th
 Ho
izo
 2006 GPOs 


 



l
 th
 G
oup Policy s
tti
g fo
 Mic
osoft T

ms
- P

fo
m 
 m
chi

-wi

 i
st
ll
tio
 of Mic
osoft T

ms o
 th
 gol


 im
g


I
 this 
x
mpl
, I will co
figu

 
 Wi

ows 10 cli

t with 
 custom Ho
izo
 2006 cli

t i
st
ll
tio
, impo
t 


 co
figu

 th
 GPO s
tti
gs fo
 Mic
osoft T

ms o
 th
 
om
i
 Co
t
oll

 


 i
st
ll Mic
osoft T

ms o
 th
 Wi

ows 10 Gol


 Im
g
.



 Ho
izo
 cli

t

I
st
ll 
 custom i
st
ll
tio
 of th
 Ho
izo
 cli

t.

- 
ow
lo

 th
 Ho
izo
 2006 cli

t, [li
k](https://my.VMw


.com/

/w

/VMw


/
ow
lo

s/i
fo/slug/

sktop_


_us

_computi
g/VMw


_ho
izo
_cli

ts/2006)
- I
st
ll th
 cli

t 


 s
l
ct "Customiz
 i
st
ll
tio
"

[![](im
g
s/Customiz
-i
st
ll-300x179.p
g)](im
g
s/Customiz
-i
st
ll.p
g) [![](im
g
s/Ho
izo
-Cli

t-216x300.p
g)](https://www.ivo





s.
l/wp-co
t

t/uplo

s/2020/08/Ho
izo
-Cli

t.p
g)

- Sc
oll 
ow
 


 s
l
ct "M

i
 Optimiz
tio
 fo
 Mic
osoft T

ms"
- 
ft

 th
 i
st
ll
tio
 


oot th
 Wi

ows cli

t



 VMw


 Ho
izo
 G
oup Polici
s

 
ow
lo

 


 co
figu

 th
 Mic
osoft T

ms GPO.

- 
ow
lo

 th
 GPO 
u

l
 f
om th
 VMw


  
ow
lo

 sit


[![](im
g
s/GPO-300x28.p
g)](im
g
s/GPO.p
g)

- 
xt

ct th
 .zip fil

- Copy 
ll th
 fil
s to th
 %syst
m
oot%
Policy

fi
itio
s fol


 o
 you
 
ctiv
 
i

cto
y
- C


t
 
 GPO 


 co
figu

 th
 T

ms offlo

i
g s
tti
gs:
    - Comput

 Co
figu

tio

        - Polici
s
            - 

mi
ist

tiv
 T
mpl
t
s
                - VMw


 Vi
w 
g

t Co
figu

tio

                    - VMw


 HTML5 F

tu

s
                        - VMw


 W


TC 


i

ctio
 F

tu

s

[![](im
g
s/

MX-300x158.p
g)](im
g
s/

MX.p
g)

- 



l
 th
 M

i
 Optimiz
tio
 fo
 Mic
osoft T

ms s
tti
g

[![](im
g
s/S
tti
gs-300x55.p
g)](im
g
s/S
tti
gs.p
g)

 

 



 V
I - Gol


 Im
g


I
st
ll th
 Mic
osoft T

ms cli

t o
 
 Wi

ows 10 32 o
 64 
its OS.

- 
ow
lo

 th
 32 o
 64 
its T

ms cli

t, h


 is 
 li
k to th
 64-
its v

sio
, [li
k](https://st
tics.t

ms.c

.offic
.

t/p
o
uctio
-wi

ows-x64/1.3.00.21759/T

ms_wi

ows_x64.msi)
- P

fo
m 
 m
chi

-wi

 i
st
ll
tio
 

c
us
 T

ms wo
't wo
k p
op

ly with 
 p

-us

 i
st
ll
tio
 o
 
 
o
-p

sist

t s
tup.

\[co

 l

gu
g
="t
xt"\] msi
x
c /i <p
th\_to\_msi> /l\*v <i
st
ll\_logfil
\_

m
> 
LLUS

=1 
LLUS

S=1 \[/co

\]

Mo

 i
fo
m
tio
 o
 i
st
lli
g Mic
osoft T

ms c

 

 fou

 h


, [li
k.](https://
ocs.mic
osoft.com/

-us/mic
osoftt

ms/t

ms-fo
-v
i) Mo

 i
fo
m
tio
 o
 i
st
lli
g VMw


 T

ms c

 

 fou

 h


, [li
k](https://
ocs.VMw


.com/

/VMw


-Ho
izo
/2006/ho
izo
-

mot
-

sktop-f

tu

s/GUI
-F68F
7

-
08F-4
FF-9

1-1F9FC71F8214.html).



 Ch
ck s
ssio
 mo



To ch
ck if th
 T

ms s
ssio
 is 
u

i
g i
 optimiz

, f
il

ck, o
 

tiv
ly (without optimiz
tio
) mo

 i
 th
 V
I s
ssio
 go th
 T

ms cli

t. I
 th
 T

ms cli

t go th
 th
 us

 
ccou
t 


 

vig
t
 to 

out 


 s
l
ct v

sio
. 
s you c

 s

 i
 th
 pictu

 

low, th
 s
ssio
 is optimiz

 (VMw


 M

i
 Optimiz

) which m


s offlo

i
g wo
ks.

[![](im
g
s/S
ssio
-300x146.jpg)](im
g
s/S
ssio
.jpg)



 Co
clusio



ft

 co
figu
i
g th
s
 s
tti
gs Mic
osoft T

ms offlo

i
g is co
figu


. Fo
 Mic
osoft T

ms offlo

i
g you 



 
t l

st 

 

v

c

 Ho
izo
 lic

s
. Mic
osoft T

ms offlo

i
g is 
ow 
v
il

l
 i
 th
 Ho
izo
 st





 su
sc
iptio
 lic

s
, s

 [li
k](https://www.VMw


.com/co
t

t/

m/
igit
lm

k
ti
g/VMw


/

/p
f/p
o
ucts/ho
izo
/vmw-ho
izo
-su
sc
iptio
-f

tu

-comp

iso
.p
f).






