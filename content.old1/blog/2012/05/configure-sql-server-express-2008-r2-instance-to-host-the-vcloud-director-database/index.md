---
titl
: "Co
figu

 SQL S

v

 
xp

ss 2008 
2 i
st

c
 to host th
 vClou
 
i

cto
 

t


s
"


t
: "2012-05-02T07:40:44.000Z"
c
t
go
i
s: 
  - "sql-2"
  - "vc
"
  - "vclou
"
t
gs: 
  - "sql"
  - "vc
"
  - "vclou
"

utho
: Ivo 





s
---

[![im
g
](im
g
s/im
g
_thum
.p
g "im
g
")](im
g
s/im
g
.p
g)





 St
ps:

- M
k
 su

 SQL S

v

 M


g
m

t Stu
io is i
st
ll

 o
 th
 vC

t

 s

v

.  S

 “[


 SQL S

v

 M


g
m

t Stu
io to Mic
osoft SQL S

v

 
xp

ss 2008 
2](https://www.ivo





s.
l/2011/12/08/


-sql-s

v

-m


g
m

t-stu
io-to-mic
osoft-sql-s

v

-
xp

ss-2008-
2/)”
- Op

 SQL S

v

 M


g
m

t  Stu
io
- Ch

g
  S

v

 
uth

tic
tio
 to Mix

 
uth

tic
tio
 (SQL S

v

 


 Wi

ows 
uth

tic
tio
 mo

)

[![im
g
](im
g
s/im
g
_thum
1.p
g "im
g
")](im
g
s/im
g
1.p
g)

- - S
l
ct “

w Qu

y”

[![im
g
](im
g
s/im
g
_thum
2.p
g "im
g
")](im
g
s/im
g
2.p
g)

- Th
 followi
g sc
ipt (f
om [vClou
 
i

cto
 i
st
ll
tio
 


 co
figu

tio
 gui

](http://www.VMw


.com/p
f/vc
_15_i
st
ll.p
f)) c


t
s 
 

t


s
 

m

 “vclou
” o
 th
 c-

iv
  


 
 sp
ci
l SQL us

 "vclou
” . Customiz
 this sc
ipt fo
 you
 

vi
o
m

t.
- P
st
 this sc
ipt i
 th
 “

w Qu

y” wi

ow”
    
    US
 \[m
st

\] 
    
    GO
    
    C


T
 

T


S
 \[vclou
\] O
 P
IM

Y
    
    (

M
 = 
'vclou
', FIL


M
 = 
'C:
vclou
.m
f', SIZ
 = 100M
, FIL
G
OWTH = 10% )
    
    LOG O

    
    (

M
 = 
'vc

\_log', FIL


M
 = 
'C:
vclou
.l
f', SIZ
 = 1M
, FIL
G
OWTH = 10%)
    
    COLL
T
 L
ti
1\_G




l\_CS\_
S
    
    GO
    
    US
 \[vclou
\]
    
    GO
    
    
LT

 

T


S
 \[vclou
\] S
T SI
GL
\_US

 WITH 
OLL

CK IMM

I
T
;
    
    
LT

 

T


S
 \[vclou
\] S
T 
LLOW\_S

PSHOT\_ISOL
TIO
 O
;
    
    
LT

 

T


S
 \[vclou
\] S
T 



\_COMMITT

\_S

PSHOT O
 WITH 
O\_W
IT;
    
    
LT

 

T


S
 \[vclou
\] S
T MULTI\_US

;
    
    GO
    
    US
 \[vclou
\]
    
    GO
    
    C


T
 LOGI
 \[vclou
\] WITH P
SSWO

 = 'vclou
p
ss', 

F
ULT\_

T


S
 =\[vclou
\], 

F
ULT\_L

GU
G
 =\[us\_

glish\],CH
CK\_POLICY=OFF
    
    GO
    
    C


T
 US

 \[vclou
\] fo
 LOGI
 \[vclou
\]
    
    GO
    
    US
 \[vclou
\]
    
    GO
    
    sp\_



ol
m
m


 \[

\_ow


\], \[vclou
\]
    
    GO
    
    - 
x
cut
 th
 sc
ipt (1)  


 m
k
 su

 it h
s 
x
cut

 succ
ssfully (2)
    
    [![im
g
](im
g
s/im
g
_thum
3.p
g "im
g
")](im
g
s/im
g
3.p
g)
    
    - Op

 St

t – 
ll P
og

ms – Mic
osoft SQL S

v

 2008 
2 – Co
figu

tio
 Tools – SQL S

v

 Co
figu

tio
 M


g


    
    - 
xp


 th
 “SQL S

v

 

two
k Co
figu

tio
” (1)
    
    - S
l
ct TCP/IP (2) 


 op

 th
 p
op

ti
s
    
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
    
    - I
 th
 IP
LL s
ctio
, s
l
ct th
 TCP po
t 


 fill i
 “1433”
    
    [![im
g
](im
g
s/im
g
_thum
5.p
g "im
g
")](im
g
s/im
g
5.p
g)
    
    - 

st

t th
 SQL S

v

 (VIM\_SQL
XP) s

vic

    
    [![im
g
](im
g
s/im
g
_thum
6.p
g "im
g
")](im
g
s/im
g
6.p
g)
    
    - Op

 th
 comm


 p
ompt o
 th
 SQL S

v

 


 ch
ck if po
t 1433 is list

i
g 
y usi
g this comm


:
    
    

tst
t -

 | fi

 "1433"
    
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
7.p
g)
    
    - Co
figu

 vClou
 
i

cto
 


 poi
t to th
 SQL 
xp

ss i
st

c

    
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
8.p
g)






