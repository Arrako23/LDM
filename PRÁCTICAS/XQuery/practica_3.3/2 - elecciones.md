# Nombre de los partidos políticos

doc("2 - elecciones.xml")/elecciones/partidos/partido/text()

Partido Popular de la Comunidad Valenciana
Partido Socialista del País Valenciano
Coalició Compromís
Esquerra Unida del País Valencià
Podemos
Ciudadanos - Partido de la Ciudadanía



# Fecha de la encuesta de El País

doc("2 - elecciones.xml")/elecciones/encuestas/encuesta[origen="El País"]/fecha

<fecha>15/05/2011</fecha>



# Año en que las encuestas vaticinaban que un partido sacaría mayoría absoluta (50 escaños):

doc("2 - elecciones.xml")/elecciones/encuestas/encuesta[partido>50]/@año

año="2011"


# Diputados obtenidos por el PSPV en elecciones anteriores al 2015:

doc("2 - elecciones.xml")/elecciones/resultados/eleccion[@año<2015]/partido[@nombre="PSPV"]/text()

38
33


# Año de las elecciones en las que fue candidato Francisco Camps:

doc("2 - elecciones.xml")/elecciones/resultados/eleccion/partido[@candidato="Francisco Camps"]/../@año

año="2007"
año="2011"


# Candidatos del Partido Popular de la Comunidad Valenciana:
Nota: Se pide una expresión compuesta, no se puede utilizar las siglas PPCV en la expresión.

for $p in doc("2 - elecciones.xml")/elecciones/partidos/partido
for $c in doc("2 - elecciones.xml")/elecciones/resultados/eleccion/partido

candidato="Francisco Camps"
candidato="Francisco Camps"
candidato="Alberto Fabra"


