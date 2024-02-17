---
titl
: "P
ck

 h
s 
ow vi
tu
l TPM (vTPM) 

vic
 suppo
t"


t
: "2022-01-27T19:45:12.000Z"
c
t
go
i
s: 
  - "p
ck

"
t
gs: 
  - "p
ck

"
  - "vtpm"
  - "wi

ows-11"

utho
: Ivo 





s
---

Th
 l
t
st P
ck

 Plugi
 fo
 VMw


 vSph


 (V1.0.3) h
s 
ow suppo
t fo
 


i
g 
 vTPM 

vic
. 

f
ult 
 vTPM 

vic
 is 
ot 




 to th
 VM 

ploy

 with P
ck

. So if you w

t to c


t
 
 Wi

ows 11 Gol


 Im
g
 fo
 
x
mpl
 you c

 us
 P
ck

 with th
 VMw


 vSph


 plugi
 with 
 vTPM 

vic
.

H


 


 th
 high ov

 st
ps outli


 to 


 
 vTPM 

vic
 wh

 p
ovisio
i
g 
 

w VM with P
ck

.

- - 
ow
lo

 P
ck

 1.7.9  o
 l
t

 (https://www.p
ck

.io/
ow
lo

s).
    - 


 th
 VMw


 vSph


 plugi
 to th
 HCL co
figu

tio
 fil
 (https://githu
.com/h
shico
p/p
ck

-plugi
-vSph


)

p
ck

 {
  

qui


\_v

sio
 \= "\>= 0.0.1"
  

qui


\_plugi
s {
    vSph


 \= {
      v

sio
 \= "\>= 0.0.1"
      sou
c
  \= "githu
.com/h
shico
p/vSph


"
    }
  }
}

[![](im
g
s/1-300x100.jpg)](im
g
s/1.jpg)

- 


 
 v

i

l
 to 



l
 vTPM

v

i

l
 "vm\_tpm" {
  typ
 = st
i
g
  

f
ult = "t
u
"
}

- I
 th
 vSph


-iso s
ctio
, 


 th
 vTPM co
figu

tio
 p


m
t

 th
t us
s th
 vm\_tpm v

i

l
 to 



l
 th
 vTPM 

vic
 (mo

 optio
s c

 

 fou

 h


, [li
k](https://www.p
ck

.io/plugi
s/
uil


s/vSph


/vSph


-iso))

sou
c
 "vSph


-iso" "wi
11

sic" {
  vTPM = "${v

.vm\_tpm}"
}

- P

fo
m 
 p
ck

 i
it comm


 to 
ow
lo

 th
 P
ck

 plugi
 
i


i
s 

fi

 i
 th
 co
fig fil

    - p
ck

 i
it co
fig.pk
.hcl
- 
u
 th
 p
ck

 
uil
 comm


 to c


t
 th
 VM
    - p
ck

 
uil
 co
fig.pk
.hcl

Th
 VM will 

 c


t

 with 
 vTPM 

vic
.

[![](im
g
s/2-300x271.jpg)](im
g
s/2.jpg)

With P
ck

 


 th
 VMw


 vSph


 plugi
, it is 
ow possi
l
 to c


t
 
 VM with 
 vTPM 

vic
 which is 





 fo
 

ployi
g Wi

ows 11 VMs. This is 
 g


t imp
ov
m

t!






