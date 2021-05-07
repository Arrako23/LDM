# Nombre de las distribuciones:

doc("1 - software.xml")/software-libre/distribuciones/distribucion/nombre/text()

Manjaro Linux
Linux Mint
Ubuntu
Debian GNU/Linux

# Kernel de las distribuciones publicadas en 2017:

doc("1 - software.xml")/software-libre/lanzamientos/lanzamiento[@año="2017"]/@kernel

kernel="4.14"
kernel="4.10"
kernel="4.13"
kernel="4.09"

# Distribuciones que no usan Gnome:

doc("1 - software.xml")/software-libre/lanzamientos/lanzamiento[@escritorio!="gnome"]

<lanzamiento distribucion="manjaro" version="17.1" año="2017" mes="12" escritorio="xfce" kernel="4.14"/>
<lanzamiento distribucion="mint" version="18.3" año="2017" mes="11" escritorio="cinnamon" kernel="4.10"/>
<lanzamiento distribucion="mint" version="19" año="2018" mes="6" escritorio="cinnamon" kernel="4.15"/>

# Versiones que se publicarán en 2018 (estamos en mayo de 2018):

doc("1 - software.xml")/software-libre/lanzamientos/lanzamiento[@año="2018" and @mes>5]

<lanzamiento distribucion="mint" version="19" año="2018" mes="6" escritorio="cinnamon" kernel="4.15"/>

# Distribuciones publicadas con kérneles de 2017

for $l in doc("1 - software.xml")/software-libre/lanzamientos/lanzamiento
for $k in doc("1 - software.xml")/software-libre/kernels/kernel
where $k/@id=$l/@kernel and $k/@año="2017"
return $l/@distribucion

distribucion="manjaro"
distribucion="mint"
distribucion="ubuntu"

# Escritorios utilizado por distribuciones derivadas de Ubuntu:

for $d in doc("1 - software.xml")/software-libre/distribuciones/distribucion
for $l in doc("1 - software.xml")/software-libre/lanzamientos/lanzamiento
where $d/derivada="ubuntu" and $d/@id = $l/@distribucion
return $l/@escritorio

escritorio="cinnamon"
escritorio="cinnamon"