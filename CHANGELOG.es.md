Lo que cambia de versión a versión, descrito desde la perspectiva de la
aplicación, no de sus entrañas. Quien quiera saber *de qué* está construida
lo encuentra en [LIZENZEN.md](LIZENZEN.md); aquí figura lo que cambia para el
trabajo con ella.

La numeración sigue el esquema habitual: el **primer** número cambia cuando
algo deja de funcionar como antes, el **segundo** con nuevas funciones, el
**tercero** con correcciones de errores.

---

## 0.10.52-alpha.20260903 – 3 de septiembre de 2026

- Un lote de más de cuatro archivos ya no se queda bloqueado después de
  responder en varias ventanas de vista previa. Los demás documentos se
  siguen preparando en segundo plano; después de una respuesta, el archivo
  correspondiente termina ahora de procesarse de forma fiable y se libera el
  siguiente lugar en el lote.
- La comparación de logotipos breves de empresa en PDF se limita ahora al texto
  reconocido en imágenes. Por tanto, en el texto normal de una página, una
  coincidencia larga del modelo que abarca varias líneas ya no hace que se
  oculte además una palabra idéntica en otro lugar.

## 0.10.51-alpha.20260903 – 3 de septiembre de 2026

- La lista de cambios aparece ahora en el idioma del usuario – en
  maskuro.com/neuigkeiten y en el programa, en «Cambios», así como en
  «Novedades» después de una actualización. Hasta ahora, las dieciocho
  versiones lingüísticas mostraban allí texto en alemán bajo un encabezado
  traducido. Cuando todavía falta una traducción, la versión correspondiente
  permanece en alemán en vez de desaparecer; la lista de versiones es la
  misma en todas partes.

## 0.10.50-alpha.20260903 – 3 de septiembre de 2026

- Los logotipos de empresa recurrentes en PDF se limpian ahora de forma
  consistente, incluso cuando el reconocimiento de texto lee el rótulo de
  forma distinta en una página o deja pasar por completo el emblema
  redondo. Una desmarcación expresa en la vista previa sigue siendo
  vinculante y ningún ajuste posterior puede anularla.
- Los precios sin moneda en tablas escaneadas se tachan ahora por completo
  también cuando el encabezado de la tabla y los valores se encuentran en
  distintas imágenes de PDF superpuestas. Cantidades, horas, pesos y
  porcentajes se mantienen; los números muy alejados entre sí ya no se unen
  por error en un solo importe.
- La búsqueda de firmas detecta ahora también trazos azules débiles bien
  fundamentados y siglas de firma rojas estrechas. Diagramas punteados,
  curvas de medición, sellos, logotipos y marcas de edición rojas anchas
  quedan excluidos de este ajuste estricto.
- Los tachados en imágenes de PDF giradas, reflejadas, cizalladas o
  recortadas alcanzan ahora el polígono de imagen real. Al mismo tiempo, los
  roles técnicos en partidas de servicios, los valores materiales de
  vehículos y neumáticos, así como la «compensación» técnica, se delimitan
  con mayor precisión frente a falsos positivos; los roles de contacto
  rotulados de forma explícita y los números de teléfono permanecen
  protegidos.
- La verificación visual antes de guardar un PDF ya no congela la ventana:
  en documentos grandes con muchos hallazgos, hasta ahora permanecía varios
  segundos sin respuesta; ahora un aviso indica que se está verificando y la
  ventana sigue dibujándose.
- La recuperación de un valor desde una imagen en el editor de correcciones
  lee ahora cada imagen original solo una vez mediante reconocimiento de
  texto; hasta ahora volvía a ejecutarse en cada nueva recuperación para las
  mismas imágenes.
- La recarga de la etapa alta y del modelo de firmas apenas necesita ya
  memoria de trabajo: el paquete de 596 MB se mantenía hasta ahora
  completo en memoria, se verificaba y se descomprimía allí mismo, más de
  un gigabyte de pico en el programa en ejecución, en equipos con 8 GB el
  momento exacto en que todo empezaba a atascarse. Ahora fluye por bloques
  al disco y se verifica y descomprime allí.
