# engrana_cnc
Pruebas para engranar juntas
La idea es engranar el eje del taladro/fresadora con una junta rotatoria para realizar fresado sincronizado.
Como primera aproximacion vamos a engranar una junta lineal ( x y o z ) con la junta rotatoria (a)
El fichero custom_postgui_z.hal contiene la configuracion para engranar la junta a con junta z 
Si se quiere engranar la junta a con otra distinta [x o y] a z basta cambiar las lineas:

net zpos-cmd makoffset.0.conductora por net [x/y]pos-cmd makoffset.0.conductora </br>
y </br>
net zpos-cmd => mux2.0.in1 por net [x/y]pos-cmd => mux2.0.in1

El engrane funciona en cualquiera de los modos, por lo que si se ejecuta un programa, la junta conducida [a] sigue a la junta conductora [x/y/z].

En la segunda etapa he engranado la pinola con la junta [a] </br>
Para ello hay que copiar el archivo custom_postgui_a.hal como custom_postgui.hal en el correspondiente directorio de configuracion.

Si no se tiene instalada la version de linuxcnc/AXIS 2.8.0-pre1-3928-g0cab365 es posible que haya que transformar custom_postgui.hal a una version anterior, con componente axis en lugar de joint.
Una posible solucion para corregir el fichero custom_postgui.hal seria :</br> 
cp custom_postgui_a.hal custom_postgui.hal</br>
patch custom_postgui.hal dif_custom_n2v</br>

Falta por hacer:
Desactivar la junta a al estar engranada porque si estando engranada se actua sobre a salta un joint error

