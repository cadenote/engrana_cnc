# engrana_cnc
Pruebas para engranar juntas con linuxcnc version 2.8</br>
La idea es engranar el eje del taladro/fresadora con una junta rotatoria para realizar fresado sincronizado.
Como primera aproximacion vamos a engranar una junta lineal [x y o z] con la junta rotatoria [a]</br>
Lo primero que tenemos que hacer es instalar los nuevos componentes hal que necesitamos.</br>
Para ello ejecutamos:</br>
halcompile --install ddt_bit.comp</br>
halcompile --install-doc ddt_bit.comp</br>
halcompile --install float_hold.comp</br>
halcompile --install-doc float_hold.comp</br>
halcompile --install makoffset.comp</br>
halcompile --install-doc makoffset.comp</br>

El fichero custom_postgui_z.hal contiene la configuracion para engranar la junta a con junta z 
Si se quiere engranar la junta a con otra distinta [x o y] a z basta cambiar las lineas:</br></br>

net zpos-cmd makoffset.0.conductora por net [x/y]pos-cmd makoffset.0.conductora </br>
y </br>
net zpos-cmd => mux2.0.in1 por net [x/y]pos-cmd => mux2.0.in1</br>

El engrane funciona en cualquiera de los modos, por lo que si se ejecuta un programa, la junta conducida [a] sigue a la junta conductora [x/y/z].</br>

En la segunda etapa he engranado la pinola con la junta [a] </br>
Para ello hay que copiar el archivo custom_postgui_a.hal como custom_postgui.hal en el correspondiente directorio de configuracion.</br>

Si se tiene instalada la version de linuxcnc/AXIS 2.7 hay que transformar custom_postgui.hal a esa version.
Una posible solucion para corregir el fichero custom_postgui.hal seria :</br> 
cp custom_postgui_a.hal custom_postgui.hal</br>
patch custom_postgui.hal dif_custom_n2v</br>
Una manera mas general es usar el ejecutable "envejece file_in file_out"</br>
Ejemplo:</br>
./envejece custom_postgui_a.hal custom_postgui_a.hal</br>
Errores pendientes :</br>
Salta joint 3 error al desengranar salvo cuando la pinola va despacio.</br> 

Falta por hacer:
Desactivar la junta [a] al estar engranada porque si estando engranada se actua sobre a salta un joint error</br>