- La búsqueda en el editor de correcciones ya no congela los PDF grandes:
  hasta ahora, la primera letra escrita en el campo de búsqueda leía todas
  las páginas de una vez; con 200 páginas la ventana se detenía dos
  segundos, y otra vez después de cada tachado. Las páginas se leen ahora
  por partes; hasta entonces el contador muestra «Leyendo…», el resultado es
  el mismo.
- Las páginas de PDF rasterizadas —tras un reconocimiento de texto o cuando
  un texto no se pudo eliminar limpiamente— se guardan ahora notablemente
  más pequeñas y sin pérdida de imagen: en lugar de codificar siempre como
  JPEG, cada página se codifica también sin pérdidas, y la versión más
  pequeña es la que se incorpora al archivo. Un escaneo limpiado se reduce
  así de 248 a 48 KB, el documento de ejercicio con reconocimiento de texto
  de 913 a 702 KB; el texto se mantiene absolutamente nítido.
- Los modelos recargados (etapa alta, firmas, rostros, segundo
  reconocimiento de texto) se liberan ahora de la memoria de trabajo
  transcurridos diez minutos sin ninguna limpieza. Hasta ahora permanecían
  cargados hasta el cierre del programa; quien usaba una vez la búsqueda de
  firmas y la etapa alta retenía de forma permanente más de dos gigabytes.
  La siguiente ejecución los recarga en uno o dos segundos; la línea de
  estado lo indica.
- PowerPoint: los nombres genéricos de los diseños de diapositiva y de los
  patrones de diapositiva («Vacío», «Diapositiva de título») ya no se
  sustituyen como si fueran un dato. «Vacío» es también un topónimo y se
  tachaba por error en cada presentación en alemán e inglés; ahora solo se
  limpian los nombres asignados manualmente a las propias diapositivas.
- En PDF, el suavizado de líneas ya no arrastra el encabezado de la línea
  siguiente hacia un hallazgo: el número del siguiente punto de una lista
  tras una fecha se consideraba número de teléfono, un encabezado de campo
  como «Código» o «Número de pedido» tras una cifra se consideraba código
  postal con localidad, y la línea de localidad bajo la dirección duplicaba
  la localidad. El hallazgo correcto, más corto, quedaba así desplazado.
  Sobre 132 PDF del corpus, de 24 hallazgos adicionales de suavizado quedan
  los dos reales; en el corpus de práctica las falsas alarmas bajan de 29 a
  21 con la misma tasa de acierto.
- «Buscar y tachar en carpeta de PDF» en el editor de correcciones ya no
  bloquea la ventana: la ejecución trabaja en segundo plano, el progreso y
  el botón de cancelar responden, y los menús o pestañas ya no pueden
  manejarse en medio de un archivo a medio terminar.
- Las páginas escaneadas con hallazgos se reescriben ahora una sola vez al
  tachar, en lugar de dos: hasta ahora el programa rellenaba los recuadros
  de los hallazgos y los de las justificaciones en dos pasadas, y la segunda
  comprimía de nuevo la imagen del escaneo recién guardada. Esto ahorra
  tiempo en escaneos grandes y evita una pérdida de calidad de imagen.
- Hojear, hacer zoom y las miniaturas en el editor de correcciones responden
  más rápido: hasta ahora cada página renderizada pasaba por una compresión
  PNG y volvía a descomprimirse solo para mostrarse, unas décimas de
  segundo por página en pantallas de alta resolución. La imagen llega ahora
  directamente, píxel por píxel igual.
- La verificación visual antes de guardar un PDF («prueba de salida») es
  unas tres veces más rápida, con el mismo resultado.
- La ventana principal aparece de nuevo un cuarto de segundo antes: la
  comprobación de si el reconocimiento de texto está listo en este equipo se
  ejecutaba al construir la ventana —en Mac incluyendo una solicitud de
  prueba al reconocimiento del sistema— y la página de ajustes de los
  componentes adicionales consultaba además el estado de los 48 idiomas.
  Ambas cosas ocurren ahora en segundo plano o solo cuando realmente se abre
  la lista de idiomas; hasta entonces se muestra «Comprobando reconocimiento
  de texto…».
- Tras una búsqueda de firmas, el programa ocupa unos 300 MB menos de
  memoria de trabajo: el modelo de reconocimiento residía hasta ahora por
  duplicado en memoria, una vez para verificar su autenticidad y otra para
  calcular. Se sigue verificando, solo que sin la segunda copia.
