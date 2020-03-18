---
title: "Disc Dumping (DiscImageCreator UI version, Español)"
---

De ahora en adelante, entenderemos el término "dumping" como el proceso
de realizar una copia digital a nuestro disco y obtener todos los datos
referentes al proceso y el resultado del mismo, mediante el empleo de
hardware y software adecuado, para validad su aporte a Redump.org.
**Esta guía de "dumping" puede ser empleada para:**

  - Cualquier formato en CD, incluyendo (aunque no se limite a los
    siguientes): juegos de videoconsola, Audio CDs y juegos de PC (el
    programa da soporte al "dumping" de juegos con las siguientes
    protecciones anticopia: SecuRom 3, CDS100, CDS200, Label Gate, XCP).
  - Cualquier formato DVD incluyendo: PlayStation 2, Xbox original, Xbox
    360, juegos de PC en este formato y/o DVD-Video. Entre los discos
    incompatibles, se encuentran los DVD-Audio.
  - Blu-Ray / BD-Rom: PlayStation 4, Xbox One y [PlayStation 3 (partial,
    no decryption key
    extraction)](PlayStation_3_Dumping_Guide "wikilink"). El dumping de
    BD-Video, es decir, cualquier formato de Bluray destinado a la
    reproducción de video, no está soportado, ver [BD-Video Dumping
    Guide](BD-Video_Dumping_Guide "wikilink").

Para el resto de sistemas, puedes ver el resto de guías aquí: [Dumping
Guides](Dumping_Guides "wikilink"). Emplearemos el término "dump" en
referencia a la copia digital que realiza DICUI, del disco físico
original.

