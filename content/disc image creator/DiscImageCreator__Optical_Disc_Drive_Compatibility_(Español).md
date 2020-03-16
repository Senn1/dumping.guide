DiscImageCreator (DIC) es una herramienta destinada al "dumping" de
discos, que trata de centrarse en ejecutar una copia perfecta de la
fuente original en formato digital. Por ello, se da la circunstancia de
que según el formato del disco, se hayan establecido unas directrices
muy concretas sobre el hardware necesario para realizar un "dumping" que
nos certifique que la copia obtenida es válida y perfecta a imagen y
semejanza del disco original.

Es decir, **para el empleo de DICUI en algunos formatos de disco se
requieren una serie de modelos de lectura y grabación de discos muy
específicos**.

## DVD

El proceso de "dumping" de los discos en formato DVD-Video y DVD-Rom es
compatible con CUALQUIER TIPO de lector o grabador que soporte la
lectura de formato DVD.

Sin embargo, el "dumping" de DVD mediante DICUI, no nos permite
confirmar si el DVD presenta algún tipo de daño u obstrucción a la
lectura completa del mismo, por lo que **en Redump solicitamos a los
usuarios que efectúen dos veces seguidas el proceso de "dumping" del
disco y comparen los hashes obtenidos** para asegurar que no hay ningún
comportamiento anómalo entre las dos copias realizadas del DVD,
confirmando que la copia realizada es correcta (es decir, si salieran
hashes distintos significaría que algún sector del DVD no ha podido
leerse correctamente y podrías estar entregando información de una copia
incorrecta).