- El reconocimiento de texto en PDF se ha vuelto notablemente más rápido:
  para cada encabezado de campo de una página («Fecha de nacimiento:»,
  «Número fiscal:») se enviaba hasta ahora una consulta propia por tipo de
  dato al reconocimiento, de nuevo en cada página, aunque el mismo
  encabezado ya hubiera aparecido diez páginas antes. La respuesta se
  recuerda ahora; un pliego de condiciones de dos páginas hacía así 324
  consultas, ahora solo las distintas. Los hallazgos son los mismos.
- Las tablas grandes vuelven a limpiarse en segundos en lugar de minutos: en
  el modo anonimizador —el predeterminado—, la comparación de valores ya
  conocidos se volvía más lenta con cada celda adicional, porque una memoria
  intermedia se descartaba y reconstruía en cada coincidencia. 5000 celdas
  necesitaban para ello unos 18 segundos, ahora medio segundo; el resultado
  es idéntico carácter por carácter.
- La ventana principal aparece de nuevo notablemente más rápido: la lista de
  países de los ajustes cargaba al construir la ventana toda la biblioteca
  de reconocimiento en primer plano —unos 0,7 segundos en Mac, en Windows
  proporcionalmente más—, aunque para ello solo se necesitan los nombres de
  los países. La lista procede ahora de un catálogo ligero; la biblioteca se
  carga como estaba previsto en segundo plano, mientras la ventana ya está
  disponible. Esto se aplica también tras cada cambio de idioma o de
  apariencia que reinicia el programa.
- El laboratorio de documentos recorre ahora por completo encabezados de
  campo recortados, sombras de valor locales y recortes de escaneo fuertes
  a través de contenedores PDF, DOCX y ODT. La matriz abarca 680 archivos de
  40 familias de documentos y 17 ejes de contenedor. Maskuro elimina en los
  nuevos perfiles, así como en los perfiles básico y de características
  completos, todos los valores esperados, sin falsa alarma medida, sin
  daño a valores que deben conservarse ni interrupciones.
- Los escaneos usados varias veces se comprueban y limpian ahora en cada
  colocación visible: el laboratorio de documentos comparte el mismo objeto
  de imagen en distintas páginas, tamaños y orientaciones dentro del PDF, y
  hace referencia varias veces a la misma parte de imagen en DOCX y ODT.
  Los nombres técnicos de marco ODT como «Escaneo de formulario pequeño
  apaisado» ya no se consideran una persona; los nombres y lugares libres
  con un inicio similar permanecen protegidos. Una conjetura genérica de
  formulario del análisis final de páginas de PDF ya no puede generar un
  gran falso positivo de dirección en una superficie de imagen ya leída de
  forma independiente. Los 120 contenedores nuevos alcanzan en el perfil
  básico y de características los 813 y 840 valores esperados
  respectivamente, sin falsa alarma, violación de conservación ni
  interrupción; la aceptación completa de características de 800 archivos
  confirma 5600/5600.
- El laboratorio alemán de OCR abarca ahora 560 escaneos de 40 familias de
  documentos. Las nuevas variantes recortan los márgenes de encabezado de
  campo y de página, o colocan una sombra directamente sobre un valor.
  Maskuro protege con ello también nombres, direcciones, fechas de
  nacimiento, claves médicas y números de identificación rotulados con un
  rotulado parcialmente dañado. Al mismo tiempo, los restos de campos de
  formulario, los encabezados oficiales y los términos jurídicos e
  informativos objetivos ya no se sustituyen como personas o lugares. Los
  perfiles básico y de características completos alcanzan 3794/3794 y
  3920/3920 valores esperados respectivamente, sin falsa alarma medida ni
  interrupción.
