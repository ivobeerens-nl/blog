---

utho
: Ivo 





s
titl
: "P
tch 
 VMw


 
SXI host with th
 
SXCLI comm


 


 choos
 th
 
ight im
g
 p
ofil
"


t
: "2023-12-08T08:29:14.000Z"
c
t
go
i
s: 
  - VMw


 
SXi
  - VMw


 vSph



  - T
ou
l
shooti
g
t
gs: 
  - VMw


 
SXi
u
l: /2023/12/08/p
tch-
-VMw


-
sxi-hosts-with-
sxcli-comm


-


-choos
-th
-
ight-im
g
-p
ofil
/
---

Wh

 i
st
lli
g 
 p
tch o
 
 VMw


 
SXi host usi
g th
 
SXCLI comm


 you 



 to sp
cify th
 im
g
 p
ofil
 th
t is 
v
il

l
 i
 th
 
SXi p
tch.

H


 


 th
 st
ps fo
 p
tchi
g 
 VMw


 
SXi host with th
 co


ct im
g
 p
ofil
:

- Go to th
 [Custom

 Co


ct P
tch 
ow
lo

s p
g
.](https://my.VMw


.com/g
oup/VMw


/p
tch
s


ch)
- 
ow
lo

 th
 p
tch 





, I
 this 
x
mpl
, I us
 
SXi p
tch **VMw


-
SXi-7.0U3o-22348816-

pot.zip**
- Uplo

 th
 p
tch to 
 

t
sto


- M
k
 
 SSH co


ctio
 to th
 
SXi host
- Pl
c
 th
 host i
 m
i
t



c
 mo



```

sxcli syst
m m
i
t



c
Mo

 s
t –



l
-t
u

```

- 
ow you 



 to k
ow which im
g
 p
ofil
s 


 
v
il

l
 i
 th
 VMw


 
SXi p
tch. To 
o this us
 th
 followi
g comm


 (

pl
c
 th
 **<

t
sto

>** with you
 

t
sto

):

```

sxcli softw


 sou
c
s p
ofil
 list -
 /vmfs/volum
s/<

t
sto

>/iso/VMw


-
SXi-7.0U3o-22348816-

pot.zip
```

- Th
 followi
g p
ofil
s 


 list

. 
s you c

 s

 th
 im
g
 p
ofil
 co
t
i
s 4 im
g
 p
ofil
s:

![
sxcli_p
ofil
](im
g
s/1.jpg)

- H


 is 
 t

l
 with so, 0, st





, 


 
o-tools m


s:

|   **Optio
**  |             **

t
ils**           |
|---------------| --------------------------------- |
| st





      | With VMw


 Tools i
clu


        |
| 
o-tools      | Without VMw


 Tools              |
| so            | S
cu
ity up

t
s o
ly im
g
       |
| o             | S
cu
ity 


 
ugfix up

t
 im
g
  |

- To i
st
ll th
 
SXi with s
cu
ity 


 
ugfix up

t
s without VMw


 Tools us
 th
 followi
g comm


 (

pl
c
 th
 **<

t
sto

>** with you
 

t
sto

):

```

sxcli softw


 p
ofil
 up

t
 -
 /vmfs/volum
s/<

t
sto

>/VMw


-
SXi-7.0U3o-22348816-

pot.zip -p 
SXi-7.0U3o-22348816-
o-tools
```
- 


oot th
 host

```

sxcli syst
m shut
ow
 


oot -
 "P
tch 
SXi 7.0U3"
```

- Wh

 th
 host is 

ck, 
xit m
i
t



c
 mo

,  m
k
 
 SSH co


ctio
 to th
 
SXi host

```

sxcli syst
m m
i
t



c
Mo

 s
t --



l
 f
ls

```

With this p
oc

u

, you c

 sp
cify th
 
ight im
g
 p
ofil
 wh

 m

u
lly p
tchi
g 

 
SXi host.






