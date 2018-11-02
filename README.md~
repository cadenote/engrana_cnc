# engrana_cnc
Pruebas para engranar juntas
La idea es engranar el eje del taladro/fresadora con una junta rotatoria para realizar fresado sincronizado.
Como primera aproximacion vamos a engranar una junta lineal ( x y o z ) con la junta rotatoria (a)
El fichero custom_postgui_z.hal contiene la configuracion para engranar la junta a con junta z 
Si se quiere engranar la junta a con otra distinta [x o y] a z basta cambiar las lineas:

net zpos-cmd makoffset.0.conductora por net [x/y]pos-cmd makoffset.0.conductora </br>
y </br>
net zpos-cmd => mux2.0.in1 por net [x/y]pos-cmd => mux2.0.in1

El engrane funciona en cualquiera de los modos, por lo que si se ejecuta un programa, la junta conducida "a" sigue a la junta conductora.

Falta por hacer:
Desactivar la junta a al estar engranada porque si estando engranada se actua sobre a salta un joint error