- La selección automática de imágenes de PDF ya no elimina fotografías de
  producto de gran superficie, etiquetas energéticas ni series de retratos
  solo por empezar en el margen superior de la página. Las imágenes de
  encabezado/pie realmente planas y los membretes que arrancan en el borde
  de la hoja se siguen eliminando. En los directorios de empleados, los
  nombres se reconocen ahora también a partir de entradas estructuralmente
  repetidas cuando el título visible del documento solo existe como imagen.
  El reconocimiento ya no está limitado a dos palabras de rol concretas y
  a la sigla «DW»: entre una y cuatro funciones partidas por salto de línea,
  así como «Durchwahl», «Nebenstelle», «Ext.» y «Extension», se deducen a
  partir de la forma constructiva común. Los roles y encabezados de sección
  permanecen aunque el modelo de lenguaje, tras la resolución de
  solapamientos, solo deje un adjetivo de rol. Las cuadrículas horizontales
  de roles ya no se consideran por error columnas de nombres. Si el OCR de
  página funde varias tarjetas en una palabra de mayúsculas internas
  extremadamente ancha, una comparación local estrecha separa las
  verdaderas casillas de palabra; de este modo no queda ni un nombre suelto
  ni una barra errónea ancha. Los logotipos de empresa repetidos de varias
  líneas se tachan ahora también en páginas sin texto de OCR utilizable y
  con hasta dos píxeles de desviación de posición, a partir de una plantilla
  de píxeles idéntica ya confirmada; al mismo tiempo, las segundas lecturas
  locales más cortas del OCR ya no pueden añadir una zona de encabezado más
  grande como nombre inventado. Los números de página ante un membrete
  corporativo ya no forman parte del nombre de la organización; los nombres
  de marca reales que empiezan con números permanecen protegidos. Varias
  palabras de producto, técnicas y de formulario medidas ya no se proponen
  como personas.
- La búsqueda de firmas en PDF se ejecuta ahora solo tras la limpieza de
  imagen por OCR, visita también páginas sin hallazgo de texto habitual y
  vuelve a proyectar correctamente los recuadros de hallazgo de páginas
  giradas al espacio del documento. Las fotografías de producto densas ya
  no se tachan como firma. Sobre campos de firma rotulados de forma
  inequívoca, un recurso estrecho a trazos cierra pequeñas lagunas del
  modelo; las líneas vacías con fecha preimpresa no lo activan. Los
  escaneos puros con hallazgos exclusivamente de OCR o de firma ya no se
  interrumpen en esta fase por un tachador de imagen que se cargaba solo en
  la rama de texto.
- Muchos documentos abiertos a la vez se mantienen distinguibles en el
  editor de correcciones: las pestañas ya no se reducen a un simple
  puntos suspensivos, y un botón de lista a la derecha muestra todos los
  nombres de archivo completos uno debajo del otro. Las pestañas pueden
  reordenarse arrastrando y cerrarse con su aspa desde la misma lista que
  en la ventana principal; el trabajo sin guardar sigue aclarándose primero
  en ese caso. Un clic derecho ofrece además «Cerrar», «Cerrar otras
  pestañas» y «Cerrar pestañas a la derecha».
- Un bloqueo breve de Windows por parte de un antivirus o del índice de
  búsqueda ya no hace que la carpeta de modelo de lenguaje o de diccionario
  completamente cargada falle con «Acceso denegado» al colocarla en su
  lugar final. Maskuro reintenta ahora este último cambio de carpeta
  durante un breve tiempo.
- El laboratorio alemán de documentos comprueba ahora los contenedores
  también con rotación de página de PDF variable, imágenes de PDF giradas
  de forma independiente, así como imágenes de tabla escaladas y recortadas
  en DOCX y ODT. Los valores de campo en imágenes visiblemente giradas
  vuelven a reconocerse por completo, los designadores técnicos de columna
  ya no se sustituyen como lugares, y los nombres con apellido común ya no
  se descomponen en hallazgos parciales duplicados por el ajuste posterior
  de consistencia. La matriz, duplicada a 320 archivos, alcanza con el
  reconocimiento de fecha, dinero y medicina activado 2240/2240 valores
  esperados sin falsa alarma medida ni interrupción.
- Los PDF de varias páginas basados en imagen, los PDF mixtos de texto e
  imagen y los escaneos incrustados en DOCX u ODT se comprueban ahora en un
  laboratorio propio de 160 archivos sobre las 40 familias de documentos
  alemanas. Los nombres técnicos de marco ODT y los códigos de dispositivo
  rotulados ya no se sustituyen como lugares; los nombres, lugares y
  direcciones reales en las mismas estructuras permanecen protegidos. Con
  el reconocimiento médico o de dinero activado se elimina además por
  completo una dosificación que sigue directamente o un intervalo de pago.
  Las ejecuciones de contenedor, de base de texto, de características de
  texto y de características de OCR alcanzan en conjunto sus respectivos
  totales completos sin falsa alarma medida ni interrupción.