## Herramientas

  - Windows computer.
  - [Compatible disc
    drive](DiscImageCreator:_Optical_Disc_Drive_Compatibility "wikilink").
  - Software:
      - [Microsoft .NET Framework 4.6.1 or
        newer](https://www.microsoft.com/en-us/download/details.aspx?id=49981)
      - [Microsoft Visual C++ 2015 Redistributable Update 3
        RC](https://www.microsoft.com/en-us/download/details.aspx?id=52685)
      - DICUI disc-dumping app: download the latest available version
        .zip file
        [here](https://github.com/reignstumble/DICUI/releases/latest).

## Dumping

  - En la carpeta donde estén incluídos los contenidos del programa
    DICUI, haz doble click en **DICUI.exe** para lanzar la aplicación.
    En la ventana que se abrirá reconocerás algunas de estas opciones:

<!-- end list -->

  - **System/Media Type**: Elige el nombre del sistema en el cual es
    reproducido tu disco, luego selecciona el formato del disco, opción
    que estará disponible para cambiar solo si el sistema da soporte a
    diversos formatos de disco (Ejemplo, Sony Playstation 2 da soporte a
    juegos en formato CD y también DVD).
  - **Output Filename**: Podrás especificar el nombre de los archivos
    que va a generar DICUI, incluyendo el "dump" en sí, te aconsejamos
    que uses el mismo nombre del título del juego o disco que vayas a
    "dumpear" (por ejemplo, **WipEout Pulse**).
  - **Output Directory**: Por defecto será **ISO\\unknown\\**, también
    te aconsejamos cambiar el nombre de la carpeta colocando el nombre
    del juego como **ISO\\Wipeout Pulse\\**. Mantener este formato te
    permite mantener diversas subcarpetas para mantener tus "dumps"
    organizados y separados dentro de una misma ruta. (NOTA: No puedes
    usar signos de puntuación en el nombre del directorio, como **" . ,
    \! ? "**)
  - **Drive Letter**: Debería ser detectado automáticamente cuando
    introduzcas el disco, pero si tienes varios lectores de discos
    conectados al sistema, entonces puedes elegir la "Letra" o "Unidad"
    especifica que contiene el disco que quieres "dumpear".
  - **Drive Speed**: Puedes dejar el valor marcado por defecto. (Modo
    Pro: Si sabes lo que estás haciendo y entiendes como funciona tu
    lector de disco, selecciona la velocidad con la que prefieras
    ejecutar el "dump", recuerda estar seguro de la velocidad máxima que
    permite tu unidad de lectura).
  - **Start Dumping**: Clickea esta opción y el proceso comenzará.
    Saltará una ventana con una interfaz repleta de líneas de comandos,
    indicando la evolución del proceso. Cuando esta ventana se cierre
    automáticamente, ¡Tu "dump" habrá concluído\!

<!-- end list -->

  - *Nota*: La opción "Scan for protection" es empleada en juegos de PC,
    concretamente en los de IBM PC. Trata de localizar posibles
    protecciones anticopia e indicar cuales son. Esta opción es
    específica para aquellos que quieran analizar el disco sin llevar a
    cabo el proceso de "dumping". En caso de que quieran llevar a cabo
    el proceso íntegro de "dumping", si seleccionamos un disco de IBM PC
    y clickamos en "Start Dumping", DICUI se encargará al final de todo
    el proceso de realizar igualmente el escaneado de medidas anticopia
    y lo dejará reflejado en el correspondiente "log" que se cree junto
    al "dump".

## Entregando la información a la base de datos de Redump.org

**¡Hora de añadir la información recogida a la base de datos\!** Los
nuevos miembros o "**dumpers**" como os llamaremos a partir de ahora,
necesitan primero registrarse en el foro
[aquí](http://forum.redump.org/topic/12228/want-to-register-please-read-first/).
Con ello, deberán solicitar y esperar una confirmación de acceso para
que su cuenta sea oficialmente activada y se retiren las restricciones
de acceso y uso del resto del foro.

Una vez realizado este proceso, podrás postear todos los datos del
"dump" en esta sección [aquí](http://forum.redump.org/forum/11/dumps/).
Cuando se hayan realizado una pequeña cantidad de aportes, se reconocerá
al usuario oficialmente con el estatus de "**Dumper**", para lo cual
podrá realizar de forma más automatizada y rápida la entrega de
información de nuevos "dumps" a través de una plantilla específica
recogida aquí: [New Disc form](http://redump.org/newdisc/).

La mitad de la información necesaria va a ser automáticamente generada
en un bloc de notas llamado **\!submissioninfo.txt**, el cual nos
servirá de plantilla para nuestro aporte de información sobre el disco
que hayamos "dumpeado". El resto de la información tendremos que
rellenarla nosotros manualmente:

*No te agobies si no eres capaz de dar con la información que
solicitamos siempre. A veces puede ser un proceso un poco tedioso hasta
que coges el punto y entiendes bien que debes buscar y que no. En
Redump, todos empezamos de cero y vamos a estar para apoyarte y guiarte
en el proceso, tratando de mostrar un compañerismo sano y el trato más
ameno posible, siempre que pongas solo un poco de esfuerzo por tu lado*.

  - **Game title**: Lo más obvio, especifica el nombre exacto del juego
    o disco que has dumpeado. Por favor, incluye el subtítulo del juego
    si el nombre trae uno (por ejemplo: Disney/Pixar Toy Story 2 - ¡Buzz
    Lightyear al Rescate\!)
  - **Disc title**: Algunos juegos que vienen editados en varios discos,
    pueden tener títulos específicos para cada uno. Ejemplo: [Armored
    Core: Nexus (Disc 1) (Evolution)](http://redump.org/disc/15041/) and
    [(Disc 2) (Revolution)](http://redump.org/disc/15042/). Si tu juego
    no ha sido editado en varios discos, ignora este apartado.
  - **Game languages**: Empieza el juego, y si este no te ha dado de
    antemano la opción de seleccionar el idioma, ve a "Opciones/Options"
    o "Configuración/Configuration" y busca algún selector de
    "Idiomas/Idiom/Language". En las plataformas actuales, el idioma es
    seleccionado automaticamente acorde al idioma de la interfaz del
    sistema, como en Xbox 360 o Playstation 3 y sucesivas versiones.
    Tratamos de animar a nuestros usuarios a que indaguen un poco cuales
    son los idiomas disponibles, pero si no es posible verificarlo,
    puedes dejar el espacio en blanco.
  - **Version**: Según el sistema, esta información puede ser
    automáticamente detectada por DICUI, pero en otros casos no. Si no
    estás seguro, déjalo en blanco. Para los juegos de PC, en muchas
    ocasiones viene especificado en la carátula del juego o del disco, o
    incluso en los menús "in-game" al lanzarlo.
  - **Edition**: Algunos juegos fueron relanzado bajo nuevas series y
    con nuevo embalaje o carátula, como las series "Platinum", "Greatest
    Hits" o "PlayStation 2 the Best" de Sony Playstation. Si un juego
    fue lanzado bajo su carátula original, simplemente selecciona
    "Original".
  - **Barcode**: Señala el código de números debajo del número de
    barras: [EAN](http://en.wikipedia.org/wiki/European_Article_Number)
    / [UPC](http://en.wikipedia.org/wiki/Universal_Product_Code) code,
    normalmente está impresa en la parte de atrás de la carátula o el
    embalaje del juego.
  - **Serial number**: Normalmente suele venir impreso en la carátula
    del disco. Si hay algún número de serie alternativo escrito en la
    carátula o el embalaje del juego, por favor, anótalo.
  - **Ring code info**: Toda información visible sobre los códigos que
    se encuentren escritos en la cara anterior o posterior del disco
    necesitan ser indicados. Los "Ring codes" suelen ser una serie de
    números y letras escritas en el lado posterior del disco, cerca del
    agujero o zona central del disco. Para más información puedes usar
    esta guía [Ring Code Guide](Ring_Code_Guide "wikilink").

Para finalizar... Comprime en un rar/zip todos los archivos generados
por DICUI junto al bloc de notas con la información anteriormente
solicitada, **EXCEPTO** el juego en sí (es decir, empaqueta todos los
archivos menos los que tengan las siguientes extensiones: .iso, .bin,
.scm, .img). El rar/zip generado puede ser adjuntado en el post donde
vayas a postear la información del dump (hay una opción de "attachment")
o subirlo a algún servidor de descarga (Google Drive, Dropbox, mega.nz,
etc) y adjuntar el link.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")