Para el dumping de Xbox OG (la Xbox original) y Xbox 360, ver esta guía:
[esta lista de lectores
compatibles](DiscImageCreator:_Optical_Disc_Drive_Compatibility#Xbox_original_.26_Xbox_360 "wikilink").

## CD-Rom / CD-Audio

Aquí vienen las curvas. El formato del CD posee particularidades muy
incómodas de cara a preservar este formato de disco en Redump. **Solo
una serie de modelos de lector marca Plextor son soportados** para
ejecutar el método de "dumping" via DICUI, siendo los siguientes modelos
los que han sido confirmados hasta el momento como compatibles para el
proceso. Por favor, recuerda que tu unidad Plextor debe estar siempre
actualizada a la última versión de firmware [final
firmware](http://www.skcj.co.jp/discon/download/index.html) (en caso
contrario, DICUI puede indicarte un fallo en el proceso). **La última
versión de firmware también está adjuntada junto al nombre de cada
modelo de la siguiente lista.**

  - Modelos USB:
      - [PX-755UF](https://archive.org/download/PlextorFirmware/px755A%20&%20px755SA_108.zip)
      - [PX-716UF](https://archive.org/download/PlextorFirmware/px716A%20&%20px716SA%20&%20px716UF_111.zip)
      - [PX-712UF](https://archive.org/download/PlextorFirmware/px712A%20&%20px712SA%20&%20px712U_109.zip)
      - [PX-708UF](https://archive.org/download/PlextorFirmware/px708A%20&%20px708UF_112.zip)

<!-- end list -->

  - Modelos SATA. Nota: Estos modelos pueden ser muy caros o díficiles
    de localizar, pero suele ser mucho más fácil y barato localizar un
    modelo IDE y usar un adaptar IDE a USB.
      - [PX-760SA](https://archive.org/download/PlextorFirmware/px760A%20&%20px760SA_107.zip)
      - [PX-755SA](https://archive.org/download/PlextorFirmware/px755A%20&%20px755SA_108.zip)
      - [PX-716SA](https://archive.org/download/PlextorFirmware/px716A%20&%20px716SA%20&%20px716UF_111.zip)
      - [PX-712SA](https://archive.org/download/PlextorFirmware/px712A%20&%20px712SA%20&%20px712U_109.zip)

<!-- end list -->

  - Modelos IDE. Nota: Como decíamos antes, los modelos IDE pueden ser
    usados con cualquier PC con un adaptador USB (recomendamos el
    adaptador "UGREEN USB to IDE Converter, USB 3.0 to IDE" que se vende
    en Amazon - NO aconsejamos comprar los adaptadores cutres chinos que
    suelen venderse en cualquier medio barato como AliExpress) o también
    en un PC de Escritorio antiguo con la pertinente conexión IDE dentro
    de la torre.
      - PX-760 series:
        [PX-760A](https://archive.org/download/PlextorFirmware/px760A%20&%20px760SA_107.zip)
      - PX-755 series:
        [PX-755A](https://archive.org/download/PlextorFirmware/px755A%20&%20px755SA_108.zip)
      - PX-716 series:
        [PX-716A](https://archive.org/download/PlextorFirmware/px716A%20&%20px716SA%20&%20px716UF_111.zip),
        [PX-716AL](https://archive.org/download/PlextorFirmware/px716l%20aka%20px716AL%20&%20px716UFL_102.zip)
      - PX-714 series:
      - PX-712 series:
        [PX-712A](https://archive.org/download/PlextorFirmware/px712A%20&%20px712SA%20&%20px712U_109.zip)
      - PX-708 series:
        [PX-708A](https://archive.org/download/PlextorFirmware/px708A%20&%20px708UF_112.zip)
      - PX-704 series:
      - [Premium2
        series](https://archive.org/download/PlextorFirmware/Premium2_103.zip):
      - Premium series: Premium, PremiumU
      - PX-W5224 series: [PX-W5224A, PX-W5224TA,
        PX-W5224TU](https://archive.org/download/PlextorFirmware/pxw5224_104.zip)
      - PX-4824 series: [PX-W4824A, PX-W4824TA, PX-W4824U,
        PX-W4824TU](https://archive.org/download/PlextorFirmware/pxw4824_107.zip)
      - PX-4012 series: [PX-W4012A, PX-W4012TA, PX-W4012S, PX-W4012TS,
        PX-W4012U,
        PX-W4012TU](https://archive.org/download/PlextorFirmware/pxw4012_107.zip)

<!-- end list -->

  - Modelos SCSI: Estos modelos solo pueden ser empleados con un PC de
    Escritorio antiguo, el cual tenga en el interior de la torre algún
    puerto compatible.
      - [PX-W4220T](https://archive.org/download/PlextorFirmware/pxw4220_104.zip),
        PX-32TS/CS, PX-83CS/85CS, PX-63CS/65CS, PX-43CS 43CE 43CH/45CS
        45CE 45CH, DM-3028/5028, DM-3024/5024, DM-3021/5021,
        DM-3020/5020

## GD-Rom

Los discos GD-Rom son probablemente el formato de disco más dificultoso
de preservar acorde al método de Redump por sus extrañas
particularidades, al presentar dos áreas diferentes de datos. Estos
discos fueron creados exclusivamente para Dreamcast y algunas unidades
alternas creadas por Sega para otros menesteres que hacían uso del
lector que empleaba Dreamcast.

Al presentar dos áreas distintas físicas donde se alojan los datos (la
LD o "Low Density area" y la HD o "High Density area"), el objetivo será
"dumpear" tanto una como otra de forma separada, para lo cual como es
esperado por desgracia, **se requiere un hardware muy especial
también**.

Para el "dumping" de la **LD area**, se aplican las mismas reglas que un
CD normal, porque usan la misma tecnología. La lista de lectores
compatibles para dumpear el "LD area" es la misma que tenéis arriba,
pero aquí os dejamos un recordatorio. La particularidad es que el modelo
Plextor PX-708 es el único modelo capaz de leer tanto el "LD area" como
la "HD".

### LD area

Modelos Plextor que dan soporte al "dumping" del **LD area**:

  - Modelos PX 7-series: PX-704, PX-708, PX-712, PX-714, PX-716, PX-755,
    PX-760
  - Modelos Premium series: Premium, Premium2
  - Modelos adicionales PX-series: PX-4012, PX-4824, PX-W5224,
    PX-W4220T, PX-32TS, PX-32CS, PX-83CS, PX-85CS, PX-63CS, PX-65CS,
    PX-43CS, PX-43CE, PX-43CH, PX-45CS, PX-45CE, PX-45CH
  - Modelos DM-series: DM-3028, DM-5028, DM-3024, DM-5024, DM-3021,
    DM-5021, DM-3020, DM-5020

### HD area

Para el **HD area**, el proceso va a ser distinto, necesitando uno de
los siguientes lectores para lograrlo. En nuestros test, hemos
confirmados que algunos funcionan mejor que otros:

**Recomendados**

  - Modelos Samsung TSSTCorp: TS-H353A aka SH-D163A, TS-H352C aka
    SH-162C

**No recomendados** (no fueron tan efectivados en comparación a los
modelos señalados como Recomendados durante nuestros tests):

  - Modelo Plextor TS-H353B
  - Modelo Samsung TSSTCorp TS-H353B

**No testeados, pero deberían funcionar(?)**

  - Modelos Lite-On: LH-18A1H, SOHD-167T, LTD-165H, SOHD-16P9S
  - Modelos Plextor: PX-W4824TA, PX-W4824TU, PX-755SA
  - Modelos Samsung TSSTCorp: TS-H353B, TS-H192C, SH-D162D
  - Modelo NEC: CDR-1901A
  - Modelo LG: GCR-8522B

## PlayStation 3 & 4

La lista de modelos compatibles procede de la siguiente fuente
[here](https://rpcs3.net/quickstart).

  - Modelos LG: BH26NS40, UH12NS30, BH16NS40, BH16NS48, BH14NS40,
    WH24NS40, WH12LS30, WH24LS30, WH26NS40, WH16NS40, WH14NS40,
    WH16NS48, BP50NB40
  - Modelos Asus: BC-08B1LT, BC-16D1HT, BC-12B1ST, BC-12D2HT, BW-12B1ST,
    BW-16D1HT
  - Modelos LITE-ON: DH-4O1S, IHBS112
  - Sony Optiarc 5300S
  - Sony PlayStation 3 stock drive
    [1](https://www.ebay.com/itm/252061696576) con el adaptador "3k3y
    ripper"[2](https://www.modchipcentral.com/store/product.php?productid=17905)
  - BENQ BR1000

## Xbox original & Xbox 360

Para "dumpear" discos de Xbox original y Xbox 360 hay dos opciones
respecto al hardware. El empleo de los modelos Kreon mencionados
facilita bastante el proceso y es más barato.

  - Kreon disc drives:
      - SATA models:
          - SH-D163A aka TS-H353A
          - SH-D163B aka TS-H353B (no funcionará con un adaptador
            externo, necesita ser montado en una PC torre de escritorio)
      - IDE models:
          - SH-162C aka TS-H352C aka SD-M2012C(?)
          - SH-D162D/TS-H352D
  - [0800 drive flasheado con custom firmware + Team Xecuter X360USB
    PRO](0800 "wikilink")

## Xbox One

Para mayor discusión sobre la compatibilidad de los diversos lectores:
[3](http://forum.redump.org/topic/16301/done-xbox-one/)

  - BDR-208D
  - BDR-209D
  - Pioneer BD-ROM BDC-TD03VA (BDC-TD03): Solo compatibles con discos
    Single Layer BD-25, no con discos Double layer (AKA Doble Capa)
    BD-50.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")
[Category:Optical Disc Drives](Category:Optical_Disc_Drives "wikilink")