- La verificación de seguridad antes de guardar muestra ahora los puntos
  llamativos del PDF como una lista seleccionable individualmente.
  «Comprobar en el editor» abre exactamente la página seleccionada y marca
  la zona; los hallazgos parciales superpuestos en el mismo lugar aparecen
  ahora solo una vez. Los nuevos textos de interfaz están completos en los
  17 idiomas de interfaz traducidos.
- Los archivos Markdown conservan al sustituir su sintaxis de enlaces,
  resaltado y notas al pie. Maskuro lee para ello una versión de idéntica
  longitud en caracteres sin marcas Markdown; los guiones bajos en
  direcciones de correo electrónico, los asteriscos de cálculo y los
  enlaces normales sin dato personal permanecen sin cambios.
- Varias entradas manuscritas en la misma página de PDF se buscan ahora en
  hasta tres pasadas. Los trazos ya encontrados solo se ocultan en la
  imagen de trabajo, para que ya no desplacen firmas más débiles; en
  páginas giradas, las áreas de tachado vuelven a caer en el lugar de
  hallazgo visible. Los rellenos de imagen de fases de seguridad anteriores
  se conservan al reescribir posteriormente.
- «Restablecer todos los ajustes» abarca ahora también «Texto en imágenes».
  Si el componente de OCR no está disponible, el interruptor permanece
  técnicamente apagado, sin marcarse por error como desviado del estado de
  entrega.
- Los fragmentos de imagen grandes en el margen superior de la página ya no
  se consideran encabezado solo por su posición. Con ello se conservan en
  particular las descripciones de artículo basadas en imagen y los
  contenidos de tabla. Los nuevos hallazgos de correo electrónico y de
  formulario, exactos por tipo, tampoco se filtran ya fuera de la
  verificación visual final en una superficie de imagen ya comprobada.
- Las líneas técnicas de posición y de artículo en ofertas de climatización
  y electricidad se distinguen ahora con mayor precisión de personas,
  lugares y organizaciones. Esto afecta, entre otros, a tipos de cable,
  alimentación de CA, números de posición y códigos de producto en
  mayúsculas; los nombres y direcciones reales permanecen protegidos.
- La verificación de PDF limpiados reales ya no confunde componentes de
  precio como `1 699,59` con números de teléfono y ya no recorta de una
  fecha completa como `08.05.2025` un supuesto dato de tarjeta. Los nombres
  tras un tratamiento terminan en el salto de línea en lugar de en la calle
  siguiente; los nombres de lugar en nombres de archivo de anexos se
  limitan al lugar real. Los colores de vehículo, los valores técnicos de
  estado, las denominaciones de actividad comercial y las formas jurídicas
  de producto también se conservan. Las lecturas de marcador de posición
  dañadas como `|PLLZ` ya no se tratan como dato personal en una segunda
  pasada de OCR.
- Las imágenes de PDF guardadas por separado reciben en la verificación
  visual final una mirada adicional en su posición de imagen original. Esta
  solo puede tachar adicionalmente valores que Maskuro ya haya reconocido
  con seguridad en la misma página. Así, por ejemplo, un pequeño sello de
  dirección girado se cubre por completo, sin inventar nuevas palabras a
  partir de encabezados de imagen o dibujos técnicos como datos personales.
- En los textos OpenDocument, las iniciales del autor de una nota
  (comentario) se vacían ahora junto con el autor. LibreOffice las guarda
  junto al nombre completo como una forma abreviada propia y muestra
  exactamente esa en el margen de la página; hasta ahora seguía apareciendo
  «SO», mientras que «Sieglinde Ortner» al lado ya era desde hacía tiempo
  un marcador de posición. Solo se vacía cuando el autor se ha sustituido
  realmente; la nota de un departamento conserva su identificación.
- En las cartas comerciales italianas, las expresiones estándar al
  principio de la frase ya no se consideran nombre ni lugar: «Restiamo a
  disposizione», «Rimaniamo», «Attendiamo», «Alleghiamo», «Comunichiamo» y
  «Auguriamo buon lavoro» quedaban hasta ahora atrapadas como supuesta
  persona o dato de lugar. Los nombres reales en el mismo lugar («Rossi
  Mario») se siguen reconociendo.
- Los escaneos a dos columnas protegen ahora identificaciones y datos de
  lugar rotulados también cuando el reconocimiento de texto entrega primero
  todos los encabezados de campo y después todos los valores. La asignación
  sigue la línea de píxeles visible y funciona también en páginas giradas
  90 grados. Las partes estrechamente separadas de una identificación de
  pasaporte o de contrato se tachan conjuntamente; las fechas de nacimiento
  rotuladas y las claves ICD y PZN también quedan cubiertas, las palabras
  técnicas siguientes se mantienen. Los nombres cortos y los nombres de
  usuario se protegen en campos exactos; las direcciones de correo
  electrónico descompuestas en varias palabras de OCR solo con proximidad
  estrecha y gramática de correo electrónico completa. Una corrección
  vinculada a un campo de caracteres confundibles, así como la relectura
  local de un campo de persona aún vacío, resuelven escaneos dañados y
  girados sin ampliar los campos objetivos ni los valores ya ocupados. Los
  márgenes de seguridad siguen el tamaño de palabra, y el perfil de
  características incluye unidades de dosis e intervalos de pago
  inmediatamente contiguos. Los formularios introducidos ligeramente
  torcidos se reproyectan geométricamente a partir de varias líneas de OCR
  de igual dirección; el ruido de redondeo o testigos contradictorios no
  bastan. Los prefijos de letras cortos se conservan ante una
  identificación con guion, y un hallazgo de dirección rotulado completo
  solo sustituye a su hallazgo parcial de calle del mismo tipo. Un
  encabezado de campo de rol mal leído solo cae en una columna de
  formulario ocupada por al menos tres encabezados conocidos; los nombres
  de chat permanecen protegidos. Un recorte de margen escaso y una
  sobreexposición local con reflejo de luz diagonal completan la matriz de
  imágenes. Los hallazgos de persona, lugar y empresa que abarcan varias
  líneas de formulario se limitan al valor respectivo en una columna de
  campo ocupada varias veces. Un valor de posición técnico solo cae con
  encabezado de posición y forma de identificación correspondiente; los
  nombres reales permanecen protegidos. También los valores de correo
  electrónico interrumpidos por el reflejo de luz se eliminan tras un
  encabezado de campo de correo electrónico explícito con un margen de
  imagen estrecho y limitado a los vecinos. Dos pares de campo-valor de la
  misma línea visible se evalúan ahora de forma independiente; los valores
  en una línea base más profunda solo se acoplan tras tres testigos
  geométricos coincidentes. Con ello, los números de identificación, las
  fechas de nacimiento y las direcciones permanecen totalmente protegidos
  incluso en diseños de formulario densos. Calle, código postal y localidad
  solo se unen dentro del mismo campo de dirección y con gramática postal
  adecuada. Los campos técnicos estrechamente delimitados para
  medios/ayudas técnicas y estado dental ya no generan falsas alarmas de
  lugar o de directorio; los nombres reales y los campos con nombres
  similares permanecen protegidos. El laboratorio alemán de documentos
  abarca ahora 440 escaneos y alcanza 2981/2981 en el perfil básico y
  3080/3080 en el perfil de características. Las once mutaciones de imagen
  y las 40 familias de documentos están al 100 por ciento, sin falsa alarma
  medida, violación de conservación ni interrupción.
- Las capas de texto de PDF con separadores de celda perdidos limitan ahora
  los hallazgos de organización, dirección y lugar según la estructura
  repetida de campo-valor. Los encabezados de campo ante valores de empresa
  y las flechas técnicas como `=>` o `->` ya no forman parte del hallazgo.
  La vista adicional para saltos de línea suaves ya no puede extender los
  hallazgos de forma jurídica y lugar a través de varias filas de tabla; una
  dirección ya completa termina antes del siguiente encabezado de campo con
  su valor. La ejecución final sobre los 1600 documentos TXT, HTML, PDF y
  DOCX elimina 10 840/10 840 valores esperados con cero falsas alarmas,
  cero violaciones de conservación y cero interrupciones.
