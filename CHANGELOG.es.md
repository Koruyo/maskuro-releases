Lo que cambia de versión a versión, descrito desde la perspectiva de la
aplicación, no de sus entrañas. Quien quiera saber *de qué* está construida
lo encuentra en [LIZENZEN.md](LIZENZEN.md); aquí figura lo que cambia para el
trabajo con ella.

La numeración sigue el esquema habitual: el **primer** número cambia cuando
algo deja de funcionar como antes, el **segundo** con nuevas funciones, el
**tercero** con correcciones de errores.

---

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

## 0.10.44-beta.1 – 1 de septiembre de 2026

- La compilación del paquete genera salidas separadas para Windows x64 y ARM64, macOS
  en Apple Silicon e Intel, así como Linux x64 y ARM64. Los nombres de paquete,
  la selección de actualización y las publicaciones distinguen la arquitectura; una
  publicación permanece bloqueada mientras falte uno de los seis destinos o su
  comprobante de dependencias. Linux ARM64 requiere, por Qt, al menos glibc
  2.39. Solo Windows x64 y macOS en Apple Silicon están por ahora completamente
  validados en hardware real; los demás paquetes de arquitectura deben marcarse
  claramente como versiones preliminares para pruebas, no para uso productivo.

- Con varios archivos, el reconocimiento ahora sigue trabajando mientras una
  vista previa espera revisión. Se muestran hasta tres vistas previas preparadas
  sucesivamente; al mismo tiempo solo se sigue procesando un documento,
  y un archivo de resultado solo se crea tras su aprobación. Una excepción
  permanente elegida en la vista previa también se aplica a los documentos
  siguientes ya preparados.

- Los certificados de redacción ahora pueden comprobarse en cualquier momento directamente en el menú Archivo contra
  el documento censurado. Maskuro distingue entre un archivo firmado
  coincidente, un comprobante coincidente pero sin firmar, una firma
  inválida y un documento que no pertenece al certificado. No se requiere una licencia
  ni la cuenta original del sistema operativo para la comprobación.
  Para puntos de verificación automáticos está disponible la misma comparación mediante
  `--zertifikat-pruefen`; los códigos de retorno distinguen coincidencia,
  error de manejo y comprobante inválido.
  La comprobación además compara el ID de Maskuro incrustado con el
  certificado; un ID ajeno introducido libremente destaca así incluso con un
  comprobante sin firmar.
  Con firma válida, el resultado de la verificación muestra además al editor
  activado por la administración con cuenta del sistema operativo, ID de cuenta
  técnica y plataforma. Los datos no confirmados de comprobantes sin firmar o
  inválidos no se emiten.

- Un nuevo laboratorio de documentos alemanes genera 160 documentos TXT, HTML, PDF y
  DOCX completamente sintéticos de diez áreas y cuatro
  variantes de estructura. El manifiesto distingue ahora explícitamente entre
  datos que deben desaparecer y textos técnicos o
  identificadores objetivos que deben conservarse; la familia de documentos, la mutación y
  la fuente de estructura pública están documentadas de forma trazable.

- El laboratorio de documentos alemanes se amplió a 280 archivos, siete formas de estructura,
  1.540 datos objetivo y 1.036 anclas de conservación. Se comprueban ahora también
  formularios numerados, campos PDF/de máscara entre corchetes e
  asignaciones técnicas `=>`. El estado completo ampliado alcanza en TXT, HTML, PDF y
  DOCX un 100 por ciento cada uno con cero falsas alarmas. Los campos de fecha y
  número de identificación entre corchetes, los separadores de flecha y las asociaciones expresamente
  rotuladas se reconocen ahora estructuralmente.

- Una segunda ampliación del laboratorio eleva el conjunto a 400 documentos, diez
  formas de estructura, 2.200 datos objetivo y 1.480 anclas de conservación. Los
  valores clave de tipo JSON, las listas YAML y los campos de formulario en mayúsculas alcanzan junto
  con el conjunto anterior el 100 por ciento con cero falsas alarmas. Las fechas de nacimiento
  y números de identificación citados, así como roles expresamente rotulados como
  personas aseguradas, solicitantes, obligadas a declarar y con poder de representación,
  se reconocen ahora también en estas formas de exportación.

- Un modo OCR separado del laboratorio de documentos alemanes genera adicionalmente
  200 escaneos de imagen puros de las 40 familias. Páginas limpias, de bajo
  contraste, de baja resolución, con artefactos JPEG y giradas 90 grados
  se vuelven a medir con recuadros de píxeles exactos, sin alterar la base
  textual comparable de 1.600 archivos. El manifiesto separa las
  características activables de fecha, dinero y medicina del perfil base y conoce
  las lecturas OCR documentadas sin contarlas como puntos objetivo adicionales. La
  medición se desglosa por mutación y familia de documentos. Los límites
  de campo estrechos evitan, entre otras cosas, que `Az` en el topónimo `Graz` censure
  una fecha siguiente como número de expediente; la matriz base actual funciona
  con cero falsas alarmas y cero interrupciones.

- Cinco familias de documentos alemanes adicionales para factura/albarán,
  banco/crédito, alquiler/administración de fincas, escuela/universidad y
  logística/aduana amplían el laboratorio a 600 archivos con 3.520 datos objetivo y 2.360
  anclas de conservación. Una vía estrecha de tablas PDF utiliza el encabezado explícito
  `Feld Angabe` cuando la capa de texto pierde separadores de celda; una nueva
  selección `--familien` acelera las mediciones parciales. Los 200 archivos nuevos
  alcanzan 1.320/1.320 con cero falsas alarmas y cero interrupciones.

- Seguro/siniestro, trabajo/salario, medicina/laboratorio, vehículo/taller y
  técnica/mantenimiento amplían el laboratorio de documentos alemanes a 800 archivos con
  4.960 datos objetivo y 3.200 anclas de conservación. Se reconocen identificadores estrechamente
  rotulados de pólizas, pacientes, inspectores y vehículos, así como nuevos campos de
  rol, dirección y organización. La nueva matriz parcial y la
  matriz completa alcanzan el 100 por ciento con cero falsas alarmas y cero
  interrupciones en TXT, HTML, PDF y DOCX.

- Construcción/licitación, energía/medio ambiente, asociación/sociedad,
  comunicación/calendario y hotel/evento elevan el laboratorio de documentos alemanes
  a 1.200 archivos con 7.920 datos objetivo y 4.800
  anclas de conservación. Se reconocen ahora también en todos los formatos de exportación nuevos campos de
  rol, empresa, dirección, registro, adjudicación,
  reserva y cuenta de usuario. Los números de contador se conservan como identificadores objetivos. La matriz parcial y
  completa alcanzan el 100 por ciento con cero falsas alarmas y cero interrupciones.

- Gastronomía/servicio de reparto, farmacia/receta, funeraria/cementerio,
  deporte/afiliación e inmobiliaria/agencia amplían el
  laboratorio de documentos alemanes a 1.400 archivos con 9.360 datos objetivo y 5.640
  anclas de conservación. Se reconocen nuevos roles de personas, campos de dirección y
  números de encargo de búsqueda. Los nombres de empresa rotulados con forma jurídica
  permanecen completamente protegidos incluso tras un salto de línea automático;
  las categorías de edad y los especialistas ya no se sustituyen erróneamente. La matriz parcial y
  completa alcanzan el 100 por ciento con cero falsas alarmas y cero interrupciones.

- Tratamiento dental, autoescuela, bomberos/intervención, comunidad energética y
  viaje combinado amplían el laboratorio de documentos alemanes a 1.600 archivos con
  10.840 datos objetivo y 6.440 anclas de conservación. Se reconocen estructuralmente nuevos roles, campos de dirección
  así como identificadores de tratamiento, formación, intervención, energía y
  contrato de viaje. La nueva matriz parcial de 200 archivos
  alcanza 1.480/1.480; la matriz completa alcanza
  10.840/10.840. Ambas se mantienen con cero falsas alarmas y cero interrupciones.

- La medición completa del laboratorio de documentos redujo, mediante formas oficiales estrechas
  y reglas de estructura, las sustituciones innecesarias de 68 a 0, las
  violaciones de conservación medidas explícitamente de 23 a 0 y las interrupciones de 3 a 0.
  La tasa de detección subió al mismo tiempo de 91,1 a 100,0 por ciento; TXT, HTML, PDF y
  DOCX alcanzan cada uno el 100 por ciento. Los encabezados de tabla
  generales como `Feld` solo se frenan en la secuencia documentada `Feld`/`Angabe`;
  un apellido igual permanece protegido. Los números de expediente judicial con letra final,
  campos con signo de igual, `Geburtsdatum des Kindes` y varios nombres individuales rotulados en la misma
  línea se reconocen por completo. Las tablas de Word y los campos de línea previa utilizan
  su encabezado de campo como contexto de reconocimiento temporal; las direcciones PDF rotuladas
  permanecen completamente protegidas incluso con un salto de línea provocado por la maquetación.

- Los campos alemanes de características personales, profesión y medicina funcionan ahora
  también con saltos de línea de Windows. Las indicaciones de sexo de una sola letra como
  `Geschlecht`/`w` quedan protegidas en la forma de línea previa. Los campos objetivos
  `Artikel-PZN` no activan, en cambio, ni un hallazgo de clave de medicamento ni de
  persona; los datos reales de PZN, ICD y ATC siguen reconociéndose.

- Los campos alemanes de formulario y número son más precisos: „DW.“ funciona ahora
  también antes de un salto de línea suave, los nombres expresamente rotulados se
  eliminan incluso en minúscula y los números de expediente puramente numéricos se
  asignan a su tipo correcto de número de identificación. A la inversa, un número
  de factura, comprobante o artículo casualmente válido según Luhn ya no se considera
  tarjeta de crédito. Las muestras de salida sintéticas HTML y PDF confirman la eliminación
  y la conservación en el documento final.
  Los números de identificación y nombres de usuario se reconocen además cuando su
  rótulo está en la línea de tabla o formulario inmediatamente anterior; los números de comprobante
  objetivos permanecen visibles también en esta forma.

- Las contraseñas se reconocen ahora también tras un encabezado de campo aislado en la
  línea anterior. Los caracteres especiales finales como `!` o `#`
  pertenecen entonces por completo al valor protegido. Los PIN de producto y artículo
  ya no se enmascaran, a la inversa, como PIN de tarjeta; los campos explícitos
  `PIN` y `Karten-PIN` permanecen protegidos.

- Los valores de formulario en minúscula se emiten ahora, en campos alemanes de dirección
  y `PLZ/Ort` inequívocos, como dirección o código postal con localidad en lugar de
  solo como localidad general. Asimismo, los valores de empresa en minúscula como
  „beispiel service“ permanecen completamente protegidos tras un campo de empresa, sin
  cortar la última palabra como supuesto siguiente encabezado de campo.

- Ayuda, preguntas frecuentes, texto de privacidad y sitio web explican ahora conjuntamente el
  comprobante de origen: ID neutral de Maskuro en el documento, asignación opcional a la
  cuenta real del sistema operativo solo en el registro de verificación local, cambio de usuario en
  Windows/macOS/Linux, así como el valor probatorio de SHA-256 y la firma.

- Los pliegos de condiciones técnicos basados en imágenes se limpian ahora con más
  cautela. Palabras técnicas inequívocas como „Abbruchhämmern“, „Deckungsrücklass“,
  „Positionsnummern“, „Einbauplatine“ o „Terminsituation“, así como formas OCR
  divididas en mitad de palabra, ya no se consideran persona ni lugar. Una oferta real
  de un ayuntamiento bajó así de 140 a 90 sustituciones inequívocas,
  sin generar nuevos hallazgos; nombres como Schneider, Lang, Bauer y Hahn
  permanecen expresamente protegidos.

- Se corrigieron más falsas alarmas de ofertas reales: „Digital signiert“
  ya no contiene una supuesta persona, un BIC se reconoce ahora también sin dos puntos
  tras su rótulo, `15000 Alternativ` ya no se considera
  código postal con localidad, y la cita de la UE „(VO (EG) 715/2007“ ya no genera una
  organización. Una oferta fotovoltaica bajó así de 26 a 16
  sustituciones; los nombres, lugares y datos de cuenta reales se conservaron.

- En los listados de empleados, la abreviatura de suplente „Stv.“ y
  un encabezado de área „FACILITY“ separado por sí solo ya no se sustituyen como
  nombre de persona. La comprobación real de 13 páginas bajó de 878 a 875
  sustituciones; los nombres, extensiones telefónicas y la denominación de la empresa permanecieron protegidos.

- Los archivos limpiados de PDF, OpenDocument y Office reciben un identificador neutral
  `MASKURO-…` en sus propiedades de documento. El informe de verificación y el
  registro de verificación firmado llevan el mismo identificador, así como valores SHA-256 de
  origen y resultado; el certificado de redacción toma el identificador del
  archivo final. Un nombre de usuario solo se añade cuando la
  administración activa expresamente el campo de usuario existente.

- La ventana principal y los ajustes están organizados con más calma: guardar, copiar,
  detalles, indicadores y la eliminación de un perfil de reconocimiento aparecen solo
  cuando la acción correspondiente es posible. Los códigos técnicos de idioma OCR y
  los ejemplos largos aparecen, cuando se necesitan, en el texto de ayuda en lugar de permanentemente en
  el área de trabajo. La página de reconocimiento se adapta mejor a ventanas más estrechas,
  sin explicaciones cortadas ni barras de desplazamiento horizontales; la advertencia sobre
  texto sin cifrar en la lista de sustitución permanece visible.

- El reconocimiento incluye más casos de contacto alemanes e internacionales: los números de teléfono ahora se comprueban para todas las regiones de país seleccionables, los roles contractuales húngaros y croatas registran también por completo los apellidos coincidentes con una profesión, y las listas numeradas de repuestos/materiales ya no provocan una falsa alarma de persona por „Mutter / Flach“. Los campos de persona con un valor objetivo claramente numérico ya no se toman como nombre; la zona legible por máquina del pasaporte (MRZ) también puede activarse y desactivarse conjuntamente a través del grupo „Identificadores“.

- Las empresas sin forma jurídica se distinguen mejor de las personas tras campos de empleador
  ambiguos: nombres como „Huber Handel“, „Müller Logistik“ o
  „Kowalski Handel“ se registran por completo como empresa, mientras que
  „Arbeitgeber: Bauer Anna“ sigue siendo un nombre de persona. La selección automática de
  país sigue teniendo en cuenta, en documentos franceses, todo el ámbito
  lingüístico francés, incluido Luxemburgo.

- Las firmas y el texto personal reconocidos dentro de una imagen se cubrían hasta ahora
  siempre con un rectángulo negro, incluso cuando para los tachados estaba configurado otro
  color u otro patrón como „Arcoíris". Estas zonas de imagen adoptan ahora también la
  representación de tachado elegida; la superficie opaca se sigue escribiendo directamente
  en los píxeles.
  espacio lingüístico francés completo, incluido Luxemburgo.

- Las firmas reconocidas y el texto personal dentro de una imagen se cubrían hasta ahora siempre con un rectángulo negro, incluso cuando para las censuras estaba configurado otro color o un patrón como „arcoíris“. Estas áreas de imagen adoptan ahora también la representación de censura elegida; la superficie opaca sigue escribiéndose directamente en los píxeles de la imagen.

- El reconocimiento en inglés se volvió a medir con once documentos reales traducidos manualmente y se mejoró de forma específica: el estado de inventario, los campos técnicos de oferta y de tienda web, así como los roles en directorios de empleados, permanecen visibles; „CV“ ya no se lee como forma jurídica en el conjunto de plantillas; los tipos de letra citados se conservan; y los nombres en encabezados verticales de currículum, listas de empleados de varias páginas, tras „Account manager“, así como nombres de empresa que empiezan con dígito, se reconocen por completo. Los números de registro mercantil austríacos funcionan ahora también tras un rótulo en inglés; la forma abreviada „Customer:“, los números de registro EAR y los números de empleador llevan su valor. Las cadenas de cotas, los tipos de cable, las referencias legales de la UE, las fechas de validez de ofertas, los lugares de cumplimiento, los fueros, los juzgados de registro, la abreviatura fiscal „NoVA“, los números técnicos en etiquetas de neumáticos, así como referencias normativas como „OVE R6-2“ y „AStV“, ya no generan falsas alarmas. Un IBAN rotulado válido termina limpiamente antes del campo de registro o del encabezado de la línea siguiente; las direcciones con complemento de zona industrial se reconocen por completo también en flujos de texto PDF con saltos de línea de Windows. Las introducciones de empresa en inglés y los nombres estructurados de cajas de ahorro se delimitan por completo. El país del documento de origen se conserva en las variantes de idioma para códigos postales e identificadores específicos de país.

- En las líneas de encabezado de destinatario y mensaje, el modelo de lenguaje podía combinar los dos primeros nombres de una lista separada por comas en un único hallazgo („Bcc: Huber, Mayer“). Ambos nombres se reconocen ahora por separado, se sustituyen y se registran en el informe — también tras „Sent:“, „Reply:“ y „Fwd:“.

- El área legible por máquina de un pasaporte o documento de identidad (MRZ) faltaba en el control de grupo „Qué se busca“. Ahora pertenece a „Identificadores“ y puede activarse y desactivarse junto con ese grupo.

- Quien elige la plantilla „arcoíris“ para los textos de sustitución obtiene ahora también las áreas censuradas en la misma apariencia; hasta ahora permanecían sorprendentemente en negro clásico. Las áreas de censura pueden después seguir cambiándose de forma independiente a otra plantilla.

- El panel de páginas del editor de corrección podía quedar vacío tras restaurar una disposición de ventana guardada, hasta que su ancho se modificaba a mano. Las miniaturas se reordenan ahora tras la construcción visible de la ventana y aparecen inmediatamente centradas en el panel.

- Las marcas de verificación de colores alrededor de los textos de sustitución en PDF apenas eran visibles según el color de categoría y de semáforo. Un contorno claro inferior separa ahora de forma fiable el marco de verificación del marcador de posición coloreado y del fondo de la página.

- Quien censura en el editor de corrección una línea cuyo documento está compuesto con interlineado estrecho (típico en ofertas y pliegos de condiciones) obtenía una barra que invadía las astas ascendentes de la línea inferior — esta quedaba después solo medio legible. La barra termina ahora en el tipo realmente dibujado de la línea vecina; la línea censurada misma permanece, con sus astas descendentes incluidas, completamente cubierta.

- El documento de práctica („Ayuda → Abrir documento de práctica“, también en el recorrido guiado) muestra ahora todos los tipos de reconocimiento: a la carta ficticia se añaden una fotografía con un rostro reconocible, una firma manuscrita, profesión y departamento, diagnóstico y medicamento — junto al nombre de empresa, el importe y la fecha, que ya estaban. Lo que la configuración predeterminada deja intencionadamente sin tocar lo explica la propia hoja, junto con el interruptor que lo elimina; el rostro de la fotografía viene pixelado de fábrica.

- Los importes monetarios en la notación alemana habitual con el símbolo detrás del número („1.240,00 €“) nunca fueron encontrados por el interruptor „Eliminar también importes monetarios“ — „1.240,00 EUR“ y „€ 1.240,00“ sí siempre. Ahora se reconocen las tres notaciones.

- La búsqueda de firmas funciona ahora también en archivos de imagen aislados: quien limpia un escaneo como JPG o PNG obtiene las firmas manuscritas en él censuradas — el mismo reconocimiento, el mismo aviso en el informe que en PDF. Las imágenes incrustadas en archivos de Office siguen sin buscarse, porque el reconocimiento allí funciona de forma medida poco fiable; la casilla se llama por eso ahora „PDF y archivos de imagen: censurar firmas manuscritas“.

- Una barra de censura podía, con interlineado estrecho, invadir visiblemente las astas ascendentes de la línea inferior y hacerla medio ilegible — la altura de la barra provenía de las métricas de la fuente, no de lo que realmente está en el papel. La barra termina ahora en la tinta realmente dibujada de la línea vecina, tanto en el editor de corrección como en la limpieza automática. La propia línea, incluidas las astas descendentes, permanece siempre totalmente cubierta; si las líneas realmente se superponen, la barra prefiere permanecer sobre la línea vecina antes que dejar algo al descubierto.

- En un directorio de empleados con rol debajo del nombre, una denominación femenina de dirección („Anna Berger“ con „Montageleiterin“ debajo) se incluyó en la sustitución del nombre — la forma masculina al lado quedó correctamente intacta. Las formas femeninas „…leiterin“ (de montaje, equipo, proyecto, obra, departamento, planta, grupo, oficina) se tratan ahora, como sus contrapartes masculinas, como denominación de función; dirección de sucursal, personal y ventas están ahora incluidas en ambas formas.

- El reconocimiento de profesiones activable no encontraba roles femeninos de dirección como „Projektleiterin“, „Teamleiterin“ o „Abteilungsleiterin“, pero sí sus formas masculinas. Ambas formas cuentan ahora por igual.

- En la ventana de vista previa, en Mac, la indicación de múltiples ocurrencias quedaba pegada directamente al término („Anna Musterfrau2ק en lugar de „Anna Musterfrau 2ק). El espacio vuelve a estar presente.

- La lupa de comparación tiene un nuevo botón junto al regulador de zoom: con una pulsación la coloca a ancho completo sobre el resultado — a media altura cada uno, y el original en la misma escala que el documento (el zoom de la lupa salta entonces al 100 %). Una segunda pulsación la vuelve a anclar pequeña en la columna izquierda y restaura el zoom de lupa anterior. El círculo de al lado ahora solo restablece el zoom — su texto de ayuda afirmaba hasta ahora, erróneamente, que también volvía a anclar la ventana.

- En la barra de herramientas del editor de corrección, la herramienta seleccionada vuelve a mostrarse como seleccionada: el botón de la herramienta activa lleva una superficie rellena con borde azul — igual que cualquier otro botón de alternancia activado de la barra (por ejemplo la lupa de comparación o el modo de aprendizaje). La marca se había perdido con el propio diseño de botones del 29 de agosto.

- Los números de posición de un pliego de condiciones („2.3.3.3, 2.3.3.4, 2.3.3.5“ uno debajo de otro) se tomaban por direcciones IP y se eliminaban del resultado; los números de tres niveles con un último componente parecido a un año („2.3.19, 2.3.20“) caían como fechas de calendario. Una secuencia numérica ascendente al inicio de línea se considera ahora lo que es — una lista de posiciones; las direcciones reales (tablas de red con entorno de palabras técnico, números superiores a 99) y las fechas reales se siguen reconociendo.

- Apellidos como „Müller“, „Fischer“, „Bauer“, „Koch“, „Wagner“, „Schneider“, „Weber“, „Jäger“, „Schmied“, „Becker“, „Schuster“, „Schäfer“ o „Meister“ permanecían en texto sin cifrar en listas de la forma „Apellido, Nombre“ (p. ej. „Participantes: Müller, Peter; Nowak, Anna“), porque son al mismo tiempo denominaciones de profesión habituales. Ahora se reconocen de forma fiable.

- Al censurar un PDF, la barra podía arrastrar consigo toda la celda en celdas de tabla estrechas: del hallazgo „D-LINK“ en un pliego de condiciones se eliminó la descripción completa del producto al lado, aunque la vista previa solo había mencionado el hallazgo. La barra sigue cubriendo líneas enteras de bloque de dirección y rótulos de campo, pero como máximo se traga tanto contenido no implicado como lo que cubre digno de protección — la descripción junto al hallazgo permanece ahora intacta.

- Tras „Restablecer vista“ en el editor de corrección, el panel de páginas quedaba vacío — las miniaturas de las páginas solo volvían a verse tras cerrar y reabrir la ventana. Ahora aparecen también directamente tras el restablecimiento, centradas como antes.

- El editor de corrección tiene una cuarta herramienta: **Eliminar** retira el texto bajo el marco sin sustituto — sin barra (censurar) y sin marcador de posición (sustituir); el hueco permanece visiblemente vacío. Funciona con precisión de palabra; si hay una imagen debajo, su fondo se despeja en blanco, y „Recuperar original“ también deshace una eliminación sin sustituto. Tiene su propio icono de barra y distintivo de mira (cruz), su propia tecla mnemotécnica en los 18 idiomas (en alemán F de entFernen).

- En la barra de búsqueda de PDF, „Carpeta …“ está ahora a la derecha de las opciones de búsqueda. Desde que, además de censurar, también existe la sustitución de hallazgos, cinco botones ya no cabían uno junto a otro con el ancho de ventana habitual — el primero se comprimía y su texto se cortaba.

- „Restablecer todos los ajustes“ restablece ahora también la casilla „Sustituir rojo/verde por otros colores“ y la marca, como a cualquier otra, con „modificado“ cuando difiere del valor de fábrica.

- Los textos de sustitución en PDF actúan ahora de forma más uniforme: donde el marcador de posición completo tendría que resultar claramente más pequeño que su línea (por ejemplo „[BEG16]“ comprimido en una palabra corta como „Das“), aparece en su lugar una forma corta al tamaño de línea („[B16]“) — bien legible en lugar de diminuta, y el número para recuperar lleva ambas notaciones. Un marcador de posición se vuelve diminuto solo cuando ni siquiera la forma más corta encuentra sitio — eso sigue siendo mejor que una barra sin información alguna.

- Un texto de sustitución multicolor (degradado o arcoíris) en un PDF solo permanecía intacto hasta la siguiente intervención: cada sustitución o censura adicional en la misma página podía comprimir marcadores de posición ya colocados hasta convertirlos en una pila de letras ilegible y aplastada — quien sustituía palabra por palabra en el editor veía, en lugar de „[BEG17]“, solo caracteres impresos unos sobre otros. Los marcadores de posición, una vez colocados, permanecen ahora tal como se colocaron.

- El interruptor para excepciones permanentes en la vista previa se llama ahora „No eliminar nunca“ — como la lista en la que inscribe; hasta ahora decía „nunca más“. La línea de hallazgo de al lado está más ordenada: el símbolo de información „ⓘ“ es más grande y más fácil de acertar, y la casilla, la marca de sustitución y el botón tienen una altura común. La frase alrededor de un hallazgo utiliza ahora realmente el ancho anunciado — la indicación de ancho anterior había descartado silenciosamente la visualización, y el fragmento se envolvía como una franja más estrecha.

- En el editor, el puntero del ratón indica ahora qué herramienta está activa: una mira para apuntar, junto a un pequeño signo — barra para censurar, flechas de intercambio para sustituir, arco de deshacer para restaurar, trama de píxeles para pixelar. Los iconos de mano anteriores desaparecieron; una mano significa en cualquier otro lugar „agarrar y desplazar“. Ahora tiene una tarea adecuada: sobre una palabra o barra resaltada en rojo, el puntero se convierte en una mano señaladora — allí basta un clic.

- „Reconocimiento máximo (IA)“ ya no ofrece un modelo de lenguaje local descargable — este nivel funciona ahora exclusivamente mediante una IA propia configurada bajo „Conectar IA propia“. Quien ya había conectado un servidor propio no nota ninguna diferencia.

- El recorrido guiado de la vista previa explica ahora también el símbolo de información „ⓘ“, que muestra la frase alrededor de un hallazgo. Y esa misma frase es más legible: un tamaño de letra mayor, más interlineado, ancho fijo en lugar de un salto de línea estrecho y apretado.
- También „Verificar archivo“, „Reglas de reconocimiento y términos propios“, „Limpiar texto“ y „Limpiar imagen“ tienen ahora su propio recorrido guiado — mediante un nuevo botón „Recorrido por la ventana“, ya que estas cuatro ventanas no tienen barra de menú propia.
- Los nombres bajo nueve rótulos de rol contractual ucranianos permanecían reconocidos de forma incompleta con un apellido homógrafo, cuando el rótulo estaba solo en su propia línea: „Покупець“/„Продавець“ (comprador/vendedor), „Поручитель“/„Боржник“ (fiador/deudor principal), „Свідок“ (testigo), „Орендодавець“/„Орендар“ (arrendador/arrendatario) y „Спадкодавець“/„Спадкоємець“ (causante/heredero). Los nombres se reconocen ahora por completo.

- El comentario de un rango con nombre en un libro de Excel (Administrador de nombres, campo „Comentario“) mantenía un nombre allí registrado sin cambios. Ahora se limpia igual que el resto del contenido del libro.

- Los nombres bajo siete rótulos de rol contractual húngaros permanecían totalmente indetectados con un apellido homógrafo: „Bérbeadó“/„Bérlő“ (arrendador/arrendatario), „Vevő“/„Eladó“ (comprador/vendedor), „Kezes“/„Főadós“ (fiador/deudor principal) y „Tanú“ (testigo). Los nombres se reconocen ahora por completo.

- Los nombres bajo el rótulo checo de comprador „Kupující“ permanecían totalmente indetectados con un apellido homógrafo. El nombre se reconoce ahora por completo.

- Los nombres bajo el rótulo ruso de tutor „Опекун“ permanecían totalmente indetectados con un apellido homógrafo. El nombre se reconoce ahora por completo.

- Los nombres bajo otros seis rótulos croatas permanecían indetectados: „Jamac“ (fiador), „Glavni dužnik“/„Dužnik“ (deudor principal/deudor), „Ostavitelj“ (causante), „Nasljednik“ (heredero/heredera) y „Vjerovnik“ (acreedor). Los nombres se reconocen ahora por completo.

- Una página HTML guardada con una subpágina incrustada en el atributo `src` de un `<embed>` (en lugar de `data` en `<object>`) mantenía sin cambios los datos personales que contenía. Ahora se limpia igual que con `<object>`.

- Los nombres bajo cinco rótulos de rol contractual daneses permanecían reconocidos de forma incompleta con un apellido homógrafo, cuando el rótulo estaba con dos puntos delante del nombre: „Arvelader“/„Arving“ (causante/heredero), „Befuldmægtiget“/„Fuldmagtsgiver“ (apoderado/poderdante) y „Værge“ (tutor). Los nombres se reconocen ahora por completo; los rótulos noruegos correspondientes se añadieron también como refuerzo.

- Los marcadores de posición en archivos de Word y PowerPoint llevan ahora el mismo color que en la apariencia elegida (monocolor, degradado, arcoíris o por categoría) — hasta ahora permanecían allí en el color de texto habitual, aunque los resultados PDF ya eran coloreados desde hacía tiempo.

- „Copiar como texto“ y „Copiar como Markdown“ colocan el texto sin cifrar del resultado directamente en el portapapeles — para pegar en un chat, correo u otro programa, sin tener que abrir antes el archivo.

- Los nombres bajo otros cinco rótulos eslovenos permanecían indetectados: „Toženec“ (demandado), „Tožnik“ (demandante), „Zastavitelj“ (pignorante), „Zastavni upnik“ (acreedor pignoraticio) y „Darovalec“ (donante). Los nombres se reconocen ahora por completo.

- El nombre del autor de un cambio de celda de tabla con seguimiento (celda insertada, eliminada o combinada en Word) permanecía en el archivo, incluso cuando el mismo nombre como autor de comentario ya había sido eliminado hace tiempo. Ahora también se elimina.

- Los nombres bajo otros nueve rótulos eslovenos permanecían indetectados: „Najemodajalec“/„Najemnik“ (arrendador/arrendatario), „Zapustnik“/„Dedič“ (causante/heredero), „Upnik“/„Dolžnik“ (acreedor/deudor), „Glavni dolžnik“ (deudor principal) y „Skrbnik“ (tutor/curador). Los nombres se reconocen ahora por completo.

- Los nombres bajo cinco rótulos eslovenos permanecían indetectados: „Izvedenec“ (perito), „Kupec“ (comprador), „Prodajalec“ (vendedor), „Naročnik“ (cliente) y „Izvajalec“ (contratista). Los nombres se reconocen ahora por completo.

- Los nombres bajo otros cinco rótulos lituanos permanecían indetectados: „Užsakovas“ (cliente), „Vykdytojas“ (contratista), „Vežėjas“ (transportista), „Siuntėjas“ (remitente) y „Arbitras“ (árbitro). Los nombres se reconocen ahora por completo.

- Los nombres bajo otros seis rótulos lituanos permanecían indetectados: „Įgaliotinis“ (apoderado), „Įgaliotojas“ (poderdante), „Naudos gavėjas“ (beneficiario, seguro), „Trečiasis asmuo“ (tercero interviniente en proceso civil), „Ankstesnis nuomininkas“ (arrendatario anterior) y „Naujasis nuomininkas“ (nuevo arrendatario). Los nombres se reconocen ahora por completo.

- Un marcador en documentos ODT (`text:bookmark`) lleva su nombre libremente asignado, a menudo denominado según el lugar al que apunta (p. ej. „Herr_Mueller_Unterschrift“) — invisible para el lector, pero textualmente en el archivo. El nombre se limpia ahora también.

- Los nombres bajo otros ocho rótulos lituanos permanecían indetectados: „Pareiškėjas“ (solicitante), „Suinteresuotas asmuo“ (parte contraria en procedimiento no contencioso), „Ekspertas“ (perito/experto), „Bankroto administratorius“ (administrador concursal), „Valdybos narys“ (miembro del consejo de vigilancia), „Direktorius“ (director general), „Palikėjas“ (causante) e „Įpėdinis“ (heredero). Los nombres se reconocen ahora por completo.

- Los nombres bajo otros siete rótulos lituanos permanecían indetectados: „Liudytojas“ (testigo), „Vertėjas“ (intérprete/traductor), „Notaras“ (notario), „Dovanotojas“ (donante), „Apdovanotasis“ (donatario), „Pirkėjas“ (comprador) y „Pardavėjas“ (vendedor). Los nombres se reconocen ahora por completo.

- Los nombres bajo otros seis rótulos lituanos permanecían indetectados: „Globėjas“ (tutor/curador), „Palikimo administratorius“ (administrador de la herencia), „Laiduotojas“ (fiador), „Pagrindinis skolininkas“ (deudor principal), „Nuomotojas“ (arrendador) y „Nuomininkas“ (arrendatario). Los nombres se reconocen ahora por completo.

- Un nombre bajo el rótulo lituano „Ieškovas“/„Atsakovas“ (demandante/demandado como parte procesal) permanecía indetectado, independientemente de si el apellido era al mismo tiempo una palabra común (p. ej. „Vilkas“ = lobo) o no. El nombre se reconoce ahora por completo.

- Una entrada de índice de personas en documentos ODT (marca de texto para el índice de términos) llevaba el nombre una segunda vez en su propia clave de ordenación — invisible en el texto continuo, pero literal en el índice generado posteriormente. La clave se limpia ahora también.

- El nombre de diapositiva y el nombre de sección de una presentación de PowerPoint (visibles en el panel de selección o en la clasificación de diapositivas) permanecían sin limpiar, porque ambos cuelgan como atributo de un elemento que no es texto de diapositiva. Ambos se reconocen ahora.

- Un nombre compuesto lituano con guion como „Petraitis-Kazlauskas“ perdía su segunda mitad en cuanto había texto continuo delante (solo al inicio del texto permanecía completo): el apellido se reconoce ahora también por completo en ese caso.

- Un nombre bajo el rótulo „Cesionar“ (croata, cesionario en la cesión de crédito) generaba una falsa alarma, porque el propio rótulo de campo se leía erróneamente como persona. Un nombre bajo el rótulo ruso „Цессионарий“ (también cesionario) permanecía, en cambio, totalmente indetectado. Ambos casos están ahora corregidos.

- Un nombre bajo el rótulo „Zedent“/„Zessionar“ (alemán, cesión de crédito) permanecía totalmente indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Bauer“). El nombre se reconoce ahora por completo.

- Un nombre bajo el rótulo „Darczyńca“/„Obdarowany“ (polaco, donante/donatario en el contrato de donación) permanecía indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Wilk“ = lobo). Asimismo, el rótulo rumano „Donatar“ (donatario) quedaba atrapado, con un apellido común, incluso como supuesto componente del nombre. Ambos casos están ahora corregidos.

- Un nombre bajo el rótulo „Wierzyciel“/„Dłużnik“ (polaco, acreedor ejecutante/deudor ejecutado, o acreedor/deudor en general) permanecía indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Wilk“ = lobo). El nombre se reconoce ahora por completo.

- Un nombre bajo el rótulo „Poręczyciel“/„Dłużnik główny“ (polaco, fiador/deudor principal en contratos de fianza) permanecía indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Wilk“ = lobo). El nombre se reconoce ahora por completo.

- Un nombre bajo el rótulo „Ubezpieczony“/„Ubezpieczający“ (polaco, asegurado/tomador del seguro en pólizas de seguro) permanecía parcial o totalmente indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Wilk“ = lobo). Asimismo, un nombre bajo „Osiguranik“/„Osiguravatelj“ (croata, los mismos roles), donde desaparecía por completo junto con el nombre de pila (p. ej. „Golub“ = paloma). Ambos nombres se reconocen ahora por completo.

- Un nombre bajo el rótulo „Pełnomocnik“/„Mocodawca“ (polaco, apoderado/poderdante en escrituras de poder) permanecía indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Wilk“ = lobo). Asimismo, un nombre bajo „Opunomoćenik“/„Opunomoćitelj“ (croata, los mismos roles), donde incluso desaparecía por completo junto con el nombre de pila. Ambos nombres se reconocen ahora por completo.

- Un nombre bajo el rótulo „Pozwany“ (polaco, demandado como parte procesal) permanecía indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Wilk“ = lobo). El nombre se reconoce ahora por completo.

- Un nombre bajo el rótulo „Najmoprimac“/„Najmodavac“ (croata, arrendatario/arrendador en contratos de alquiler) permanecía indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Kovač“ = herrero). El nombre se reconoce ahora por completo.

- Un nombre bajo el rótulo „Pracodawca“/„Pracownik“ (polaco, empleador/empleado como parte contractual en contratos de trabajo) permanecía parcialmente indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Krawiec“ = sastre). El nombre se reconoce ahora por completo.

- Hungría solo tenía en el catálogo de países los identificadores personales y el NIF-IVA: el número de registro mercantil (Cégjegyzékszám) se reconoce ahora, siempre que la palabra de campo „Cégjegyzékszám“ o la abreviatura „Cg.“ esté inmediatamente delante — el número mismo no lleva dígito de control.

- Estonia solo tenía en el catálogo de países el Isikukood: el Käibemaksukohustuslase number (NIF-IVA en cada factura estonia) se reconoce ahora con dígito de control.

- Letonia solo tenía en el catálogo de países el Personas kods: el PVN reģistrācijas numurs de personas jurídicas (identificador de empresa en cada factura letona) se reconoce ahora con dígito de control.

- Un correo electrónico con contenido cifrado (envoltorio S/MIME o PGP/MIME, `multipart/encrypted`) se mostraba, sin advertencia alguna, como aparentemente completamente verificado, aunque su contenido real estaba cifrado y por tanto no verificado. Estos correos ahora advierten de ello, igual que un adjunto no verificado.

- Malta faltaba en el catálogo de países: el NIF-IVA maltés (VAT number) se reconoce ahora.

- Luxemburgo faltaba en el catálogo de países: el NIF-IVA luxemburgués (n° TVA) se reconoce ahora.

- Un „Изчакайте“ búlgaro („¡Espere!“) situado al inicio de frase se notificaba como indicación de lugar — el mismo límite del modelo que antes con formas de interpelación húngaras, polacas, checas y de otros idiomas sin modelo de lenguaje propio. La falsa alarma ahora ya no se produce.

- Un nombre bajo el rótulo „Zleceniodawca“, „Zleceniobiorca“ (polaco), „Prestator“ (rumano), „Naručitelj“ o „Izvođač“ (croata) permanecía parcial o totalmente indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Wilk“, „Vuk“ = lobo, „Vulpe“ = zorro, „Sokol“ = halcón). El nombre se reconoce ahora por completo.

- Un nombre bajo el rótulo „Nadawca“ (polaco), „Afsender“ (danés) o „Pošiljatelj“ (esloveno) permanecía parcial o totalmente indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Sowa“ = búho, „Bager“ = panadero, „Volk“ = lobo). El nombre se reconoce ahora por completo.

- Un nombre bajo el rótulo „Gavėjas“ (lituano) o „Prejemnik“ (esloveno) permanecía parcial o totalmente indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Vilkas“ = lobo). Igual que ya ocurría con „Primatelj“ (croata) y „Modtager“ (danés), el nombre se reconoce ahora por completo.

- Un encabezado de circular como „To All Staff“ o „To All Employees“ se reconocía erróneamente como nombre de persona y se eliminaba. Esto ya no ocurre.

- Un nombre bajo el rótulo „Primatelj“ (croata) o „Modtager“ (danés) permanecía parcialmente indetectado cuando el apellido era al mismo tiempo una palabra común (p. ej. „Golub“ = paloma, „Bager“ = panadero). Igual que ya ocurría con „Odbiorca“ (polaco) y „Destinatar“ (rumano), el nombre se reconoce ahora por completo.

- Un nombre completo en la línea de firma de un documento danés, noruego o griego permanecía parcialmente indetectado cuando el rótulo „Underskrift“ o „Υπογραφή“ estaba solo encima del nombre — en el caso griego, el apellido incluso se reconocía como indicación de lugar en lugar de como nombre. Igual que ya ocurría con „Подпись“ (ruso), el nombre se reconoce ahora por completo.

- El texto en una foto de teléfono depositada de lado (la habitual toma vertical, que solo se muestra en posición correcta mediante una marca de rotación de imagen) podía pasar desapercibido para el reconocimiento de texto, porque hasta ahora leía los píxeles brutos, en posición horizontal. Estas fotos se giran ahora a la posición correcta antes de la lectura — como ya ocurría antes con el reconocimiento facial.

- Un nombre completo en la línea de firma de un documento ruso, ucraniano o lituano permanecía parcialmente indetectado cuando el rótulo „Подпись“, „Підпис“ o „Parašas“ estaba solo encima del nombre — el nombre de pila o el patronímico se perdían. Igual que ya ocurría con „Potpis“ (croata), el nombre se reconoce ahora por completo.

- Un rostro en una foto de teléfono depositada de lado (la habitual toma vertical, que solo se muestra en posición correcta mediante una marca de rotación de imagen) podía pasar desapercibido para el reconocimiento facial, porque hasta ahora comprobaba los píxeles brutos, en posición horizontal. Estas fotos se giran ahora a la posición correcta antes de la búsqueda.

- Un nombre completo en la línea de firma de un documento croata permanecía parcialmente indetectado cuando el rótulo „Potpis“ estaba solo encima del nombre o con dos puntos delante — el nombre de pila se perdía, ya fuera en línea propia o en „Potpis: Nombre Segundo nombre Apellido“. Igual que ya ocurría con „Unterschrift“ y „Signature“, el nombre se reconoce ahora por completo.

- Un nombre de casada tras las abreviaturas de estado civil „verh.“ (casada/casado) y „verw.“ (viuda/viudo) permanecía hasta ahora totalmente indetectado, ya fuera entre paréntesis, tras coma o pegado sin espacio („Anna Meier (verh. Weber)“, „Klaus Bauer (verw.Fischer)“) — igual que ya ocurría con „geb.“, ahora se reconoce de forma fiable.

- Un nombre tras la firma de apoderado „ppa.“ (p. ej. en la línea de firma de un correo electrónico o carta comercial) permanecía hasta ahora parcial o totalmente indetectado con un apellido homónimo de profesión como „Bauer“ o „Koch“ — igual que ya ocurría con „gez.“, ahora se reconoce de forma fiable.

- El número del documento de identidad polaco (dowód osobisty) solo se reconocía sin espacio entre serie y número („ABS123456“). Pero el documento no imprime la indicación exactamente así — oficialmente hay un espacio entre ambos („ABS 123456“), y en esta notación el número permanecía hasta ahora indetectado.

- Un PNG animado (APNG, p. ej. una grabación de pantalla corta guardada como PNG en lugar de GIF) se verificaba y limpiaba hasta ahora solo con su primera imagen, sin que esto se notificara — como antes con el WebP animado, Maskuro notifica ahora que cada imagen adicional permanece sin verificar en el resultado.

- Una imagen WebP animada (p. ej. de una herramienta de captura de pantalla o una aplicación de chat con varias imágenes en un archivo) se verificaba y limpiaba hasta ahora solo con su primera imagen, sin que esto se notificara — como antes con un TIFF de varias páginas, Maskuro notifica ahora que cada imagen adicional permanece sin verificar en el resultado.

- Un nombre de pila doble esloveno con guion („Ana-Marija Novak“) perdía su primera mitad en cuanto le precedía texto continuo — el mismo error que antes en polaco. „Ana-“ permanecía sin sustituir en texto sin cifrar, mientras el resto del nombre ya se había sustituido.

- Un nombre de pila doble polaco con guion („Anna-Maria Kowalska“) perdía su primera mitad en cuanto le precedía texto continuo o una preposición como „z“/„od“ — el resto del nombre se sustituía, „Anna-“ permanecía sin sustituir en texto sin cifrar.

- Fórmulas de cortesía kazajas „Хабарласыңыз“/„Байланысыңыз“ (contáctenos) y formas verbales serbias „Помоћи“, „Чекамо“ y „Пишите“ sin modelo de reconocimiento de idioma propio se reconocían erróneamente como nombre de persona o lugar en frases telefónicas.

- La palabra de cortesía azerbaiyana „Xahiş“ (por favor/solicitud) sin modelo de reconocimiento de idioma propio se reconocía erróneamente como nombre de persona en frases telefónicas.

- Palabras indonesias y malayas de cortesía/interpelación sin modelo de reconocimiento de idioma propio como „Silakan“, „Mohon“ (indonesio), „Sila“ y „Tolong“ (malayo) se reconocían erróneamente como nombre de persona o lugar en frases telefónicas.

- La forma de interpelación uzbeka „Kutamiz“ (esperamos) sin modelo de reconocimiento de idioma propio se reconocía erróneamente como lugar en frases telefónicas.

- Formas de interpelación turcas sin modelo de reconocimiento de idioma propio como „Arayınız“ (llame) y „Bekliyoruz“ (esperamos) se reconocían erróneamente como nombre de persona en frases telefónicas.

- Formas de interpelación en otros idiomas sin modelo de reconocimiento de idioma propio (checo, eslovaco, griego) como „Zavolejte“ (llame), „Prosíme“ (le rogamos) y „Περιμένουμε“ (esperamos) se reconocían erróneamente como nombre de persona o lugar en frases telefónicas.

- Formas de interpelación húngaras y polacas como „Hívjon“ (llame), „Kérjük“ (le rogamos), „Várjuk“ (esperamos), „Zadzwoń“ (llame) y „Czekamy“ (esperamos) se reconocían erróneamente como nombre de persona o lugar en frases telefónicas.

- En una lista de nombres numerada sin forma de tabla (p. ej. „1. Robert Brown“, debajo „2. Mary Johnson“), un nombre con determinados apellidos ingleses (entre otros „Brown“, „White“, „Green“, „Black“, „Young“) se pasaba por alto por completo — el modelo de lenguaje había añadido el número de la línea siguiente al nombre, con lo que el hallazgo ya nunca coincidía exactamente.

- En el modelo de lenguaje polaco, la inicial del nombre de pila antepuesta a un apellido (p. ej. „J. Kowalski“, „A. Nowak“) permanecía sin reconocer y sin limpiar en el texto — solo se sustituía el apellido. Otros idiomas comprobados (entre otros alemán, inglés, rumano, croata, húngaro, ruso) ya incluían esa misma inicial desde antes.

- Un nombre de persona tras un título en minúscula como „dr.“, „ing.“
  o „dipl. ing.“ no se reconocía en absoluto en húngaro, rumano y croata —
  no solo se perdía el título, sino el nombre completo
  (p. ej. „dr. Kovács Béla“, „ing. Andrei Popescu“, „dipl. ing. Marko
  Horvat“).
- En actas de sesión eslovenas, una denominación de rol pura antes de los dos puntos (p. ej. „Tajnik:“, „Podpredsednik:“, „Poročevalec:“, „Predsedujoči:“) se reconocía erróneamente como nombre de persona en cuanto en otro lugar del acta ya figuraba un nombre real de interviniente.
- En actas de sesión rusas, una denominación de rol pura antes de los dos puntos (p. ej. „Секретарь:“, „Докладчик:“, „Докладчица:“) se reconocía erróneamente como nombre de persona en cuanto en otro lugar del acta ya figuraba un nombre real de interviniente.
- En actas de sesión rumanas, una denominación de rol pura con artículo determinado antes de los dos puntos (p. ej. „Secretarul:“, „Președintele:“, „Vicepreședintele:“, „Moderatorul:“, „Consilierul:“) se reconocía erróneamente como nombre de persona — „Președintele“ ya por sí solo, los demás además en cuanto en otro lugar del acta ya figuraba un nombre real de interviniente.
- En actas de sesión croatas, una denominación de rol pura antes de los dos puntos (p. ej. „Izvjestiteljica:“, „Zapisničar:“/„Zapisnicar:“, „Predsjedavajući:“) se reconocía erróneamente como nombre de persona.
- Una dirección de apartado de correos polaca „Skrytka pocztowa“ tras un
  rótulo de remitente o destinatario (p. ej. „Odbiorca: Skrytka
  pocztowa 45“) se reconocía erróneamente como nombre de persona.
- Una dirección de apartado de correos croata „Poštanski pretinac“ tras el
  rótulo de dirección „Adresa:“ (p. ej. „Adresa: Poštanski pretinac
  45“, también con „br.“ añadido para el número) se reconocía erróneamente
  como nombre de persona.
- Un lugar sin más rótulo en texto continuo noruego (p. ej. „Anna Hansen bor i Oslo“) no se reconocía — el modelo de lenguaje propio nombra allí los lugares mayormente con una etiqueta propia, hasta ahora no asignada, en lugar del habitual „LOC“.
- Una fecha en el orden ISO año-mes-día con guion o
  punto (p. ej. „2024-12-31“) no se reconocía en absoluto como
  fecha en algunos idiomas — más llamativamente en lituano, donde los escritos
  oficiales indican las fechas mayoritariamente en este orden.
- Un NIF-IVA húngaro (közösségi adószám) en la forma de 11 dígitos
  igualmente válida oficialmente, sin separadores (p. ej.
  „12345678123“ en lugar de „12345678-1-23“) no se reconocía.
- Un número fiscal polaco NIP con los separadores en la agrupación 3-2-2-3
  (p. ej. „856-73-46-215“, como es habitual en facturas de empresas y
  autónomos) no se reconocía — solo acertaba la agrupación
  3-3-2-2 para personas físicas.
- Un nombre de empresa bajo el rótulo de campo eslovaco
  „Zamestnávateľ:“ o „Názov zamestnávateľa:“ (empleador/empresa) no se
  reconocía.
- Un nombre de empresa bajo el rótulo de campo rumano
  „Angajator:“ o „Denumire angajator:“ (empleador/empresa) no se
  reconocía.
- Un nombre de empresa bajo el rótulo de campo húngaro
  „Cég:“ o „Munkáltató:“ (empresa/empleador) no se
  reconocía.
- Un nombre de empresa bajo el rótulo de campo polaco
  „Pracodawca:“ o „Nazwa firmy:“ (empleador/empresa) no se
  reconocía.
- Un nombre de empresa bajo el rótulo de campo esloveno
  „Podjetje:“ o „Delodajalec:“ (empresa/empleador) no se
  reconocía.
- Un nombre de empresa bajo el rótulo de campo croata
  „Tvrtka:“ o „Poslodavac:“ (empresa/empleador) no se
  reconocía.
- Un importe monetario escrito con la moneda en minúscula (p. ej.
  „500 euro“) no se reconocía, solo acertaba con mayúscula inicial („Euro“).
- El apellido tras „Schwager“/„Schwägerin“ (cuñado/cuñada; p. ej. „Der Schwager Bauer
  erhält die Erbschaft.“) no se reconocía.
- En una dirección turca sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „34000 İstanbul İstiklal
  Caddesi No: 45“) el número de la calle permanecía sin limpiar.
- En una dirección eslovaca sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „831 01 Bratislava Hlavná
  15“) el número de la calle permanecía sin limpiar.
- Un país de nacimiento sin más rótulo en un campo de formulario
  croata (p. ej. „Zemlja rođenja: Njemačka“) no se reconocía.
- Un país de nacimiento sin más rótulo en un campo de formulario
  lituano (p. ej. „Gimimo valstybė: Vokietija“) no se reconocía.
- Un país de nacimiento o de residencia sin más rótulo en un campo de formulario
  polaco (p. ej. „Kraj: Niemcy“) no se reconocía.
- Una nacionalidad o lugar de residencia sin más rótulo en
  un campo de formulario esloveno (p. ej. „Državljanstvo: Nemčija“) no
  se reconocía.
- Un país de residencia sin más rótulo en un campo de formulario
  noruego (p. ej. „Bosted: Tyskland“) no se reconocía.
- Nueva página de ajustes „Notificaciones“ (antes un apartado en „Programa“): los tres avisos de la barra de tareas (vista previa lista, procesamiento terminado, actualización descargada) tienen ahora un lugar propio.
- Nuevo: el resultado puede depositarse adicionalmente como archivo de texto puro (.txt) o con la extensión .md al lado — para seguir procesándolo en una IA u otro programa.
- En un dato de contacto croata con el rótulo „Osoba za kontakt“/„Kontakt osoba“ (p. ej. „Osoba za kontakt: Golub Marko“) el nombre permanecía totalmente sin reconocer cuando el apellido era al mismo tiempo un sustantivo común (Golub = „paloma“).

- En un dato de contacto rumano con el rótulo „Persoana de contact“/„Persoană de contact“ (p. ej. „Persoana de contact: Lup Ion“) el nombre permanecía totalmente sin reconocer cuando el apellido era al mismo tiempo un sustantivo común (Lup = „lobo“) y el nombre de pila muy corto y genérico.

- En un dato de contacto polaco con el rótulo „Osoba
  kontaktowa“/„Osoba do kontaktu“ (p. ej. „Osoba kontaktowa: Wilk
  Adam“) el apellido no se reconocía cuando era al mismo tiempo un
  sustantivo común (Wilk = „lobo“, Zielony = „verde“).

- En una dirección rumana sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „010061 București Strada
  Victoriei 30“) el número de la calle permanecía sin limpiar.
- En una dirección serbia sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „11000 Beograd Bulevar
  Kralja Aleksandra 73“) el número de la calle permanecía sin limpiar.
- En una dirección griega sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „104 32 Αθήνα Ερμού 15“)
  el número de la calle permanecía sin limpiar.
- En una dirección eslovena sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „1000 Ljubljana Slovenska
  cesta 58“) el código postal permanecía sin limpiar.
- En una dirección lituana sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „LT-01100 Vilnius
  Gedimino pr. 9“) el código postal permanecía totalmente sin limpiar.
- En una dirección húngara sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „1052 Budapest Kossuth
  Lajos utca 12“) el código postal permanecía sin limpiar.
- Un apellido tras „Erben“ (herederos; p. ej. „Die Erben Wagner erhielten die
  Mitteilung fristgerecht.“) permanecía en el contexto de herencia/sucesión casi
  siempre sin reconocer.
- Un apellido tras „Geschwister“ (hermanos; p. ej. „Die Geschwister Bauer wohnen
  in Linz.“) permanecía hasta ahora casi siempre sin reconocer — a diferencia de
  „Familie“/„Ehepaar“, esto no afectaba solo a nombres homónimos de profesión (Koch,
  Bauer, Richter), sino a apellidos cualesquiera en esta posición.
- Un apellido tras „Ehepaar“ o „Eheleute“ (matrimonio; p. ej. „Das Ehepaar Koch
  zieht um.“) no se reconocía cuando era al mismo tiempo un
  sustantivo común o una denominación de profesión (Koch, Bauer, Richter).
- Un número de pedido, encargo o artículo normal en la cuadrícula de agrupación
  típica de un número fiscal o de seguridad social
  (p. ej. „030 4471 2298“) se censuraba erróneamente como tal sin ningún
  rótulo asociado.
- Un número de comprobante/expediente en el formato „año/número consecutivo“ (p. ej. en
  „Rechnung Nr. 4/2024/778899“) se censuraba erróneamente como número de teléfono
  por el reconocimiento de números de llamada.
- Un nombre tras „Herr“/„Frau“ con una cadena de título académico de varias
  palabras delante („Herr Dr. med. Weber“, „Herr Prof. Dr. Krause“) permanecía
  hasta ahora totalmente desprotegido — hasta ahora solo se reconocía una
  sola palabra de título entre el tratamiento y el nombre.
- Un número de expediente judicial en el formato clásico con abreviatura de
  sala/cámara („4 Ca 1523/24“, „Az.: 7 O 234/25“) permanecía hasta ahora totalmente
  desprotegido — tampoco se reconocía la forma abreviada habitual „Az.“/„Gz.“ junto
  al rótulo desarrollado.
- Un número de tarjeta de crédito separado por un salto de línea en medio de su
  agrupación de cuatro dígitos — por ejemplo en una columna de tabla estrecha —
  permanecía hasta ahora totalmente desprotegido.
- Un número de identificación fiscal separado por un salto de línea en medio de su
  agrupación — por ejemplo en una
  columna de tabla estrecha o un campo de formulario — permanecía hasta ahora totalmente
  desprotegido.
- Un número de seguridad social separado por un salto de línea en medio de su
  agrupación — por ejemplo en una columna de tabla estrecha —
  permanecía hasta ahora totalmente desprotegido, ni siquiera
  parcialmente sustituido.
- Un número de calle con rango como „12a-14b“ o „3-5“ solo se sustituía a la
  mitad — la segunda parte tras el guion permanecía visible en el resultado.
- Un número de bastidor (FIN/VIN) separado en medio de sus 17 caracteres por
  un salto de línea, espacio o guion — por ejemplo en
  una columna de tabla estrecha o un campo de matrícula del vehículo — permanecía
  hasta ahora totalmente desprotegido.
- Un saludo de carta/correo como „Liebe Anna!“ o „Lieber Hans“ — sin
  coma tras el nombre, la forma más frecuente en correos informales — dejaba el
  nombre totalmente desprotegido, también en el documento completo con
  texto continuo y fórmula de despedida debajo.
- La misma laguna afectaba también a los saludos informales de chat/correo „Hallo Anna!“,
  „Hi Anna!“, „Hey Anna!“ y „Servus Anna!“ sin coma — el nombre permanecía
  igualmente totalmente desprotegido.
- Un bloque de firma puro que comienza directamente con „MfG“ o „Herzlichst“
  — por ejemplo copiado del portapapeles, sin frase precedente — dejaba
  el nombre debajo totalmente desprotegido.
- Un campo con varias personas, por ejemplo „Angehörige: Kaczmarek, Piotr
  (Sohn), Kaczmarek, Anna (Ehefrau)“, fusionaba ambos nombres junto con la
  indicación entre paréntesis en un único hallazgo, mucho demasiado largo — el segundo
  nombre permanecía en parte desprotegido en el resultado.
- Una calle sin sufijo „-straße“/„-weg“ — como es habitual
  en zonas rurales, por ejemplo „Am Marktplatz 5“ o „Im Grund 12“ — no se
  reconocía cuando le seguía una línea de código postal-localidad, por ejemplo en un
  certificado de empadronamiento: „Neue Anschrift: Am Weidengarten 17, 54295 Trier“
  perdía la calle por completo, solo se eliminaba el código postal.
- Un nombre tras un rótulo de campo compuesto con
  barra (p. ej. „Name/Vorname: Bauer Klaus“) en parte no se
  reconocía — un apellido ambiguo como „Bauer“ permanecía sin el
  comprobante de campo indetectado. La misma laguna afectaba a campos combinados como
  „PLZ/Ort: 04109 / Leipzig“. Lo mismo valía para campos combinados con
  conector escrito en lugar de barra, por ejemplo
  „Vor- und Nachname: Bauer Klaus“ o „Nachname bzw. Vorname: …“.
- Una fecha de nacimiento en la forma „Datum der Geburt: …“ y una fecha de defunción
  en la forma „Todesdatum: …“ o „Datum des Todes: …“ no se
  reconocían — solo acertaban „Geburtsdatum: …“ y „Sterbedatum: …“.
- Una fecha de boda en la forma „Datum der Heirat: …“ o „Datum der
  Hochzeit: …“ no se reconocía — solo acertaban „Hochzeitsdatum: …“,
  „Heiratsdatum: …“ y „Datum der Eheschließung: …“, aunque
  la fecha de divorcio, naturalización y unión civil conocían desde hacía tiempo la misma
  forma „Datum der X“.
- Una fecha de divorcio en la forma „Datum der Scheidung: …“ no se
  reconocía — solo acertaban „Scheidungsdatum: …“ y la forma verbal pospuesta,
  aunque la fecha de naturalización y unión civil conocían la misma
  forma „Datum der X“ desde el principio.
- Una fecha de unión civil no se reconocía hasta ahora en absoluto — ni con
  rótulo („Verpartnerungsdatum: …“, „Datum der Lebenspartnerschaft:
  …“) ni en texto continuo („… wurden am … verpartnert“). Ahora se sustituye, igual que
  la fecha de nacimiento, boda, divorcio y naturalización, como propio
  tipo de dato.
- Una fecha de naturalización no se reconocía hasta ahora en absoluto — ni con
  rótulo („Einbürgerungsdatum: …“) ni en texto continuo („… wurde am …
  eingebürgert“). Ahora se sustituye, igual que la fecha de nacimiento, boda y
  divorcio, como propio tipo de dato.
- Una fecha de divorcio no se reconocía hasta ahora en absoluto — ni con
  rótulo („Scheidungsdatum: …“) ni en texto continuo („Die Ehe wurde
  am … geschieden“). Ahora se sustituye, igual que la fecha de nacimiento, defunción y
  boda, como propio tipo de dato.
- Una fecha de boda tras el signo genealógico de matrimonio „⚭“ sin rótulo
  no se reconocía, aunque la fecha de nacimiento y defunción en la misma línea
  mediante asterisco y cruz ya se reconocían — ahora también se reconoce la
  fecha de boda.
- Una fecha de defunción tras la cruz de esquela sin rótulo
  („*03.06.1940 †21.11.2023“) no se reconocía, aunque la fecha de nacimiento
  delante mediante el asterisco genealógico ya se reconocía — ahora también se reconoce la
  fecha de defunción.
- El apellido antes del nombre de pila al final de una línea de asunto/ticket con texto
  temático antepuesto y guion separador („Betreff: Reklamation - Bauer, Anna“) no se
  reconocía con un apellido homónimo de profesión — ahora se reconoce.
- Los números de solicitante y aspirante tras su rótulo
  („Bewerbernummer: 4471829“, „Antragstellernummer: 7654321“) pasaban
  por completo desapercibidos al reconocimiento — ahora se reconocen.
- Sustituir ya no censura cuando no hay espacio para un
  marcador de posición legible — un marcador demasiado pequeño se escribe ahora más
  pequeño en lugar de convertirse en una barra vacía, siempre que quede algo de
  espacio. Además, nuevo: si un hallazgo en una imagen (membrete,
  fondo de escaneo) se rotula o solo se censura puede ajustarse ahora
  independientemente del resto del tipo de resultado. Y un hallazgo
  en una imagen que se elimina por completo se rotulaba como si la
  imagen permaneciera — el marcador de posición estaba en claro sobre un fondo que nunca
  se censuraba, y así desaparecía de forma invisible sobre el ahora
  papel blanco.
- Un hallazgo en una imagen **conservada** se censuraba siempre al
  sustituir en blanco y negro, independientemente de la representación elegida
  (colores de categoría, arcoíris…) — visible como ruptura entre etiquetas
  coloridas en el texto continuo y barras negras en el membrete. El
  fondo de imagen sigue ahora el mismo color que el marcador de posición al lado.
- El reconocimiento del número de identificación de vehículo (FIN/VIN) marcaba
  incondicionalmente cualquier código alfanumérico de 17 dígitos sin I/O/Q como
  número de bastidor — también números de pedido, serie y clave de licencia
  que casualmente tienen la misma forma. Ahora solo cuenta con una
  palabra de contexto cercana („FIN“, „VIN“, „Fahrgestell“, „Chassis“ o similar).
- En sistemas de tickets/calendario, el reconocimiento de nombres arrastraba tras „Assigned to“/
  „Closed by“ o similar la siguiente palabra de campo, cuando seguía directamente
  en la misma línea sin separador („Assigned to Max Mustermann Priority High“
  se convertía en „Max Mustermann Priority“). En encabezados de commit de Git, el
  reconocimiento de nombres arrastraba igualmente la **siguiente** clave de trailer, cuando dos
  líneas quedaban unidas por un solo espacio en lugar de un salto de línea
  („Author: julia bergmann Reviewed-by: …“ se convertía en „julia bergmann
  Reviewed-by“). Ambos frenos añadidos.
- El nombre tras „p.A.“, „zH“/„zHd“, „i.A.“/„i.V.“ y „geb.“ arrastraba una
  palabra de departamento inmediatamente siguiente al mismo hallazgo, cuando estaba sin
  separador en la misma línea („p.A. Max Mustermann Buchhaltung“
  se convertía en „Max Mustermann Buchhaltung“, „i.A.Max Mustermann Vertrieb“ en
  „Max Mustermann Vertrieb“). El mismo freno que en „Assigned to“/
  trailers de Git añadido ahora también aquí.
- Un IBAN rotulado directamente encima de la línea BIC, BLZ o SWIFT arrastraba
  su rótulo consigo dentro de su propio hallazgo, porque „BIC“ y „BLZ“
  parecían ellos mismos otro bloque de números — de „IBAN: DE89 …
  0130 00“ y la línea de debajo resultaba un único hallazgo demasiado
  amplio, y el rótulo de la línea siguiente desaparecía también al
  limpiar. Afectaba casi a cualquier dato bancario con IBAN y BIC
  uno debajo del otro.
- El panel de hallazgos indica ahora **dónde** está un marcador de posición que no
  puede encontrar en la página. Dos casos solo notificaban hasta ahora „no encontrado“,
  aunque la sustitución había tenido lugar: si el marcador de posición está en texto
  secundario no visible — por ejemplo la dirección de referencia de un enlace, una anotación o
  un campo de formulario —, la línea lo indica ahora como aviso propio
  („en texto secundario“), y el clic lo explica. Y si el marcador de posición se
  escribía acortado por falta de espacio („[N382]“ en lugar de „[NAM382]“), el clic
  sobre la línea larga salta ahora al lugar de la forma corta y menciona la
  renombración; la asociación entrelaza expresamente ambas líneas para
  ello.
- Si el mismo valor de sustitución aparece varias veces en el documento, cada clic
  adicional sobre la línea del panel salta en círculo al siguiente hallazgo — también entre
  límites de página; la línea de estado cuenta („hallazgo 2 de 4“), y el
  lugar recién señalado está enmarcado de forma más intensa que los demás. Y si
  un marcador de posición solo está en la lista de hallazgos, pero en ningún lugar del documento
  (porque el lugar quedó absorbido en una sustitución superpuesta), la
  línea de estado lo indica ahora, en lugar de que el clic quede mudo y sin efecto.
- Un nombre de pila abreviado tras „an“ o „für“ se reconoce ahora de forma fiable como
  nombre — „Überweisung an M. Wagner“ y „Rechnung für M. Wagner“
  permanecían hasta ahora a menudo sin limpiar, mientras que el mismo nombre con otro
  rótulo delante (por ejemplo „Zahlungsempfänger:“) ya se encontraba.
  Afectaba sobre todo a líneas de extracto de cuenta y contabilización.
- „Angeklagter“/„Angeklagte“/„Beschuldigter“/„Beschuldigte“ (acusado/a) cuentan ahora como
  campo de nombre: si un nombre en documentos de proceso penal estaba directamente tras
  uno de estos rótulos, hasta ahora no se reconocía en absoluto para
  aproximadamente la mitad de los nombres comprobados — ni nombre ni apellido.
- El lugar seleccionado con clic en el panel de hallazgos se enmarca ahora en azul en lugar de
  marcarse en amarillo — en las superficies coloreadas del semáforo de verificación el amarillo del
  hallazgo de búsqueda no se distinguía. Además, el clic encuentra ahora también
  valores de sustitución de varias palabras (nombres inventados, números enmascarados): hasta ahora
  el clic quedaba sin efecto en tales líneas, porque el hallazgo se buscaba solo palabra
  por palabra.
- Padres adoptivos, de acogida y padrastros/madrastras („Adoptivvater“, „Pflegemutter“,
  „Stiefvater“ y otros) se reconocen ahora como campo de nombre; el nombre
  pasaba antes desapercibido sin limpiar.
- Las tablas y listas ricas en números ya no se descartan erróneamente:
  si un número corto (por ejemplo una parte de número de cliente leída como
  número de teléfono) se sustituía, la verificación final notificaba la misma
  secuencia de dígitos como dato restante incluso cuando en otro lugar solo estaba
  contenida por casualidad en un número completamente distinto — y entonces no entregaba
  ningún resultado en absoluto. Un número cuenta ahora solo como resto donde
  aparece como número propio.
- Actas de estado civil: „Vater:“/„Mutter:“ se reconoce ahora como campo de nombre; el nombre del progenitor pasaba antes desapercibido sin limpiar.
- Otros roles familiares („Pate“, „Großvater/-mutter“, „Ehepartner“,
  „Lebenspartner“, „Onkel“, „Tante“) se reconocen ahora como campo de nombre;
  el nombre pasaba antes desapercibido sin limpiar.
- El código bancario alemán (Bankleitzahl) se reconoce ahora también agrupado oficialmente
  („370 400 44“, „370.400.44“, „370-400-44“, „370/400/44“), ya no
  solo como ocho dígitos consecutivos.
- El número alemán de seguro de pensiones se reconoce ahora también con punto,
  guion o barra entre los cinco bloques
  („65-170839-J-08-8“, „65.170839.J.08.8“), ya no solo con espacio.
- La ventana principal aparece más rápido: las bibliotecas de reconocimiento
  (Presidio junto con la infraestructura del modelo de lenguaje) se cargaban hasta ahora ya
  durante la construcción de la ventana — en Windows unos cuatro segundos, antes de que
  hubiera algo que ver. Ahora se cargan por completo en segundo plano; el
  botón „Limpiar“ se habilita, como hasta ahora, solo cuando todo está listo.
- Los documentos de Office con muchas imágenes o vídeos se escriben más rápido:
  los medios ya comprimidos se guardan en el paquete de resultado
  en lugar de comprimirse inútilmente una segunda vez — hasta ahora eso no ahorraba
  ni un byte y hacía los JPEG más bien más grandes.
- Las hojas de cálculo y otros documentos formados por muchas unidades de
  texto pequeñas se verifican más rápido: el reconocimiento de idioma procesa ahora
  todas las celdas y párrafos de un documento en un solo pase en lugar de
  individualmente — con los mismos hallazgos comprobados (400 celdas: de unos
  4,7 a 2,5–3,5 segundos).
- Las páginas PDF de tipo lista (índices, listas de posiciones) son notablemente
  más rápidas al insertar los marcadores de posición: la búsqueda de espacio por
  rótulo recorría hasta ahora todas las palabras de la página — ahora solo
  el entorno de la línea, con el mismo resultado comprobado (en una
  página con 300 rótulos, unas dieciséis veces más rápido).
- Los documentos ricos en imágenes ahorran varios pasos de trabajo innecesarios por imagen:
  el conteo de rostros y códigos en páginas PDF ya no decodifica
  la imagen de página dos veces, la verificación de metadatos ya no descifra
  una imagen limpia en absoluto, las imágenes pixeladas se escriben con la
  compresión PNG normal en lugar de la más lenta (mismo
  tamaño, un tercio del tiempo), y sin marca de agua configurada
  se omite la reescritura inútil de todo el PDF al final.
- Los PDF escaneados con reconocimiento de texto activado terminan notablemente
  más rápido: cada página se renderizaba hasta ahora dos veces en resolución completa
  (una vez para leer, una vez para rasterizar) — la imagen se
  reutiliza ahora. Y en Windows/Linux, el reconocimiento de texto lee las
  franjas de un escaneo grande en un solo paso en lugar de con un
  arranque de programa propio por franja.
- Los documentos grandes se limpian notablemente más rápido: la comparación de valores ya
  encontrados crecía hasta ahora con el número de hallazgos (un
  bloque de texto de 64 KB costaba al final de un archivo grande alrededor de un
  segundo solo para eso, ahora una sesentava parte), y la búsqueda de formas
  jurídicas de empresa recorría todas las ~280 formas del catálogo sobre cada
  fragmento de texto (ahora unas veinte veces más rápido, con los mismos
  hallazgos comprobados).
- Un nombre directamente tras „Beste Grüße“/„Beste Wünsche“ sin
  texto ni signo de puntuación precedente no se reconocía en absoluto — un
  bloque de firma puro sin texto continuo delante hacía desaparecer el nombre
  sin dejar rastro.
- Un campo de dirección al inicio del documento con un apellido
  homónimo de profesión („Bauer Anna“, „Koch Stefan“ como primera línea sobre calle y
  localidad) permanecía hasta ahora en parte sin reconocer o se clasificaba como
  indicación de lugar en lugar de persona — sin frase precedente, al modelo de lenguaje le
  faltaba la construcción gramatical que de otro modo permite reconocer „Bauer“
  como nombre y no como profesión.
- Un nombre tras la marca de firma „gez.“ con un apellido
  homónimo de profesión antes del nombre de pila („gez. Bauer Anna“ al
  final de una resolución o sentencia) permanecía hasta ahora incompletamente reconocido —
  solo se encontraba el nombre de pila, el apellido desaparecía sin dejar rastro.
- Un nombre directamente tras un número de cliente, número de contrato o
  número de identificación similar sin línea propia („Vertragsnummer 55219 Bauer
  Anna“, „Kundennr. 4711 Bauer Anna“) con un apellido homónimo de profesión
  permanecía hasta ahora incompleta o totalmente sin reconocer.
- El icono en la barra de menú de macOS es ahora una plantilla que se adapta,
  como los iconos vecinos, al modo claro y oscuro — con las dos
  barras troqueladas sigue siendo reconocible como Maskuro. Si el
  vigilante del portapapeles está en marcha, lo indica un punto separado en la
  punta del escudo.
- Un clic en el panel de hallazgos lleva ahora también en el modo de anonimización
  al lugar del hallazgo: cambio de página, desplazamiento hasta la imagen, marcado en amarillo. Hasta ahora
  el clic quedaba allí sin efecto, porque aún consideraba los marcadores de posición como
  sin número — desde que cada hallazgo lleva su propio número, el
  lugar es inequívoco. Solo con el marcador de posición realmente sin número, la línea de estado
  sigue explicando por qué no se puede determinar ningún destino de salto.
- El primer guardado en el editor de corrección (Ctrl+S o el
  botón de disquete) pregunta ahora por el lugar, como „Guardar como…“ —
  preconfigurado con la carpeta del original y el nombre del resultado. Hasta ahora
  el archivo acababa sin previo aviso junto al original. Quien ya haya elegido antes
  el lugar de guardado mediante la línea de estado no se le pregunta de nuevo;
  cada guardado adicional sigue escribiendo, como hasta ahora, el mismo archivo.
- Si la verificación de seguridad antes de guardar notifica un lugar llamativo,
  „Volver a la verificación“ conduce ahora hasta él: el primer hallazgo se desplaza a la vista
  y se enmarca en rojo, la línea de estado lo menciona. Hasta ahora se quedaba uno solo con
  el número de página y las coordenadas de punto. Desde la ventana principal, el editor se
  abre entonces en ese lugar. También ante el aviso de un número de página
  divergente, el botón conduce ahora hasta allí — a la primera página que
  solo existe en uno de los dos documentos.
- Quien cambia la vista previa a „Uno al lado del otro en dos columnas“ obtiene
  ahora automáticamente una ventana en la que caben ambas pistas — hasta ahora
  se apretujaban en el ancho anterior, hasta que se arrastraba manualmente. Se ensancha
  como máximo hasta el borde de la pantalla y nunca se vuelve a estrechar; un
  ancho arrastrado manualmente se mantiene.
- El apellido y el nombre de pila en columnas de tabla separadas (p. ej. „Nachname | Vorname“
  en una confirmación de inscripción o una exportación CSV) permanecían al descubierto — cada
  celda por sí sola parecía para el reconocimiento una palabra cualquiera sin
  contexto de nombre. Ahora se reconocen.
- El apellido y el nombre en el reverso de una licencia de conducir tarjeta UE permanecían
  al descubierto — allí están tras los códigos de campo oficiales „1.“ y „2.“
  en lugar de tras una palabra alemana, y precisamente eso los dejaba sin reconocer.
  Se reconocen ahora cuando el número de la licencia (código de campo „5.“)
  está al lado.
- El nombre de pila del titular del vehículo en el permiso de circulación permanecía
  al descubierto — está tras el código de campo oficial „C.1.2“ en lugar de tras
  una palabra alemana como „Vorname“, y precisamente eso lo dejaba sin reconocer.
  El apellido y el nombre de pila bajo los códigos de campo C.1, C.1.1 y C.1.2 se
  reconocen ahora.
- La primera línea de la zona legible por máquina (MRZ) en el pasaporte o el
  documento de identidad permanecía al descubierto — lleva el nombre en el formato
  „APELLIDO<<NOMBRE“ y se escapaba por completo también con el nuevo reconocedor de MRZ
  para la línea de dígito de control. Un hallazgo cuenta ahora solo cuando
  directamente al lado hay una segunda línea MRZ válida por dígito de control — la
  línea del nombre misma no tiene dígito de control propio.
- La segunda línea de la zona legible por máquina (MRZ) en el pasaporte o
  documento de identidad permanecía totalmente sin reconocer — contiene el número de pasaporte,
  la fecha de nacimiento y de caducidad en texto claro, pero no acertaba con ningún
  reconocedor existente. Un reconocedor propio comprueba ahora los cuatro
  dígitos de control ICAO.
- Una matrícula de vehículo sin ningún espacio respecto al rótulo permanecía al descubierto —
  „KennzeichenM-AB1234“ o „KFZ-KennzeichenM-AB1234“ no se
  reconocían en absoluto, porque la comprobación de matrícula subyacente exige antes de la matrícula
  un carácter que no forma parte de palabra. Afectaba a datos de vehículo donde no
  había espacio entre la palabra de campo y la matrícula.
- Un número de teléfono sin ningún espacio respecto al rótulo permanecía al descubierto —
  „Handynummer0171/2345678“ o „Tel0171/2345678“ no se
  reconocían en absoluto, porque la comprobación de número subyacente exige antes del
  número un espacio o signo de puntuación. Afectaba a datos de contacto donde
  no había espacio entre la palabra de campo y el número.
- Un apellido de soltera tras la abreviatura „geb.“ no se reconocía en absoluto —
  „Julia Bergmann (geb. Weber)“ solo encontraba „Julia Bergmann“, el punto en
  „geb.“ hacía que el modelo de lenguaje omitiera por completo el nombre siguiente.
  Afectaba a datos de persona con apellido de soltera entre paréntesis o tras coma.
- El nombre de pila antes de un apodo entre comillas permanecía al descubierto, cuando
  el tratamiento y el título estaban juntos delante — „Herr Dr. Klaus 'KP' Peters“
  daba solo „Peters“, „Klaus“ permanecía legible. Afectaba a firmas
  y datos de contacto con título y apodo.
- Un nombre tras la forma abreviada sin punto „zH“/„zHd“ (a la atención de) no se
  reconocía en absoluto — a diferencia de „z.Hd.“ con punto, la estructura de frase
  faltante arrastraba el nombre consigo. Afectaba a direcciones sin punto en la
  abreviatura.
- Un nombre tras „p.A.“ (en casa de) no se reconocía en absoluto — el punto
  en la abreviatura hacía que el modelo de lenguaje omitiera por completo el
  reconocimiento del nombre. Afectaba a facturas y solicitudes con dirección colectiva.
- Un nombre tras „i.A.“/„i.V.“ (por orden de/en representación de) pegado sin punto no se
  reconocía en absoluto, por ejemplo „i.A.Robert Lang“ sin
  espacio — el mismo error de construcción de frase que en „p.A.“. Afectaba a
  líneas de firma y firmas de correo electrónico de casos de representación.
- Una lista de asistencia pura con viñeta sin ningún otro
  dato („- Max Mustermann“, también con punto al final de línea) perdía todos los
  nombres por el mismo freno que en realidad solo debería proteger enumeraciones objetivas como
  „- Farbe: Blau“. Estas listas se reconocen ahora.
- Los archivos que ya no se podían limpiar vuelven a poder
  limpiarse. Un valor que ya había sido sustituido por el reconocimiento podía
  volver a encontrarse en su propia marca ya sustituida como „[SVNR1]“
  — la verificación final descartaba entonces un archivo impecablemente limpiado. Además,
  una referencia telefónica en una tabla CSV se elimina ahora también, y quien
  restringe la búsqueda a tipos individuales la obtiene ahora igual en todo el
  documento — también en el texto alternativo de una imagen, un
  encabezado de Excel, una lista desplegable o un atributo HTML.
- Un nombre tras el encabezado de correo „To:“ (o „To“ sin dos puntos)
  no se reconocía, porque un modelo de lenguaje ajeno leía toda la línea como
  un único hallazgo poco llamativo y engullía por completo el nombre en ella
  — a diferencia de „Cc:“, „Bcc:“ o „From:“ ante el mismo
  nombre. Un nombre tras „To“ se encuentra ahora de forma fiable.
- La fecha de boda no se podía tratar como fecha en reglas propias
  („desplazar“ se rechazaba con „solo existe para fechas“), faltaba en la
  asignación de grupo de los tipos de hallazgo — con lo que no se podía desactivar
  mediante las marcas „Qué se busca“ — y recibía, en lugar de una
  abreviatura corta como en la fecha de defunción, el texto completo como marcador de posición.
  Corregido para las seis tablas de abreviatura/rótulo.
- Un valor deseleccionado conscientemente en la vista previa podía sin embargo censurarse
  en otro lugar: si se deseleccionaba, por ejemplo, una dirección de correo, la
  dirección misma permanecía, pero su parte local sin dominio se
  sustituía en cuanto coincidía con el nombre de usuario derivado de una
  persona seleccionada adicional („anna.musterfrau@beispiel.de“ junto a „Anna
  Musterfrau“). Un texto deseleccionado permanece ahora tabú en todo el documento,
  independientemente del tipo de hallazgo del que proceda.
- Una fecha de nacimiento permanecía sin reconocer cuando un libro de familia o
  extracto de estado civil la llevaba bajo un encabezado común con el
  lugar de nacimiento („Geburtsdatum, Geburtsort: 19.11.1982, Steyr“) — la
  segunda palabra de campo entre „Geburtsdatum“ y la fecha hacía que el
  reconocimiento fallara por completo hasta ahora.
- Un número de teléfono ya reconocido permanecía legible en su forma de confirmación
  abreviada, cuando en otro lugar del mismo documento se mencionaba solo con los
  últimos cuatro dígitos („erreichbar unter der Nummer
  ...5678“, „Rückruf unter ...5678“) — la misma forma que en IBAN y
  tarjeta de crédito.
- Un número de tarjeta de crédito ya reconocido permanecía legible en su forma de
  confirmación abreviada, cuando en otro lugar del mismo documento se mencionaba
  solo con los últimos cuatro dígitos („Ihre Kreditkarte
  endet auf ...0366“) — la misma forma habitual en confirmaciones de pago
  que en el IBAN.
- Un IBAN ya reconocido permanecía legible en su forma de confirmación abreviada,
  cuando en otro lugar del mismo documento se mencionaba solo con los
  últimos cuatro dígitos („Die IBAN endet auf ...3201“) — una
  forma habitual en correos de confirmación.
- Un interviniente en un chat o acta de sesión permanecía sin reconocer, cuando
  ante su nombre había un tratamiento („Herr Bauer: …“, „Frau Koch: …“) —
  y con ello a menudo afectaba también a la siguiente línea de interviniente en la misma acta,
  porque quedaban demasiado pocas líneas reconocidas para
  clasificar el documento como acta en absoluto.
- Una fecha de nacimiento permanecía sin reconocer, cuando la palabra de campo „geboren“ estaba
  DETRÁS de la fecha en lugar de delante („Das Kind wurde am 14.01.2026 geboren“) — así
  formula, por ejemplo, un certificado de excedencia parental o de protección de maternidad
  la fecha de nacimiento del hijo. Los patrones anteriores siempre presuponían la palabra de campo antes
  de la fecha.
- Un rótulo de formulario con un signo de reacción o marca de verificación directamente delante
  („Ansprechpartner 😊:“, „Kontaktperson ✓:“) ya no se reconocía como
  rótulo, y el nombre debajo o detrás quedaba por ello a veces solo
  incompletamente encontrado (p. ej. solo el apellido en „Mayer
  Roman“).
- La misma laguna afectaba también a datos especialmente protegidos según el art. 9
  del RGPD (religión, salud, sindicato): un signo de reacción directamente
  antes del separador o salto de línea („Konfession 😊: römisch-katholisch“)
  hacía que el rótulo fallara por completo, y el dato permanecía completamente
  sin reconocer.
- Una dirección con nombre compuesto con guion en la localidad (p. ej. „79761
  Waldshut-Tiengen“, „78050 Villingen-Schwenningen“) perdía por completo el
  código postal, aunque la propia localidad se reconocía y censuraba —
  en un documento de vehículo o carta, el código postal permanecía así
  legible.
- Una columna de tabla sin espacio de columna (extracto de texto PDF real) podía,
  bajo una columna de nombres, censurar erróneamente como persona también dos
  mayúsculas casualmente contiguas, por ejemplo dos topónimos en
  una línea de datos; esto ahora solo ocurre cuando ningún otro
  hallazgo en el mismo lugar ya reconoce otra cosa.
- La misma columna de nombres censuraba, en la misma forma de línea, también dos
  palabras técnicas desconocidas para el modelo de lenguaje (p. ej. „Frontend Backend“, „Turbo
  Modul“) erróneamente como persona, porque allí ningún otro hallazgo activaba el
  freno; ahora exige además que al menos una de las dos
  palabras sea leída por el propio modelo de lenguaje como nombre propio.
- El número alemán de seguro de pensiones no se reconocía en su
  agrupación oficial completa (p. ej. „65 170839 J 08 8“ — tal como aparece en
  el carné de seguridad social y la nómina) y permanecía en el original;
  solo se reconocían la notación compacta
  y la forma agrupada solo hasta la letra.
- El número de identificación fiscal no se reconocía en absoluto en su notación oficial
  (agrupación 2-3-3-3, p. ej. „48 836 075 988“ — tal como aparece en cada
  liquidación fiscal real y cada notificación de la Oficina Central Federal de
  Impuestos) y permanecía en el original; solo estaba cubierta la
  agrupación más rara 3-3-3-2.
- El número fiscal de Renania del Norte-Westfalia (p. ej. „221/5147/0815“, con
  segundo grupo de cuatro dígitos en lugar de tres) no se reconocía en absoluto en
  liquidaciones fiscales y permanecía en el original — cada
  otro estado federado ya estaba cubierto.
- En contratos de trabajo, un nombre tras el rótulo
  „Arbeitgeber:“ se pasaba por alto por completo en cuanto el apellido era al mismo tiempo una
  palabra común (p. ej. „Bauer Anna“) — „Arbeitgeber“ figura tanto
  como rótulo de nombre como de empresa en la lista, y la
  asignación de empresa sobrescribía la asignación de nombre.
- En un encabezado de contrato de alquiler con los rótulos „Vermieter:“/„Mieter:“
  se pasaba por alto un apellido que es al mismo tiempo una palabra común (p. ej.
  „Bauer“) — solo se reconocía el nombre de pila. Las partes arrendatarias numeradas
  („Mieter 1:“, „Mieter 2:“) se veían afectadas adicionalmente, incluso
  con nombres sin esta ambigüedad.
- En un acta judicial con los rótulos „Zeuge:“/„Kläger:“/
  „Beklagter:“ (también con numeración, „Zeuge 1:“, „Zeuge 2:“) se pasaba por alto
  igualmente un apellido que es al mismo tiempo una palabra común (p. ej. „Bauer“) —
  solo se reconocía el nombre de pila.
- En certificado de herencia, poder, procedimiento monitorio y contrato de
  compraventa, se pasaba por alto un apellido que es al mismo tiempo una palabra
  común (p. ej. „Bauer“) tras
  rótulos como „Erblasser:“, „Erbe:“, „Vollmachtgeber:“,
  „Bevollmächtigte:r“, „Antragsgegner:“, „Schuldner:“, „Gläubiger:“,
  „Käufer:“, „Verkäufer:“, „Vermächtnisnehmer:“ o
  „Testamentsvollstrecker:“ — en parte solo se reconocía el nombre de pila,
  en parte se perdía el nombre completo.
- En una lista de varias partes ante el separador de rúbrica „./.“ (p. ej.
  „Sand, Werner und Huber, Anna ./. Wechsler, Martina“), la primera
  parte permanecía sin enmascarar — solo se reconocía la parte
  directamente contigua a „./.“.
- En el separador de rúbrica „./.“ (p. ej. „Sand./.Wechsler“), el nombre
  tras el signo se pasaba por alto por completo cuando no había ningún espacio —
  el reconocimiento solo acertaba con espacio antes y después.
- El apellido „Wahr“ se pasaba por alto por completo cuando aparecía solo
  (p. ej. „Frau Wahr bearbeitet Ihren Vorgang.“) — la palabra figura casualmente
  también en la lista de palabras alemanas comunes, que de otro modo filtra
  hallazgos de nombre de frases como „Das ist wahr.“.
- Apellidos como „Los“, „Weit“, „Rund“ u „Hoch“ se pasaban por alto por
  completo cuando aparecían solos (p. ej. „Herr Hoch übernahm die
  Leitung.“) — las cuatro palabras figuran casualmente también en la lista
  de palabras alemanas comunes, que de otro modo filtra hallazgos de nombre de
  frases como „Rund einhundert Gäste kamen zur Feier.“.
- Apellidos como „Ganz“ o „Recht“ se pasaban por alto por completo cuando
  aparecían solos (p. ej. „Herr Ganz unterschrieb den Vertrag.“) — ambas
  palabras figuran casualmente también en la lista de palabras alemanas comunes,
  que de otro modo filtra hallazgos de nombre de frases como „Ganz genau, das stimmt.“.
- Un campo de formulario con un asterisco o un número de nota al pie en
  superíndice tras el rótulo (p. ej. „Konfession*:
  römisch-katholisch“ o „Religionszugehörigkeit¹: evangelisch“) no se
  reconocía y permanecía en texto claro — solo acertaba la forma sin este
  signo.
- El mismo campo seguía permaneciendo en texto claro cuando había incluso dos
  signos de nota al pie tras el rótulo (p. ej. „Konfession**:
  römisch-katholisch“ o „Gewerkschaft¹²: ver.di“).
- Un número de versión como „Softwareversion 4.2.1.19“ o „Firmware Build
  2.0.4.11“ ya no se censura erróneamente como dirección IP. Lo mismo
  vale ahora para números de comprobante y expediente como „Rechnungsnummer
  10.20.30.40“ o „Bestellnummer 7.8.9.10“.
- Dos IBAN directamente uno debajo del otro (p. ej. el propio y el de un
  socio comercial extranjero en el encabezado de factura) ya no se reconocían
  ambos — el segundo permanecía sin advertir.
- Un IBAN rotulado a veces arrastraba consigo la palabra siguiente de la frase
  („Bankverbindung AT61 … wird belastet“ se censuraba hasta incluir „wird“),
  en cuanto la palabra siguiente estaba en minúscula — el resto en texto claro
  al lado permanecía intacto.
- Las direcciones de Liechtenstein se reconocen ahora („FL-9490 Vaduz“), igual que
  ya antes las alemanas, austríacas y suizas.
- El número de pasaporte se reconoce y elimina ahora tras su rótulo
  (p. ej. „Reisepassnummer: C01X00T471“).
- El número de permiso de residencia y de certificado de empadronamiento se reconocen ahora tras su
  rótulo y se eliminan.
- Un número de identificación tras su rótulo se reconoce ahora también cuando
  separa una raya en lugar de dos puntos (p. ej. „Kundennummer – K903944“).
- Un dato bancario rotulado como „IBAN“ o „Kontonummer“ se reconoce ahora
  también cuando separa una raya en lugar de dos puntos.
- Un nombre tras un rótulo como „Kontaktperson (Vertrieb)“ o
  „Sachbearbeiter/in“ se reconoce ahora también con complemento entre paréntesis o
  terminación de barra neutra en cuanto al género.
- La misma forma de género con asterisco („Sachbearbeiter*in“) se reconoce ahora
  también.
- Un nombre tras un rótulo se reconoce ahora también cuando un
  signo igual separa en lugar de dos puntos (p. ej.
  „Ansprechpartner = Mayer Roman“ o „Kontaktperson=Mayer Roman“), como es habitual en
  archivos de configuración o encabezados CSV. Si varios de estos
  pares rótulo-valor están separados por punto y coma en una línea, ahora solo
  se reconoce el primer valor en lugar de toda la línea restante.
- Un par de coordenadas GPS tras la palabra „Koordinaten“ se reconoce ahora de forma fiable
  (p. ej. „Koordinaten: 48.2082, 16.3738“) — la palabra llevaba la forma flexiva incorrecta
  en el catálogo interno.
- Un número de identificación tras su rótulo (número de cliente, número de contrato,
  número de expediente, número de documento de identidad y un centenar más de palabras de campo)
  ya no se reconocía en cuanto el rótulo no aparecía exactamente con la
  capitalización almacenada — „kundennummer:“ en un
  correo electrónico o „KUNDENNUMMER:“ en un encabezado de formulario permanecían intactos.

### Nuevo

- **Los valores de sustitución realistas son ahora un ejemplo elegido conscientemente
  en lugar de un valor predeterminado.** La tabla de excepciones en la pestaña „Marcador de posición“ empieza
  vacía. Un nuevo botón introduce allí, si se desea, valores falsos plausibles para nombre,
  lugar, dirección, organización, correo electrónico, teléfono, extensión e IBAN. Deja
  expresamente los importes monetarios en el marcador de posición numerado; la estrategia
  „inventar“ sigue pudiendo elegirse manualmente para tipos individuales.
- **El nivel de IA puede usar la tarjeta gráfica.** En Windows puede descargarse para ello
  un paquete adicional de apenas 17 MB; después el nivel de IA calcula
  notablemente más rápido en una tarjeta gráfica adecuada que en el procesador.
  Quien no tenga una o no descargue nada sigue trabajando sin cambios — solo
  más lento. En macOS la aceleración ya viene integrada de todos modos.
- **Dos nuevas notificaciones a través del icono de la barra de tareas**: cuando la
  vista previa está lista para revisión antes de sustituir, y cuando un
  procesamiento ha terminado. Ambas están activadas por defecto y pueden
  desactivarse individualmente en *Ajustes → Programa → Notificaciones*.

### Modificado

- **El número de documento de identidad y de la licencia de conducir se reconocen ahora** cuando
  su rótulo está delante („Personalausweisnummer: …“,
  „Führerscheinnummer: …“) — hasta ahora ambos pasaban desapercibidos a cualquier reconocimiento.
- **Maskuro sigue ahora los diseños de contraste de Windows.** Quien tenga activado
  uno bajo *Ajustes → Accesibilidad → Diseños de contraste*
  lo obtenía hasta ahora en todas partes menos aquí: Maskuro aplicaba entonces sus
  propios colores. Ahora se mantiene el diseño del sistema — ventana,
  listas, zona de depósito, registro y colores de estado. El semáforo de verificación coloreado en
  la vista previa y la ventana de corrección se omite allí conscientemente; lo que dice
  ya figura desde hace tiempo al lado como signo y como palabra.
- **La necesidad de verificación ya no está solo en el color.** Rojo, naranja y
  verde tienen un brillo casi igual — quien tiene daltonismo rojo-verde veía en
  la vista previa y el panel de hallazgos una lista sin diferencias, y eso es
  aproximadamente uno de cada doce hombres. Cada línea lleva ahora además un signo que
  se distingue en la forma: ▲ verificar primero, ● verificar, ○ bien documentado,
  ◆ sin valoración. El texto de ayuda breve lo indica en palabras, y un
  lector de pantalla lo lee en voz alta.
- **Alt vuelve a abrir los menús como de costumbre.** La barra de menú no tenía
  atajos de teclado: quien no usa el ratón tenía que recorrer cada menú con
  las flechas. Ahora cada entrada lleva una letra subrayada —
  Alt+D para „Datei“, desde allí B para „Beenden“ —, y eso en todos
  los idiomas de la interfaz.
- **Los elementos de control vuelven a indicar a un lector de pantalla para qué sirven.**
  En la ventana de corrección, la ventana de reglas, el registro, las listas de palabras,
  la ayuda, el recorrido de búsqueda y otras cinco ventanas, las listas,
  campos de búsqueda, listas desplegables y reguladores solo se anunciaban hasta ahora como „árbol“ o
  „cuadro combinado“ — sin decir de qué. Unos cuarenta lugares llevan
  ahora un nombre. (La ventana principal estaba en orden desde agosto; las
  ventanas que se añadieron después nunca habían seguido ese paso.)
- **Quien maneja con el teclado ve en todas partes dónde está.** En los
  reguladores de necesidad de verificación, en la casilla de verificación y en el botón „no eliminar nunca“ de la
  vista previa, en los encabezados de tipo dentro de ella, en el panel de páginas de la
  ventana de corrección y en la barra lateral de los ajustes faltaba el
  marco que el sistema pone normalmente alrededor del elemento de control con el foco.
- **Una letra de sistema mayor ya no corta nada.** Quien ajusta bajo
  *Accesibilidad → Tamaño de texto* por encima del 175 % perdía hasta ahora el final
  de los rótulos en la supervisión de carpetas y en los campos de
  atajos de teclado. La lista de capítulos de la ayuda cortaba nombres de capítulo largos ya
  con letra normal; ahora los envuelve en varias líneas y menciona el nombre
  completo en el texto de ayuda breve.

- **El reconocimiento se ha vuelto notablemente más rápido.** El reconocedor de
  números de identificación rotulados („Kundennummer: K903944“) comprobaba hasta ahora por
  fragmento de texto más de 1200 patrones individuales sucesivamente — ese era el mayor
  factor individual del tiempo de reconocimiento, en cada párrafo y cada celda de tabla.
  Ahora es un único patrón con el mismo resultado: en el corpus de medición
  no cambia ni un solo hallazgo, el nivel base por fragmento de texto se vuelve
  unas tres a cuatro veces más rápido.
- **La ventana aparece de inmediato al iniciar.** Hasta ahora la ventana principal cargaba
  las herramientas de idioma completas antes de siquiera mostrarse — unos
  cuatro segundos de tiempo ciego en cada inicio. Los modelos se cargan ahora, como estaba
  previsto, en segundo plano, mientras la ventana ya está visible; el
  botón de limpiar se habilita, como hasta ahora, solo cuando todo está listo. También
  las llamadas de la línea de comandos de mera información (por ejemplo `--version`) responden
  ahora de inmediato en lugar de tras varios segundos.
- **Las imágenes se leen solo una vez con el reconocimiento automático de idioma.**
  Hasta ahora, el reconocimiento de texto con el ajuste predeterminado
  „idioma: automático“ recorría dos veces la misma imagen — una vez para la
  presunción de idioma, otra para la verificación propiamente dicha. Los archivos de imagen,
  las imágenes del portapapeles y la ventana de texto terminan así aproximadamente el
  doble de rápido; con el reconocimiento de texto desactivado, la lectura que hasta ahora
  seguía ejecutándose sin notarse desaparece por completo.
- **Las páginas web y correos guardados se limpian más rápido.** Los
  valores en atributos HTML, comentarios y bloques de datos incrustados
  se reconocían hasta ahora individualmente — una página municipal con cientos
  de rótulos planteaba cientos de consultas individuales al reconocimiento. Ahora
  se recopilan y se reconocen solo una vez por valor distinto;
  en el corpus de medición no cambia ningún hallazgo, .html y .eml son aproximadamente un
  tercio más rápidos.
- **También las ubicaciones secundarias de hojas de cálculo y presentaciones se reconocen
  de forma agrupada.** Los textos alternativos, cadenas de fórmula, rótulos de gráfico,
  comentarios, cachés de tabla dinámica y propiedades de documento planteaban por
  valor una consulta de reconocimiento propia — un libro con miles de filas de tabla dinámica,
  correspondientemente miles. Ahora se ejecuta una pasada recopilada sobre los
  distintos valores, y la pasada completa de repaso al final solo se ejecuta ya
  cuando realmente han aparecido nuevos valores desde el texto continuo.
  En el corpus de medición no cambia ningún hallazgo.
- **Los PDF ricos en formularios se limpian más rápido.** Campos, notas,
  marcadores y referencias repiten los mismos valores masivamente
  („Off“ en cada casilla de verificación, el mismo autor en cada anotación) —
  cada uno planteaba hasta ahora su propia consulta de reconocimiento. Por ejecución, un
  valor se reconoce ahora solo una vez; la sustitución y el repaso de coherencia
  siguen ejecutándose sin cambios por lugar.
- **Los archivos de tabla grandes (.csv/.tsv) se limpian notablemente más
  rápido.** Los cuatro repasos de tabla descomponían hasta ahora cada uno
  el mismo archivo por sí solo carácter por carácter en celdas (con 40 MB, unos 30 s
  de trabajo adicional); ahora la descomposición se ejecuta una vez. El reconocimiento de encabezados de columna
  (columnas de fecha de nacimiento y número de personal) plantea, en lugar de una consulta por
  celda, una agrupada — con hallazgos idénticos, unas veinte veces
  más rápido. Y el resumen de columnas de nombre de listas de personal grandes
  ya no es cuadrático en el número de filas.
- **El panel de indicadores ya no congela la ventana.** Al desplegar
  los indicadores, con muchos archivos grandes se leía primero todo su texto y
  la ventana se quedaba así congelada durante segundos. El cálculo se ejecuta ahora en
  segundo plano; el panel se abre de inmediato y añade los números después.
- **El informe del recorrido de búsqueda ya no congela la ventana.** Tras
  recorrer varios miles de archivos, la carpeta común se recalculaba para cada
  archivo afectado; en ejecuciones grandes la ventana quedaba así congelada
  decenas de segundos. El informe aparece ahora de inmediato.
- **Los PDF con reconocimiento de texto se verifican más rápido.** Cada página se
  convertía innecesariamente dos veces a formato PNG durante la relectura; ahora se
  reutiliza la imagen ya disponible. El resultado no cambia, solo la verificación
  transcurre con más fluidez.
- **Las anotaciones de degradado en imágenes grandes ya no se atascan.** Al
  arrastrar los tiradores de una anotación con degradado, este se
  recalculaba hasta ahora punto por punto — en una captura de pantalla grande, una
  pausa visible. El resultado es el mismo, solo sin la pausa.

### Corregido

- **La cruz para eliminar un archivo de la lista vuelve a ser una
  X sencilla.** La nueva herramienta del editor „Eliminar“ había usado por error
  el mismo identificador de icono y por ello mostraba también su cruz roja junto con
  la línea de texto discontinua en cada línea de archivo. Ambas acciones
  tienen ahora nombres de icono separados y conservan cada una su representación
  correspondiente.
- **Los datos de varias partes se reconocen en los PDF también a través de un
  salto de línea visible.** Maskuro lee el texto de página generado geométricamente
  adicionalmente como vista de texto continuo con el mismo desplazamiento. Esto vale para todos los
  reconocedores de nivel base y superior, así como patrones de búsqueda propios, no solo para el
  caso „Diabetes mellitus Typ 2“ visible en primer lugar. Las líneas vacías y los límites de
  tabla o sección reconocidos siguen siendo límites duros; los hallazgos siguen
  ajustándose exactamente a las palabras a censurar.
- **El ejemplo en „Seudonimizar“ se contradecía a sí mismo.** La frase
  prometía „misma persona, mismo número“ y mostraba luego dos
  números diferentes — exactamente la imagen que es correcta en „Anonimizar“.
  Ambos ejemplos ahora coinciden con su propia frase.
- **Un marcador de posición recién colocado podía, al „recuperar el original“,
  quedar como una mezcla de letras superpuestas en lugar de desaparecer.**
  Un marcador de posición de un solo color colocado hasta ahora escribía un
  comando de salida propio por carácter, de los cuales solo el primero llevaba una
  matriz de texto propia — en la siguiente edición del mismo lugar (por ejemplo
  „recuperar“ justo después), los demás comandos de carácter recibían por turnos
  los índices de carácter del primero, y el marcador de posición se descomponía en
  dos posiciones superpuestas. Un marcador de posición de un solo color recibe
  ahora un único comando de salida para todo su texto.

- **Si el mismo valor censurado o eliminado figuraba bajo dos líneas en
  la ventana de corrección y ambas se marcaban para la anulación, la
  segunda línea contaba erróneamente como „no unívoca“ — aunque el valor ya
  hacía tiempo que se había recuperado.** Ambas líneas cuentan ahora como completadas.

- **El nombre tras „Reply-To:“ se encuentra ahora.** En un encabezado de correo
  como „Reply-To: Huber“, el nombre permanecía hasta ahora totalmente sin reconocer — el
  modelo de lenguaje leía „Reply-To:“ como una persona propia, incorrecta, y pasaba por alto
  el nombre real que seguía.

- **Las palabras de encabezado de correo „Reply“ y „Fwd“ ya no se censuran ellas mismas
  como nombre.** En una línea de asunto como „Fwd: Angebot von Huber“
  se reconocía y censuraba hasta ahora, además del nombre, también la propia palabra de encabezado
  como persona.

- **„Arbeitgeber: Siemens AG“ se reconoce ahora como empresa, ya no como
  persona.** Si el valor de empresa tras el rótulo „Arbeitgeber“ llevaba una
  forma jurídica como GmbH, AG o KG, seguía siendo, a pesar del
  reconocimiento de organizaciones activado, un hallazgo de persona — solo el caso más estrecho sin
  forma jurídica („Wollmuth und Partner“) se reconocía hasta ahora como empresa.

- **Una dirección reconocida una vez ya no permanece en otro lugar.**
  Si una dirección postal se reconocía y sustituía en un lugar,
  la misma dirección podía quedar sin tocar en un segundo lugar — por ejemplo en
  un pie de página difícil de leer de un documento escaneado, donde el
  reconocimiento de texto automático la leía mutilada. Las direcciones se eliminan ahora,
  como los nombres y empresas desde hace tiempo, de forma consistente en todo el documento.

- **Los correos con varios destinatarios se dañaban silenciosamente al limpiarlos.**
  Un mensaje `.msg` con dos o más destinatarios perdía, al guardar,
  partes de su estructura interna, de modo que el resultado limpiado quedaba
  incompleto. La causa era una confusión de componentes internos con el mismo nombre,
  que aparecen con cada destinatario. Estos mensajes ahora se
  reconstruyen por completo de nuevo.

- **Dos de los documentos de prueba incluidos no se podían abrir en Word ni
  en PowerPoint.** Quien descargaba el corpus de medición obtenía con
  `format_dokument.docx` „Error al abrir el archivo en Word“ y con
  `format_praesentation.pptx` „El archivo está dañado“. Ambos archivos
  ya estaban defectuosos antes de que Maskuro los tocara — la versión
  limpiada solo propagaba el error. LibreOffice abría ambos
  sin problemas, por lo que a nadie le había llamado la atención.

- **Una IA propia en internet se contacta ahora de forma cifrada.** Quien
  introduce en la IA propia una dirección externa sin „https://“ (como suele
  figurar en la nota de TI), la alcanzaba hasta ahora mediante una
  conexión sin cifrar — el texto sin censurar salía en texto claro. Estas
  direcciones se contactan ahora mediante „https://“; un servidor en la
  propia red sigue siendo accesible sin cambios. Si el servidor sigue una redirección
  a otro equipo, la clave de acceso ya no viaja con ella.

- **Incluso una imagen dañada pierde ahora sus metadatos ocultos.**
  Si una imagen incrustada ya no se podía abrir por completo (por ejemplo una
  foto cortada), hasta ahora conservaba sus datos EXIF y GPS —
  el lugar de captura y el nombre del fotógrafo permanecían invisibles en el resultado. Estas
  imágenes se liberan ahora también de esos datos, incluso cuando ya
  no se pueden mostrar en absoluto.

- **Un archivo incrustado que no se podía limpiar se notifica ahora
  en lugar de incluirse silenciosamente.** Si en una presentación o
  libro había un objeto incrustado demasiado anidado o que no se
  podía abrir, hasta ahora permanecía sin cambios en el resultado, sin aviso —
  el archivo se consideraba limpiado. Estos casos figuran ahora en la advertencia
  „NO pudieron verificarse“, igual que un formato antiguo incrustado.

- **Las listas oscuras vuelven a ser uniformemente oscuras y legibles.** En macOS
  las listas de archivos alternaban entre líneas casi negras y gris claro; en
  la corrección, el mismo valor de verificación verde, naranja o rojo se veía por ello
  diferente según la línea. Ventana, listas, tipografía, marcador de posición y selección proceden
  ahora de una paleta clara/oscura común. La lista de hallazgos codificada por color
  además ya no coloca rayas de cebra bajo sus colores.

- **Los datos de profesión con „als“ se censuraban erróneamente como nombre.** Una frase
  como „Als Koch ist er seit vier Jahren bei uns tätig.“ perdía la profesión,
  no solo un nombre — „als“ introduce una indicación de rol igual que „der“
  o „die“. Los apellidos reales en el mismo lugar (p. ej. con un tratamiento
  delante) permanecen intactos.

- **Un encabezado de tabla podía arrastrar un número de posición hacia un importe monetario**
  (solo con la opción „Eliminar también importes monetarios“ activada). Si una
  línea terminaba en una moneda („… Einzelpreis EUR“) y la
  siguiente empezaba con un número, de ello resultaba erróneamente un importe a través
  del salto de línea. El separador entre moneda y número permanece
  ahora en la misma línea.

- **Una abreviatura corta en mayúsculas podía engullir toda una parte de la frase,
  o pegarse delante de un nombre correctamente reconocido.** Si en
  una línea había una palabra de dos letras en mayúscula como „DI“, „AG“ o „KG“ —
  abreviaturas cotidianas, no nombres —, toda la línea se buscaba de prueba
  en minúscula, y la abreviatura arrastraba a veces
  palabras vecinas (también verbos) hacia un único supuesto nombre.
  Solo a partir de tres letras, una palabra en mayúscula activa ahora esta
  segunda verificación. Con siglas algo más largas como „CEO“ o „USB“
  quedaba un segundo error: el nombre ya correctamente encontrado („Schneider“)
  se llevaba consigo al resultado la sigla antepuesta como prefijo
  („CEO Schneider“). La sigla queda ahora fuera.

- **Una fecha de nacimiento sin espacio detrás permanecía intacta.** Si tras
  „geb.“ no había ningún espacio antes de la fecha — como es habitual en formularios de
  composición estrecha („geb.14.03.1988“) —, Maskuro no reconocía el campo y dejaba la fecha
  intacta. Formas abreviadas frecuentes como „Geburtsdat.“ o „Geb.-Dat.“
  se reconocen ahora también.

- **Un IBAN con barras como separador permanecía intacto.** Igual que en
  los números de teléfono („0664/1234567“), algunas plantillas escriben también el IBAN
  en bloques con barra („AT48/3200/0000/1234/5864“) en lugar de con
  espacio o guion. Esta notación se reconoce ahora también.

- **Un número de seguridad social austríaco con guion, punto
  o barra permanecía intacto o estaba mal rotulado.** Entre
  los dos bloques numéricos hasta ahora solo estaba previsto un espacio;
  notaciones como „1237-010180“, „1237.010180“ o „1237/010180“
  no se reconocían (o, en el caso de la barra, con el tipo incorrecto).
  El dígito de control sigue confirmando cada hallazgo, independientemente del
  separador.

- **Un nombre tras „c/o“ en una dirección no se
  eliminaba en absoluto.** „c/o Max Mustermann, Hauptstraße 5, 1010 Wien“ censuraba
  la calle y la localidad, pero dejaba el nombre detrás totalmente intacto. El
  nombre se reconoce ahora; „c/o“ mismo permanece visible como indicación
  de dirección.

- **Un número de tarjeta de crédito agrupado con puntos permanecía intacto.**
  Notaciones como „4111.1111.1111.1111“ no se reconocían; los números
  separados con espacio o guion no se veían
  afectados. La suma de control sigue confirmando cada hallazgo.

- **Un número de identificación fiscal agrupado con guiones permanecía
  intacto, y un NIF-IVA austríaco con guion o punto también.**
  Espacio, barra y punto ya estaban previstos en el número fiscal,
  faltaba el guion; en el NIF-IVA („ATU12345678“) faltaban
  el guion y el punto tras el prefijo. El dígito de control del número fiscal
  sigue confirmando cada hallazgo.

- **Un valor de campo entre comillas permanecía intacto, por ejemplo en una
  línea de tipo JSON como „vorname“: „Max“.** El reconocimiento mediante un
  rótulo de campo („Vorname: …“) presuponía hasta ahora que ni el
  rótulo ni el valor mismo estuvieran entre comillas. Estas
  líneas se reconocen ahora también — igual que rótulos de campo con
  un punto de lista YAML antepuesto („- Vorname: Max“) o un
  tabulador en lugar de un espacio antes de los dos puntos.

- **La palabra de encabezado de correo „Sent“ se censuraba ella misma como nombre.**
  En un encabezado como „Sent: Huber“ acertaba hasta ahora tanto „Sent“ como
  el nombre real; palabras de encabezado emparentadas como „Subject“ o
  „Betreff“ siempre habían quedado intactas. „Sent“ permanece ahora
  también intacto.

- Un nombre tras los encabezados „Errors-To:“ o „Resent-From:“ permanecía
  indetectado cuando dicha línea estaba copiada en texto claro (por ejemplo un
  mensaje reenviado o un informe de incidencia) — a diferencia de
  „Reply-To:“ o „Return-Path:“, aquí el nombre se perdía por completo en lugar de
  quedar solo delimitado de forma imprecisa. Ahora se encuentra.
- Un mismo archivo daba a veces un resultado distinto en dos
  limpiezas: si dos reconocimientos coincidían exactamente en el mismo lugar
  con la misma longitud y la misma certeza (p. ej. „Sozialversicherungs-
  nummer 1237/010180“ como AT_SVNR o como número de identificación general), dependía
  del azar cuál ganaba — el valor se eliminaba en ambos casos,
  solo cambiaba el rótulo del marcador de posición. El empate se resuelve
  ahora siempre de la misma manera.
- Una denominación de función directamente antes de un sustantivo (p. ej. „Behandelnder
  Arzt: Dr. …“ o „Zuständiger Sachbearbeiter ist …“) se censuraba a veces
  erróneamente también, como si fuera ella misma un nombre. Los apellidos reales
  al lado permanecen intactos.
- Un apellido real que casualmente tiene el mismo aspecto que un adjetivo
  (p. ej. „Schöne“, „Lange“, „Junge“) y está inmediatamente antes de otro
  sustantivo (por ejemplo „Kontaktperson: Schöne Assistentin“), permanecía desde la
  última corrección sin censurar en el texto — una fuga de datos. Solo una
  lista estrechamente delimitada de denominaciones de función reales (p. ej. „Behandelnder“,
  „Zuständiger“) se trata ahora como no-nombre en esta forma.
- Un apellido aislado al final de un hallazgo de nombre de varias líneas,
  que casualmente tiene el mismo aspecto que un adjetivo (p. ej. „Schwarz“,
  „Kurz“, „Alt“, „Frisch“, „Gut“, „Reich“), permanecía sin reconocer ante unos
  dos puntos inmediatamente siguientes — la limpieza lo confundía
  con un rótulo de campo como „Telefon:“. Una lista cerrada de
  apellidos ambiguos conocidos lo protege ahora.
- Un apellido aislado que casualmente es una palabra alemana común
  („Gross“/„Grosse“, „Gut“, „Kurz“, „Lang“/„Lange“) se perdía
  hasta ahora **por completo** — incluso en frases simples como „Herr
  Gross unterschrieb den Vertrag.“ La razón estaba en la lista de palabras
  vacías propia de spaCy, que contiene estas palabras; una lista cerrada de
  apellidos conocidos las protege ahora del descarte.
- En contratos de trabajo, préstamo, fianza, fideicomiso e insolvencia,
  así como en tutela/curatela y encargos de peritaje, se pasaba por alto un
  apellido que es al mismo tiempo una palabra común (p. ej. „Bauer“) tras
  rótulos como „Auftraggeber:“, „Auftragnehmer:“, „Arbeitnehmer:“,
  „Versicherter:“, „Darlehensgeber:“, „Darlehensnehmer:“, „Bürge:“,
  „Sicherungsgeber:“, „Treuhänder:“, „Treugeber:“, „Insolvenzverwalter:“,
  „Gutachter:“, „Sachverständiger:“, „Vormund:“ o „Pfleger:“
  — en parte solo se reconocía el nombre de pila, en parte se perdía el nombre completo.
- En el aviso legal se pasaba por alto un apellido que es al mismo tiempo una
  palabra común (p. ej. „Bauer“) tras los rótulos „Geschäftsführer:“,
  „Geschäftsführerin:“, „Vertretungsberechtigt:“, „Inhaber:“ o
  „Inhaberin:“ — con „Geschäftsführer:“/„Inhaber:“ se perdía el nombre
  completo, con „Vertretungsberechtigt:“ solo se reconocía el nombre de pila.
- Un bloque de contacto cuyo rótulo estaba solo en su línea y llevaba la
  forma de género neutra con dos puntos („Ansprechpartner:in“, con el nombre
  debajo) se pasaba por alto **por completo** — los dos puntos se leían como
  separador de campo, „in“ como valor de campo (descartado), y el
  nombre real en la línea siguiente nunca volvía a entrar en juego. La forma con asterisco
  („Ansprechpartner*in“) no se veía afectada.
- Si el nombre y el rótulo con la misma forma de género con dos puntos estaban en
  **una** línea („Ansprechpartner:in Anna Berger“), el marcador de posición arrastraba
  la palabra „in“ consigo a la sustitución, en lugar de eliminar solo el nombre —
  el nombre mismo seguía reconociéndose por completo.
- Un nombre en una columna de tabla bajo un encabezado de columna de persona (p. ej.
  „Name Vorname Geburtsdatum“ sobre „Bauer Anna 03.05.1985“, como en una
  nómina) se pasaba por alto por completo en cuanto entre las
  columnas había solo un único espacio y ninguna línea empezaba con un
  número de apartado — exactamente la forma en la que un
  extracto de texto PDF real entrega tales líneas.
- En un chat o acta de sesión con nombres de interviniente antes de los
  dos puntos (p. ej. „Bauer 🙂: Ich stimme dem Vorschlag zu.“), el
  nombre permanecía totalmente sin reconocer en cuanto había un signo de reacción entre el nombre
  y los dos puntos y el apellido era al mismo tiempo una palabra común
  („Bauer“, „Koch“, „Schneider“ y similares) — un acta completa podía
  quedar así sin un solo interviniente reconocido.
- La misma laguna de línea de interviniente existía también con otros signos intermedios
  antes de los dos puntos: un complemento de estado entre paréntesis („Bauer (Vorsitz):
  …“, „Bauer (abwesend): …“), una hora entre corchetes
  („Bauer [14:32]: …“) y un signo de nota al pie directamente junto al nombre
  („Bauer*: …“). También aquí el interviniente permanecía totalmente sin reconocer,
  en cuanto el apellido era al mismo tiempo una palabra común.
- Si una persona ya reconocida figuraba en un fragmento de acta o
  registro adjunto al mismo mensaje (por ejemplo un ticket de soporte) además
  como nombre de usuario en la forma „vorname.nachname“ — en minúscula,
  sin espacio, unido por un punto —, este
  nombre claro permanecía legible, aunque el mismo nombre ya estaba
  censurado en la carta.
- La misma laguna de nombre de usuario existía también con un guion bajo en lugar de
  un punto („vorname_nachname“) — un formato igualmente común en
  fragmentos de acta y registro.
- Y también en orden inverso el nombre de usuario permanecía legible
  („nachname.vorname“ o „nachname_vorname“) — algunos sistemas anteponen
  el apellido en el nombre de usuario del registro en lugar de ponerlo al final.
- Una fecha de defunción permanecía sin reconocer cuando no había ningún otro dato al lado
  („Herr Bauer ist am 12.03.1985 verstorben“) — para eso hasta ahora no
  existía ningún reconocimiento propio, y la fecha genérica no actúa con este
  umbral estándar.
- Una fecha de defunción permanecía sin reconocer también cuando la frase usaba la forma verbal
  en lugar del participio („Frau Meier verstarb am 12.03.1985“,
  „Er starb am 12.03.1985“) — hasta ahora solo acertaban „ist … verstorben“/„ist … gestorben“.
- Una fecha de boda permanecía sin reconocer, en cualquier forma en que apareciera
  („Eheschließung am 12.03.2010“, „Hochzeitsdatum: 12.03.2010“, „Herr und
  Frau Bauer heirateten am 12.03.2010“) — para eso hasta ahora no
  existía ningún reconocimiento propio, y la fecha genérica no actúa con este
  umbral estándar.

- **En el editor de corrección, un segundo marco sobre un marcador de posición recién
  colocado podía dejar un resto de carácter en rojo**, por ejemplo
  „[G“ en lugar de „[BEG1]“ — sin ninguna advertencia, porque el resto ya no pertenecía
  al dato confidencial (ese ya se había eliminado en el primer paso), sino
  solo al propio marcador de posición. La causa estaba en la coloración: un
  marcador de posición recién colocado se escribía carácter por carácter en el archivo,
  incluso con un color único predeterminado — un marco posterior sobre el mismo lugar
  ya no encontraba con ello un texto coherente al que
  pudiera referirse. Ahora un marcador de posición de un solo color figura como una
  pieza única en el flujo, como siempre hacía la limpieza automática; solo
  un degradado real o texto arcoíris sigue necesitando caracteres
  individuales. La comprobación integrada reconoce además ahora un resto de este tipo
  también cuando la cadena exacta del marcador de posición ya
  no aparece.
- Una lista de nombres numerada con numeración jerárquica escalonada
  („1.1 Max Mustermann“, „1.2 Huber Franz“ …) perdía todos los nombres por
  el mismo freno que en realidad solo debería proteger enumeraciones reales y
  listas de posiciones — sin encabezado de columna sobre la lista no había
  ningún testigo al que un nombre pudiera aferrarse para salvarse.
- Un nombre en una línea de inicio de sesión en inglés de un registro de sistema
  („Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2“)
  no se reconocía — el modelo de lenguaje alemán solo lo encontraba cuando delante
  estaba „invalid user“, si no, permanecía intacto. Estos fragmentos de registro
  a menudo se adjuntan sin cambios a un informe de incidencia. Los nombres tras „for“
  ante una dirección IP se reconocen ahora de forma fiable.
- El nombre del deudor en la referencia de mandato SEPA de un
  extracto de cuenta o diario de contabilización (p. ej. „MREF+Mustermann Klaus+SVWZ+
  Miete August“) permanecía al descubierto — sin espacio, sin estructura de frase, solo
  campos en mayúscula separados por „+“, y en el orden allí habitual
  „apellido nombre“, el reconocimiento tampoco lo encontraba por
  casualidad. Se reconoce ahora.
- La calle junto con el número en la primera línea de una tabla de direcciones
  (p. ej. „Nachname | Vorname | Straße | PLZ | Ort“) permanecía al descubierto — el
  modelo de lenguaje adivinaba allí un lugar incorrecto, pero más largo, a través de
  varias columnas, que desplazaba el hallazgo de dirección correcto y más corto.
  Se reconoce ahora.
- La misma fuga se producía con un tabulador en lugar de „|“ o „;“ como
  separador de columna — allí la dirección incluso desaparecía por completo en lugar de
  solo perderse en parte. Se reconoce ahora.
- Una calle con número permanecía al descubierto cuando directamente después, sin
  espacio, seguía un código postal con coma (p. ej. „Bahnhofstrasse
  12,80331 München“, como en una columna de tabla separada por comas) — la
  coma parecía un decimal de una cantidad, y el patrón por ello ni siquiera
  consideraba la calle como dirección. Se reconoce ahora.
- Una calle con número permanecía al descubierto cuando directamente después, sin coma,
  seguía el prefijo de localidad „St.“ (Sankt) (p. ej. „Hauptstraße 5 St.
  Pölten“, un membrete sin código postal antepuesto) — „St.“ parecía
  la unidad de cantidad de piezas, y el patrón por ello ni siquiera
  consideraba la calle como dirección. Se reconoce ahora.
- Un complemento de puerta/escalera tras un número de casa (p. ej. „Lerchenfelder
  Gürtel 43/12“) permanecía visiblemente al descubierto cuando directamente después había una sola
  letra que casualmente coincidía con una unidad de medida (p. ej.
  „h“ de hora) — la dirección se limpiaba entonces solo hasta el número de casa sin
  su complemento, en lugar de acertar por completo o nada.
- Una línea de asunto con un apellido homónimo de profesión antes del
  nombre de pila („Betreff: Bauer Anna“, „Betreff: Bauer, Anna“) permanecía hasta ahora
  totalmente sin reconocer — incluso en medio del documento con una frase
  completa precedente. Se reconoce ahora.
- Un número fiscal alemán con espacio, punto o guion
  entre los bloques (p. ej. „Steuernummer: 30 815 08153“ o
  „30.815.08153“) permanecía hasta ahora sin reconocer — solo se encontraba la notación
  con barra. Se reconoce ahora.
- Un nombre tras un rótulo de campo médico („Patient:“,
  „Hausarzt:“, „Behandelnder Arzt:“, „Überweisender Arzt:“ y sus
  formas femeninas) permanecía hasta ahora sin reconocer cuando el apellido era al mismo tiempo
  una palabra alemana común (p. ej. „Patient: Bauer Thomas“).
  Se reconoce ahora.
- Un nombre tras el rótulo de campo „Zahnarzt“ en línea propia (p. ej.
  „Zahnarzt“, debajo „Huber Franz“) permanecía hasta ahora sin reconocer — ni el nombre
  ni el apellido. „Zahnärztin“ y la forma simple „Arzt“ no se veían
  afectadas. Se reconoce ahora.
- Un apellido tras „Herr“/„Frau“, al que seguía una fórmula de lenguaje administrativo como
  „zur Kenntnisnahme“, „zur Unterschrift“ o „zur Weiterleitung“,
  se interpretaba hasta ahora de forma demasiado amplia y arrastraba la fórmula al hallazgo de nombre
  — de „Frau Petra Klein zur Vertretung in allen Angelegenheiten“
  se sustituía „Petra Klein zur Vertretung“, y el resto de la frase quedaba
  gramaticalmente mutilado. Los predicados nobiliarios reales como „von der Leyen“
  o „zu Guttenberg“ permanecen intactos.
- La misma sobreextensión por fórmula de lenguaje administrativo se ocultaba también tras el nombre
  en un encabezado de correo „To:“, un código de matriculación (C.1/C.1.1/C.1.2),
  un código de licencia de conducir, un campo de formulario entre corchetes
  („[Vorname]: …“) y una fórmula de despedida sin punto — en todos esos casos
  „zur“/„von“ y similares arrastraban una fórmula siguiente como „zur Unterschrift“ o
  „zur Vertretung“ hacia el hallazgo, en parte incluso la mera
  palabra partícula misma quedaba como resto de nombre en el resultado. También aquí
  los predicados nobiliarios reales se conservan por completo.
- El número de matrícula tras su rótulo no se reconocía hasta ahora en
  absoluto — „Matrikelnummer 7654321“ pasaba por completo desapercibido al
  reconocimiento, ni como número de identificación ni mediante el modelo de lenguaje, porque el
  número solo no tiene forma reconocible.
- Lo mismo valía para el número de participante — „Teilnehmernummer 4471829“ pasaba
  por completo desapercibido, ni como número de identificación ni mediante el modelo de lenguaje.
- En el currículum, el nombre bajo el encabezado de sección „Persönliche
  Daten“ a menudo pasaba total o parcialmente desapercibido al reconocimiento, cuando estaba sin tratamiento
  en la forma „apellido nombre“ directamente debajo.
- Lo mismo valía para el encabezado de sección „Kontaktdaten“ — allí
  el nombre pasaba incluso totalmente desapercibido, no solo en parte.
- En un certificado de empadronamiento o lista de solicitudes con una columna combinada
  „Name, Vorname“ (notación del registro civil, valor p. ej.
  „Mustermann, Max“ en una celda), el nombre pasaba por completo desapercibido al
  reconocimiento cuando seguía otra columna como la fecha de nacimiento.
- Una fecha de nacimiento en la forma habitual en el documento de identidad y el certificado de
  empadronamiento „Geburtsdatum/-ort: 22.07.1978 / Rostock“ no se
  reconocía — solo acertaba la forma con coma „Geburtsdatum, Geburtsort: …“.
- „Bürgerservice“ y „Bürgerbüro“ se censuraban ocasionalmente erróneamente como lugar,
  especialmente tras una raya como separador de enumeración
  (por ejemplo „Wenden Sie sich an das Bürgerservice – Bürgerbüro …“).
- Un número de teléfono rotulado que un salto de línea partía por la mitad
  (por ejemplo desde una columna estrecha de membrete o una extracción de texto PDF
  según el ancho de columna: „Telefon: 0176 12\n34567“) se censuraba en parte solo
  a la mitad — el resto tras el salto de línea permanecía legible.
- Un número de identificación rotulado (número de cliente, de socio, de contrato y
  similares) que un salto de línea partía por la mitad (por ejemplo „Kundennummer:
  K903\n944“ desde una columna estrecha) se censuraba solo a la mitad —
  el resto tras el salto de línea permanecía legible.
- Un nombre con título académico ante una denominación de profesión tras coma
  (por ejemplo „Dipl.-Ing. Sabine Roth, Projektleiterin“) permanecía totalmente
  desprotegido — la línea parecía un encabezado de columna tabular
  y se descartaba erróneamente como contenido objetivo.
- El título „Dr.-Ing.“ (un grado de ingeniería alemán frecuente) ante un
  nombre no se incluía en el valor de persona enmascarado y permanecía
  legible — la misma trampa del guion que en „Dipl.-Ing.“.
- Los títulos „Dipl.-Kfm.“, „Dipl.-Kffr.“ y „Dipl.-Psych.“ (licenciado en
  administración de empresas/economista/psicólogo) ante un nombre no se incluían en el
  valor de persona enmascarado y permanecían legibles — la misma
  trampa del guion que en „Dipl.-Ing.“ y „Dr.-Ing.“.
- Una dirección MAC en la notación Cisco con puntos en lugar de dos puntos
  (p. ej. „aabb.ccdd.eeff“, tal como la emiten los registros de switch y los tickets de soporte)
  no se reconocía en absoluto y permanecía legible.
- Un apellido tras „Familie“ (p. ej. „Die Familie Gruber unterschreibt
  den Vertrag“) permanecía, según la construcción de la frase, sin reconocer y por tanto legible —
  también con predicado nobiliario delante („Familie von der Leyen“).

- En una dirección croata sin signo de puntuación separador entre
  código postal+localidad y calle+número (p. ej. „10000 Zagreb Ulica Ivana
  Lučića 5“) el número de la calle permanecía sin limpiar.

- En un dato de contacto lituano con el rótulo „Kontaktinis
  asmuo“ (p. ej. „Kontaktinis asmuo: Vilkas Jonas“) el apellido
  no se reconocía cuando era al mismo tiempo un sustantivo común (Vilkas =
  „lobo“, Vanagas = „azor“).

- Un país de nacimiento o de residencia sin más rótulo en un
  campo de formulario danés (p. ej. „Fødeland: Tyskland“ o „Bopæl:
  Tyskland“) no se reconocía.

- Un país de nacimiento o de residencia sin más rótulo en un
  campo de formulario rumano (p. ej. „Țara: Germania“ o „Țara de
  reședință: Franța“) no se reconocía.

- Un nombre de empresa bajo el rótulo de campo lituano „Darbdavys:“
  o „Įmonės pavadinimas:“ (empleador/empresa) no se reconocía.

- Un nombre de empresa bajo el rótulo de campo ruso
  „Работодатель:“ o „Наименование организации:“
  (empleador/empresa) no se reconocía.

- Una fecha escrita con nombre de mes en rumano (p. ej.
  „31 decembrie 2024“) no se reconocía.

- Un apellido de soltera húngaro tras la abreviatura „szül.“ (p. ej. „Nagy
  Éva (szül. Kovács)“) no se reconocía y permanecía visiblemente legible.

- Una página de perfil HTML guardada (o un correo con una página web adjunta)
  podía dejar el nombre civil sin limpiar, cuando estaba solo
  en los campos de perfil Open Graph `profile:first_name`/`profile:last_name`/
  `profile:username` — estos llevan el nombre desglosado en lugar de
  descriptivo como `og:title` y ahora también se limpian.

- Una notificación de no entrega (bounce/NDR) a menudo llevaba los encabezados del
  correo originalmente no entregado (remitente, destinatario, asunto) en una
  tercera parte adjunta propia — esta permanecía totalmente intacta en la versión
  limpiada. Esa parte se limpia ahora igual que el resto del
  informe de entrega.

## 0.10.42-alpha.20260827 – 27 de agosto de 2026

### Novedades

- **Los perfiles de detección con nombre hacen que distintos casos de
  trabajo sean accesibles con un solo gesto.** En *Ajustes → Detección →
  Qué se elimina* se puede guardar la selección actual de categorías y
  tipos y volver a aplicarla al instante mediante un campo de selección. El
  perfil fijo *Estándar* corresponde al estado de entrega anterior y no se
  puede eliminar. Un perfil solo modifica qué se elimina; el idioma, el
  tipo de salida, la profundidad de detección, así como los términos y
  patrones de búsqueda propios, permanecen intactos.

- **El tipo de resultado se elige ahora directamente antes de limpiar.** Un
  campo de selección común en la ventana principal determina para todo el
  lote si Maskuro inserta marcadores de posición legibles, tacha o elimina
  sin sustituto. Los dos campos separados para PDF y Office en la ventana
  de ajustes han desaparecido; con ello la decisión importante es visible y
  ya no puede divergir sin querer en lotes mixtos. El recorrido guiado
  explica la nueva selección antes de la primera limpieza.

- **Los temas y las marcas de agua marcan claramente los PDF terminados si
  así se desea.** Doce estilos completos armonizan los textos sustitutos y
  las superficies de tachado; nuevos son Pride, así como primavera, verano,
  otoño e invierno. *Expediente secreto* incorpora directamente un `TOP
  SECRET` diagonal. Independientemente de ello, se puede elegir un texto de
  marcado libre o una imagen, icono o SVG propio con color y opacidad. Los
  gráficos importados se incrustan sin sus metadatos y siguen disponibles
  si el archivo de origen se traslada. Al corregir, Maskuro sustituye su
  marca de agua anterior en lugar de superponerla varias veces. Las marcas
  de agua de texto se dibujan como última capa de PDF con un contorno claro,
  para que sigan siendo visibles también sobre imágenes oscuras y texto
  denso. El editor de correcciones ignora por completo la marca de agua de
  Maskuro y ya no la ofrece como candidata a tachado.

- **Los propios temas de salida se pueden guardar y compartir.** La mezcla
  actual de texto sustituto, tachado y marca de agua recibe un nombre,
  permanece en los ajustes y se puede exportar o importar como JSON libre
  de texto en claro. La vista previa de impresión en blanco y negro avisa
  de contrastes débiles; el confeti opcional de éxito permanece
  exclusivamente en la interfaz.

- **Una última prueba de exportación y un requisito de verificación
  explicativo cierran la ronda de presentación.** Antes de guardar
  definitivamente, Maskuro compara de nuevo cada punto de PDF conocido con
  valor exacto en la capa de texto y en los píxeles renderizados; los
  avisos indican exclusivamente página y coordenadas. En el editor, *¿Por
  qué está esto cubierto?* muestra categoría, vía de detección y margen de
  seguridad, nunca el texto en claro eliminado, y nunca en el documento
  final.

- **Las barras de tachado ahora pueden ser bonitas.** En *Ajustes →
  Apariencia* hay disponibles colores predefinidos, selectores de color
  libres, degradados, arcoíris, rayas, puntos, flores, estrellas,
  corazones, huellas, nubes, rayos, granos de café, patos, soles, hojas,
  copos de nieve, patrones de papel, rotulador, cinta adhesiva y patrones
  aleatorios reproducibles, con vista previa inmediata. Los textos
  sustitutos reciben opcionalmente un color, un degradado, un arcoíris, una
  píldora o una etiqueta. Los colores por categoría distinguen nombres,
  direcciones, contactos y datos médicos. El PDF adopta el diseño completo;
  Word, PowerPoint, OpenDocument y HTML usan el color base opaco elegido.
  La protección no cambia con ello: Maskuro elimina primero el contenido
  confidencial y dibuja el color o el patrón solo después sobre el lugar
  vacío.

- **Maskuro vuelve a estar disponible para Linux, como AppImage, DEB, RPM y
  archivo portable.** DEB y RPM inscriben en el sistema la entrada de
  programa, las asociaciones de archivo, el comando de terminal y el
  icono; el AppImage funciona sin instalación. Las actualizaciones se
  mantienen, en una instalación DEB o RPM existente, en el mismo formato de
  paquete, y de lo contrario prefieren el AppImage.

- **La verificación visual ya no presenta el texto de PDF normal por
  segunda vez como hallazgo nuevo.** El vistazo final de OCR y la
  reconstrucción segura de las páginas visibles siguen totalmente activos;
  pero por defecto solo cuentan como nueva fuente de hallazgo las zonas que
  la verificación de texto de página y de imagen individual aún no han
  leído. Con ello, las líneas de producto no se convierten en nombres o
  empresas nuevos solo por una segunda lectura de OCR divergente. Quien
  siga queriendo dos juicios independientes sobre todo el texto visible
  activa en los ajustes *Volver a verificar como dato toda la página de PDF
  visible*.

- **Los PDF se pueden ver de forma continua, hoja por hoja o a doble
  página.** Tres iconos de vista compactos se sitúan abajo, justo junto a
  «Ancho» y «Página». Continua se desplaza por el borde de la hoja hacia la
  siguiente página; Página única mantiene la rueda del ratón en la hoja
  actual; Doble página muestra un pliego, hace editable la hoja pulsada y
  mueve Adelante/Atrás un pliego entero. Las miniaturas de página y la lupa
  comparativa se abren además en una columna base izquierda notablemente
  más estrecha, dejando más espacio a la página de trabajo.

- **Ahora se ve lo que ha hecho la etapa de IA.** Después de cada ejecución
  aparece bajo «Detalles», por archivo, una línea al respecto: «Etapa de
  IA: 12 casos límite verificados, 3 descartados»; y si no encontró nada
  que cambiar, también se indica. Hasta ahora la etapa más costosa
  permanecía completamente muda: no era posible reconocer desde fuera si
  siquiera se había consultado.

  Quien necesite más detalle, activa en «Ajustes → IA» *Registrar cada
  consulta de IA en el protocolo*. Entonces el archivo de protocolo
  registra, por consulta, tamaño, duración y número de hallazgos, además
  del tiempo de espera causado por un límite de cantidad de la contraparte.
  El botón «Mostrar archivo de protocolo» de al lado abre la carpeta; se
  encuentra en el directorio de datos de la aplicación, que en Windows está
  oculto y que nadie encuentra por sí mismo. En el archivo solo figuran
  tamaños, nunca texto de sus documentos.

- **Maskuro reconoce cuando su servicio de IA limita el número de
  solicitudes.** Los servicios alojados a menudo solo permiten unas pocas
  solicitudes por minuto; cuatro no es raro. Las que sobran no se
  rechazan, sino que deben esperar, y de dos segundos por respuesta se
  pasa a cuarenta. Hasta ahora eso parecía que el modelo era lento. Ahora
  Maskuro lee el límite de la respuesta del servicio, ya no envía más
  consultas simultáneas de las que se aceptan, indica el límite bajo
  «Comprobar conexión» y lo incluye en la estimación de duración.

- **La vista previa de página usa su Word, Excel y PowerPoint, y con ello es
  unas seis veces más rápida.** Hasta ahora necesitaba LibreOffice, que
  está instalado en muy pocos equipos de oficina; quien no lo tenía veía un
  botón que exigía una instalación de terceros. Ahora rige: si Microsoft
  Office está instalado, se usa automáticamente, sin configuración, sin
  descarga, sin que usted tenga que marcar nada. LibreOffice sigue siendo
  la segunda vía, e incluso la primera para archivos OpenDocument; si uno
  falla, se prueba el otro.

  La diferencia se nota sobre todo al trabajar: tras cada sustitución la
  página se recompone, y eso cuesta con Office alrededor de medio segundo
  en lugar de tres. La primera visualización de un documento sigue
  tardando unos segundos; después sigue sus acciones sin tiempo de espera.

  Su propio Word abierto no se toca en el proceso: Maskuro inicia una
  sesión propia e invisible, abre el archivo solo en modo lectura,
  desactiva las macros y cierra todo de nuevo en cuanto se cierra la
  ventana de corrección. Los archivos protegidos por contraseña se
  rechazan, en lugar de quedar colgados en un diálogo invisible.

- **La configuración inicial pregunta ahora también por rostros, códigos y
  firmas, y carga todo lo que falte de una sola vez.** Junto a la detección
  ampliada, en la primera página figuran los tres interruptores de imagen:
  hacer irreconocibles las zonas de rostro, hacer irreconocibles códigos de
  barras y QR, tachar firmas manuscritas en páginas de PDF. El límite a PDF
  figura visiblemente junto a la marca; los archivos de Office no se
  examinan automáticamente en busca de firmas. Bajo las marcas se indica
  cuántos megabytes cuesta el clic en «Siguiente». La carga se realiza
  después en **una** ventana con **una** barra de progreso conjunta,
  en lugar de en varios diálogos sucesivos; una cancelación termina todo el
  proceso y no deja nada a medias. Quien no quiera nada de esto, quita las
  marcas; entonces tampoco se carga nada.

- **La vista previa se puede filtrar según necesidad de verificación y
  plegar por tipo.** Sobre la lista hay un control deslizante *Ocultar bien
  fundamentados*: cuanto más a la derecha esté, más oculta desde el verde
  hacia el rojo; en el extremo derecho solo queda lo que el programa ha
  supuesto por sí solo. Un clic sobre el encabezado de un tipo lo pliega.
  Ambas cosas son una ayuda de lectura, no una selección: lo que se oculta
  o se pliega sigue marcado y se sustituye; cuántos valores son en ese
  momento se indica bajo el control. En listas cortas el control no
  aparece. El cambio a dos columnas mantiene ahora además los interruptores
  *nunca más*.

- **La lista de imágenes puede abrirse sola antes de cada ejecución.** Quien
  quiera decidir sobre cada imagen individualmente, marca en «Imágenes» la
  nueva casilla *Definir individualmente antes de cada ejecución*. La
  lista con vista previa aparece entonces sola al limpiar, en lugar de que
  usted tenga que pulsar «Definir individualmente…» cada vez; si la
  cancela, tampoco se limpia. Si ninguno de los archivos elegidos contiene
  una imagen, no aparece nada. Por defecto la casilla está desactivada.

- **Maskuro encuentra firmas manuscritas en páginas de PDF y las elimina de
  los píxeles.** Hasta ahora, la firma permanecía visible bajo un documento
  limpiado: el reconocimiento de texto lee letra impresa, y lo que no lee
  no se sustituye. La búsqueda es un interruptor propio y necesita un
  modelo de reconocimiento que se recarga una única vez.

  Encuentra, según lo medido, unas 84 de 100 firmas y las cubre en
  aproximadamente cuatro quintas partes. Es una ayuda, no una garantía:
  tras cada ejecución, el informe indica cuántas se encontraron, también
  cuando no había ninguna, porque eso puede significar que no había
  ninguna o que se pasó por alto una. En 72 páginas comerciales reales sin
  firma, no inventó ninguna.

  Una firma **dibujada** se encuentra, pero no se elimina: consiste en
  líneas, no en píxeles, y una barra encima sería solo una cobertura bajo
  la cual las líneas permanecerían. Estos lugares se cuentan y se indican,
  para que se puedan tachar uno mismo en la ventana de corrección.

  Los archivos de Word, Excel, PowerPoint y OpenDocument no se examinan
  automáticamente en busca de firmas. La interfaz, la configuración
  inicial, la descarga del modelo, la línea de comandos y el manual
  mencionan ahora este límite de forma explícita.

- **El recorrido guiado ahora también pasa por la vista previa, la ventana
  en la que usted decide.** Con el documento de ejercicio se abre por sí
  sola, incluso si por lo demás ha desactivado la vista previa (su ajuste
  se mantiene tal cual está). Se explica qué significan los colores, por
  qué en cada línea solo hay una pregunta —¿hay siquiera una persona
  aquí?— y para qué sirve «nunca más». En los colores, el foco recae sobre
  una línea bien fundamentada, normalmente el IBAN, el ejemplo verde que
  menciona la frase; después sobre la peor fundamentada, y allí puede usted
  hacer clic en medio de la explicación: quita la marca, el valor permanece
  en el documento. En una lista larga, la ventana de la guía se abre más
  grande, para que la explicación no quede sobre las líneas. Si la ventana
  se abre una segunda vez, el recorrido también explica por qué: la página
  terminada se vuelve a leer como imagen, y en ese proceso surgen
  fragmentos que parecen un nombre.

- **El editor se abre a gran tamaño la primera vez.** Original, resultado,
  barra de herramientas y lista de hallazgos están uno junto a otro y
  tenían muy poco espacio en el tamaño base anterior. Quien reduce la
  ventana recupera su tamaño la próxima vez; a nadie se le impone nada.

- **Un doble clic sobre un marcador de posición lo recupera**: en Word,
  Excel, PowerPoint, OpenDocument, texto, correo electrónico y HTML. Y
  quien arrastra sobre varios marcadores de posición y elige «Recuperar
  selección» recupera de una vez todos los que hay dentro. Ya no hace falta
  acertar exactamente el corchete. Los marcadores de posición que, al
  anonimizar, representan varios valores distintos quedan excluidos de
  esto; se cuentan y se indican, no se adivinan.

- **El manual tiene un capítulo «Vista previa antes de sustituir».** La
  ventana está activada por defecto y es la única en la que usted decide;
  en el manual hasta ahora solo figuraba en una frase secundaria. Ahora se
  explica qué significa una marca (se aplica a **cada** hallazgo, no solo
  al indicado), por qué en cada línea solo hay una pregunta que responder,
  qué efecto duradero tiene «nunca más» y por qué la ventana puede abrirse
  una segunda vez en un PDF. En los dieciocho idiomas, y en la lista de
  ajustes el interruptor también figura ahora.

### Cambios

- **El panel «Valores sustituidos» tiene un control deslizante sobre los
  colores, y el modo de aprendizaje ya no está ahí.** Con más de ocho
  valores, sobre la lista hay el mismo control deslizante que en la
  ventana de vista previa: *Ocultar bien fundamentados* reduce la vista a
  lo que realmente hay que revisar. Esto no cambia nada en el documento, y
  cuántas líneas de cuántas se ven figura debajo; el campo de búsqueda y el
  control cuentan en conjunto. La casilla *Modo de aprendizaje* ha
  desaparecido del panel; sigue estando en el menú *Herramientas* y en la
  barra de herramientas.

- **El panel «Valores sustituidos» muestra ahora los mismos colores que el
  documento.** Cada línea está resaltada igual que el lugar en el
  documento y que el valor en la vista previa: rojo significa «adivinado
  por sí solo, aquí conviene mirar dos veces primero», verde «reconocido
  por un patrón con nombre». Dentro de cada tipo, lo más inseguro figura
  arriba; así que usted trabaja la lista de arriba abajo y ve primero lo
  más importante. Hasta ahora todo aparecía con el mismo brillo y
  ordenado alfabéticamente.

- **El modo de aprendizaje viene desactivado de fábrica.** Tras una
  corrección en la ventana de corrección, el programa preguntaba hasta
  ahora por sí solo si de ahí debía surgir una regla propia. Esta pregunta
  llega en medio del trabajo; quien no la pidió la percibe como una
  interrupción. Quien quiera las reglas activa el botón *Modo de
  aprendizaje* en la barra de herramientas; la elección rige entonces de
  forma permanente, en ambos sentidos.

### Solucionado

- **Los archivos de reglas exportados se marcan ahora explícitamente como
  dignos de protección.** Los términos y excepciones propios pueden estar
  en texto claro en ellos; además, el archivo puede contener la sal de
  hash con la que se pueden confirmar valores presuntos. Por eso, la
  exportación exitosa muestra un aviso de advertencia y pide proteger el
  archivo y entregarlo solo conscientemente a destinatarios autorizados.

- **La última verificación de seguridad ya no retiene archivos de oficina
  limpiados por causa de sus propios marcadores de posición.** Una sigla de
  tipo como «SVNR» también aparece en `[SVNR1]`; hasta ahora se consideraba
  un supuesto resto de texto en claro y el archivo terminado se descartaba.
  Al mismo tiempo, ahora se rastrean también los números de teléfono e IBAN
  allí donde Office guarda el mismo dato sin espacios visibles en una
  referencia o en un archivo incrustado.

- **Word, Excel, PowerPoint y OpenDocument ya no dejan ninguna copia de
  campo descubierta tardíamente.** Cuando un valor se reconoce por primera
  vez en un almacén secundario o en un archivo de oficina incrustado, un
  seguimiento estricto limpia también las copias visibles y ocultas leídas
  previamente. Los marcadores de posición de referencia ya generados no se
  vuelven a sustituir en el proceso.

- **Al recuperar individualmente una lista desplegable de Word, ya no viene
  arrastrada sin preguntar una selección vecina.** El párrafo original
  completo solo se adopta cuando también sus atributos ya no contienen
  marcadores de posición abiertos.

- **Los escaneos difíciles de leer pierden menos datos relacionados entre
  sí.** Una lectura alternativa de OCR con tratamiento y nombre de dos
  partes se conserva; el fragmento de calle, el número y el código
  postal-localidad protegen juntos toda la línea de dirección, incluso si
  se descompone en bloques de OCR vecinos. Los campos de factura y de
  artículo, así como las líneas de evento contiguas, no se ven arrastrados
  en el proceso. Una fecha válida descompuesta tras «nacido» en varias
  palabras de OCR y signos de puntuación también se vuelve totalmente
  irreconocible.

- **El confeti de éxito ahora es visible al abrir automáticamente el
  editor.** Los fragmentos salen disparados directamente del botón
  *Limpiar*, en lugar de llover desde el borde superior de la ventana. El
  editor solo espera a la primera ráfaga, de 850 milisegundos, y se abre
  automáticamente después; sin el confeti activado sigue sin haber
  retraso.

- **El contador de páginas y la barra de zoom ya no saltan de un lado a
  otro al pasar por encima de los iconos de vista.** Qt redistribuía el
  espacio libre de la línea de estado en cuanto aparecía allí el aviso de
  un símbolo. Ambos grupos de control mantienen ahora su anchura natural y
  posición fija al pasar el cursor por encima.

- **La medición de velocidad de un servidor de IA conectado siempre
  fallaba**, en todos los servidores, desde que existe la IA propia.
  Consultaba con un límite de respuesta estrecho e intentaba después leer
  la respuesta así truncada; eso tenía que fallar, y se guardaba «no
  medido». Las consecuencias se veían por todas partes: la estimación de
  duración calculaba su servidor con la velocidad del modelo incluido en
  un equipo de oficina, y en los ajustes figuraba de forma permanente que
  la velocidad aún no se había medido. Ahora se mide según la cantidad que
  ha generado el servidor, y no según el contenido de su respuesta.

- **«Detección máxima (IA): lenta» figuraba ahí incluso cuando no era
  cierto.** El rótulo y el aviso describían el modelo incluido en un
  equipo de oficina: «un modelo de lenguaje en este equipo», «hasta una
  hora en documentos grandes». Quien tenía conectado un servidor de IA
  propio leía ahí dos cosas falsas: el cálculo no se hace en su equipo, y
  la respuesta llega en segundos en lugar de horas. Ambas cosas proceden
  ahora de la medición. Si no hay ninguna disponible, la aplicación ya no
  afirma nada, sino que indica que aún no se ha medido.

- **Recuperar ahora también actúa sobre una selección arrastrada.** Quien
  arrastraba sobre varios marcadores de posición y quería pulsar
  *Recuperar selección* encontraba el botón en gris: solo se activaba si
  la marcación era **exactamente** un marcador de posición, cosa que
  arrastrando sobre un párrafo nunca ocurría. El camino detrás de ello ya
  existía, solo que nadie llegaba a él. Ahora basta con marcar la zona;
  todos los marcadores de posición contenidos en ella se recuperan de una
  vez.

- **Recuperar bloqueaba el programa si la lupa comparativa estaba
  abierta.** La lupa recuerda el lugar bajo el puntero del ratón, para
  seguirlo en el original. Al recargar tras una recuperación, devolvía ese
  lugar en una forma que la vista de texto no podía interpretar; y como un
  error así en pleno interfaz cierra el programa, la recuperación se había
  convertido en un bloqueo. La lupa está abierta en el estado básico, así
  que afectaba al camino habitual.

- **Tras recuperar, la vista ya no salta al principio del documento.** En
  un escrito largo, tras cada acción desaparecía el lugar en el que se
  estaba trabajando en ese momento. Ahora el párrafo que estaba arriba
  antes permanece arriba.

- **Sin LibreOffice, la vista previa de página indica de dónde viene, en
  lugar de simplemente faltar.** Los dos botones *Vista previa de página*
  y *Tachar como PDF* estaban bloqueados e indicaban en el consejo
  emergente solo que no se había encontrado LibreOffice; no había ninguna
  vía hacia él en ninguna parte de la aplicación. Un clic abre ahora un
  aviso con el camino hacia el LibreOffice gratuito y de código abierto. El
  manual y las preguntas frecuentes estaban equivocados en este punto:
  anunciaban un componente para recargar que la aplicación no ofrece.

- **Antes de la entrega, el archivo terminado se recorre por completo una
  última vez, ahora también en Word, Excel, PowerPoint, LibreOffice,
  correo electrónico, HTML y texto.** Hasta ahora solo el PDF tenía esta
  última mirada. Todas las verificaciones anteriores buscan en un lugar
  que alguien nombró previamente; un almacén en el que nadie pensó,
  por tanto, tampoco lo verifica nadie. Al final, Maskuro busca ahora sin
  distinción todo lo que ha sustituido, en cada parte del paquete. Si algo
  permanece, **no** se genera ningún resultado, y el mensaje indica el
  valor. Un documento que se considera limpiado es peor que ninguno.

- **Los nombres presentes en `<script>` y `<style>` se comunican ahora.**
  Ambos siguen intactos: ahí hay código de programa, y una sustitución en
  medio de un identificador convierte una página web en una página web
  rota. Pero hasta ahora no se avisaba de ello, y ese era el error: una
  regla de estilo `content: "Anna Musterfrau"` está **visible** en pantalla
  para el destinatario, y en el resultado seguía apareciendo mientras el
  programa informaba de la página como limpiada.

- **En los ajustes se pueden volver a cargar y eliminar los modelos
  adicionales.** El botón junto a «Detección ampliada» y «Detección máxima
  (IA)» terminaba, al pulsarlo, en la ventana de informe de errores, en
  lugar de obtener el modelo. La segunda vía —la casilla en la detección,
  que pregunta por sí sola por el modelo— nunca se vio afectada.

- **Los nombres presentes en nombres de hoja y de rango de una tabla se
  comunican ahora.** El nombre de una hoja figura en la pestaña de abajo,
  el nombre de un rango con nombre en el cuadro de nombres y en cada
  fórmula que lo usa. Ninguno de los dos se sustituye, como hasta ahora
  —las fórmulas remiten a través de ellos, y un libro con errores de
  referencia no ayuda a nadie—, pero ahora se indica ahí. Hasta ahora el
  aviso solo aparecía para el nombre de hoja de un libro de Excel: un rango
  con nombre «Bezuege_Brunnthaler» salía sin más, y en una hoja de
  LibreOffice el programa callaba por completo. Una hoja «Notizen Ortner»
  se consideraba así limpiada, y la primera mirada del destinatario caía
  sobre el nombre.

  Solo se comunica lo que realmente lleva a una persona: una palabra que de
  todos modos ya se sustituyó en el mismo libro, o un hallazgo que
  selecciona una de varias palabras. Una palabra suelta como «Zustaendig»
  o «Bezug_Umsatz» ya no dispara ningún aviso; antes lo habría hecho, y un
  aviso que aparece cada dos libros nadie lo lee ya a partir del tercero.

- **«Recuperar original» ahora recupera realmente todo.** En algunos
  documentos faltaban después caracteres sueltos: de «Seestraße 14» salía
  «Seestraße 4», de «An:» un «An», de «nordlicht-planung» un «nordlicht
  planung», y líneas enteras no volvían en absoluto. Precisamente ahí ya no
  se podía seleccionar nada con el ratón ni tachar nada más: el texto
  seguía en el papel, pero el programa ya no lo conocía. Afectaba a
  caracteres estrechos —el uno, los dos puntos, el guion— en documentos que
  componen cada carácter por separado; el documento de ejercicio es uno de
  ellos.

- **Y esos mismos documentos ya no se convierten en imagen al limpiar.**
  Como quedaba un carácter así, la verificación posterior informaba de un
  resto y la página se rasterizaba por precaución. El texto sobre ella era
  después solo una reproducción: ya no se podía buscar, ya no se podía
  marcar, era más grande en el archivo. El documento de ejercicio ahora
  permanece como texto real en ambas páginas.

- **Las marcas de color ya no permanecen sobre el texto recuperado.** Quien
  deshacía una sustitución seguía viendo el rectángulo de color sobre la
  palabra restaurada; afirmaba «aquí se eliminó algo», aunque allí volvía a
  estar el original.

- **Una barra ya no delata cuán larga era la palabra debajo.** Al tachar,
  la barra en líneas cortas cubre ahora **toda** la línea: bloque de
  dirección, datos de cabecera, celda de tabla estrecha. Si la línea
  entera no cabe (la fila de tabla habitual con tres columnas), se
  mantiene el campo; en una línea de texto corrido se mantiene la palabra
  exacta, porque de lo contrario un nombre en medio de la frase ennegrecía
  toda la frase. Y las barras que están una debajo de otra se hacen **de
  igual longitud**: en el bloque de dirección hay un valor en cada línea,
  y tres barras de distinta longitud seguían delatando cuánto medían las
  líneas. Crecen solo hasta donde el papel está libre; ante una columna
  vecina la barra se detiene.

- **«Línea completa» tacha ahora realmente toda la línea.** Hasta ahora la
  barra terminaba en el siguiente hueco mayor, es decir, al final del
  campo. En texto corrido eso no se notaba, ahí el campo es la línea; en
  datos de cabecera y tablas sí: de «Nombre: Anna Musterfrau   
  Departamento: Ventas» salía una barra que terminaba exactamente en la
  última letra del nombre, con lo que su longitud volvía a quedar
  registrada en la hoja. La barra recorre ahora desde la primera hasta la
  última palabra de la línea y arrastra consigo las columnas vecinas.
  Quien solo quiera cubrir el valor elige «Palabras»; el modo automático
  sigue tachando por campo sin cambios.

- **Antes de la entrega, el archivo terminado se recorre una última vez.**
  Todas las verificaciones anteriores buscan en un lugar que alguien
  nombró previamente: texto de página, rectángulo de hallazgo, superficie
  de imagen. Pero un PDF tiene más almacenes de los que una enumeración
  puede abarcar: anotaciones, valores de formulario, marcadores,
  información del documento, adjuntos de archivo, JavaScript. Al final,
  Maskuro busca por eso sin distinción en el archivo escrito todo lo que
  ha sustituido, en todas partes excepto en el texto de página, donde el
  mismo texto también puede aparecer de forma permitida. Si algo permanece
  ahí, **no** se genera ningún resultado, y el mensaje indica el valor. Un
  documento que se considera limpiado es peor que ninguno.

- **Lo que no se pudo verificar ya no cuenta como verificado.** De tres
  formas, hasta ahora un fallo de la verificación posterior parecía un
  resultado limpio. Una página cuya capa de texto no se podía leer se
  consideraba especialmente limpia, ya que ahí no había nada que
  encontrar; ahora se rasteriza. Si una página con un hallazgo restante no
  se podía rasterizar como alternativa, se entregaba en silencio; ahora la
  limpieza prefiere interrumpirse. Y la contraprueba en la ventana de
  corrección informaba, tras un error propio, «nada restante», sin poder
  distinguirse en la ventana de que todo se hubiera eliminado; ahora
  aparece el aviso junto con el botón «Rasterizar página».

- **«Restablecer valores predeterminados» no restablecía casi ningún
  ajuste.** Nueve de veintidós casillas quedaban sin cambios tras la
  acción, entre ellas la vista previa, «Abrir después los archivos
  limpiados», la ventana de corrección, el guardado inmediato y ambas
  casillas de actualización. El archivo guardado sí se había vaciado, pero
  la ventana retenía los valores antiguos y los volvía a escribir en el
  siguiente clic. Ahora vuelve cada casilla, y la marca «modificado»
  desaparece con ella.
- **«Guardar automáticamente informe de verificación por cada limpieza»
  aparecía marcado, pero estaba desactivado.** Tras el restablecimiento la
  casilla seguía marcada mientras el valor estaba borrado; ya no se
  generaba ningún informe, sin que nada lo indicara. Lo mismo ocurría con
  el protocolo de verificación y la propia grabación de pantalla; su
  atajo de teclado ahora también se activa o desactiva correctamente de
  inmediato al restablecer.

- **Las barras de una línea ahora se ven iguales.** Hasta ahora, cada
  hallazgo traía su propia barra, y su altura procedía del tipo de letra de
  la palabra afectada. En una línea con rótulo y valor de distintos
  tamaños había, por tanto, un trazo grueso y otro fino uno junto al otro
  con bordes desalineados, y donde dos hallazgos solo estaban separados por
  un espacio quedaba encima un hueco claro. Las barras de una misma línea
  tienen ahora el mismo borde superior e inferior, y lo que solo separa un
  espacio se convierte en una sola barra. Lo que debe permanecer visible
  entre dos hallazgos —la coma tras el nombre, un rótulo, un importe— sigue
  manteniéndolos separados. Se aplica tanto a páginas compuestas como a
  escaneos.

- **Las pestañas bajo «Acerca de este programa» vuelven a empezar por
  arriba.** Protección de datos, condiciones de licencia y avisos de
  licencia se abrían en medio del texto; quien las leía tenía que
  desplazarse primero hasta arriba del todo para ver la primera línea.

- **El lápiz ya no abre una segunda ventana de editor, sino que trae al
  frente la existente.** Hasta ahora se creaba una nueva con cada clic. La
  ventana no tiene entrada propia en la barra de tareas; quien la
  minimizaba ya no podía llegar a ella y volvía a hacer clic; al restaurar
  la ventana principal, todas las ventanas acumuladas pasaban entonces al
  frente de golpe. Ahora los documentos adicionales aterrizan en la barra
  de pestañas de la ventana abierta, y un documento que ya está ahí no
  recibe una segunda pestaña.

- **«Detección ampliada» ya no lleva la marca «modificado» mientras le
  falta su modelo.** Se entrega activada, pero sin el modelo recargable no
  puede estarlo en absoluto; en los ajustes, la línea figuraba por eso
  como modificada en cada equipo recién configurado, aunque nadie la
  hubiera tocado. Por qué la casilla está desactivada lo dice ahora
  únicamente su rótulo: «Modelo aún no cargado».

- **La franja de introducción explicaba el lienzo de PDF en archivos de
  Office y de texto.** Ahí decía «hacer clic en una palabra la tacha»,
  pero en un archivo de Word un clic no tacha nada, ahí se marca y luego se
  pulsa un botón. Ahora dice lo que rige en la vista correspondiente.
- **La barra de herramientas estaba abarrotada de rótulos en la vista de
  texto.** «Sustituir selección», «Tachar selección», «Recuperar
  selección», «Vista previa de página» y «Tachar como PDF» aparecen ahora
  como icono, igual que sus homólogos en un PDF. Sus nombres permanecen en
  la ayuda breve y en el menú.
- **Ctrl+rueda del ratón en la lupa comparativa no movía su control
  deslizante de zoom.** La letra se hacía más grande, mientras el control
  y el porcentaje de al lado seguían indicando el valor anterior.
- **El instalador de una actualización no pasaba al primer plano**; había
  que hacer clic primero en la barra de tareas (solo Windows).
- **Un año al inicio de línea se consideraba código postal austriaco.** En
  un currículum, de «2020 Estrategias de venta» salía un marcador de
  posición: desaparecía toda la línea. Un número de cuatro cifras entre
  1900 y 2099 necesita ahora una segunda señal de dirección: la calle
  encima, una palabra de campo delante, un código de país o un nombre de
  lugar conocido. Los bloques de dirección lo tienen; las columnas de años,
  no.
- **Un par mes-año se consideraba número de teléfono.** De «Desde 08.2010
  123-Verkauft GmbH» salía un «número de teléfono»: mes, año y las
  primeras cifras del nombre de la empresa a continuación.
- **El informe decía «verificado mediante reconocimiento de texto» y
  callaba lo que este no lee.** Si se conservan imágenes, ahora se indica
  que lo manuscrito en ellas no se encuentra: una firma o un nombre
  anotado a mano permanece. Hasta ahora esta frase solo aparecía en
  páginas escaneadas; un PDF normal con una firma incrustada no recibía ni
  una palabra al respecto.
- **Un marcador de posición sobre fondo de imagen tachado quedaba en el
  borde izquierdo de su barra.** Cuando se encuentra un valor en una
  imagen —por ejemplo, un nombre escrito a máquina junto a una firma
  escaneada—, la zona de imagen debe tacharse en todo su ancho. El
  marcador de posición, más corto, dejaba al lado negro desnudo, lo que
  parecía dos operaciones. Ahora se sitúa centrado sobre la barra.

## 0.10.41-alpha.20260826 – 26 de agosto de 2026

### Nuevo

- **Tras el período de prueba, una ventana recuerda la licencia una vez
  por inicio.** Aparece cinco minutos después de iniciar (no de inmediato,
  para no estorbar a nadie antes del primer paso) y espera mientras se
  ejecuta una limpieza. Desde ahí hay un camino a la compra y otro a
  introducir una clave ya comprada; „Más tarde" la cierra en cuanto
  transcurren los cinco segundos del botón. No se bloquea nada: el nivel
  gratuito sigue funcionando como hasta ahora.

- **La espera antes de una ejecución en el nivel gratuito dura ahora diez
  segundos en vez de treinta.** Debe recordar la licencia, no detener el
  trabajo.

- **Los tres avisos sobre la licencia ahora tienen el mismo aspecto.**
  Espera, recordatorio en los últimos días de prueba y aviso tras el
  período de prueba llevan la misma franja, la misma estructura y los
  mismos botones; el tiempo restante figura en el botón en vez de como
  número grande al lado.

- **La lista de hallazgos en la vista previa vuelve a estar una debajo de
  otra.** A partir de nueve valores era de dos columnas; al recorrerla, la
  mirada salta entre dos carriles, y aquí se decide línea por línea. Quien
  prefiera los dos carriles los vuelve a activar abajo a la izquierda de
  la ventana; la elección queda guardada, y al cambiar, los valores ya
  desmarcados siguen desmarcados.

- **El nivel de IA está abierto a quien conecte su propio servidor de
  IA.** „Ajustes → IA" reúne todo: la conexión, qué puede hacer la IA, qué
  se le encarga hacer, y encima el interruptor del nivel junto con la
  contraverificación, en cuanto hay un servidor configurado. Un modelo de
  lenguaje que calcula en el propio puesto de trabajo sigue reservado:
  necesita varios minutos para diez páginas, y con eso no sirve para el
  día a día.

- **Se puede conectar una IA propia.** En vez del modelo de lenguaje
  incluido, puede responder un modelo más grande en otro equipo, un
  servidor de la organización o una estación de trabajo con tarjeta
  gráfica potente. Se requiere un servicio con interfaz compatible con
  OpenAI (Ollama, LM Studio, llama.cpp-server, vLLM, LocalAI); se
  configura en „Ajustes → IA propia" junto con una comprobación de
  conexión que consulta de verdad al modelo, mide la velocidad y
  determina la forma de respuesta posible. Varios fragmentos de texto se
  procesan entonces en paralelo en vez de uno tras otro.

- **Ahora se puede configurar qué puede hacer la IA y qué se le
  encarga.** Tres interruptores deciden sobre la evaluación de casos
  límite, la búsqueda autónoma y la búsqueda en texto corrido; la
  instrucción al modelo aparece literalmente ahí, se puede ampliar con
  términos propios de la organización y restablecer al valor
  predeterminado con un botón.

- **Si con ello el texto sale de la propia red, se advierte antes de
  cada ejecución.** Maskuro reconoce por la dirección si el servidor de
  IA está en la organización, y nombra a un proveedor conocido por su
  nombre. El aviso se puede desactivar, pero solo con la confirmación
  expresa de estar autorizado para esa transmisión, y solo para
  exactamente esa dirección. Eso no cambia el proceso: la transmisión
  sigue constando en el registro y en el informe de verificación de cada
  archivo. En la línea de comandos no se pregunta, sino que se detiene;
  ahí se necesita `--ki-auswaerts-erlauben`.

- **La vista previa antes de sustituir está activa por defecto en
  instalaciones nuevas y ahora también se aplica a contenidos del
  portapapeles limpiados expresamente, así como a texto e imágenes que se
  pegan en el programa.** En lotes de documentos sigue apareciendo
  exactamente una vista previa por documento con todas las páginas; la
  limpieza inmediata silenciosa de copias cortas deliberadamente no abre
  ninguna ventana.

- **Los hallazgos se pueden activar y desactivar en la vista previa
  sobre toda la línea coloreada.** La casilla ahora es grande y de alto
  contraste; además, un campo de estado muestra „Sustituir" o, tachado,
  „Sustituir", de modo que los valores seleccionados y desmarcados se
  distinguen de inmediato incluso sobre colores de confianza oscuros.

- **También los PDF con contraverificación de seguridad visible abren la
  vista previa solo una vez por documento.** Los términos desmarcados
  permanecen desmarcados para el testigo de página posterior; su
  verificación sigue funcionando, sin interrumpir la misma ejecución con
  un segundo diálogo.

- **Las palabras sustitutas tienen el mismo aspecto en el editor de
  retoque también en páginas rasterizadas.** Si el marcador rojo está en
  los píxeles en vez de en la capa de texto del PDF, ahora recibe de
  todos modos la misma superficie de fondo coloreada según la confianza
  que un marcador de texto PDF normal.

- **Ya la vista previa antes de sustituir muestra la necesidad de
  revisión de los términos encontrados.** Cada línea lleva el mismo color
  rojo-naranja-verde que después el sustituto en el editor. Dentro de una
  categoría, la baja seguridad y los candidatos rojos a falsa alarma
  quedan arriba, los indicios verdes sólidos abajo; los empates se
  mantienen alfabéticos. Si el mismo valor procede de varios hallazgos,
  cuenta por precaución su evaluación más dudosa. Los casos especiales sin
  evaluar aparecen en amarillo neutro entre rojo y naranja.

- **El resultado ahora se puede copiar directamente como archivo desde
  el editor de retoque.** „Copiar resultado" coloca la versión limpiada
  actual en el portapapeles, sin cerrar el editor ni tener que volver a
  buscar el archivo en la lista principal. Ante una edición manual aún no
  guardada, antes se ejecuta automáticamente la vía de guardado segura
  completa; „Copiar imagen" se mantiene como función separada para
  píxeles puros.

- **Las palabras sustituidas muestran de un vistazo en el editor qué
  debería revisarse primero.** Una mera conjetura del modelo de lenguaje
  es roja, aunque spaCy le asigne de forma genérica un 85 por ciento.
  Otros juicios de modelo sin respaldo se quedan como máximo en naranja;
  los indicios nombrados fuertes pueden volverse verdes. El trabajo
  manual y las asignaciones antiguas sin evaluación valorable permanecen
  en amarillo neutro. También las barras de tachado automáticas llevan
  estos colores en la vista previa del editor, ahora también cuando la
  barra forma parte de una página PDF rasterizada. Para ello la
  asignación debe encajar y la caja de palabra anterior debe estar
  demostrablemente cubierta de negro opaco; la negrita normal no se
  colorea. En el PDF guardado, todas las barras siguen siendo opacas y
  negras sin cambios.

- **Lo que se desmarca en la vista previa se puede recordar de forma
  permanente.** Donde usted quita la marca, está diciendo: aquí el
  reconocimiento se equivocó. Hasta ahora eso solo valía para ese
  documento. Ahora aparece en la línea un interruptor „nunca más";
  pulsado, el valor pasa de forma permanente a la lista „No eliminar
  nunca" y en adelante se considera inofensivo en cualquier documento.
  Bajo la lista consta qué se vuelve permanente, antes de que pulse
  „Sustituir". Deliberadamente no existe la dirección contraria: lo que
  se encontró una vez, el reconocimiento lo vuelve a encontrar.

- **Un botón restablece todos los ajustes al estado de entrega.** Está
  abajo a la izquierda en la ventana de ajustes y pregunta antes. Sus
  archivos, su licencia, sus propias reglas de reconocimiento y el inicio
  automático quedan intactos; lo que su administración impone sigue
  vigente. Además, cada ajuste que se aparta del estado de entrega lleva
  la nota „modificado", así se ve de un vistazo qué se ha cambiado.

### Modificado

- **Un resultado ya no se deposita por sí solo, sino solo al guardar.**
  Una ejecución desde la ventana escribe primero su versión limpiada en
  un lugar provisional; el archivo „…_bereinigt" junto al original solo
  se crea cuando usted pulsa „Guardar". Hasta entonces el resultado se
  puede ver, retocar y copiar. Cada línea terminada tiene para ello un
  botón de guardar, bajo la lista aparece „Guardar todo", y en el editor
  rige Ctrl+S. Si vacía la lista o cierra el programa, se le pregunta; lo
  que nadie deposita, tampoco queda en ningún sitio. „Mostrar en la
  carpeta" está bloqueado antes de guardar; el lugar provisional no es un
  destino al que se envía a alguien. El archivo de asignación se guarda
  junto con ello.

  En los ajustes, bajo „Programa", „Depositar los resultados de
  inmediato junto al original" recupera el comportamiento anterior. La
  línea de comandos, la vigilancia de carpetas y el vigilante del
  portapapeles siguen depositando de inmediato sin cambios; ahí no hay
  nadie que pueda guardar.

- **La barra de herramientas del editor de retoque está ordenada.** El
  modo de aprendizaje ahora está en el extremo derecho junto a la lupa
  comparativa y „Valores sustituidos"; los tres interruptores que activan
  y desactivan un modo de funcionamiento quedan así juntos. „Aplicar a
  todas las páginas" se ha desplazado junto a las tres formas de tachado,
  porque solo ahí hace algo. „Copiar resultado", „Archivo – Restablecer" y
  „Aplicar a todas las páginas" prescinden de rótulo; su nombre sigue
  apareciendo en la información sobre herramientas y en el menú. Entre
  „Sustituir" y „Recuperar original" hay un separador: ambos son
  direcciones opuestas y, uno junto al otro, parecían dos variantes de la
  misma herramienta.

- **El icono de „Copiar resultado" ahora muestra un documento.** Dos
  hojas con la esquina doblada y líneas de texto, en vez de dos hojas
  iguales con una pequeña flecha en la esquina. „Copiar imagen" lleva a
  cambio el símbolo de imagen, para que ambos se distingan sin rótulo. El
  botón „Copiar" en la lista de resultados muestra el mismo icono de
  documento; deposita el mismo archivo.

- **Los ajustes están ordenados y provistos de encabezados.**
  „Reconocimiento" tiene ahora cuatro secciones: *Qué se elimina*, *Cómo
  se sustituye*, *Con qué minuciosidad se busca* y *Antes y después de la
  ejecución*. El reconocimiento facial y los códigos de barras/QR están
  junto a las imágenes, donde se buscan; „Programa" está dividido en
  *Archivos de resultado*, *Al iniciar*, *Actualización*, *Visualización*
  y *Información enviada a nosotros*, y el añadido al nombre del archivo
  de resultado está junto a los archivos de resultado en vez de entre
  idioma y apariencia.

- **El reconocimiento avanzado está activado de fábrica**, incluso antes
  de que se cargue su modelo de idioma. Antes el valor predeterminado
  dependía del stock de modelos, y un equipo recién configurado
  funcionaba de forma permanente en el nivel más débil. La ventana de
  configuración ofrece el modelo para cargar en la primera página y
  menciona el coste al lado. Si falta, la casilla lo sigue diciendo, en
  vez de simular un nivel que no funciona.

- **Las dos listas de términos ahora se llaman lo que hacen:** „Eliminar
  siempre" en vez de „Términos propios" y „No eliminar nunca" en vez de
  „Excepciones".

- **La ventana de vista previa es más clara.** A partir de nueve valores
  aparecen en dos columnas, las líneas son más finas, y el número de
  hallazgos aparece justo detrás del término en vez de en el borde
  derecho.

- **En el editor de retoque, Sustituir va antes que Tachar**, en la
  barra de herramientas, en el menú „Herramientas" y en el clic derecho
  sobre la página. Sustituir es el caso normal: un marcador se puede
  pulsar y recuperar, una barra no.

- **Menos botones duplicados en el editor.** „Guardar como…" y „Copiar
  imagen" solo están ya en el menú Archivo, con sus atajos de teclado
  habituales. En la barra queda uno de cada: Guardar y „Copiar
  resultado"; dónde se guarda ya consta en la línea de estado y se puede
  cambiar ahí con un clic.

- **El vigilante del portapapeles ya no se ofrece en el primer inicio.**
  Interviene en cada operación de copiar del sistema; quien ve el
  programa por primera vez no puede valorar eso. En los ajustes sigue
  disponible, ahí con la cláusula correspondiente al lado.

- **La apariencia clara deslumbra menos.** El fondo de la ventana venía
  hasta ahora del estilo del sistema respectivo, y era así la única
  superficie grande que nadie había decidido, casi blanco en Windows.
  Ahora es un blanco roto, igual en cada sistema.

- **El recorrido y el manual explican los colores.** Lo que significan
  rojo, naranja, verde y amarillo tras una palabra sustituida figura
  ahora como parada propia en el recorrido y como párrafo en el manual,
  en todas las versiones de idioma.

### Corregido

- **El manual y las preguntas frecuentes mostraban marcadores que ya no
  existen.** Desde el cambio a la forma corta, Maskuro escribe `[NAM1]`;
  en la ayuda seguía apareciendo `[NAME1]`, y la frase „Por defecto es
  `[NAME1]`" era simplemente falsa. En las diecisiete versiones traducidas
  aparecía además la marca **alemana** en vez de la propia: un lector
  español veía `[NAME1]`, donde su programa escribe `[NOMB1]`. Lo mismo
  con la extensión del archivo de resultado: todas las versiones
  prometían `_bereinigt`, mientras el programa crea `_limpiado`,
  `_nettoyé` o `_除去済み`. También se veían afectadas la forma sin número
  (al anonimizar todo se llama `[NAM]`, no `[NAME]`) y el identificador
  derivado del valor al aplicar hash.

- **La ventana de vista previa ya solo interrumpe una vez por documento,
  y una segunda vez solo si de verdad aparece algo nuevo.** Un PDF se lee
  desde dos vías: una desde el flujo de contenido y, al final, desde la
  página renderizada y visible. Hasta ahora cada una preguntaba por
  separado. Ahora rige: lo que usted decidió en la primera ventana sigue
  vigente, y los valores que ya estaban ahí no vuelven a aparecer. Si en
  cambio la revisión visual de las páginas terminadas encuentra algo que
  antes no estaba en ningún sitio, se le vuelve a presentar, solo eso,
  sin los valores ya decididos.

- **La ventana de vista previa ahora dice según qué se debe decidir.**
  En vez de „Quitar la marca = el valor se mantiene", que dice lo que
  *hace* la marca pero no cuándo quitarla, ahora dice: quite la marca en
  todo lugar donde no haya un valor personal; ahí el reconocimiento se
  equivocó. Además, cada ventana nombra la pasada de verificación de la
  que proceden sus valores.

- **Los marcadores tienen el mismo aspecto en todo el documento.** En
  páginas que se reconstruyen como páginas de imagen por la vía OCR, los
  marcadores visibles se ponían hasta ahora en tipografía de máquina de
  escribir: „[PLZ4]" aparecía ancho y con serifas junto a un „[NAM1]"
  estrecho de la misma página. Ahora llevan la misma tipografía sin
  serifas que en el resto, y tampoco se ponen ya más anchos de lo
  previsto al ajustarlos. La capa de búsqueda invisible conserva su
  propia tipografía; necesita medidas fiables, no aspecto.

- **En la barra de herramientas del editor ya no hay separadores
  dobles.** Donde falta todo un grupo de herramientas para el tipo de
  archivo abierto (en un PDF, por ejemplo, vista de páginas y
  renderizado), hasta ahora quedaban ambas rayas alrededor del hueco.

- **Al recuperar, ya no queda ocasionalmente solo un lugar blanco.** Un
  texto original ya restaurado con exactitud ya no se cubre de blanco por
  la caja ancha y agrupada de su marcador eliminado. En recuperaciones
  mixtas de texto e imagen, además, el texto solo se inserta de forma
  invisible cuando la imagen de página ya lleva visible exactamente ese
  estado original. Esto vale para marcos, panel de hallazgos y adjuntos
  PDF.

- **„Recuperar original" ya no ofrece innecesariamente rasterizar la
  página.** La estricta verificación de resto de texto sigue activa al
  tachar y sustituir. Al recuperar se omite: ahí el contenido original
  vuelve deliberadamente, y las palabras vecinas sin cambios dentro del
  marco de recuperación ampliado no eran un error de limpieza, sino una
  falsa alarma.

- **El recorrido por el editor ahora explica „Sustituir" y „Recuperar
  original" como pasos propios.** Ambas herramientas se destacan
  directamente en la barra y describen que un marco trazado inserta un
  marcador o recupera el contenido original de ese lugar desde el archivo
  fuente.

- **También los marcadores específicos de país se mantienen ahora en un
  máximo de cuatro letras.** Estos tipos faltaban hasta ahora en el
  catálogo central de siglas y por ello podían aparecer escritos en
  extenso, por ejemplo `[UMSATZSTEUER_ID1]`. Las ejecuciones nuevas
  escriben en su lugar `[UID1]`; todos los tipos alemanes e ingleses
  reconocidos automáticamente siguen siendo inequívocos. Incluso las
  siglas calculadas de otros idiomas de interfaz ya no crecen más allá de
  cuatro caracteres en caso de coincidencia de nombre. Los rótulos de
  reglas propias siguen llamándose exactamente como se introdujeron.

- **Sustituir ahora usa todo el espacio de línea realmente libre antes
  de tachar.** El límite rígido anterior del triple del ancho de palabra
  original generaba barras incluso en campos de formulario mayormente
  vacíos. También los hallazgos de la contraverificación OCR visible
  reciben ahora, con texto PDF ocupado, un marcador legible; permanecen
  en negro el contenido puro de imagen, anotación y vector, el modo de
  tachado elegido, así como los estrechamientos reales en los que no
  cabe ni siquiera una forma corta inequívoca.

- **Un marcador ya visible ya no se vuelve a escribir en rojo por
  encima al rasterizar por seguridad.** El rasterizado ahora toma el
  sustituto existente de la imagen de página y solo crea una copia de
  búsqueda invisible. Si una barra de seguridad debe cubrir exactamente
  ese lugar, se renueva toda la caja real del marcador en vez de solo su
  ancla original más corta.

- **„Recuperar original" ya solo marca objetivos seguros dentro del
  marco trazado.** Todos los términos sustituidos dentro se iluminan uno
  por uno con exactitud; el texto corrido sin cambios queda intacto. Las
  barras de tachado vectoriales reales también se marcan individualmente
  si bajo su superficie negra de PDF hay texto original. En páginas
  rasterizadas, la vista previa renuncia deliberadamente a una supuesta
  superficie de barra: la anterior búsqueda por píxeles unía ahí letras,
  subrayados y líneas de tabla en grandes superficies rojas en lugares
  equivocados. La propia restauración no se ve afectada por esto.

- **Al restaurar en páginas rasterizadas, el texto vuelve a aparecer.**
  Últimamente ahí quedaba un lugar vacío con rectángulos coloreados
  encima. El texto recuperado estaba en el documento, pero quedaba
  cubierto por el fondo blanco de un marcador que se dibuja más atrás en
  la construcción de la página.

- **Los colores de verificación ya no se superponen varias veces.** El
  mismo lugar se coloreaba por cada entrada de la asignación; en una
  página, cinco hallazgos reales, cada uno pintado cinco veces, hasta que
  la marca pálida se convertía en un bloque saturado. Y ya no aparecen
  sobre palabras que no se sustituyeron en absoluto: si el valor original
  todavía está en la página, ahí tampoco hay ya ninguna marca.

## 0.10.40-beta.1 – 24 de agosto de 2026

### Corregido

- **Las barras de tachado del editor ahora tienen un margen de seguridad.**
  Los marcos de palabra, línea y libres cubren también los glifos que
  sobresalen y los píxeles de borde suavizados; una verificación de
  renderizado asegura además que no quede ningún resto visible ni texto
  original legible.

- **Los textos de reemplazo siguen siendo legibles y de longitud uniforme y
  corta.** Los nombres, direcciones y términos libres nuevos aparecen, por
  ejemplo, como `[NAM1]`, `[ADR2]` y `[BEG3]`. El límite mínimo fijo es de
  4,5 puntos; en caso de falta de espacio primero se acorta y se amplía el
  espacio de línea disponible. Las asignaciones antiguas con marcadores
  largos siguen siendo legibles y recuperables.

- **Las sustituciones de varias palabras desde el panel de coincidencias
  están protegidas contra marcas duplicadas y restos del original.** La
  regresión se mantiene con y sin marcadores numerados; por cada hallazgo se
  conserva exactamente una asignación conjunta.

- **El contenido del portapapeles recuperado no se vuelve a limpiar de
  inmediato en macOS.** Aunque la firma del sistema cambie con retraso tras
  la escritura, Maskuro reconoce de forma fiable su propio contenido.

### Nuevo

- **El editor puede restablecer un archivo por completo a la versión de
  salida recién limpiada.** «Archivo – Restablecer» descarta, tras una
  confirmación, todas las correcciones de la pestaña actual, incluidas la
  lista de sustituciones y los contadores. El comando está bloqueado si no
  hay cambios y a su vez puede deshacerse con «Deshacer».

- **Las fechas desplazadas ahora conservan su cronología de forma fiable en
  varios archivos.** El desplazamiento común se ancla de forma permanente
  en las reglas ya al activar la estrategia; además, el desplazamiento ya no
  puede ser de cero días, lo que dejaría la fecha real visible sin que se
  note.

- **El trabajo manual en PDF cubre ahora el proceso profesional completo de
  tachado.** Términos individuales, listas y patrones habituales pueden
  buscarse y tacharse de forma segura en el PDF abierto o en todos los PDF
  de una carpeta; las páginas completas y los rangos de páginas se pueden
  seleccionar directamente. El color, la superficie blanca neutra, el texto
  de superposición, la tipografía, la alineación y la repetición cuentan con
  vista previa, y los códigos reutilizables pueden gestionarse e
  importarse/exportarse. La limpieza de PDF elimina, a elección, todo el
  contenido oculto mediante una reconstrucción completa o solo las clases de
  datos seleccionadas. La opción más segura está claramente recomendada, los
  patrones de búsqueda no válidos se explican y las ejecuciones por carpeta
  escriben exclusivamente copias del resultado.

- **La estadística de uso voluntaria muestra ahora instalaciones y cambios
  de versión.** Para ello, Maskuro genera un identificador de instalación
  aleatorio y almacenado localmente. No contiene datos de dispositivo,
  usuario ni licencia; el servidor solo guarda su valor SHA-256. La
  estadística sigue pudiendo desactivarse por completo en los ajustes.

- **El recorrido guiado es ahora un ejercicio guiado a través de ambas
  ventanas.** Coloca él mismo el documento de práctica ficticio en la lista,
  explica el camino hasta la limpieza y continúa automáticamente en el
  editor tras la ejecución. Quien interrumpe el recorrido también termina
  esta continuación.

- **Se reconocen empresas de otras quince jurisdicciones.** Quien limpia
  documentos del Báltico, Bélgica, Escandinavia, Chequia, Polonia, el
  sudeste de Europa, Singapur, Brasil o México ya no pierde nombres de
  empresa porque su forma jurídica fuera desconocida; entre las nuevas se
  incluyen OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s.,
  S.K.A., Pte. Ltd., así como S.A. de C.V. y S. de R.L.

### Cambiado

- **Las barras de herramientas del editor aprovechan ahora su espacio de
  forma más específica.** Los iconos estándar inequívocos y las formas de
  herramienta directamente reconocibles aparecen en la barra sin texto
  repetido; las acciones ambiguas conservan su nombre. En «Vista» puede
  desactivarse «Mostrar rótulos de herramientas» para reducir ambas barras
  por completo a iconos. Los mensajes emergentes y los menús siguen estando
  completamente rotulados, y la elección se recuerda.

- **El modo de aprendizaje ahora está visible de forma permanente en la
  barra de herramientas.** Puede activarse y desactivarse directamente ahí,
  incluso cuando el panel de valores sustituidos está cerrado. La barra de
  herramientas, el menú de herramientas y la antigua marca en el panel
  muestran siempre el mismo estado.

- **«Restablecer» en la lupa de comparación ahora solo restablece su
  zoom.** El botón restaura el valor predeterminado de 125 por ciento sin
  anclar la lupa, moverla ni cambiar el tamaño de su ventana. Para todo el
  diseño sigue siendo responsable «Restablecer vista».

- **Los errores y las sugerencias ahora también pueden notificarse a través
  del botón de ayuda.** «Notificar error…» y «Enviar sugerencia…» aparecen
  allí ahora igual que en el menú de ayuda clásico; ambos caminos abren el
  informe de errores seguro ya existente o la lista pública de sugerencias.

- **El menú de la bandeja del sistema es más corto y está mejor
  organizado.** Los dos comandos con atajo de teclado global —limpieza del
  portapapeles y captura de pantalla— aparecen ahora directamente uno debajo
  del otro con una columna común de atajos a la derecha. «Restaurar el
  último contenido original» desaparece de ahí; el botón de restauración,
  más comprensible, sigue disponible en la ventana principal.

- **Las páginas legales son accesibles directamente en «Ayuda → Aspectos
  legales».** El submenú lleva a las condiciones de licencia, la política
  de privacidad, el aviso legal y las condiciones generales en maskuro.com.
  Las indicaciones sobre el derecho de desistimiento permanecen en la
  compra, en el sitio web.

- **Los PDF tachados manualmente se reconstruyen por completo al
  guardar.** Se conservan las páginas y su capa de búsqueda recién leída;
  los metadatos, adjuntos, marcadores, comentarios, valores de formulario,
  capas ocultas, índices de búsqueda, scripts, contenidos recortados y
  contenidos ocultos en otros objetos no se trasladan al archivo de salida.
  Después, la tipografía y los gráficos vectoriales consisten en píxeles:
  ese es el precio del límite demostrable frente al árbol de objetos PDF
  ajeno.

- **Ctrl+Mayús+B toma ahora, de forma predeterminada, una captura de
  pantalla con Maskuro en todos los sistemas.** La tecla Imprimir pantalla y
  sus combinaciones siguen pudiendo asignarse aparte. En el menú del icono
  de la bandeja del sistema, los atajos de teclado globales aparecen ahora a
  la derecha de los comandos correspondientes. Las asignaciones propias
  guardadas se conservan.

- **El editor se inicia con las páginas y la lupa de comparación a la
  izquierda.** El panel de páginas queda arriba, la lupa de original abierta
  justo debajo; los valores sustituidos permanecen a la derecha. Una
  disposición propia guardada de forma deliberada sigue teniendo prioridad.

- **El documento de práctica ya no está permanentemente en la ventana
  principal.** Forma parte del ejercicio guiado y, además, sigue siendo
  accesible en «Ayuda».

- **El primer inicio lleva directamente al ejercicio práctico.** La guía
  rápida ilustrada ya no se ofrece como segunda vía de entrada, con
  contenido duplicado; sigue siendo accesible en cualquier momento en
  «Ayuda → Guía rápida».

- **El icono inactivo de la bandeja del sistema permanece a todo color.**
  Ahora muestra el mismo escudo intenso de Maskuro que el modo activo del
  portapapeles; solo con la vigilancia activa se añade el punto luminoso
  verde.

- **El documento de práctica permanece en Maskuro.** El botón de entrada
  genera el PDF ficticio y lo añade directamente a la lista de archivos,
  pero ya no abre un visor de PDF adicional.

- **La búsqueda en la ventana de revisión sigue siendo fluida al
  escribir.** El espacio para el contador de coincidencias ya se reserva al
  abrir; su primer texto ya no modifica el lienzo ni desencadena una nueva
  ejecución de rasterizado de PDF.

- **Los nombres de fabricante en las indicaciones de marca siguen
  siendo visibles.** Una entrada como «Fabricante: TRILUX o equivalente»
  describe la mercancía necesaria y ya no se tacha como empresa solo por
  este rótulo. Los campos de proveedor, empresa y fabricante no se ven
  afectados por esto.

- **Las mediciones del corpus cuentan los aciertos tachados en exceso como
  falsos positivos.** Cuando Maskuro elimina el nombre esperado pero se
  lleva de paso parte de la frase, ahora aumenta el número de falsos
  positivos. El informe indica además los excesos por separado; por eso, los
  números de falsos positivos anteriores ya no son directamente
  comparables.

### Corregido

- **Los términos técnicos y oficiales de documentos originales alemanes se
  tachan con menos frecuencia como nombres o lugares.** El equipamiento de
  vehículos, las líneas de posición y suma, los términos de contratación
  pública y protección de datos, las referencias legales, así como los
  nombres de archivo de materiales públicos, ahora solo se frenan con su
  contexto factual probado. Una diéresis perdida en el reconocimiento de
  texto en «Marz 2026» sigue protegida como mes; «Marz» sin referencia de
  fecha puede seguir siendo un nombre o lugar real.

- **«Recuperar original» toma de inmediato todo el ancho necesario.** Si el
  marco solo abarca una palabra de un valor asignado, Maskuro lo amplía por
  sí solo, a partir de la asignación y de la línea original, hasta cubrir el
  dato completo; por ejemplo, de «Planungs» a «Nordlicht Planungs GmbH». El
  marco que queda accesible después también muestra el ancho total
  realmente recuperado.

- **«Recuperar original» muestra ahora las barras negras como objetivo
  inequívoco.** Al pasar el cursor por encima o arrastrar, toda la barra
  detectada se ilumina en rojo con un contorno de contraste claro, en lugar
  de solo un recuadro de texto apenas identificable al lado. Esto también
  se aplica a páginas rasterizadas, en las que la barra ya solo consiste en
  píxeles.

- **El recorrido guiado del editor ya no omite estaciones cuando los
  paneles estaban cerrados.** Para la guía, Maskuro abre y ordena
  temporalmente por sí mismo el panel de páginas, la lupa de comparación y
  los valores sustituidos. Tras «Finalizar» o una interrupción, se recupera
  la disposición personal. Si una herramienta no está disponible en
  absoluto para un tipo de documento, su explicación se mantiene como pausa
  de texto en lugar de desaparecer sin más.

- **«Sustituir» sigue siendo visible incluso en el recurso de seguridad de
  PDF.** Cuando Maskuro tenía que reconstruir una página como imagen debido
  a un carácter restante o a un flujo de texto dañado, las sustituciones
  correctas solo quedaban de forma invisible en la capa de búsqueda,
  mientras que en la página había barras negras. Ahora, los valores de
  sustitución realmente aplicados se mantienen visibles en rojo y
  localizables a lo largo de todas las reconstrucciones por rasterizado y
  OCR.

- **Los avisos sobre la versión limpiada siguen siendo legibles en el modo
  oscuro.** El título de la versión, la línea de mando y la introducción
  toman ahora su color de texto directamente de la ventana Qt realmente
  mostrada.

- **Los marcos de tachado vuelven a colocarse sobre el texto en páginas PDF
  rasterizadas.** Los recuadros de palabra invisibles eran, según la
  tipografía original, más estrechos que las letras visibles. Esto producía
  huecos en la barra o dejaba legible la última letra. Los recuadros
  conservan ahora el ancho, la altura y la dirección de escritura de la
  palabra visible.

- **«Qué hay de nuevo» vuelve a empezar desde arriba del todo.** El diálogo
  del registro de cambios coloca ahora explícitamente el cursor de texto y
  la barra de desplazamiento al principio tras finalizar la construcción de
  la ventana, en lugar de empezar a mitad de las novedades según el estado
  de Qt.

- **Cerrar durante el reconocimiento de palabras del escaneo se mantiene
  silencioso.** Una ejecución de OCR en segundo plano que está terminando ya
  no envía datos a una ventana de revisión ya cerrada.

- **Las expresiones de tiempo relativas ya no se confunden con nombres.**
  Maskuro conoce ahora expresiones fijas como «hoy», «ayer», «mañana» y «la
  próxima semana» a partir de los datos oficiales de calendario del idioma
  del documento correspondiente.

- **Salir durante la primera carga del modelo limpia correctamente.** Quien
  cierra Maskuro o la ventana de revisión inmediatamente después de
  abrirla ya no deja ningún hilo todavía trabajando en el reconocimiento de
  idioma nativo al finalizar el proceso. Esto evita el informe de fallo
  esporádico al salir; una carga ya en curso se completa de forma ordenada.

- **Los diálogos de inicio retardados ya no aparecen después de salir.**
  Quien cierra la ventana principal poco después del inicio ya no recibe
  después, de forma invisible o retrasada, la pregunta sobre el mejor
  reconocimiento, las novedades o la introducción.

- **HTML y el correo electrónico conservan sus finales de línea.** En
  Windows, la serialización HTML mezclaba LF y CRLF tras la limpieza y la
  restauración. El contenido y el formato eran correctos, pero el archivo
  ya no era idéntico byte a byte. Los archivos HTML y los mensajes MIME
  vuelven a adoptar ahora la escritura de su origen.

- **Los nombres de empresa con una preposición permanecen completos.**
  Detrás de una preposición, Maskuro cortaba nombres como «Gesellschaft für
  Systemtechnik mbH» o «Bank für Arbeit und Wirtschaft AG» en la palabra
  «für». Ahora se reconoce el nombre de empresa completo; los inicios de
  frase reales como «Wir sind bei Alpha GmbH versichert» siguen siendo
  visibles.

- **Los nombres de empresa chinos permanecen completos antes de su forma
  jurídica.** Un componente de marca interpretable como verbo podía
  descartar el nombre completo pese al añadido inequívoco «有限公司». En
  escrituras sin mayúsculas y minúsculas, el ancla oficial de forma
  jurídica tiene ahora prioridad sobre este límite incierto de categoría
  gramatical.

- **Las páginas PDF se convertían en imágenes sin necesidad.** En PDF de
  varias páginas cuyas páginas comparten una lista de tipografías —algo que
  los generadores habituales crean así—, todas las páginas siguientes tras
  la primera perdían la referencia a sus tipografías. La consecuencia era
  doble: las diéresis ya no eran localizables en el resultado
  («Auftragsbestätigung» no se podía encontrar), y la verificación posterior
  daba entonces por pasadas por alto letras que nunca estuvieron en la
  página; rasterizaba páginas de texto intactas convirtiéndolas en
  imágenes, con lo que dejaban de ser localizables, copiables y resultaban
  notablemente más grandes. En el corpus de prueba, esto afectó a cuatro de
  diecisiete páginas.
- **Una coma sola ya no desencadena el rasterizado.** Si un área encontrada
  termina en la palabra, el signo de puntuación de al lado sigue
  perteneciendo justamente a ella. Pero una coma o un punto no es un dato
  pasado por alto, y el rasterizado cuesta la página completa. Las letras y
  los dígitos siguen siendo un motivo para volver a repasar.

## 0.10.38-alpha.20260824 – 24 de agosto de 2026

### Nuevo

- **Los nombres de empresa sin forma jurídica ahora se reconocen cuando
  su rótulo los nombra.** „Lieferant: Kranzbichler Handels GmbH" siempre
  se había eliminado; la forma jurídica delata la empresa. „Lieferant:
  Dehner Märkte" quedaba sin tocar, y en ofertas, licitaciones y pedidos
  el proveedor suele figurar exactamente así. Lo mismo vale para
  „Firma:", „Hersteller:", „Fabrikat:", „Arbeitgeber:" y sus equivalentes
  en otros ocho idiomas, también cuando el rótulo está solo en su línea
  y el nombre debajo.

  Lo que tras el rótulo *no* es una empresa permanece intacto:
  „Lieferant: siehe Anlage" no se tacha; si no, ahí pondría „Lieferant:
  [ORGA1]", y eso afirmaría un nombre que nunca existió. Los rótulos tras
  los que igual de a menudo hay una persona („Kunde:", „Auftraggeber:")
  quedan deliberadamente excluidos.

- **Una imagen insertada ahora también se puede editar.** En la ventana
  „Limpiar imagen" hay, junto a „Copiar resultado", un botón *Editar en
  el editor*: la imagen se limpia y luego se abre para retocar, rotular y
  resaltar; el mismo camino que sigue una captura de pantalla.

- **Los números tras su rótulo también se encuentran cuando nombran a
  una contraparte comercial.** Hasta ahora caían los números de cliente,
  contrato y personal; ahora también el número de deudor, de acreedor y
  de proveedor, el número de empleador austríaco, el registro ANKÖ y el
  número WEEE, EAR y EPR de un fabricante, tanto en alemán como en
  inglés. Además Maskuro entiende ahora la forma de escribir cabeceras de
  oferta con espacio antes de los dos puntos („Kunden-Nr : K903944").
  Los números de artículo, pedido, encargo, oferta y factura permanecen
  intactos: nombran el proceso o la mercancía, no a la persona. Quien
  quiera eliminarlos igualmente, los guarda como patrón de búsqueda
  propio.

- **Ahora ve cuánto tardó un archivo.** En la línea terminada aparece la
  duración junto al idioma reconocido („terminado · Alemán · 2,4 s"), en
  el resumen la del conjunto de la ejecución, en la bandeja de cifras la
  suma, y en el informe de verificación figura como campo propio. Con
  varios archivos, la línea revela cuál de ellos costó el tiempo.

- **Las escrituras no admitidas por el OCR del sistema se pueden leer
  como alternativa si hay un archivo de idioma disponible.** Hasta ahora
  regía: si el reconocimiento de texto propio del sistema no domina una
  escritura (en el Mac, por ejemplo, devanagari), en el resultado
  aparecía „Imagen(es) NO fueron verificadas", y los datos en la imagen
  quedaban sin tocar. Ahora interviene el reconocimiento de texto
  incluido si existe el archivo de idioma correspondiente. Como una
  imagen leída así es menos fiable que una verificada de forma regular,
  el resultado lo indica: „leída con el procedimiento alternativo, por
  favor revise". Medido en un estado intermedio histórico de la prueba en
  hindi: **diez datos más encontrados y cuatro falsas alarmas menos**
  (64 % → 73 %). El valor final actual figura más arriba y no debe
  confundirse con este.

- **El reconocimiento de texto pregunta por el idioma correcto.** Para
  todos los idiomas de documento excepto alemán e inglés se usaba hasta
  ahora el modelo de reconocimiento inglés, incluso cuando el archivo de
  idioma adecuado estaba disponible. En Windows eso afectaba a cada
  idioma; griego, japonés o hindi se leían ahí con el modelo inglés.

- **Un asistente de configuración en el primerísimo inicio.** (Quien ya
  ha usado Maskuro no lo recibe; „primer inicio" significa el primer
  inicio, no el primer inicio tras esta actualización.) Tres preguntas en
  vez de seis imágenes: el idioma de sus documentos, si se lee también
  texto en imágenes, y cómo quiere acceder a Maskuro en el día a día. Al
  final siguen los tres caminos: documento de práctica, recorrido o la
  guía rápida ilustrada. Todo se puede omitir, y „Ayuda → Repetir la
  configuración" lo recupera.

- **F1 abre el manual en el capítulo correspondiente.** En la ventana
  principal, en los ajustes (ahí según la página), en la ventana de
  revisión y en la gestión de idiomas; en la ventana de retoque mediante
  Mayús+F1, porque F1 ahí muestra desde siempre los atajos de teclado.
  Hasta ahora la ayuda siempre empezaba arriba, en 25 capítulos.

- **Nuevo primer capítulo del manual: „Empezar en tres minutos".** Cuatro
  pasos, no se necesita más para un documento, en las 18 versiones de
  idioma.

- **Un recorrido por la ventana.** „Ayuda → Recorrido por la ventana"
  pone un foco sobre un elemento de control tras otro y escribe una
  frase al lado; en la ventana principal ocho paradas, en la ventana de
  retoque siete. A diferencia de la guía rápida ilustrada, explica la
  ventana ante la que usted está sentado en ese momento. Se cancela en
  cualquier momento con Esc.

- **Un documento de práctica para probar sin riesgo.** Bajo la zona de
  depósito aparece ahora „Abrir documento de práctica" (también en el
  menú Ayuda). Genera una hoja inventada (nombre, dirección, teléfono,
  IBAN, número de la seguridad social), y en la hoja consta a la vez qué
  puede hacer con ella y qué verá después. Ni una palabra pertenece a una
  persona real; el primer documento que envíe por Maskuro no tiene por
  qué ser uno real.

- **„Solo revisar…" está ahora junto a „Limpiar".** Muestra dónde hay
  datos personales (archivo, tipo y cantidad) sin cambiar ni escribir
  nada. Quien ha depositado un documento puede así revisarlo antes de
  limpiarlo. Hasta ahora esta vía solo estaba en el menú Archivo bajo
  „Revisar carpeta…" y funcionaba sobre toda una carpeta en vez de sobre
  los archivos depositados.

- **Cuando no se encuentra nada, ahora consta a qué puede deberse.** Por
  ejemplo: en el archivo hay imágenes, pero „Verificar también texto en
  imágenes" está desactivado. O: el idioma configurado no coincide con
  el del documento. Y si no se da ninguno de esos casos, Maskuro también
  lo dice.

- **La ventana de retoque le saluda la primera vez con tres frases:**
  hacer clic tacha una palabra, arrastrar un área, a la derecha están los
  valores sustituidos. „Entendido" retira el aviso de forma permanente;
  „Ayuda → Mostrar de nuevo la introducción" lo recupera.

- **Ahora también se pueden pulsar palabras en páginas escaneadas.**
  Hasta ahora solo se podían pulsar palabras donde el PDF trae consigo
  una capa de texto; en un escaneo no era posible, y en el mismo
  documento podía variar de página a página. Esas páginas ahora se leen
  una vez con reconocimiento de texto; después se pulsan las palabras
  como en cualquier otro sitio. La línea de estado dice qué está
  ocurriendo.

- **La bandeja de páginas vuelve a ser una superficie.** Se detenía en
  mitad de su columna: barra de título cortada, al lado una franja de
  otro color, y la página actual solo se reconocía por un recuadro
  coloreado tras su número. Ahora llena su columna, se puede ensanchar,
  y la página actual se resalta como mosaico completo, con una vista
  previa de página sin distorsionar dentro.

- **Los lugares sustituidos brillan en amarillo pálido.** En la vista de
  páginas, con ello se ve de un vistazo dónde se sustituyó algo; el mismo
  color que usa la lupa comparativa sobre el original. El marco rojo al
  señalar con el ratón se mantiene sin cambios.

- **„Restablecer vista" en la ventana de retoque** (menú „Vista"). Quien
  ha movido, desacoplado o cerrado la bandeja de páginas o la lista de
  hallazgos vuelve a colocar todo donde estaba en el primer inicio.

### Modificado

- **Los marcadores son más cortos.** De `[SOZIALVERSICHERUNGSNR_1]` sale
  `[SVNR1]`, de `[ORGANISATION_1]` un `[ORGA1]`, de `[EMAIL_1]` un
  `[MAIL1]`. El motivo no es estético: un marcador más largo que el
  valor que sustituye descoloca la línea y en una columna de tabla
  estrecha ya no encuentra sitio; ahí quedaba hasta ahora una barra
  negra, y esta ya no le dice a nadie que ahí había algo. Donde existe
  una abreviatura habitual, esa es la que aparece (`[BLZ1]`, `[KFZ1]`,
  `[IBAN1]`). Los resultados de ejecuciones anteriores siguen siendo
  utilizables: la forma antigua se sigue reconociendo, y los archivos de
  asignación de ayer funcionan sin cambios.

- **El icono del programa ahora tiene el mismo aspecto en todas
  partes.** En la barra de menú del Mac aparecía hasta ahora un
  distintivo monocolor que el propio sistema coloreaba de negro o
  blanco; en la barra de tareas de Windows, uno verde o gris. Ahora cada
  barra lleva el mismo distintivo azul de Maskuro. Cómo saber si se
  vigila el portapapeles sigue siendo igual de claro: si la vigilancia
  está activa, hay un punto verde en el distintivo; si está en reposo, el
  mismo distintivo aparece pálido. También en los tamaños más pequeños
  aparecen ahora ambas barras de tachado en el distintivo; hasta ahora la
  barra de tareas solo mostraba una.

- **Los rostros se reconocen con un modelo cuyas imágenes de
  entrenamiento se obtuvieron con consentimiento.** Ahora se entrega
  MediaPipe BlazeFace (Apache-2.0); el detector anterior se mantiene
  integrado y se puede seleccionar, pero ya no se incluye por defecto,
  porque su origen de entrenamiento no está aclarado de forma
  concluyente. Para el reconocimiento no cambia nada: en 324 retratos y
  143 imágenes sin rostro, la nueva versión encuentra la misma cantidad
  con los mismos pocos errores y necesita un tercio del tiempo.

- **OCR es el ancla de seguridad para la garantía PDF más fuerte.** La
  ejecución normal de PDF lo usa y genera la construcción mínima
  completa. Quien desactiva OCR expresamente obtiene la vía de objetos
  más compatible; la interfaz, el mensaje final y el manual ahora dicen
  expresamente que esta vía no ofrece la misma protección frente a
  canales PDF ocultos desconocidos.

- **La puerta de venta ahora también bloquea el modelo YuNet incluido
  hasta ahora.** La licencia MIT del peso exacto sigue documentada, pero
  no basta como liberación de producto conservadora para la cadena de
  datos de entrenamiento públicamente visible a través de WIDER FACE.
  Antes de la venta se requiere una aclaración por escrito o la
  sustitución por un modelo con una cadena de datos y pesos comercial
  sólida.

- **Los nombres de empresa y organización ahora se eliminan por
  defecto.** Hasta ahora se mantenían mientras no se solicitaran
  expresamente. Ese era el valor predeterminado equivocado para una
  carta comercial: quien reenvía una oferta no quiere que en ella se lea
  al comitente. „Kranzbichler Handels GmbH", „Institut für Bauphysik" y
  similares se tratan por ello como un nombre. Quien lo necesite de otro
  modo lo desactiva en la ventana; en la línea de comandos, el
  modificador se llama ahora `--ohne-organisationen`. El antiguo
  `--mit-organisationen` se sigue aceptando y ya no hace nada, para que
  los scripts y accesos directos existentes no se rompan. Las fechas e
  importes de dinero siguen quedando excluidos sin cambios.

- **Tachar ahora tiene tres formas en vez de dos casillas.** „Palabras",
  „Línea entera" y „Marco libre" están como una sola elección uno junto
  al otro; siempre rige exactamente una. Hasta ahora „Líneas de texto" y
  „Línea entera" eran dos interruptores independientes que podían estar
  ambos pulsados, y el marco libre no era en absoluto un botón, sino el
  estado desactivado del primero. Los tres aparecen visiblemente junto a
  su herramienta y están en gris mientras se elige otra herramienta.

### Mejorado

- **El primer documento está listo alrededor de un segundo antes.**
  Antes de que empiece la limpieza, Maskuro determina el idioma del
  documento, y para ello obtenía hasta ahora las listas de palabras de
  los 48 idiomas por una vía que cargaba mucho más que las palabras. Eso
  era aproximadamente la mitad del tiempo de espera hasta el primer
  resultado. El propio reconocimiento no cambia: ve las mismas palabras
  que antes, solo que más rápido. Cada documento adicional no se veía
  afectado de todos modos.

- **Los documentos con párrafos muy largos se verifican más rápido.** En
  un párrafo sin salto de línea, Maskuro lo volvía a leer entero por cada
  lugar encontrado; ahora basta una vez. Cuanto más largo el párrafo,
  mayor la diferencia; medido, alrededor de una séptima parte menos de
  tiempo de cálculo. En el resultado no cambia nada.

### Corregido

- **Con una empresa a menudo desaparecía media frase.** Si un nombre de
  empresa estaba en texto corrido („Information über die Gottwald GmbH
  & Co KG", „… (AGB) der Musterbetriebe GmbH"), no solo se tachaba el
  nombre, sino todo lo anterior hasta el inicio de la frase. El texto se
  volvía ilegible, y parecía que se había tachado al azar. Los nombres
  de empresa que llevan ellos mismos un „für" o „und" („Bank für Arbeit
  und Wirtschaft AG") permanecen completos sin cambios.

- **Los nombres de empresa quedaban en membretes, aunque se habían
  eliminado en el texto.** En una oferta, la sede de la empresa seguía
  legible en la imagen del membrete, el mismo lugar que Maskuro había
  tachado en el texto corrido; en el texto buscable del resultado
  incluso seguía ahí de forma invisible. Lo que se elimina una vez ahora
  también se elimina donde solo existe como imagen. Esto también actúa
  en logotipos y marcas denominativas dibujadas como gráfico.

- **macOS preguntaba en cada inicio por la grabación de pantalla**,
  incluso cuando el permiso ya se había concedido hacía tiempo. El aviso
  al iniciar probaba una grabación, y precisamente eso trae a pantalla el
  diálogo del sistema. Ahora, al iniciar, solo pregunta el propio
  Maskuro, y solo una vez; el sistema solo pregunta cuando usted realmente
  toma una captura de pantalla.

- **Términos técnicos se confundían con lugares y empresas.**
  „Einspeisepunkt", „Flachdach", „Verteileranlage", „Meldersockel" y
  docenas de palabras similares desaparecían de ofertas y pliegos de
  condiciones. Maskuro las reconoce ahora por su palabra base: lo que
  termina en „-anlage", „-punkt" o „-kanal" es una cosa. Los nombres de
  lugar como Berlín, Melk o Wieselburg no tienen esa palabra base y
  permanecen intactos, igual que direcciones como „Der Graben" o „Alter
  Markt".

- **Documentos en japonés, coreano, chino, tailandés y gujarati podían
  hacer que el programa se cerrara inesperadamente.** Si un documento en
  uno de esos cinco idiomas contenía una dirección de internet sin
  „https://" delante, la limpieza se interrumpía con un error interno; con
  la ventana abierta, con ello se perdía también el resto del trabajo.
  Los cuarenta y ocho idiomas de documento seleccionables ahora funcionan
  todos; si falta el diccionario de frecuencia para un idioma, el dato en
  caso de duda se mantiene en vez de desaparecer.

- **Los rótulos de campo solo protegían en alemán e inglés.**
  „Reference" quedaba sin tocar, el italiano „Riferimento" y el
  portugués „Referência" se eliminaban como dato de lugar; el mismo
  nombre de campo, la misma línea, resultado distinto. Quien no trabaja
  en inglés quedaba con ello en peor posición. Maskuro conoce ahora los
  mismos nombres de campo en los once idiomas mantenidos.

- **„Recuperar original" recuperaba de más en páginas escaneadas.** Un
  marco sobre una línea tachada de un bloque de dirección volvía a
  revelar **todo el bloque**, y la página quedaba desgarrada: restos de
  barra seguían ahí, de los que sobresalían finales de palabra sueltos.
  La causa era que las barras superpuestas en una página rasterizada se
  tocan entre sí y por ello se consideraban una única superficie. Ahora
  se recupera exactamente la línea a la que apunta el marco; las líneas
  vecinas siguen tachadas, y la barra de la línea alcanzada desaparece
  por completo.

- **Las cantidades en listas de posiciones se confundían con
  direcciones.** En una línea como „1.4  Kabelgraben  100,00  m" se
  sustituía „Kabelgraben 100" como calle con número de casa. Esas líneas
  ahora se mantienen; las direcciones reales, también „Hauptplatz 1, 3250
  Wieselburg", se siguen reconociendo sin cambios.

- **Ante un nombre de empresa desaparecía media frase.** De „Vertrag
  zwischen der Firma Gottwald GmbH & Co KG und dem Auftraggeber." salía
  „[ORGANISATION_1] und dem Auftraggeber."; el inicio de la frase había
  desaparecido, y con él la indicación de qué se trataba. Ahora solo cae
  el propio nombre de empresa. Donde la palabra genérica forma parte del
  nombre („Deutsche Bank AG", „Universität Wien"), todo sigue como hasta
  ahora.

- **En un acta quedaban sin tocar hablantes cuyo nombre es a la vez una
  profesión.** „Bauer:", „Koch:", „Weber:" ante una intervención se
  pasaban por alto, „Gruber:" al lado no; Maskuro necesitaba hasta ahora
  al menos un nombre reconocido en el documento para leer siquiera las
  líneas como intervenciones. Si el documento lleva un encabezado como
  „Ergebnisprotokoll" o „Niederschrift", ahora basta con eso. Las líneas
  de nota („Achtung: …", „Hinweis: …") permanecen intactas.

- **Un rótulo de campo desaparecía junto con su valor.** De „Projekt:
  Sanierung und Erweiterung Gemeindezentrum" salía un único marcador;
  también había desaparecido la palabra „Projekt:", y con ella la
  indicación de qué había ahí. Los rótulos ahora se mantienen. Donde un
  rótulo forma parte del dato y lleva su significado („Durchwahl 214"),
  no cambia nada.

- **El reconocimiento máximo no eliminaba términos técnicos.**
  „Flachdach", „Einspeisepunkt", „Elektrotechnik" y términos técnicos
  similares se sustituían como lugar o empresa incluso con el nivel de
  IA activado; la IA nunca recibía precisamente esos hallazgos para
  evaluación. Ahora también los verifica: en un corpus de textos de
  licitación y contrato desaparecen así los 27 desaciertos, sin que
  quede ningún dato real.

- **Palabras genéricas para tipos de institución se confundían con
  organizaciones.** En un texto contractual desaparecían „Hochschulen
  und Universitäten", „Staatliche und private Schulen", „Akademische
  Lehrkrankenhäuser", „Bildungseinrichtung" y „Zulieferfirmen"; palabras
  que no nombran un lugar concreto, sino un tipo de lugar. Ahora se
  mantienen. Si delante hay un nombre propio („EU-Kommission"), se sigue
  sustituyendo, y los nombres de empresa no están cubiertos en absoluto
  por esta regla.

- **Los nombres en listas solo caían si eran habituales.** En una lista
  de participantes o asistencia bajo un encabezado de columna „Name" se
  eliminaban „Anna Huber" y „Thomas Müller", pero no „Wójcik Aleksandra"
  o „Kücükgöl Sinan"; la misma línea, la misma estructura. Quien lleva
  un nombre menos frecuente quedaba así peor protegido. Ahora decide el
  encabezado de columna: lo que está bajo „Name" es un nombre. Una lista
  de posiciones con encabezado de columna técnico permanece intacta.

- **Un número de teléfono tras „Durchwahl" se cortaba por la mitad.** De
  „Durchwahl 0732 771190" salía „[DURCHWAHL_1] 771190"; la segunda mitad
  del número quedaba legible. Ahora el número completo cae entero, y el
  rótulo se mantiene. Una extensión real („Durchwahl 214") se sustituye
  sin cambios junto con su rótulo.

- **Algunos PDF ya no se podían limpiar en absoluto.** Si un perfil de
  color o los metadatos de una imagen no se podían eliminar de forma
  demostrable, la ejecución se interrumpía sin resultado; se veían
  afectados documentos comerciales normales como páginas de condiciones
  generales, pliegos de requisitos y licitaciones. Esos archivos ahora
  se limpian, y un aviso nombra los lugares que quedaron abiertos:
  pueden llevar un identificador de dispositivo, de generador o de
  captura. El original permanece intacto como siempre.

- **Los roles contractuales se confundían con personas.** „Bieter",
  „Verbraucher", „Mieter", „Käufer", „Auftraggebers" y unas cuarenta
  palabras de rol más se sustituían cuando aparecían sin artículo, en
  encabezados de contrato, columnas de tabla y líneas de firma. Un texto
  contractual sin un solo dato personal se volvía así ilegible en
  algunos lugares. Esas palabras ahora se mantienen. Si al lado hay una
  indicación de persona (un tratamiento, un nombre de pila, una palabra
  de campo como „Ansprechpartner"), se sigue sustituyendo: „Herr Bieter"
  y „Frau Käufer" son nombres. Los apellidos frecuentes que a la vez son
  profesiones (Bauer, Richter, Koch) no están cubiertos en absoluto por
  la regla.

- **Una calle escrita de forma abreviada se pasaba por alto cuando el
  número de casa estaba pegado directamente al punto.**
  „Schlesischestr.31" no se consideraba dirección, y como el código
  postal contiguo obtiene su apoyo del hallazgo de dirección, también
  quedaba sin tocar. En el resultado, la dirección se podía reconstruir
  a partir de la calle y el código postal, y eso solo en algunas páginas
  del mismo documento. Ahora ambos caen juntos. Las denominaciones
  técnicas con un número añadido („Kabelrinne200") permanecen intactas.

- **Una dirección en dos líneas se fusionaba en un único marcador.** Si
  en un bloque de dirección el código postal estaba sobre la calle,
  Maskuro unía ambas líneas en un solo hallazgo: en el resultado
  desaparecía el salto de línea, y el código postal quedaba legible
  delante. Ahora cada línea se encuentra y sustituye por separado, y la
  disposición del texto se conserva. La misma causa arrastraba a veces
  también el apellido de la línea anterior hacia la dirección.

- **La vía PDF máxima ya no incorpora objetos originales.** Con el
  reconocimiento de texto activado, Maskuro reconstruye cada página por
  completo a partir de la imagen PDFium visible. En el nuevo archivo
  mínimo solo entran esa página de imagen y una capa de búsqueda
  recién generada, limitada al texto OCR, no el árbol de objetos ajeno
  con comentarios, adjuntos, acciones, capas, metadatos, perfiles de
  color o claves privadas. Esto también vale para contenido en
  apariencias de anotación, patrones, fuentes tipo 3, objetos de forma y
  máscaras suaves. El archivo fuente permanece intacto.

- **Se pasaban por alto rostros y códigos en gráficos PDF anidados.**
  Ambos detectores ahora ven además la imagen de página renderizada
  completa. Con ello también alcanzan a los detectores los retratos y
  códigos QR/de barras en anotaciones, patrones, glifos tipo 3 y máscaras
  de transparencia; las zonas reconocidas se hacen irreconocibles, si
  está activado, antes de la reconstrucción mínima. La propia detección
  sigue siendo falible.

- **Un motor OCR faltante terminaba en PDF con un error interno.** La
  ejecución máxima ahora se interrumpe de forma controlada y sin archivo
  de destino, en vez de generar un archivo incompleto o sin verificar.

- **Varios valores reales de contacto y comerciales pasaban
  desapercibidos mientras se sustituía texto técnico.** Los campos de
  nombre con saltos de línea, los nombres bancarios y de empresa, las
  formas jurídicas, los números de identificación rotulados, las fechas
  de nacimiento, así como los límites de teléfono, URL e IBAN, se
  verifican con más precisión. Al mismo tiempo, los países en texto
  técnico, las palabras de rol y genéricas, los códigos de
  artículo/norma, las columnas de cifras y las abreviaturas normales
  permanecen intactos con más frecuencia.

- **Las líneas OCR mixtas y giradas se leían mal.** Las palabras
  verticales inciertas ahora se releen localmente enderezadas; los
  valores técnicos latinos en texto no latino reciben un testigo inglés
  independiente. Un dígito suelto inseguro solo se corrige si dos
  secuencias de dígitos cercanas coinciden. Las formas jurídicas polacas
  en la forma OCR „sp. z 0.0." se leen en contexto cerrado como „sp. z
  o.o.".

- **La medición de imagen podía pasar por alto restos parcialmente
  visibles.** Ahora verifica fragmentos locales superpuestos, distingue
  la escritura blanca de marcador sobre una barra negra de los glifos
  originales y transfiere las cajas de imagen bruta también a PDF
  mínimos girados y recién renderizados. El corpus principal sintético
  fijo alcanza así 1.392/1.392 datos de referencia eliminados con 0
  falsas alarmas y 0 errores de procesamiento. Esto es un comprobante de
  corpus, no una promesa general del 100 %.

- **Los modelos de idioma no comerciales ya no se ofrecen.** Las seis
  variantes de spaCy italianas y griegas bajo CC BY-NC-SA 3.0 se han
  eliminado del catálogo, la descarga y la vía de carga; también se
  ignoran las carpetas de modelo ya existentes. Ambos idiomas usan en su
  lugar el modelo multilingüe con licencia MIT.

- **El nombre bajo „Ansprechpartner" solo se eliminaba a medias.** Si el
  rótulo está solo en una línea y debajo „Nachname Vorname", el nombre de
  pila se mantenía en cuanto era a la vez una palabra corriente: de
  „Mayer Roman" salía „[NAME_1] Roman". Esas líneas ahora se toman
  enteras. Un departamento en el mismo lugar („Technischer Innendienst")
  sigue intacto. Corregido de paso: „Ansprechpartner" no contaba en
  absoluto como campo de nombre, aunque „Kontaktperson" sí lo hace desde
  siempre.

- **El nombre de empresa sin forma jurídica quedaba sin tocar cuando
  había una palabra de sector en medio.** „Kranzbichler Handels GmbH" se
  eliminaba, el „Kranzbichler" desnudo tres párrafos después no; con
  „Kranzbichler GmbH", en cambio, sí. Ahora funcionan ambos. Las
  palabras corrientes quedan excluidas de esto: „Deutsche Bank AG" no
  convierte un „deutsche" del texto en empresa.

- **El mismo valor se llamaba en el mismo documento a veces nombre y a
  veces lugar.** „Anna Musterfrau … Musterfrau" daba „[NAME_1]" y
  „[ORT_1]"; en el segundo lugar falta el nombre de pila, y sin él se
  convertía en un lugar. Ambos se eliminaban, pero se leía como dos
  cosas distintas. Un valor conserva ahora la denominación de su primera
  aparición.

- **Las fechas dejaban de eliminarse.** Una fecha compuesta solo de
  cifras („01.03.2026") caía, desde la última versión, en una
  verificación pensada para nombres, y quedaba en el documento; también
  en el modo „desplazar", y sin línea en el informe de verificación. Se
  veía afectado solo quien había activado expresamente las fechas.

- **Los países y continentes ya no se tachan.** „Die Lieferung geht in
  die Vereinigten Staaten", „Marktschwäche in Asien", „die Norm gilt in
  Rumänien"; esos datos no dicen nada sobre una persona y ahora se
  mantienen. Si el nombre de país, en cambio, forma parte de una
  dirección o está tras un rótulo como „Wohnsitz" o „Geburtsort", se
  sigue eliminando. **Las ciudades no se ven afectadas**: „Ich bin
  gerade in Bilbao" sigue siendo un dato sobre una persona y se sigue
  tachando.

- **Palabras abreviadas se convertían en direcciones web.** Si en el
  texto aparece „bzw. deutsche" o „incl. der", algunos PDF entregan el
  punto sin espacio; de ahí salía „bzw.de" o „incl.de", una dirección
  válida con terminación de país, y se eliminaba. Esos pares de palabras
  ahora se mantienen. Las direcciones reales no se ven afectadas,
  tampoco sin „www." delante.

- **Las columnas de cifras de balances se tachaban como números de
  teléfono.** En informes anuales y tablas de precios, el año anterior y
  el actual aparecen uno junto al otro: „64.518  65.133". Eso se
  consideraba un número de teléfono y se eliminaba, igual que rangos de
  números como „12200-23200" y una fecha con un número a continuación.
  Esos números ahora se mantienen. Al contrario, un número de teléfono
  real se reconoce con más seguridad: los rótulos „Telefon", „Fax",
  „Mobil", „Durchwahl" y sus equivalentes en los demás idiomas de
  interfaz ahora cuentan también; hasta ahora el programa solo
  reconocía ahí las palabras en inglés.

- **Los nombres en una tabla numerada quedaban sin tocar.** Una lista de
  participantes o tabla de personal en la forma habitual, encabezado de
  columna, debajo „1.1 Auersperg Bernhard Montage 03.03.2026", no se
  limpiaba en absoluto: esas líneas parecían la lista de posiciones de
  una oferta, donde los términos técnicos deben mantenerse. Si el
  encabezado de columna lleva un rótulo de persona („Name", „Nachname",
  „Surname"…), las líneas debajo ahora se consideran nombres. Las listas
  de posiciones siguen intactas sin cambios, también cuando en el
  membrete pone „Sachbearbeiter:".

- **De un nombre a veces salían dos marcadores uno junto al otro.**
  Cuando un apellido también estaba solo en el documento, el
  postprocesamiento sustituía en un lugar como „Anna Musterfrau GmbH"
  primero el apellido y luego el nombre de pila; en el resultado eso
  parecía dos personas distintas. Ahora gana el nombre conocido más
  largo.

- **Los valores inventados no figuraban en ninguna asignación.** Quien
  había elegido „Inventar valores" obtenía un resultado en el que „Anna
  Musterfrau" se había convertido en „Greta Mayrhofer"; en la asignación
  no constaba nada de eso en cuanto en el mismo documento aparecía
  siquiera una sustitución anónima. Con ello no se podía recuperar
  ningún valor inventado, y el archivo de asignación callaba la
  sustitución. Lo más delicado era lo tercero: quien lee el resultado ve
  un nombre creíble y no tiene ninguna indicación de que sea inventado.
  Ahora cada sustitución figura en la asignación.

- **La asignación llamaba „sustituido" a lo tachado.** Un correo
  comparte una asignación con sus adjuntos, y el adjunto puede tacharse
  mientras el texto del correo lleva un marcador. En la asignación
  figuraba entonces lo mismo para los tres lugares, „sustituido", y la
  recuperación buscaba en el adjunto un marcador que ahí no existe: la
  barra quedaba sin tocar. Ahora consta por cada hallazgo lo que
  realmente ocurrió ahí, y ambos adjuntos se recuperan.

- **Los valores que solo estaban en una imagen no se podían
  recuperar.** En el panel de hallazgos figuraban por duplicado: una vez
  como marcador que no existía en ningún sitio del documento („El
  marcador no se encontró en el documento"), otra como lugar tachado. La
  primera línea era pura contabilidad y ha desaparecido.

- **Los valores tachados solo se podían recuperar una vez.** Si el mismo
  valor está en varios lugares, un clic los recupera todos; pero las
  demás líneas se mantenían en el panel de hallazgos, y el siguiente
  clic sobre ellas comunicaba „No es inequívoco". Ahora desaparecen con
  él.

- **Las recuperaciones faltaban en el registro de verificación cuando el
  modo de aprendizaje estaba desactivado.** Quien restauraba un valor
  recuperado en la ventana de retoque no volvía a encontrar el proceso
  en el registro de verificación en cuanto las preguntas de aprendizaje
  estaban desactivadas; el comprobante dependía de un interruptor que
  solo se refiere a las propuestas de reglas. Con el registro de
  verificación activado, ahora se pregunta por el motivo
  independientemente de eso y se escribe la línea.

- **Los archivos arrastrados al interior quedaban sin limpiar, y ni
  siquiera se comunicaba.** Quien arrastra un archivo dentro de un
  documento en vez de enviarlo como adjunto hace que Word o PowerPoint lo
  depositen por completo en el documento. Después quedaba sin cambios en
  el resultado, con su nombre de archivo y ruta de origen originales, y
  estos en la práctica a menudo llevan ellos mismos un nombre. Esos
  archivos ahora se limpian como el resto del documento.

- **Y donde eso no es posible, Maskuro lo dice.** Si en un objeto
  incrustado hay un formato antiguo (Word 97, Excel 97) para el que no
  existe limpieza, ahora aparece un aviso de ATENCIÓN con el nombre del
  archivo. Hasta ahora se entregaba en silencio sin cambios.

- **Palabras rotas y siglas se confundían con nombres.** Cuando una
  palabra en un PDF está separada al final de línea, al leerla algunos
  archivos generan un fragmento: „Jahresent… gelts", „Gewerbli…". Esos
  fragmentos, palabras pegadas („TürverschlussmitV") y siglas desnudas
  („JY", „FFB") se tachaban como si fueran nombres. Ahora se mantienen.
  Un nombre con el mismo daño de separación se sigue tachando mientras
  haya un tratamiento; y los nombres que llevan de por sí una mayúscula
  dentro de la palabra (McKenzie, MacDonald, LeBlanc) no se ven
  afectados por esto de todos modos.

- **Las medidas y los meses se consideraban dirección.** En documentación
  técnica se tachaban „2000 Lux", „1200 Mbit", „1500 Watt", „5308 Platz"
  y „2022 Mrz"; cuatro dígitos y una palabra en mayúscula parecían un
  código postal con localidad. Un código postal ahora solo cuenta cuando
  hay además una señal de dirección: un indicativo de país, un rótulo de
  campo, el inicio de línea, una calle en la línea de arriba o un lugar
  que también ve ahí el reconocimiento de idioma. En cinco pliegos de
  condiciones desaparecen así 14 tachados falsos, sin que quede ninguna
  dirección real.

- **El reconocimiento más preciso sustituía de más.** El nivel activable
  „reconocimiento más preciso" confundía en documentos comerciales
  alemanes términos técnicos con nombres y lugares („Photovoltaikanlage",
  „Einspeisepunkt", „Flachdach", „Personaleingang") y tachaba
  denominaciones de empresa en listas de posiciones corrientes. La causa
  era una protección: sus hallazgos quedaban excluidos de las
  verificaciones que reconocen una línea de posición o de directorio.
  Esa protección ahora solo rige para nombres de varias partes, para lo
  que existe el nivel; „Anna Huber" en una línea de directorio sigue
  reconocida, una sola palabra técnica en una línea de posición
  desaparece. En una licitación técnica esto reduce a la mitad los
  tachados falsos del nivel, sin perder ningún nombre.

- **Los diagramas traían consigo sus datos de origen completos, sin
  verificar.** Quien inserta un gráfico en Word o PowerPoint hace que el
  programa deposite en el documento, como archivo propio, la tabla a
  partir de la cual se calculó. Visibles son solo las pocas cifras del
  gráfico; en la tabla está toda la lista, incluidas las filas que ni
  siquiera aparecen en el gráfico. Esa tabla se entregaba hasta ahora sin
  cambios. Ahora se limpia también, con los mismos marcadores que el
  resto del documento.

- **Lo mismo para objetos incrustados en archivos OpenDocument** (ODT,
  ODS, ODP): un gráfico o una tabla insertados quedaban intactos.

- **Documentos Word: las notas al pie y al final no se limpiaban.** Su
  texto permanecía completo en el resultado, también nombres,
  direcciones y números de cuenta. Se veía afectado cualquier documento
  Word con una nota al pie o al final. Igualmente quedaba sin tocar un
  bloque de autotexto que viaja de forma invisible con el documento.

- **Word: datos en listas de selección, comentarios y descripciones de
  imagen.** Las entradas de un campo de selección (visibles solo al
  desplegarlo), el autor de un comentario, la descripción de un dibujo y
  la dirección tras una instrucción de referencia seguían en el
  resultado.

- **Excel: la tabla dinámica registraba los datos de origen una segunda
  vez.** Un libro con una tabla dinámica conserva en ella una copia
  completa de las filas evaluadas, invisible, pero en el archivo. Esa
  copia quedaba hasta ahora sin cambios, incluso cuando en la propia hoja
  todo estaba sustituido. Se veía afectada cualquier evaluación que se
  compartiera con una tabla dinámica.

- **Excel: comentarios de conversación y sus autores.** El texto de un
  comentario del tipo más reciente y el directorio de comentaristas
  (nombre visible e identificador de inicio de sesión, en empresas
  normalmente la dirección de correo) seguían en el resultado. El mismo
  directorio en documentos Word también.

- **Propiedades de documento autodefinidas en Word y Excel.** Campos
  como „Mandant" o „Aktenzeichen", que un despacho añade a sus
  plantillas, no se limpiaban hasta ahora. No se ven en ninguna vista y
  aun así viajan con cada copia.

- **Hojas de cálculo (ODS): la lista de selección de una celda.** Igual
  que en Excel desde la versión anterior, ahora también en tablas
  OpenDocument se limpia lo que aparece al desplegar una celda. Las
  referencias a otras celdas permanecen intactas, para que la lista siga
  funcionando.

Todos estos lugares se pueden recuperar como de costumbre a través de la
asignación.

- **Mensajes de Outlook: un archivo dañado terminaba la limpieza de
  forma abrupta.** Ciertos archivos `.msg` rotos provocaban una
  interrupción en vez de un aviso; ahora se leen en la medida en que son
  legibles.

- **El archivo de asignación ahora solo es legible para usted.**
  Contiene los datos originales en texto claro y hasta ahora estaba con
  los permisos habituales junto al resultado; en un almacenamiento
  compartido, cualquiera podía abrirlo. En el propio resultado limpiado
  no cambia nada; este sí debe compartirse.

- **Los modelos de idioma recargados se verifican con más precisión
  antes de descomprimir.** Un paquete manipulado, por ejemplo de una
  publicación empresarial desde la que se sirven varios puestos de
  trabajo, podía depositar archivos fuera de la carpeta prevista al
  descomprimir. En la recarga habitual no cambia nada.

- **Tomar una captura de pantalla y se limpia de inmediato.** Con
  `Ctrl+Mayús+B`, mediante „Archivo → Tomar captura de pantalla…" o desde
  el icono en la barra de tareas, arrastra un marco sobre la pantalla. Lo
  que hay dentro sigue después el mismo camino que cualquier otro
  archivo: el reconocimiento de texto lee el texto en pantalla, se
  tachan nombres, direcciones, números de teléfono y direcciones de
  correo, y después la imagen queda abierta en el editor, donde puede
  retachar con un marco lo que se pasó por alto. La imagen limpiada
  llega al escritorio (o a su carpeta de salida configurada); la captura
  **en bruto** no se guarda en ningún sitio y se elimina al cerrar. El
  reconocimiento de texto se activa para esta ejecución, aunque
  normalmente esté desactivado; en una imagen no se encontraría nada sin
  él. En el Mac, el sistema pregunta la primera vez por el permiso
  „Grabación de pantalla".

- **Ahora se puede dibujar sobre imágenes: rectángulo, elipse, flecha,
  texto y marcas de paso numeradas.** En seis colores y tres grosores de
  trazo, seleccionables con las teclas 1 a 5. Está pensado para capturas
  de pantalla e instrucciones: mostrar lo importante sin tener que abrir
  para ello un segundo programa. Deshacer y el ajuste con los tiradores
  funcionan como para cualquier barra; una anotación se puede así mover
  y redimensionar después de colocada.
  **Dibujar expresamente no es tachar.** Un rectángulo dibujado es un
  marco, no una barra: lo que hay debajo permanece legible y sale con el
  archivo. Para eliminar datos siguen existiendo „Tachar" y „Pixelar";
  por eso las herramientas de dibujo están en una línea propia de la
  barra de herramientas, y la línea de aviso lo dice mientras una de
  ellas esté seleccionada.

- **La imagen editada pasa con un clic al portapapeles.** „Copiar
  imagen" en el editor (o `Ctrl+C`) la deposita tal como está; pegar
  basta para llevarla a un mensaje o correo. Con ello, el camino desde
  pulsar la tecla hasta el chat tiene cuatro pasos y no necesita ninguna
  carpeta.

- **Además, un resaltador, sombras y degradados.** „Resaltar" colorea
  una superficie sin cubrirla; el contenido debajo sigue siendo legible,
  y precisamente en eso se diferencia de la barra. „Sombra" destaca una
  anotación de un fondo agitado, „Degradado" deja que el color se
  desvanezca en la dirección de arrastre; ambos valen para las seis
  herramientas de dibujo.

- **Corregido antes de que afectara a nadie:** la nueva línea de
  herramientas habría aparecido casi vacía para cualquiera que ya
  hubiera usado Maskuro; la distribución de ventana recordada procedía
  de antes y no le habría dejado espacio. Una distribución obsoleta
  ahora se descarta; la ventana del editor aparece entonces una vez en
  su distribución básica.

- **La propia captura de pantalla se puede desactivar.** Quien está
  acostumbrado a Greenshot, ShareX o la Herramienta de recorte desactiva
  en „Ajustes → Programa" „Tomar captura de pantalla con Maskuro".
  Maskuro entonces ni siquiera registra el atajo de teclado; queda para
  su herramienta, y el cambio surte efecto de inmediato, sin reiniciar.
  Una imagen así capturada se puede seguir limpiando: Ctrl+V la trae del
  portapapeles a la ventana.

---

## 0.10.37-alpha.20260821 – 21 de agosto de 2026

### Nuevo

- **Al anonimizar, ahora cada hallazgo lleva su propio número.** Hasta
  ahora todas las personas se llamaban `[NAME]`, todos los lugares
  `[ORT]`; con ello ya no se podía decir qué lugar pertenecía a qué
  valor, y no había nada que recuperar. Ahora los números siguen
  contando por aparición: el mismo nombre aparece en tres lugares como
  `[NAME_1]`, `[NAME_3]` y `[NAME_7]`. En el documento sigue sin poderse
  reconocer qué lugares pertenecen juntos, pero con el archivo de
  asignación se puede recuperar cada uno individualmente. Por ello el
  archivo de asignación vuelve a poder elegirse también al anonimizar;
  consérvelo separado del resultado.
- **Meses, días de la semana, monedas, unidades y formas jurídicas de
  empresa en los 48 idiomas de documento ya no se consideran nombres ni
  lugares.** Los nombres de calendario y de unidades proceden de Unicode
  CLDR (generados, no escritos a mano), las formas jurídicas del derecho
  de sociedades de cada país, también de varias palabras („sp. z o.o.",
  „Pty Ltd") y antepuestas („株式会社"). Donde un nombre de mes es a la
  vez un nombre de pila (Julio, Augusto, Mayo), decide la forma: con día
  o año al lado, una fecha; si no, un nombre. Además, tratamientos y
  títulos, fórmulas de despedida completas, tipos de documento y palabras
  base de calle para 28 idiomas con modelo de idioma propio, siglas
  legales (RGPD, UStG, ABGB, § 6 Abs 1 Z 27 UStG) y nombres de idioma
  como valor de campo („Idioma: Alemán"). Las listas están en „Ayuda →
  Listas de palabras…".
- **India: se reconocen dirección y código PIN** — „15 गांधी मार्ग", „नई
  दिल्ली 110001" igual que „15 Gandhi Marg, New Delhi 110001". El paquete
  de país India solo conocía hasta ahora números de identificación; en
  documentos en hindi las direcciones se quedaban por eso sin tocar.
- **Cada archivo de Office limpiado se abre una vez más como paquete
  antes de la entrega.** Un extracto de texto no nota si Word, Excel o
  LibreOffice rechazarían el archivo (entrada duplicada, XML roto, una
  parte faltante). Y se cuenta contra el original lo que una limpieza
  nunca puede cambiar: páginas de un PDF, hojas, filas y celdas de una
  tabla, diapositivas de una presentación. Si la prueba salta, aparece un
  aviso de ATENCIÓN en el resultado y en el informe de verificación; el
  original permanece intacto.
- **También la automática tacha el campo entero.** En modo de tachado, la
  barra en líneas cortas (bloque de dirección, celda de tabla, datos de
  cabecera) cubre la línea entera en vez de solo el valor encontrado: una
  barra del largo de la palabra revela cuánto medía la palabra. El rótulo
  e importes al lado se mantienen, y las líneas de texto corrido (más
  largas que la mitad del ancho de texto) se siguen tachando palabra por
  palabra, para que un nombre en mitad de una frase no ennegrezca la
  frase entera.
- **Lo recuperado vuelve a verse como en el original.** „Recuperar
  original" y „Deshacer sustitución" en el editor de PDF ahora reescriben
  la zona exactamente desde el archivo fuente: la misma fuente
  tipográfica, el mismo tamaño, el mismo color y posición, en un escaneo
  los mismos píxeles. Hasta ahora el texto se recolocaba en una fuente
  sustituta y se veía reconociblemente reconstruido. La barra de un
  tachado anterior desaparece por completo, en vez de cubrirse de blanco;
  un fondo de celda coloreado en una tabla se conserva. Esto también vale
  en páginas giradas, para texto de objetos de formulario incrustados y
  para **campos de formulario rellenados**: en la copia de trabajo
  rasterizada para ello, el fragmento vuelve de la página original
  renderizada de nuevo, también donde ninguna capa de texto conoce el
  valor del campo. También las **imágenes sustituidas** en el PDF vuelven
  así: pixeladas, difuminadas o eliminadas por completo, entera la imagen
  o solo el fragmento trazado. Solo donde el archivo fuente ya no está
  junto al resultado se mantiene la vía anterior.
- **Los valores tachados y eliminados sin sustituto también se pueden
  recuperar en Word, Excel, PowerPoint y OpenDocument.** Hasta ahora la
  recuperación necesitaba ahí un marcador en el texto; una barra o un
  hueco no tenían camino de vuelta. Ahora el panel de hallazgos ofrece
  las líneas „tachado" y „eliminado" en cuanto el archivo fuente intacto
  está junto al resultado: Maskuro compara el resultado con el original y
  vuelve a colocar el valor en el lugar de la barra o el hueco, con su
  formato incluido; una línea de ejecución partida se vuelve a unir.
  Vale igual para texto, HTML, correo y los adjuntos de Office de un
  correo; si el texto del correo lleva un marcador y el adjunto una
  barra, ambos se recuperan de una vez.
- **También los adjuntos PDF de un correo o un mensaje de Outlook se
  pueden recuperar**: marcadores (numerados y anónimos), barras y lo
  eliminado sin sustituto. Sin lienzo, el lugar procede del adjunto
  original; vuelve el valor exacto en cada glifo, en el orden de lectura
  del original.
- **Los valores enmascarados se pueden recuperar**, en el PDF y en la
  vista de texto. Una máscara („**** **** **** **** 3201") nunca es
  inequívoca, dos números llevan la misma; por ello la recuperación nunca
  toma el camino literal, sino que pregunta al original qué valor estaba
  en ese lugar. Hasta ahora esas líneas ni siquiera eran operables en el
  panel de hallazgos.
- **Las imágenes incrustadas en Word, Excel, PowerPoint y OpenDocument se
  pueden recuperar.** Un valor tachado en la imagen vuelve a través de su
  línea del panel; Maskuro lee la imagen original y recupera exactamente
  ese lugar; una imagen difuminada, eliminada o editada con rostros y
  códigos la recupera entera la nueva entrada „Recuperar imágenes
  incrustadas" del menú Editar desde el archivo fuente, también a través
  de los adjuntos de Office de un correo o un mensaje de Outlook. Una
  imagen que cuelga como adjunto propio y se tachó por reconocimiento de
  texto vuelve igualmente por su línea del panel.
- **Los valores inventados se pueden recuperar en la vista de texto.**
  Hasta ahora el panel comunicaba ahí „No es inequívoco". Ahora la
  recuperación busca el valor en el original y exige en ese mismo lugar
  del resultado exactamente el sustituto inventado; un nombre inventado
  nunca se sustituye literalmente en todas partes, podría estar en
  cualquier lugar como valor real.
- **La recuperación en Word, Excel, PowerPoint y OpenDocument conserva el
  formato del original.** Si un valor se extendía sobre varios
  fragmentos de ejecución („Anna" normal, „Musterfrau" en negrita y
  rojo), hasta ahora volvía entero al primer fragmento y perdía la
  negrita y el color. Ahora los caracteres se reparten de nuevo como en
  el original; un párrafo de Word queda después idéntico byte a byte al
  original. Lo mismo vale para páginas HTML, la parte HTML de un correo y
  el cuerpo HTML de un mensaje de Outlook (.msg); en el correo, además,
  se conserva el doctype, que la limpieza eliminaba hasta ahora en
  silencio.
- **Los archivos de texto conservan su codificación.** La limpieza y la
  recuperación escriben ahora `.txt`, `.md` y `.csv` en la codificación en
  que se entregaron: UTF-8 con y sin BOM, UTF-16, Windows-1252. Hasta
  ahora un archivo Windows-1252 siempre se convertía en UTF-8, y un
  archivo UTF-16 volvía dañado, incluso cuando no había nada que
  sustituir.
- **Las imágenes recuperadas conservan su modo de color.** Un escaneo en
  escala de grises vuelve como escala de grises en vez de como un
  archivo RGB tres veces más grande, una paleta como paleta, blanco y
  negro como blanco y negro; en toda la imagen con los mismos valores
  que en el original. Vale para archivos de imagen y para imágenes en
  PDF. CMYK y 16 bits permanecen en RGB, porque el resultado PNG no
  puede llevar ninguno de los dos.
- **Un marco en la imagen recupera toda la edición que toca.** Los
  rostros pixelados llevan un margen alrededor del recuadro reconocido;
  quien trazaba el marco solo sobre el rostro conservaba un anillo
  pixelado. Ahora el marco crece hasta el cambio contiguo respecto al
  original; basta un marco sobre la zona de los ojos. Las barras
  separadas al lado se mantienen; en una foto eliminada o difuminada por
  completo sigue rigiendo el marco trazado. Vale para archivos de imagen
  e imágenes en PDF.
- **Barras de tachado sobre toda la línea.** En el modo de línea del
  editor, la barra ahora recorre desde la primera hasta la última palabra
  de la línea, ya no solo sobre la palabra encontrada; una barra del
  largo de la palabra revela cuánto medía la palabra, y a partir de seis
  caracteres delante de un código postal se puede adivinar un nombre de
  lugar. Rótulos, importes y columnas de tabla junto al valor se
  mantienen; la barra cubre el campo, no la línea de la factura. El
  nuevo interruptor „Línea entera" junto a „Líneas de texto" vuelve al
  modo palabra por palabra cuando las palabras vecinas deben
  mantenerse; la elección se recuerda.

### Corregido

- **Las imágenes en páginas HTML y correos quedaban sin verificar; el
  nombre en el logotipo seguía legible tras la limpieza.** Una imagen
  incrustada en la página (dirección ``data:``) no se tocaba en absoluto,
  solo su texto alternativo; el logotipo en la rama HTML de un correo
  (imagen en línea sin nombre de archivo) pasaba por alto el filtro de
  adjuntos; y en el adjunto de imagen con nombre, la regla de imagen
  „difuminar"/„eliminar" no tenía efecto. Ahora las tres siguen el mismo
  camino que un archivo de imagen: reconocimiento de texto en la imagen
  conservada, rostros, códigos, metadatos y la regla de imagen. El
  informe nombra las imágenes, también el aviso si quedan sin verificar
  por falta de reconocimiento de texto, y „Recuperar imágenes
  incrustadas", así como la recuperación desde el panel de hallazgos,
  también conocen estas imágenes.
- **Un archivo de Office con imagen no se podía limpiar en absoluto si
  el reconocimiento de texto no dominaba el idioma.** En el Mac lee el
  reconocimiento de texto propio del sistema; para hindi, griego, croata
  o lituano no puede, y desde hace poco también lo dice; pero en Word,
  Excel, PowerPoint y OpenDocument eso interrumpía **toda** la limpieza,
  y no se generaba ningún archivo. El texto, sin embargo, se podía
  limpiar sin problema; solo la imagen no era legible. Ahora el archivo
  se escribe como con PDF e imágenes individuales, y en el resultado
  consta que las imágenes NO fueron verificadas, con el motivo y la
  referencia a „Gestionar idiomas".

- **En libros de Excel quedaban nombres en listas desplegables.** La
  lista de un campo desplegable (validación de datos) se limpia ahora
  como cualquier otro contenido de celda; las referencias a rangos de
  celdas permanecen intactas, para que el libro se mantenga íntegro.
- **Donde el marcador no cabía, aparecía una barra negra; ahora aparece
  una forma más corta.** `[NACI_1]` en vez de `[NACIMIENTO_1]`, y solo
  cuando ni siquiera la forma más corta cabe, se tacha. Una barra ya no
  le dice a nadie que ahí había algo; un marcador corto sí lo dice. El
  editor de retoque ya lo hacía; la limpieza automática hasta ahora no.
  El archivo de asignación registra ambas formas de escritura con el
  mismo valor, para que también lo acortado se pueda recuperar.
- **El primer clic en „Sustituir" dejaba la ventana de retoque parada un
  momento.** El reconocimiento que da al marcador su tipo (`[NAME_3]` en
  vez de `[BEGRIFF_3]`) se cargaba justo en ese momento, unos dos o tres
  segundos. Ahora se prepara en segundo plano al abrir la ventana;
  medido, de 2289 milisegundos pasó a 193.
- **Dos limpiezas simultáneas podían cargar el mismo modelo de idioma
  por duplicado**, por ejemplo la vigilancia de carpetas y la ventana
  principal. Como cada modelo ocupa varios cientos de megabytes, la
  necesidad de memoria se duplicaba brevemente con ello. Ahora la segunda
  ejecución espera al modelo de la primera.
- **El lugar en la línea de fecha ahora se elimina también cuando el
  modelo de idioma no lo reconoce por sí solo:** lo que se encuentra con
  seguridad como código postal con localidad („3335 Amstetten") arrastra
  su nombre de lugar por todo el documento, como un apellido a partir de
  un nombre completo. Y una sigla con cifra delante de un nombre („T3
  Hofbauer Christian") permanece legible, en vez de desaparecer dentro
  del marcador.
- **Se cerraron tres fugas de la relectura de un pedido real:** el
  gestor „T3 Hofbauer Christian" se consideraba encabezado de columna por
  la sigla „T3" y quedaba legible; un lugar que el modelo de lenguaje
  leía a través del salto de línea hasta el encabezado de columna se
  tragaba „Pos." y dejaba el nombre de pila del cliente sin tocar; y un
  nombre con tratamiento („Herr Robert Köttel") solo arrastraba el
  apellido, no el nombre de pila, y para eso cada „Herr". Las siglas son
  ahora solo letras, los nombres de dos palabras ya no son un
  encabezado, los hallazgos se recortan ante un encabezado de columna, y
  el tratamiento no cuenta como parte del nombre.
- **El lugar en la línea de fecha („Melk, 05.08.2026") justo debajo del
  bloque de dirección permanecía legible.** El modelo de lenguaje lo
  pegaba con el lugar de la línea de código postal en un solo hallazgo, y
  este caía entero contra el patrón de código postal. Ahora el resto que
  sobresale queda como hallazgo propio. Encontrado por la nueva
  relectura del resultado (`werkzeuge/zweitlesung.py`).
- **Mac: un escaneo en un idioma que el reconocimiento de texto propio
  del sistema no domina (por ejemplo hindi, griego, croata, lituano) se
  consideraba verificado.** Se leía con el recurso de respaldo inglés, la
  escritura extranjera permanecía en la imagen, y el informe decía „nada
  encontrado". Ahora dice „Imagen(es) NO fueron verificadas" con el
  motivo, y la gestión de idiomas ya no promete reconocimiento de texto
  para esos idiomas solo porque exista un archivo de idioma de
  Tesseract.
- **En el PDF, el signo de puntuación tras una palabra sustituida se
  mantiene.** De „Aufnahme am 01.03.2026, Entlassung am 04.03.2026." salía
  hasta ahora „Aufnahme am [DATUM_1] Entlassung am [DATUM_2]": faltaban la
  coma y el punto final, tanto con marcadores como con fechas
  desplazadas. Ahora solo se elimina el valor reconocido, no la palabra
  entera hasta el siguiente espacio; la coma, el punto y coma, el punto o
  el paréntesis que le siguen permanecen en su lugar, y el marcador no
  se extiende sobre ellos.
- **Ruso y ucraniano funcionaban sin notarlo con el modelo multilingüe
  más débil**, cuando faltaba un paquete auxiliar para el análisis de
  formas de palabra (`pymorphy3`); los propios modelos entonces no se
  podían cargar, y „Львів" se convertía en persona. Para el reconocimiento
  de nombres, el análisis de formas de palabra no es necesario; el
  modelo se carga ahora sin él, y los lugares vuelven a ser lugares.
- **Los avisos de licencia en 16 idiomas estaban desactualizados.** Ahí
  seguía diciendo que el código fuente MPL se entregaba „a petición",
  QPDF figuraba como MPL-2.0, faltaban siete componentes en la tabla
  (wordfreq, Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet),
  el párrafo de spaCy estaba en inglés, y al final colgaba una sección
  sustituta en inglés. Ahora las 18 versiones están al nivel de la
  alemana: archivos fuente permanentes en maskuro.com/quellcode/oss/,
  QPDF Apache-2.0, vía Qt-LGPL, origen de modelos. También la tabla en
  inglés tiene las líneas faltantes.

- **Palabras contractuales en genitivo alemán („des Angebotsinhaltes",
  „des Anbotes", „des Terminplanes") ya no se consideran lugar.** Una
  sola palabra tras un artículo de genitivo o dativo con desinencia de
  flexión es una palabra de categoría; los nombres de lugar no se
  flexionan („nach Graz"). Si el lugar aparece en otro sitio del
  documento sin artículo („Burgenland"), también „des Burgenlandes" se
  sigue reconociendo.
- **Los valores desplazados, enmascarados e inventados rasterizaban la
  página PDF.** La verificación posterior tras la eliminación solo
  permitía en el rectángulo de hallazgo un marcador entre corchetes; una
  fecha desplazada („01.07.2026") o un valor enmascarado („****1234") se
  consideraba un resto pasado por alto, y la página se convertía por
  precaución en imagen, no así con „Sustituir". Ahora esas páginas
  permanecen como texto, y la recuperación desde el panel o el marco
  vuelve a entregar el original.
- **Los valores sustitutos de varias palabras no se podían deshacer en
  el PDF a través del panel de hallazgos.** Un nombre inventado („Greta
  Mayrhofer") o un IBAN enmascarado („**** **** **** **** 3201") consta
  de varias palabras; la búsqueda de hallazgos comparaba palabra por
  palabra y comunicaba „El marcador no se encontró en el documento".
  Ahora se leen juntas las palabras consecutivas de la misma línea.
- **Tras recuperar un valor eliminado sin sustituto, su línea del panel
  se mantenía.** Los valores que la estrategia „tachar" en modo marcador
  elimina sin sustituto no tienen marcador con el que el panel pudiera
  medir una desaparición. Ahora la línea se tacha en cuanto el valor
  vuelve a estar en el documento.

- **Compuestos abreviados como „E-Helfer" o „U-Bahn" ya no se consideran
  nombre.**
- **Restos de separación silábica („Leis-") y compuestos larguísimos
  („Bauarbeitenkoordinationsgesetzes", „Baustellenkoordinator") ya no se
  consideran nombre o lugar.** En un texto de licitación escaneado se
  tacharon así 28 palabras menos.
- **Las listas de posiciones de ofertas escaneadas ya no se consideran
  un directorio de nombres.** La pasada adicional para directorios
  (líneas cortas) convertía „Kälterohr" y „Außengeräte" en personas;
  ahora se suspende en cuanto hay números de posición como „1.1.5" al
  inicio de línea. Las líneas de fecha en cadenas de correo no cuentan
  ahí como números de posición.
- **Encabezados de columna y números de posición de ofertas escaneadas
  („Pos.", „Pos. 1.1.3", las siglas „E/L/S") se consideraban nombre o
  lugar.** Una abreviatura sola en su línea, un rótulo junto con un
  número y letras sueltas por línea no lo son.
- **La página „respiraba" en la ventana de retoque tras abrir la lupa
  comparativa**: en „Ancho de página" y „Ajustar", la escala depende de
  la ventana de visualización, y eso cambia con cada barra de
  desplazamiento que aparece o desaparece; cada acción siguiente movía la
  página un poco. El lienzo lo compensa ahora automáticamente hasta que
  se estabiliza. Y los botones de zoom, el deslizador y los atajos de
  teclado mantienen el centro de la imagen incluso cuando al ampliar
  aparece una barra de desplazamiento.
- **Los escaneos guardados en horizontal ahora se leen en vertical, y la
  letra pequeña en escaneos grandes ya no se pierde.** Una oferta
  escaneada de 24 páginas conservaba legibles en cada pie de página seis
  IBAN bancarios, número de registro mercantil y NIF: el escaneo estaba
  girado 90° en el PDF, y el reconocimiento de texto omitía líneas
  enteras en imágenes muy grandes según su tamaño. Ahora se tiene en
  cuenta el giro visible y las imágenes grandes se leen en bandas
  superpuestas; los pies de página quedan en negro.
- **Las calles con nombre de persona con guion antes de la palabra base
  („Josef Admanseder-Straße 7", „Abt-Karl-Straße 8",
  „Dr.-Karl-Renner-Straße 12") se reconocen como dirección.** En el
  membrete de una oferta escaneada, una dirección así quedaba legible
  porque el patrón exigía un espacio antes de „Straße".
- **Los IBAN del reconocimiento de texto con una O en vez de 0 o una l
  en vez de 1 se reconocen ahora.** En letra pequeña de un escaneo, el
  reconocimiento de texto suele leer cifras como letras; el número
  tenía entonces la forma de un IBAN, pero el dígito de control no
  cuadraba, y quedaba sin tocar. Si falla el dígito de control, ahora se
  prueba la lectura con cifras; si entonces cuadra, es el IBAN. Los
  dígitos de control realmente incorrectos siguen siendo incorrectos.
- **Fragmentos de frase como „folgenden Codes auf der" se consideraban
  lugar.** Un nombre o lugar que empieza con una palabra en minúscula no
  lo es, salvo con partículas nobiliarias („van Gogh", „de Vries").
- **En el editor quedaba la última letra junto a la barra de tachado**
  („…6", „…t", „…g"), y la barra tenía la altura del marco trazado en vez
  de la de la línea. La causa: si el editor no podía medir la página,
  consideraba cualquier marco como „ninguna palabra alcanzada" y lo
  aplicaba exactamente, sin la regla de que media palabra nunca queda.
  Lo mismo ocurría con instrucciones de texto sueltas que el editor no
  podía ubicar. Ahora siempre cuenta además la caja de la palabra: lo
  que el marco solapa de forma sustancial cae por completo.
- **La última letra de una palabra sobresalía de la barra de tachado.**
  La barra se medía según el ancho de avance de las métricas de fuente;
  si la fuente dibuja un glifo más ancho, su resto quedaba junto a la
  barra. La caja de un carácter ahora también incluye el glifo dibujado.
- **El mensaje sobre convertir una página en imagen prometía
  demasiado.** „La presentación se mantiene igual" no es cierto tras
  rasterizar: la fuente y los gráficos se vuelven píxeles, el archivo
  crece. El mensaje lo dice ahora, y también nombra el segundo motivo por
  el que se rasteriza (la reconstrucción habría dañado la página).
- **El texto tras un valor eliminado se desplazaba hasta un punto hacia
  la izquierda.** Al reconstruir una línea, el inicio se medía por el
  borde del glifo, la continuación por el origen de trazo; el ancho de
  avance de la primera letra quedaba como error („C" 0,5 pt, „I" 1,0 pt).
  Ahora la reconstrucción calcula de forma continua con el origen de
  trazo; el resto de la frase queda al décimo de punto en su lugar.
- **Se reconocen el NIF austríaco con espacios („ATU 187 35901") y un
  número de registro mercantil sin „FN" bajo su rótulo („Firmenbuchnummer:
  30799v").** Ambos estaban escritos a mano en un formulario de
  licitación escaneado y permanecían legibles, aunque el reconocimiento
  de texto los había leído correctamente.
- **Las páginas PDF en horizontal se convertían en imagen sin motivo
  tras el tachado.** La verificación de integridad comparaba el original
  y el resultado en la vista girada, pero calculaba sus zonas de
  tachado sin girar; en una página con indicación de giro, el propio
  tachado quedaba entonces junto a su zona y se consideraba daño. Esas
  páginas ahora conservan su capa de texto y sus gráficos vectoriales.
- **También páginas rectas se convertían en imagen a veces sin
  necesidad**, cuando el texto tras un marcador se desplazaba un punto;
  algo permitido, pero la comparación de imagen era más fina que su
  propia tolerancia. Ahora compara en medios puntos y así cumple su
  tolerancia con exactitud: hasta dos puntos de desviación no activa
  nada, más allá sí.
- **Los datos en objetos de formulario incrustados permanecían sin
  tocar.** Algunas plantillas colocan el membrete o el pie de carta como
  formulario propio que la página solo incrusta. Un hallazgo ahí se
  planificaba y se contaba como eliminado, pero nunca se escribía; el
  texto seguía ahí, y solo el rasterizado de toda la página lo capturaba.
  Ahora se reescribe el propio formulario; un formulario que está en
  varias páginas, una sola vez.
- **Páginas PDF se rasterizaban a imagen aunque no había quedado nada
  legible.** Una oferta de siete páginas lo sufría en seis; crecía de
  73 kB a 3,3 MB y perdía su fuente en una imagen. La causa eran
  espacios que aparecen varias veces seguidas en el documento, pero que
  el lector solo comunica una vez: el texto tras un dato eliminado se
  desplazaba su ancho hacia la derecha, la verificación posterior
  encontraba la palabra vecina en el rectángulo de hallazgo y recurría al
  rasterizado. Los restos de línea conservados quedan ahora de nuevo
  exactamente en su lugar; la misma oferta se limpia ahora sin una sola
  página rasterizada (76 kB).
- **Nombres de clave y cabeceras de factura se consideraban personas.**
  En un archivo de acceso se sustituía el nombre de la variable de
  entorno („AWS_ACCESS_KEY_ID"), no solo su valor; en una factura en
  inglés, el encabezado „Bill to" caía como nombre de pila. Un
  identificador en versales con guiones bajos nunca es un nombre, y una
  palabra en una línea que en conjunto es un rótulo de campo, tampoco;
  el destinatario debajo se sigue encontrando.
- **La búsqueda en la ventana de retoque se atascaba en páginas PDF
  grandes.** Cada letra en el campo de búsqueda volvía a rasterizar la
  página, aunque solo cambiaba el resaltado. La imagen de página
  renderizada ahora se mantiene mientras página, zoom y vista sean los
  mismos, también el original en la lupa comparativa; hojear, hacer zoom
  y un nuevo estado de archivo se dibujan de nuevo como hasta ahora.
- **Los números de posición en ofertas se consideraban dirección IP o
  número de teléfono.** Una línea de artículo como „1.3.3.4 … 5-Port
  Gigabit Switch" convertía el número de estructura en dirección de red,
  porque „Port" contaba como entorno técnico; ahora solo cuenta como dato
  independiente („Port 80"), no como parte de palabra. Y „1.3.3.6
  216879" (número de posición más número de artículo) ya no se tacha
  como número de teléfono. Las direcciones IP y números de teléfono
  reales en esas listas se siguen reconociendo.
- **Las líneas de artículo en ofertas se consideraban código postal con
  localidad.** „35252 DIETZEL SALR" (número de artículo con fabricante) y
  „1000 AWG" (cantidad con sección de conductor) se tachaban en líneas de
  posición numeradas como dirección, porque una palabra en mayúsculas
  tras un número se consideraba nombre de lugar en versales. En listas
  de posiciones ya no ocurre; „1080 WIEN" en el bloque de dirección y los
  lugares en minúscula se siguen reconociendo en todas partes.
- **El reconocimiento adicional de nombres tachaba en ofertas líneas de
  rol y encabezados de columna.** „Partiestundensatz Monteur +
  E-Helfer" se consideraba persona 49 veces, el encabezado de columna
  „Pos. Bezeichnung Menge EH" se consideraba lugar 19 veces; un pedido de
  19 páginas quedaba con ello ilegible. Esos hallazgos en líneas de
  posición ahora caen si ellos mismos llevan caracteres que ningún
  nombre tiene (más, barra, cifra, sigla), también cuando la línea
  termina en un importe („Alternativ Markt … - PV/LS AC-Versorgung 1
  290,00"). Los nombres en directorios y listas, para lo que existe el
  nivel, permanecen intactos.
- **„Der Kunde" convertía en las condiciones comerciales cada „Kunde" en
  nombre.** Si el reconocimiento adicional de nombres incluía el artículo
  en el hallazgo, este se consideraba nombre de dos palabras y protegía
  las otras 35 apariciones de la misma palabra. Ahora se resta el
  artículo, y „der Kunde" cae como ya lo hacía „des Kunden".
- **Los rótulos se consideraban valor.** „E-Mail" se tachaba siete veces
  como dirección de correo, „Telefonnummer" y „Faxnummer" como número de
  teléfono. Una dirección sin @ y un número de teléfono sin cifras ya
  no cuentan.
- **Siglas de columna de una letra („L: 154,50", „S: 0,00") se
  consideraban nombre**, 25 veces en una oferta fotovoltaica. Una sola
  letra no es ni nombre ni lugar.
- **Páginas PDF se convertían en imagen con mucha más frecuencia de lo
  necesario.** Dos causas, ambas halladas en ofertas reales: si un PDF
  coloca cada glifo como instrucción propia y bajo ella hay un glifo de
  espacio sin carácter de texto, la asignación se desplazaba desde ahí
  en uno; del valor eliminado quedaba la última letra („ŠkodaTopCar**d**"),
  y la verificación posterior rasterizaba la página con razón. Y una
  palabra separada al final de línea („Datenschutz-") se consideraba
  desplazada por la marca de guion de la biblioteca de lectura. Ambos
  corregidos: una oferta de vehículo pasó de 4 páginas rasterizadas a 0,
  un pedido de 19 páginas de 7 a 0; la fuente sigue siendo fuente, el
  archivo se mantiene pequeño.
- **Se corrigieron otros dos motivos de rasterizado:** si un documento
  trae consigo una fuente llamada „F1", los marcadores sobre imágenes se
  ponían en esa fuente y eran ilegibles; ahora la fuente de rotulación
  propia recibe un nombre libre. Y si a la biblioteca de lectura le
  falta un espacio en mitad de una instrucción de texto larga, el lugar
  ahora se demuestra también con fuentes multibyte (mismo código, mismo
  carácter) en vez de adivinarse hacia el final; antes quedaba una letra
  del valor eliminado y el resto del texto se desplazaba visiblemente.
  Además dos últimos casos: una instrucción de docenas de glifos de
  espacio hacía que la asignación se descarrilara (el nombre después
  quedaba sin tocar), y un encabezado grande con ancho de avance no
  encontraba su primer carácter (el nombre de la empresa quedaba sin
  tocar). **De nueve ofertas reales, ya no se rasteriza ni una sola
  página**; antes eran 30 de 90.
- **Al rasterizar, las imágenes desaparecían bajo un bloque negro.** Si
  una página debe convertirse en imagen, se renderiza desde el original,
  y eso no conoce ninguna limpieza de imagen. Hasta ahora, por eso, *toda*
  superficie de imagen de la página caía bajo una barra, también las
  intactas. En una oferta, la dirección y dos logotipos de certificado
  estaban en la misma imagen de membrete; la barra se llevaba también los
  logotipos. Ahora se inserta la imagen ya limpiada: la dirección en ella
  está tachada, todo lo demás sigue visible. Una imagen eliminada deja
  papel blanco en vez de un recuadro negro.

- **Los escaneos limpiados se volvían varias veces más grandes que el
  original.** Cada imagen en la que se tachaba algo volvía al archivo
  como imagen bruta sin comprimir; en un escaneo de 24 páginas, con ello
  crecía de 11,8 a 52,9 MB. Las imágenes ahora conservan el tipo en que
  llegaron: una foto sigue siendo una foto, un escaneo de fax sigue en
  blanco y negro, una imagen sin color no se guarda como imagen en
  color. El mismo archivo mide ahora 15,6 MB, sin diferencia visible.

- **Los archivos PDF escaneados de equipos de oficina volvían como un
  patrón de rayas.** Esos escaneos colocan la fuente como una capa
  nítida en blanco y negro sobre una imagen en color gruesa; Canon,
  Xerox y Kofax construyen así sus archivos. Al tachar en la imagen, esa
  capa se reescribía mal; el resultado era ilegible. En una oferta de
  seis páginas afectaba a nueve de dieciséis imágenes. Ahora se trata
  correctamente, en su propio color, y los lugares tachados en ella
  desaparecen de verdad.

- **„Eliminar todas las imágenes" le quitaba el texto a una página
  escaneada.** La capa de fuente de tal escaneo es técnicamente una
  imagen; se eliminaba o difuminaba con el resto, y quedaba una hoja
  vacía. Ahora se mantiene; logotipos, sellos y firmas siguen
  cediendo.

- **La verificación de páginas PDF dañadas ya no rasteriza por un
  desplazamiento minúsculo.** Un fragmento de texto reanclado al
  limpiar puede desplazarse hasta dos puntos; la comparación de imagen
  lo contaba de todos modos como daño y reconstruía la página como
  imagen; con ello se perdían gráficos vectoriales como líneas de tabla,
  y sobre los hallazgos había una barra en vez de un marcador. La
  comparación ahora permite el mismo pequeño desplazamiento que la
  verificación de palabras; los daños reales se siguen detectando.

- **La recuperación de muchos valores seguidos ya no fallaba en
  Windows por „Acceso denegado".** Quien deshacía muchas líneas del
  panel en rápida sucesión en un archivo de Office podía fallar por un
  bloqueo de archivo pasajero del antivirus; el intercambio ahora espera
  brevemente esos bloqueos.

- **La vía de Windows para la transmisión de comandos terminaba al
  verificador en vez de verificarlo.** La comprobación de vida de la
  instancia en escucha enviaba en Windows, por error, un Ctrl+C real a
  su propio grupo de consola; ahora consulta al sistema sin señal.

- **Los rótulos de campo de varias palabras no surtían efecto, pero sí
  sus fragmentos.** „Date of birth", „Bank account", „Cuenta bancaria" y
  „Numero de cliente" estaban en la lista de rótulos, pero se
  descomponían ahí en palabras sueltas y por ello nunca coincidían;
  quedaban fragmentos de palabra como „de" y „of", que desde entonces se
  consideraban rótulo; pero „de" es parte de un nombre („Anna de
  Vries"). Ambas cosas corregidas: las expresiones ahora surten efecto
  como conjunto, los fragmentos han desaparecido.

- **Las fórmulas de despedida alemanas con „ß" se trataban como nombre
  de persona pese a estar en la lista.** Bajo „Herzliche Grüße" o „Mit
  freundlichen Grüßen" aparecía en el resultado un marcador, aunque
  ambas expresiones estaban desde siempre en la lista de exclusión. La
  causa era una forma de escritura que nunca coincidía en la
  comparación; afectaba a ocho entradas en cinco listas. Ahora todas
  surten efecto.

- **„John Staff" quedaba sin sustituir.** Un apellido que es a la vez un
  encabezado de columna en inglés era descartado junto con el filtro de
  rótulos. El encabezado sigue intacto, el nombre debajo se vuelve a
  sustituir.

- **Los valores de campos de formulario rotulados permanecen
  protegidos en el nivel de IA.** El árbitro local del nivel de IA
  recibía hasta ahora también para evaluación hallazgos cuyo significado
  ya confirmaba el rótulo del campo („Geburtsdatum:" sobre el valor), y
  podía descartarlos. Esos valores estructuralmente confirmados ya no se
  le presentan. El archivo de asignación indica ahora además, para cada
  sustitución, la vía de reconocimiento („comprobante").

- **Una página PDF cuyo texto conservado sufrió daño al limpiar ahora
  se reconoce y se reconstruye como imagen del original.** En algunas
  fuentes de generador, los fragmentos de texto conservados podían
  aparecer tras la limpieza como bloques negros o palabras juntas,
  aunque todos los datos a eliminar se habían eliminado correctamente.
  Maskuro compara ahora el resultado palabra por palabra y píxel por
  píxel con el original; una página dañada se sustituye por su imagen
  limpia, con barras de tachado sobre los hallazgos, zonas de imagen
  tachadas y texto buscable. La página sigue siendo legible, la
  eliminación fiable.

### Modificado

- **En las interfaces traducidas, cada término técnico se llama ahora
  igual en todas partes.** Para una misma palabra alemana había, según
  la ventana, dos o tres traducciones en paralelo: el registro de
  verificación se llamaba en noruego a veces „Revisjonslogg", a veces
  „Kontrollogg"; el nivel gratuito, a veces „Gratisnivå", a veces
  „Gratisversjon"; y de forma similar en una docena de idiomas más.
  Quien buscaba un ajuste lo encontraba en la siguiente ventana con otro
  nombre. Se unificó en la palabra que la interfaz usa de todos modos
  con más frecuencia.

  Con ello salieron a la luz lugares donde una palabra representaba dos
  cosas **distintas**: francés, griego y coreano usaban para „tachar" y
  „enmascarar" la misma expresión, precisamente donde el programa
  explica la diferencia („Tachar elimina sin sustituto, Enmascarar
  conserva la forma"). Ahora ambas están diferenciadas. Para sueco esa
  decisión sigue pendiente: ahí tachar se llama „maskera", la misma
  palabra que enmascarar.

- **La pregunta sobre el tipo de uso en el primer inicio ha
  desaparecido.** Poco después de iniciar aparecía una ventana
  („¿Privado o en la empresa?"), y en los ajustes había una línea al
  respecto. Ambas cosas ya no existen, sin sustituto. Un dato del que no
  depende nada indica erróneamente quién quiere la licencia equivocada,
  y quien es honesto no lo necesita; costaba a cada uno un clic en un
  momento en el que nadie piensa en tipos de licencia. Qué licencia es la
  correcta figura donde se decide: en la página de precios, en la caja y
  en la ayuda. Las organizaciones que despliegan Maskuro de forma
  centralizada siguen indicando el tipo de uso a través del archivo de
  directrices.

- **Los avisos sobre el tipo de licencia nombran el caso del que se
  trata.** La licencia privada es exclusivamente para uso privado;
  cualquier trabajo profesional o comercial necesita la licencia
  empresarial, también como autónomo sin empleados. Eso figuraba así en
  las condiciones de licencia, pero ni en el programa ni en la ayuda:
  ahí siempre se hablaba solo del dominio de empresa, y eso precisamente
  no cubre este caso; el equipo de un autónomo no pertenece a ningún
  dominio. El aviso al leer una licencia privada lo dice ahora, así como
  el capítulo de licencias de la guía y las preguntas frecuentes, que han
  recibido una entrada propia para ello. No se bloquea nada.

- **Las vías aún no entregadas están ahora reunidas.** Los ajustes han
  recibido una página „Desarrollador"; ahí están el reconocimiento
  máximo (IA) junto con su contraverificación, el catálogo de listas de
  palabras y la vigilancia de carpetas. Las tres están construidas, pero
  no probadas en la práctica; por eso solo son visibles con una licencia
  de desarrollador, y en todas partes a la vez: la página, las entradas
  de menú y el efecto en la ejecución dependen de la misma decisión. Sin
  esa licencia, un nivel de IA activado antes queda sin efecto; su
  ajuste no se elimina y vuelve a regir en cuanto se entregue la vía.

### Mejorado

- **„Qué se busca" muestra otras tres listas del reconocimiento de
  nombres.** Los tratamientos tras los cuales la palabra siguiente se
  lee como nombre; los títulos y cargos que después **no** son todavía
  el nombre („Herr Bürgermeister Huber"); y los ochenta rótulos
  multilingües con los que se reconocen números de expediente, trámite y
  caso. Los tres siempre surtían efecto, pero no se veían en el resumen.

- **„Qué se busca" muestra dos listas de palabras que faltaban hasta
  ahora.** Los tratamientos y títulos que convierten en nombre a la
  palabra anterior („Herr", „Frau", „Dr.") y las siglas de las
  organizaciones de normalización con las que Maskuro distingue una
  referencia normativa como „ÖNORM B 2110" de una persona. Ambas influyen
  en el reconocimiento desde siempre, pero no aparecían en el resumen.

- **Listas de posiciones, índices, enumeraciones de equipamiento y
  referencias normativas permanecen legibles.** El reconocimiento ahora
  ve la forma de la línea: un nombre adivinado en una línea de estructura
  („1.3.1 Energieerdkabel 1kV"), una línea de índice con puntos guía, una
  enumeración („- carga inalámbrica con anillo magnético"), sobre una
  línea de cantidad/precio, en un encabezado de columna o tras „mediante"
  es un término técnico y ya no se sustituye. Los nombres reales
  permanecen protegidos, por tratamiento, rótulo de campo y el
  comprobante en otro lugar del documento; en el corpus de medición
  ningún dato perdió su protección. En el corpus comercial, las falsas
  alarmas bajan así de 25 a 6.

- **Encabezados, rótulos de formulario y fórmulas de despedida se
  confunden con menos frecuencia con nombres, en alemán e inglés.** Las
  listas de palabras con las que Maskuro distingue términos técnicos de
  nombres de persona han crecido notablemente: rótulos de facturas,
  formularios y correspondencia oficial („Aktenzeichen",
  „Verwendungszweck", „Kostenstelle", „Sort code", „Subtotal"),
  encabezados de sección de solicitudes e informes („WERDEGANG",
  „QUALIFIKATIONEN", „SUMMARY", „REFERENCES"), tipos de documento en
  alemán e inglés („Auftragsbestätigung", „Niederschrift", „Timesheet",
  „Agreement"), así como formas imperativas de instrucciones („Sende…",
  „Select…"). El lado inglés estaba hasta ahora llamativamente escaso.

- **Los campos rotulados ahora revelan también qué contienen cuando el
  rótulo es compuesto.** „Lieferanschrift", „Rechnungsadresse",
  „Sachbearbeiterin", „Kontoinhaber", „Contact person" y „Billing
  address" asignan ahora el valor al lado o debajo al mismo tipo que el
  simple „Anschrift" o „Name"; en un formulario relleno con casillas eso
  es la diferencia entre encontrado y pasado por alto.

- **En la ventana de retoque, la rueda del ratón sigue avanzando en el
  borde de la página.** Quien sigue desplazando al final de una página
  llega arriba de la siguiente; quien retrocede al principio llega abajo
  de la anterior; con ello un documento se puede recorrer de principio a
  fin sin tocar los botones de página. El teclado (Av Pág/Re Pág) ya
  podía hacerlo; una breve pausa entre dos cambios de página evita que la
  inercia de un trackpad arrastre por la mitad del documento.

- **Las miniaturas de página en la ventana de retoque están centradas en
  su bandeja.** Hasta ahora se pegaban al borde izquierdo, y al
  ensancharla solo crecía el margen vacío de la derecha.

- **La barra de herramientas de la ventana de retoque muestra sus
  grupos.** Los separadores ahora tienen espacio y color, „Buscar" y
  „Aplicar a todas las páginas" aparecen como grupos propios junto a las
  herramientas, y „Aplicar" solo aparece ya en tipos de documento donde
  puede tener efecto. Cada entrada de la barra y los menús lleva ahora
  una imagen: „Líneas de texto" y la lupa comparativa han recibido
  iconos propios (la lupa compartía el suyo hasta ahora con
  „Antes/después"), además zoom, página entera, ancho de página, girar,
  hojear y los atajos de teclado. „Abrir con el programa del sistema"
  está ahora también en la barra junto a Imprimir; el camino del
  resultado terminado al programa habitual es un clic, no un recorrido
  por el menú.

- **En la limpieza del portapapeles vuelve a constar que hay que
  revisar.** En los ajustes, el aviso figura de forma permanente junto
  al interruptor: Maskuro puede pasar por alto datos personales o
  tratarlos mal, el texto pegado debe revisarse antes de compartirlo. Al
  activarlo, además lo menciona el mensaje, y se anota en el área de
  salida, también cuando no hay ningún icono ejecutándose en el área de
  notificación. En cada operación de copiar individual, deliberadamente
  no aparece: un aviso que llegara cincuenta veces al día ya no se
  leería después de la tercera vez.

## 0.10.36-beta.1 – 20 de agosto de 2026

### Mejorado

- **Los documentos comerciales técnicos ya no se tachan en exceso.** Cuatro
  frenos de reconocimiento, obtenidos de once ofertas y pedidos reales: los
  números de estructura („1.3.1.1") ya no se consideran direcciones IP, las
  referencias normativas („ÖNORM EN 62446") y los códigos de identificación
  ya no se consideran código postal o número de teléfono, y las palabras de
  rol tras artículos („el cliente", „del comitente") ya no se consideran
  nombres; en las condiciones comerciales de una oferta real, las 46
  palabras de rol vuelven así a ser legibles en lugar de tachadas. Las
  direcciones con indicativo de país („A 3390 Melk", „D-94032 Passau") se
  eliminan ahora por completo, en vez de dejar el código postal huérfano.

- **Las listas de palabras ahora se pueden consultar por completo.** En
  „Ayuda → Listas de palabras…" se pueden examinar las listas locales de
  reconocimiento y contraverificación, con idioma, propósito, fuente y
  contenido. Entre ellas también están las listas de Wordfreq, médicas,
  personales y gestionadas centralmente, así como las reservas de valores
  sustitutos inventados. El manual describe el catálogo en una sección
  propia.

- **Las líneas de archivo terminadas muestran el idioma de reconocimiento
  utilizado.** Tras „terminado" aparece ahora, por ejemplo, „Alemán" o
  „Inglés", para que una selección automática de idioma inadecuada se note
  de inmediato. Si tuvo que intervenir otro idioma instalado, una flecha
  muestra ambos idiomas.

- **La nueva lupa comparativa muestra al leer de inmediato el lugar
  correspondiente en el original.** Su fragmento ampliado del original
  sigue al puntero del ratón sobre el resultado, que sigue siendo editable;
  en texto, sigue al párrafo. La lupa se puede usar anclada al borde de la
  ventana o extraerse como ventana propia y maximizable. Su zoom se puede
  ajustar directamente entre 50 y 300 por ciento y se recuerda igual que la
  activación. „Restablecer" devuelve también una lupa maximizada o anclada
  de forma desfavorable a un tamaño manejable a la izquierda. Los valores
  originales sustituidos aparecen resaltados en amarillo en la lupa, para
  que las palabras afectadas llamen la atención de inmediato al leer. Una
  vez activada, se abre de nuevo en futuros documentos adecuados, incluso
  tras reiniciar el programa. El conmutador antes/después existente se
  mantiene en el menú de vista. El manual la describe en una sección
  propia.

- **Los avisos de código abierto y de modelos ahora son exactos por
  versión.** La construcción del paquete genera una lista de componentes
  legible por máquina junto con los hashes de los textos de licencia
  incluidos. Las fuentes MPL, el origen de los modelos, las revisiones
  fijas, los cambios y el SHA-256 se documentan por separado; los modelos
  descargados posteriormente reciben su comprobante de origen directamente
  en la carpeta del modelo. Las listas móviles de referencia de Tesseract y
  spaCy quedaron fijadas de forma permanente. Los artefactos de venta
  permanecen bloqueados hasta que todas las fuentes y anexos de modelos
  estén publicados y verificados.

- **El conjunto de datos local de wordfreq está completamente documentado
  en cuanto a licencia.** La construcción del paquete verifica la versión
  3.1.1, 39 listas pequeñas sin modificar, incluido CJK, y el mapa de
  caracteres chinos, contra cantidad, tamaño y suma de comprobación del
  manifiesto. El aviso de código Apache-2.0, la licencia completa
  CC-BY-SA-4.0, la atribución, las fuentes de datos y las listas grandes,
  Jieba y no compatibles omitidas están documentadas en el paquete.

- **Las palabras comunes de oración se tachan por error con menos
  frecuencia.** Un diccionario de frecuencia local sirve como
  contraverificación adicional cuando el reconocimiento de nombres toma un
  verbo, pronombre, artículo o preposición por una persona. El diccionario
  nunca decide solo: los sustantivos, los nombres de varias partes y los
  nombres en campos, listas y tras tratamientos siguen protegidos. Chino,
  japonés y coreano usan exclusivamente los límites exactos de token de sus
  modelos de idioma ya existentes; para idiomas no disponibles no se emplea
  ningún idioma de diccionario supuestamente similar. Para ello no se
  transmite ningún texto de documento a internet.

- **Los términos técnicos de producto y equipamiento ya no se confunden
  tan fácilmente con nombres o lugares.** La contraverificación local ahora
  combina frecuencia, categoría gramatical, formación técnica de palabras y
  campos temáticos. Así permanecen en el documento, por ejemplo,
  „Travel-Assistent", „Family-Bonus", „WLTP-Wert", „Easy-Start" y términos
  compuestos de número, titular o freno. Los componentes en inglés también
  se consultan localmente en texto técnico alemán; los nombres propios
  reales, los tratamientos y los campos de persona y lugar mantienen la
  prioridad. Además, una „garantía del fabricante de 2 años" ya no se
  considera una edad.

- **Los derechos de licencia de Qt/PySide ahora son completamente
  trazables.** El paquete del programa contiene además el texto completo de
  la GPL-3.0, las versiones exactas de Qt, una oferta de código fuente y
  una guía en alemán/inglés para sustituir las bibliotecas dinámicas,
  incluida la nueva firma local en macOS. Una compilación de venta queda
  bloqueada mientras los archivos fuente exactos de la versión entregada no
  estén disponibles en la propia página de código fuente.

- **La licencia y el estado de actualización ahora indican con claridad,
  para cada nivel, qué es válido.** En la ventana de licencia y en los
  ajustes de actualización figura si las actualizaciones están incluidas,
  hasta qué día llegan y si la versión en uso sigue siendo utilizable de
  forma permanente. Las licencias privadas ya no instalan, tras la fecha
  límite, ninguna versión aparecida después; incluso un instalador recién
  descargado reconoce, por su fecha de publicación fija incorporada, si la
  clave introducida lo cubre. La última versión privada cubierta sigue
  siendo utilizable de forma permanente. Si en cambio finaliza una
  suscripción empresarial, terminan el uso y las actualizaciones; el
  período de prueba y el nivel gratuito no se abren como atajo.

- **Las licencias privadas permanentes ahora encuentran también, tras una
  reinstalación, la versión correcta del programa.** Un catálogo de
  versiones firmado recoge todas las versiones estables y sus paquetes. Si
  el último instalador cubierto por la compra ya no está disponible, puede
  usarse automáticamente en su lugar exactamente la siguiente versión
  estable disponible más reciente, nunca una beta o nightly. En caso de una
  instalación demasiado nueva, el cliente puede instalar la versión
  permitida o pasar a la página de compra para un nuevo período de
  actualización; un retroceso nunca ocurre en silencio. Esto también se
  aplica a las instalaciones MSI gestionadas.

- **El tachado automático de rostros ahora está descrito con claridad.**
  La ayuda del programa y el texto de protección de datos denominan la
  función „Reconocer y hacer irreconocibles zonas de rostros" y la
  delimitan de identificación, reconocimiento, comparación facial,
  plantillas biométricas y bases de datos de personas o rostros. También
  advierten claramente de que el reconocimiento completamente local puede
  pasar por alto zonas o marcarlas por error, y que por ello el resultado
  debe revisarse visualmente. También en un archivo de imagen limpiado de
  forma individual, el informe de resultado indica ahora las zonas de
  rostro reconocidas y pixeladas; una falta de reconocimiento de texto ya
  no se describe erróneamente como archivo completamente sin modificar.

## 0.10.36-alpha.20260820 – 20 de agosto de 2026

### Corregido

- **Los datos anonimizados ahora pueden recuperarse por completo
  independientemente del orden.** La recuperación anterior buscaba el valor
  a través de anclas de texto visibles. En tablas densas, marcadores
  directamente contiguos y depósitos internos invisibles de Office/correo
  faltaban esas anclas; a veces un término solo podía recuperarse después de
  que otro texto en claro creara por casualidad un ancla nueva. Ahora se
  compara el resultado con el original por cada soporte de formato real con
  la asignación completa, y solo se escriben los lugares realmente ocupados
  del valor elegido.

- **Nombres, direcciones de correo, números y términos de verificación
  propios siguen siendo manejables de forma inequívoca incluso con
  reconocimiento superpuesto.** Si el mismo valor en claro está asignado a
  dos tipos, decide el marcador realmente presente en el lugar del hallazgo
  junto con la línea de la barra lateral pulsada. Un par valor/marcador no
  ocupado sigue quedando bloqueado con seguridad.

- **Los casos especiales de correo ya no dejan marcadores ocultos.** Esto
  vale para asuntos codificados en MIME, adjuntos de texto y nombres
  separados por marcado HTML en EML y MSG. El HTML en UTF-8 sin indicación
  de codificación propia tampoco se recodifica ya a mojibake en cada paso de
  edición en archivos de Outlook; los resultados anteriores ya escritos así
  siguen siendo recuperables.

### Mejorado

- **Una nueva matriz de verificación atiende cada línea anónima de la
  barra lateral por separado y deliberadamente al revés.** Comprueba los 14
  formatos de texto, ofimática, web y correo, así como PDF, y a continuación
  también fórmulas, atributos, relaciones, comentarios, cabeceras de correo,
  adjuntos y depósitos internos secundarios. La ejecución completa en macOS
  comprende ahora 149/149 scripts de verificación en verde.

## 0.10.35-alpha.20260820 – 20 de agosto de 2026

### Mejorado

- **Las mediciones de idioma ahora realmente comparan lo comparable.** El
  corpus de medición regular contiene los mismos 14 casos de documento con
  las mismas siete tareas de texto y cuatro tareas de imagen en alemán e
  inglés. Una ejecución completa repite exactamente esta matriz para los
  doce idiomas de corpus disponibles. Los formularios, tablas, chats y otras
  pruebas de estructura aún no traducidas por completo se conservan, pero se
  muestran por separado y ya no se mezclan en las cuotas por idioma.

- **La ejecución completa escribe un informe de medición propio por cada
  idioma.** Sin selector de idioma se comprueban deliberadamente alemán e
  inglés; `--alle-sprachen` solicita el corpus completo de doce idiomas y se
  interrumpe antes del primer documento si falta un idioma o un caso. Los
  resultados con el mismo nombre se guardan en carpetas de idioma separadas.
  El informe global indica, además de la tasa de hallazgos ponderada,
  también el promedio no ponderado de las tasas por idioma.

- **La comparación de idiomas abierta ahora también muestra su límite
  real.** En la ejecución regular con reconocimiento de texto, alemán e
  inglés eliminan 218/218 datos conocidos sin falsa alarma. La prueba
  completa con reconocimiento de texto y nivel alto elimina 1.255/1.308
  datos con 17 falsas alarmas; once idiomas alcanzan el 100 por ciento,
  hindi el 51 por ciento. Las cuotas completas anteriores se basaban en
  cantidades desiguales de documentos y valores de referencia y no son
  comparables con la nueva matriz.

## 0.10.34-alpha.20260819 – 19 de agosto de 2026

### Corregido

- **Los nombres que aparecen varias veces siguen accesibles en la barra
  lateral después de una sola restauración.** Hasta ahora, toda la línea del
  nombre desaparecía ya tras la primera restauración de un lugar `[NOMBRE]`.
  Los demás lugares con el mismo nombre quedaban entonces como marcador de
  posición y a veces incluso bloqueados, hasta que se restauraban otros
  nombres. Ahora la línea desaparece recién tras el último lugar; el texto
  claro ya restaurado no vuelve a anonimizarse automáticamente. Esto rige
  igualmente para una restauración colectiva parcialmente lograda y para la
  herramienta de marco en PDF.

- **«Deshacer sustitución» funciona también desde la vista previa de
  Office.** La página visible allí es solo una vista previa PDF efímera;
  ahora se modifica correctamente el documento de Word, hoja de cálculo o
  presentación subyacente, y luego se renueva la vista previa.

- **La restauración ahora recupera por completo también las contrapartes
  ocultas de un valor.** En archivos de Word, OpenDocument, Excel y
  PowerPoint, los mismos datos pueden estar además en fórmulas,
  comentarios, gráficos, valores de campo, textos alternativos y destinos
  de referencia; HTML, EML y MSG los llevan además en atributos, JSON,
  cabeceras de mensaje y anexos. Hasta ahora, según el formato, quedaba una
  parte como marcador de posición. Ahora cada dato ofrecido en la zona de
  resultados puede restaurarse de forma independiente y en cualquier orden.
  Los metadatos, historiales de cambios y cabeceras de transporte eliminados
  intencionalmente siguen eliminados por motivos de seguridad.

- **Al restaurar desde imágenes ya no queda una línea de borde negra.** El
  borde derecho e inferior de un marco se trazaban al copiar desde el
  original con un píxel de margen insuficiente cada uno. Las coordenadas
  ahora coinciden con el tachado.

### Mejorado

- **La verificación de lanzamiento ahora somete cada una de las 22
  extensiones de archivo compatibles a un recorrido completo.** Los
  archivos con contenido se limpian, se restauran todos los valores
  ofrecidos y luego se verifican a fondo. A esto se añaden manejo real de
  la barra lateral, comparaciones de imagen a nivel de píxel y un renderizado
  visible en LibreOffice de los siete formatos de oficina. Las pruebas de
  regresión pequeñas se mantienen donde cubren un caso propio de error o de
  seguridad; se ha eliminado una prueba HTML comprobadamente duplicada y la
  prueba del modo blanco y negro ya retirado.

- **El corpus de medición completo de esta versión está disponible para
  volver a medir.** El paquete contiene 294 documentos sintéticos en doce
  formatos y doce idiomas, 2.564 datos conocidos, cuatro listas de valores
  esperados legibles por máquina y una guía. La descarga en la página de
  calidad usa un nombre de archivo dependiente del contenido, para que los
  navegadores no entreguen por error una versión anterior desde la caché.

## 0.10.33-alpha.20260819 – 19 de agosto de 2026

### Nuevo

- **También en archivos de imagen se pueden recuperar ahora lugares
  concretos del original.** La herramienta de marco „Recuperar original"
  copia de vuelta los píxeles en la misma posición desde el archivo fuente
  intacto. El camino permanece bloqueado si falta la fuente o tiene otras
  dimensiones de imagen; así no puede insertarse contenido de un lugar
  desplazado.

### Mejorado

- **Las barras de tachado manuales encajan ahora por defecto en las líneas
  de texto.** Un trazo sobre varias líneas genera por línea una barra de
  altura uniforme y deja libre el espacio en blanco entre ellas. Para
  firmas, gráficos y otros casos especiales, „Marco libre" vuelve a la
  altura elegida libremente.

- **El editor explica el siguiente paso directamente encima del
  documento.** El aviso cambia según el tipo de documento y la herramienta,
  e indica si se espera un clic en una palabra, una selección de texto o un
  marco. Además, la herramienta, el puntero del ratón y la vista previa en
  vivo muestran ya antes de soltar lo que va a ocurrir.

### Eliminado

- **Se eliminó la salida en blanco y negro propensa a errores.** En
  algunos PDF, los campos de texto invisibles quedaban desplazados respecto
  a la página rasterizada; la aparente reducción del tamaño del archivo no
  compensaba ese riesgo de seguridad y presentación. La limpieza normal de
  PDF y el rasterizado selectivo de páginas problemáticas se mantienen.

## 0.10.32-alpha.20260819 – 19 de agosto de 2026

### Nuevo

- **La vigilancia de carpetas ahora sí funciona en segundo plano.**
  Entrada, salida y reglas están en una página propia bajo „Ajustes". Se
  inicia y se detiene desde el icono de Maskuro en la barra de tareas o de
  menú; la entrada aparece solo con la licencia habilitada para ello. La
  ventana de ajustes se puede cerrar después y la ventana principal
  minimizar al icono sin detener la vigilancia.

- **El editor de retoque ahora tiene un interruptor permanente de modo de
  aprendizaje.** Está en la zona de hallazgos y en el menú „Herramientas".
  Si se desactiva, no aparecen preguntas sobre crear reglas propias, ni al
  recuperar ni tras correcciones manuales. Maskuro recuerda la elección
  para todos los documentos que se abran en el futuro; la propia
  recuperación funciona sin cambios.

### Corregido

- **El gran modelo adicional se puede volver a cargar.** El almacenamiento
  público rechazaba con 403 el identificador genérico estándar de Python.
  Las descargas de modelos usan ahora la misma vía de red designada de
  Maskuro que los demás servicios propios; el archivo de casi 596 MB y su
  suma de comprobación no cambian.

- **Una lupa comparativa maximizada ya no queda como una barra estrecha
  pegada al borde superior al anclarse.** Antes de anclarla, su estado de
  ventana libre se normaliza. Un estado maximizado guardado también se
  devuelve a un tamaño modificable en la siguiente apertura.

- **Una recuperación colectiva en tablas y otros formatos de texto ahora
  sí recupera todos los valores seleccionados.** En marcadores
  anonimizados como `[EMAIL]`, Maskuro escribía los valores hasta ahora
  uno tras otro. En cuanto se sustituía el primero, avanzaban los números
  de todos los hallazgos restantes, pero el plan ya calculado seguía
  apuntando a los números antiguos. Con ello solo volvía una parte de la
  selección. Ahora todos los valores elegidos del mismo marcador se
  escriben conjuntamente y con números de hallazgo estables. Si un lugar
  se vuelve inequívoco solo gracias a otro valor recuperado, Maskuro lo
  vuelve a comprobar en la misma pasada; el orden de la selección ya no
  importa.

- **„Deshacer sustitución" ya no omite valores seleccionados en PDF.** Si
  un marcador estaba muy cerca de otra palabra, o si en el original una
  coma colgaba directamente del valor, la verificación de posición podía
  atribuir por error la palabra vecina o el signo de puntuación al valor.
  Al recuperar en conjunto, quedaban entonces marcadores y líneas de
  hallazgo sueltos. La verificación ahora se orienta por el inicio real de
  la palabra y también tiene en cuenta una rotación de página distinta
  entre el original y el resultado.

- **El texto de PDF recuperado conserva ahora su tamaño original.** Hasta
  ahora servía de referencia el marcador ya establecido en tamaño más
  pequeño; además, también regía para el texto original el límite máximo
  de 11 puntos pensado para marcadores. Ahora se toman del archivo fuente
  la caja original y el tamaño de fuente original, tanto con la
  herramienta de marco como al recuperar desde el panel de hallazgos.

### Mejorado

- **El aviso de revisión ahora nombra con más claridad el riesgo
  residual.** Dice expresamente que Maskuro puede pasar por alto datos o
  tratar mal algunos datos, y exige, antes de cualquier publicación o
  entrega, una revisión completa y, si es necesario, una corrección
  manual. Esto también vale para el texto del portapapeles y está
  reproducido por completo en las 17 traducciones.

- **El registro de verificación ahora arranca también dentro de sus
  líneas sin nombre de usuario.** El propio registro sigue desactivado
  hasta que una organización lo active de forma consciente. Después, sin
  una directriz empresarial adicional, ni en una línea ni en el nombre de
  un archivo mensual central aparece un nombre de usuario; ahí sirve para
  la separación segura un seudónimo no adivinable, derivado solo del
  secreto de perfil local aleatorio. El diálogo de licencia ya no
  recomienda la activación, presupone „Sin registro" y advierte de
  antemano sobre el comité de empresa, la representación del personal y
  la protección de datos.

- **Sustituir ahora nombra lo que sustituye.** Un nombre marcado se
  convierte en `[NAME_3]`, un lugar en `[ORT_1]`, un número de teléfono en
  `[TELEFON_2]`, en vez de convertirse todo, como hasta ahora, en
  `[BEGRIFF_n]`. El tipo se reconoce al hacer clic; si no es inequívoco
  (una palabra corriente, o un nombre *y* un lugar en una selección), se
  mantiene el término general. Un marcador que afirma un tipo que no es
  correcto sería peor que uno que no nombra ninguno.

- **Las herramientas de la ventana de retoque ahora tienen una tecla.**
  **S** tacha, **E** sustituye, **Z** recupera el original, **V**
  pixela. En la vista de texto actúan de inmediato sobre la selección, en
  la vista de página eligen la herramienta. **Las letras siguen el
  idioma** en el que usted maneja el programa (inglés B/R/O/P, italiano
  O/S/R/P), porque una regla mnemotécnica solo ayuda en el propio idioma.
  La tecla figura en el botón. Quien está escribiendo en la barra de
  búsqueda sigue escribiendo letras normalmente; ahí no actúan.

- **El programa comunica una vez al día en qué estado se ejecuta, sin
  ningún identificador.** Con ello contamos cuántas instalaciones se usan
  y cómo se reparten entre período de prueba, nivel gratuito y licencia.
  Se envían estado, sistema operativo, versión, canal, país, idioma,
  entorno y nivel de reconocimiento; **nada sobre sus documentos y nada
  por lo que se pudiera reconocer su equipo**. Dos comunicaciones suyas
  nos parecen comunicaciones de dos personas distintas; no se puede
  rastrear a partir de ahí un camino individual. Qué se envía exactamente
  y cómo se puede desactivar figura en el texto de protección de datos,
  punto 5.

- **Las páginas introducidas en horizontal ahora se enderezan por sí
  solas.** Una hoja que se escaneó torcida, sin registrarlo, se reconoce
  en el retoque por el flujo del texto y endereza la vista. Donde eso no
  es posible (en un escaneo puro sin texto legible), dos nuevas entradas
  en el menú „Vista" giran a mano (Ctrl+Mayús+L y Ctrl+Mayús+R). Solo se
  gira la visualización: en el archivo no cambia nada con ello, y tachar
  sigue afectando exactamente al lugar en el que se hace clic.

- **La compilación local lleva ahora sus licencias de forma completa y
  visible.** La construcción determina los paquetes de Python realmente
  incluidos, coloca sus textos de licencia junto con un resumen de
  versiones bajo `lizenzen` y se interrumpe ante cualquier laguna.
  También Qt, Tesseract y el modelo de rostros tienen sus textos
  necesarios; las condiciones del propio Maskuro se incluyen como
  contrato de licencia.

- **Ahora se ve en qué marcador está el cursor de texto.** Quien hace
  clic en un marcador lo ve iluminarse por completo, incluidos los
  corchetes y el número. El botón „Recuperar selección" ya se activaba
  antes con un simple clic; solo que no se veía qué marca había
  capturado. El resalte se mantiene incluso cuando el ratón se desplaza
  hacia el botón.

- **El puntero del ratón ahora indica qué herramienta está seleccionada.**
  Cuatro herramientas comparten la misma zona y el mismo gesto; hasta
  ahora todas tenían el mismo aspecto. Retícula significa tachar, mano
  cerrada sustituir, mano abierta recuperar.

- **Un documento de Office preparado ahora es rechazado por el propio
  programa.** Un archivo de Word, Excel u OpenDocument puede traer
  instrucciones que, al abrirse, incorporen a su texto un archivo ajeno
  de su equipo o saturen la memoria de trabajo. Ambas cosas ya se
  rechazaban hasta ahora, pero por la biblioteca XML incorporada, no por
  Maskuro. Ahora el propio programa lo decide, independientemente de qué
  versión de esa biblioteca esté en el paquete. Para documentos normales
  no cambia nada.

### Corregido

- **El panel de hallazgos ahora elimina los marcadores tachados.** Si por
  ejemplo se tachaba `[NAME_1]` en la ventana de retoque, su línea de
  valor permanecía hasta ahora a la derecha, aunque en el documento ya no
  hubiera un lugar así. La línea desaparece ahora con el último hallazgo;
  si el mismo marcador aparece todavía en otro lugar, se conserva.

- **Al recuperar en una página girada, la palabra vecina ahora se
  mantiene.** La barra de tachado sobresale intencionadamente un poco del
  texto; ese margen estrecho ya podía llevarse por delante una palabra
  contigua como „im". Ahora solo cuenta un solapamiento claro, no el
  contacto en el borde.

- **Una segunda sustitución en la misma línea se llevaba por delante lo
  que seguía.** Quien sustituía dos veces seguidas „Sachbearbeitung Quaxi
  Blubbo übernimmt" obtenía „Sachbearbeitung [ORT_1] [ORT_2]": la palabra
  que seguía había desaparecido sin sustituto, sin ningún aviso. La causa
  era el marcador contiguo: el resto de la línea empieza tras la primera
  sustitución con un espacio, y la búsqueda de su posición de texto
  capturaba el corchete de cierre del vecino. A partir de ahí todo estaba
  desplazado un carácter. Se veía afectada cualquier línea en la que se
  sustituyera o tachara dos veces, también al recuperar junto a ella.

- **Sustituir ya no tacha cuando el marcador es demasiado largo.** Si
  junto a la palabra no había espacio para `[BEGRIFF_2]`, la zona se
  cubría hasta ahora de negro, y con ello tampoco se veía ya que ahí
  había algo, y mucho menos se podía recuperar. Ahora se escribe una
  forma más corta: `[BEGR_2]`, `[BE_2]`, en último caso `[B_2]`. El
  número correlativo se mantiene en cada nivel; por él vuelve a encontrar
  el lugar la recuperación. Solo donde ni siquiera cabe la más corta, se
  mantiene la barra.

- **Sustituir dejaba el texto sin tocar si en la misma línea ya se había
  tachado antes.** Quien en la ventana de retoque recuperaba un nombre
  del original, sustituía de él el nombre de pila (ahí no había espacio,
  se puso una barra) y después sustituía el apellido, obtenía el
  marcador colocado, pero el nombre **no se eliminaba**. Solo se notó por
  el aviso de la revisión posterior. La causa era la propia línea: tras
  el primer tachado, su resto empieza con un espacio, y en eso la
  búsqueda de la posición de texto no encontraba apoyo. Esto afectaba a
  cada segundo tachado en la misma línea.

- **Un reconocimiento avanzado activado sin su modelo ahora se nota.** La
  casilla podía estar marcada mientras el modelo faltaba; los ajustes
  valen para cada instalación, pero el modelo está junto al programa. La
  limpieza se ejecutaba entonces sin ese nivel, sin decir nada al
  respecto. Ahora la casilla indica que falta el modelo, y el resultado
  lleva un aviso. Su elección hecha una vez se mantiene guardada: en
  cuanto el modelo esté cargado, vuelve a surtir efecto.

- **Al anonimizar, ahora se recupera el término correcto.** Quien
  sustituía varios términos a mano y después recuperaba uno de ellos
  obtenía siempre el **primero**: de „Schmidt" salía „Müller". La
  asignación recordaba solo una sustitución por marcador, y al anonimizar
  todos llevan el mismo marcador; el segundo término y cada uno de los
  siguientes se perdía. Ahora cada valor obtiene su propia línea, también
  en la lista de sustituciones, que antes era demasiado corta.

- **En tablas ahora también se puede recuperar.** En un CSV o una lista
  de personal, los marcadores están directamente unos junto a otros,
  separados solo por un punto y coma. Hasta ahora el programa no podía
  determinar ahí qué valor había estado en qué lugar, y se negaba: con
  `[NAME]` funcionaba, con `[GEBURTSDATUM]` y `[TELEFON]` no. Ahora
  descompone la línea en todos los marcadores. Si un lugar sigue siendo
  realmente ambiguo, sigue negándose: un valor reescrito de forma
  incorrecta sería peor que una información que no llega.

- **Y ahora se ve la negativa.** Estaba en gris apagado en el borde
  inferior de la ventana, y la frase era tan larga que se cortaba;
  parecía como si no pasara nada en absoluto. Las frases se han acortado,
  y la línea se ilumina unos segundos en el color de aviso.

- **Una recuperación ahora se mantiene también tras la siguiente
  intervención.** Quien, al anonimizar, recuperaba varios lugares y
  después sustituía otra cosa, encontraba todos los lugares recuperados
  de nuevo sustituidos y tenía que empezar de cero. La causa era la
  asignación: conservaba el valor, y el ajuste automático para marcadores
  uniformes lo volvía a recuperar en la siguiente escritura. Ahora rige:
  lo que usted recupera, queda recuperado; otros lugares del mismo valor
  no se ven afectados por ello.

- **En archivos de texto, Word, Excel y correo, ahora sí basta con un
  clic en el marcador.** El aviso al respecto ya figuraba en la versión
  anterior, pero el botón „Recuperar selección" seguía bloqueado mientras
  no hubiera nada marcado con exactitud; no se llegaba, pues, al camino
  que habría establecido la propia selección.

### Corregido

- **El registro de verificación ya no revela el nombre del archivo.**
  Registra los archivos deliberadamente como valor de dispersión en lugar
  de en texto claro, porque un nombre de archivo revela el cliente y el
  objeto del litigio. Pero ese valor de dispersión se podía confirmar por
  tanteo; una ruta no es un número aleatorio. Ahora entra en el cálculo un
  valor aleatorio de esta instalación: contar y distinguir en el registro
  sigue funcionando, recalcular desde fuera ya no.

## 0.10.31-alpha.20260819 – 19 de agosto de 2026

### Mejorado

- **También en archivos de texto y de hojas de cálculo el marcador de
  posición se enciende en rojo al señalarlo.** Hasta ahora, la vista previa
  roja solo existía en una página PDF. Ahora ambas vistas muestran lo mismo:
  lo que está en rojo es lo que afectará el próximo clic, y basta con hacer
  clic dentro para restaurarlo.

- **Basta un clic sobre una palabra: el rectángulo lo coloca el propio
  editor.** En la ventana de retoque, hasta ahora había que arrastrar un
  rectángulo sobre cada lugar. Ahora basta un clic: el marco se ajusta a la
  palabra y sigue siendo manipulable, es decir, se puede seguir ampliando o
  desplazando. Al pasar el ratón por encima, la palabra ya se enciende en
  rojo, de modo que se ve de antemano qué afectaría el clic. Donde no hay
  ninguna palabra, se arrastra un marco como antes.

- **Ya no hace falta apuntar con exactitud con el rectángulo.** Quien
  arrastra un rectángulo sobre un marcador de posición o un tachado
  siempre se refiere al lugar completo, nunca a la mitad. El marco crece
  entonces por sí solo hasta abarcar el conjunto que toca: todo el
  marcador de posición, toda la barra o, en una hoja escaneada, toda la
  superficie tachada. Nunca se vuelve más pequeño que el marco arrastrado.

- **Ahora el tachado se hace palabra por palabra.** Un marco sobre la mitad
  de una palabra tachaba hasta ahora solo esa mitad, y un nombre tachado a
  medias sigue siendo un nombre. Las palabras tocadas caen ahora por
  completo; la vecina queda intacta.

- **En texto y hojas de cálculo basta un clic dentro del marcador de
  posición.** «Restaurar selección» exigía hasta ahora marcar exactamente
  el marcador de posición junto con los corchetes. Ahora basta con
  colocar el cursor dentro; la selección salta visiblemente a todo el
  marcador de posición.

- **Bélgica se ha añadido como país.** Se puede seleccionar en los ajustes;
  a partir de ahora se reconocen los números de teléfono belgas, el número
  del Registro Nacional (con dígito de control), el número de IVA/empresa
  (con dígito de control), direcciones en ambos idiomas oficiales y el
  código postal con la localidad. Hasta ahora los números de teléfono
  belgas quedaban sin tocar porque el país ni siquiera figuraba en el
  catálogo.

- **El canal de actualización ahora indica cuán pronto recibe novedades, no
  cuán lejos.** Quien tenía seleccionado «Versión de prueba» no recibía
  siquiera la oferta de una nueva vista previa o de una nueva versión
  estable, y tenía que cambiar de canal a mano para enterarse. Ahora
  también se ofrece todo lo que es más fiable: «Versión de prueba» recibe
  versiones de prueba, vistas previas y versiones estables; «Vista previa»
  recibe vistas previas y estables. Nunca al revés: en «Vista previa» no se
  ofrece ninguna versión de prueba, aunque sea más reciente.

- **En la ventana de ajustes las líneas vuelven a estar más separadas.**
  Las cuatro páginas usaban espaciados propios en lugar de la retícula
  vigente en el resto del programa; en la página «Detección» en particular,
  las casillas de verificación quedaban notablemente demasiado juntas.

### Corregido

- **Los formularios PDF rellenados ya no aparecen vacíos en la edición
  manual.** Maskuro convierte para ello exclusivamente la copia de trabajo
  efímera en páginas estáticas: los valores introducidos se vuelven
  visibles y pueden tacharse de verdad; los campos de formulario legibles ya
  no quedan ocultos en el archivo. El original permanece interactivo y sin
  modificar. Esto rige ahora también para formularios XFA dinámicos: un
  PDFium compatible con XFA construye primero los valores y los saltos de
  página, y a continuación se genera un nuevo PDF compuesto exclusivamente
  por páginas estáticas de imagen. Si falla la construcción XFA, el archivo
  se rechaza de forma segura en lugar de abrirse aparentemente vacío.

- **«Cancelar» ahora también surte efecto durante la detección más
  precisa.** Hasta ahora el botón se bloqueaba al hacer clic, pero el
  proceso seguía calculando hasta el último bloque; en un archivo largo son
  minutos sin salida, y el botón parecía mientras tanto haber funcionado.
  Ahora el proceso termina en el siguiente bloque.

- **En archivos CSV ahora también se encuentran nombres aunque no haya
  espacio delante de ellos.** En `P-1000;Brunnthaler, Elisabeth` el número
  de personal queda pegado al nombre a través del punto y coma, y para la
  detección eso era una sola palabra sin ningún nombre dentro; en listas de
  personal, según la fila, el nombre completo quedaba entonces sin tocar.
  Los números de teléfono, las fórmulas y el número de columnas del archivo
  no se ven afectados.

- **Ahora se reconoce un nombre cuyo nombre de pila y apellido llevan
  ambos un guion.** «Marie-Luise Habsburg-Ott» quedaba sin tocar en medio
  de la frase, mientras que «Dragan Mitrović» sí se encontraba en la misma
  frase: precisamente la combinación de dos mitades unidas se le escapaba
  al modelo de lenguaje. Palabras compuestas como «Nord-Süd-Verbindung» o
  «Software-Entwickler» no se ven afectadas.

## 0.10.30-beta.1 – 18 de agosto de 2026

### Mejorado

- **El tamaño de fuente de la vista de texto ahora se puede ajustar de
  forma visible.** El deslizador abajo a la derecha, que hasta ahora solo
  hacía zoom en la vista de páginas, ajusta en la ventana de retoque, en
  archivos de texto y de Office, el tamaño de fuente (50–300 %), lo mismo
  que „Aumentar"/„Reducir" en el menú Vista. Ctrl+rueda del ratón siempre
  pudo hacerlo, pero eso solo lo sabía quien lo había probado; ahora el
  deslizador, la indicación y la rueda funcionan juntos.

- **En la apariencia oscura ahora hay una hoja blanca sobre una superficie
  de trabajo oscura.** Hasta ahora era al revés: alrededor de la hoja
  quedaba una superficie clara, y el propio texto aparecía claro sobre
  oscuro. Ahora la hoja se mantiene blanco papel con texto negro en ambas
  apariencias, como una página PDF, que en modo oscuro tampoco se vuelve
  oscura, y la superficie alrededor es oscura.

### Corregido

- **Tras un tachado en mitad de una frase, el resto de la frase ya no se
  pierde.** Quien en la ventana de retoque pasaba tres veces por el mismo
  lugar (sustituir, tachar, luego „Recuperar original") obtenía borrado
  el inicio de la frase: de „Rückfragen richten Sie bitte an das
  Rechnungswesen." quedaba „bitte an das Rechnungswesen.", sin aviso. Se
  veía afectado cualquier lugar del que ya se hubiera eliminado algo antes
  en mitad de una línea.

- **Un error de inicio ya no arrastra consigo el cierre.** Cuando la
  construcción de la ventana principal fallaba, después también fallaba
  el cierre desde el icono de la barra de tareas, y ese segundo error
  ocultaba en el informe de errores la causa real. Ahora el programa se
  cierra limpiamente también desde una ventana a medio construir, y los
  ajustes guardados quedan intactos con ello.

- **„Antes/después" ya no salta al inicio del documento.** Quien había
  desplazado hacia abajo en la ventana de retoque y cambiaba al original
  para comparar, aterrizaba de nuevo arriba del todo, y tenía que volver a
  buscar el lugar a mano. La vista ahora permanece en la misma línea, en
  ambos sentidos.

- **Al tachar quedaba la última letra en líneas de texto justificado.**
  Cuando una instrucción de texto dibuja más glifos de los que la
  biblioteca de lectura comunica como caracteres (en texto justificado
  suele tragarse un espacio), la asignación se desplazaba en uno, y de
  „Dr. Michael Handler aus Willendorf" salía „[NAME] r aus f": dos letras
  sueltas en mitad de la frase limpiada (hallado en un acta municipal
  real). La asignación ahora se verifica con el texto literal de la
  propia instrucción donde este es legible; ahí ya no se adivina.

- **„Lerchenfelder Gürtel 43/12" solo se eliminaba a medias.** Los
  patrones de dirección no conocían „Gürtel", „Kai", „Lände", „Zeile",
  „Markt" ni „Graben" como palabra base de calle, y el número de casa no
  podía llevar partes con barra (43/12, casa/puerta); el número quedaba
  junto al marcador. Ambas cosas se han completado; las direcciones de
  Viena y Salzburgo caen ahora por completo.

- **Las páginas web guardadas siguen siendo funcionales tras la
  limpieza.** Las direcciones que la carga diferida („lazy loading")
  guarda en atributos data (`data-lazy-src`, `data-lazy-srcset`) se
  sustituían como enlaces (dieciséis en una página municipal real), y las
  imágenes de la página después ya no cargaban. Las direcciones web ahora
  se mantienen ahí, igual que en `src` y `href`; los nombres, direcciones
  de correo y números de teléfono en atributos data se siguen
  sustituyendo.

- **Los documentos japoneses y coreanos se procesaban como chino.** El
  reconocimiento de idioma metía las tres escrituras en el mismo saco, no
  encontraba palabras funcionales en texto japonés (sin espacios) ni en
  coreano (con partículas pegadas), y entonces tomaba simplemente el
  primer idioma CJK del catálogo. Un acta municipal japonesa y un acta de
  sesión coreana se leían así con el modelo chino. Ahora decide la propia
  imagen de la escritura: kana significa japonés, hangul significa
  coreano.

- **Más desaciertos de la prueba de campo en otros diez idiomas:** cargos
  como „Primar", „Gradonačelnik", „Ordfører", „Başkanı" o „Δήμαρχος" ya no
  se consideran nombres de persona; los rótulos de campo turcos („Adı",
  „Soyadı") y las palabras de conversación griegas („Ωραία", „Βεβαίως") ya
  no caen; los números de resolución y de párrafo con fecha
  („323/25-6-2008", „27 30.09.2024") ya no son números de teléfono; y los
  fragmentos de frase con punto („10.An", „T.U.EE", „…pa") ya no se
  sustituyen como direcciones web.

### Nuevo

- **Informes de verificación automáticos, si se desea.** Una casilla en
  los ajustes (página „Programa") deposita por sí sola, tras cada
  limpieza, un PDF de informe de verificación, con marca de tiempo en el
  nombre, en una carpeta propia, nunca junto al resultado. A posteriori no
  se puede generar una hoja; quien lo necesita para el expediente, lo
  tiene siempre así. El depósito está desactivado por defecto.

- **El registro de verificación ahora se puede activar en el programa.**
  Al leer una licencia empresarial, Maskuro pregunta una vez si se debe
  llevar el registro; un comprobante solo vale si funciona desde el
  principio. Para ello hay un interruptor en los ajustes (página
  „Programa", visible con licencia empresarial o en el período de
  prueba); el archivo de directrices de la administración sigue vigente y
  puede forzar el valor como hasta ahora. Una línea de registro propia
  „activado" registra desde cuándo se lleva; con ello también queda
  documentado y firmado el inicio del registro. El registro sigue
  desactivado por defecto.

- **La bandeja de cifras muestra ahora lo que hizo el nivel de IA.** Una
  nueva línea indica cuántos hallazgos inciertos evaluó el modelo,
  cuántos conservó y cuántos descartó, y cuántos encontró adicionalmente;
  hasta ahora su trabajo era invisible si no se hacía clic en cada valor
  en el editor de retoque. Solo números, nunca valores ni justificaciones;
  sin trabajo de IA, la línea no aparece.

- **Ahora también se puede recuperar en correos electrónicos y páginas
  HTML.** En `.eml`, `.msg` y páginas web guardadas, hasta ahora no se
  podía deshacer un marcador; la aplicación lo decía con honestidad, pero
  precisamente el correo es el formato con más datos personales. Ahora la
  recuperación funciona igual ahí: desde el panel de hallazgos, con
  selección marcada y también con marcadores anonimizados. La rama HTML
  invisible de un correo (lo que Outlook realmente muestra) se actualiza
  con ello, para que la vista y el mensaje digan lo mismo.

- **El panel de hallazgos también recupera valores anonimizados, por
  valor.** „Deshacer sustitución" estaba bloqueado hasta ahora en archivos
  anonimizados, porque „[NAME]" representa a todos los nombres a la vez.
  Ahora la recuperación consulta en el original qué lugar pertenece a qué
  valor (en el PDF por las coordenadas del hallazgo, en la vista de texto
  mediante la comparación con el original) y recupera exactamente los
  lugares del valor elegido. Las líneas de los demás valores permanecen.

- **También los marcadores anonimizados se pueden recuperar
  individualmente.** Al anonimizar, todos los datos de un tipo se llaman
  igual; „[NAME]" representa a cada persona, y hasta ahora eso
  significaba: recuperar individualmente no es posible. Ahora se consulta
  el original, que de todos modos está junto al resultado: en la vista de
  texto, marcar el marcador y elegir „Recuperar selección"; vuelve
  exactamente ese lugar con exactamente su valor. Si el valor no se puede
  leer sin ambigüedad en el original, la aplicación lo dice, en vez de
  adivinar. Con ello sigue sin generarse ningún archivo de asignación.

- **La ventana de retoque se abre por sí sola tras la limpieza.** Ninguna
  herramienta lo encuentra todo; por eso la mirada de revisión sobre el
  resultado forma parte del caso normal, no de un clic extra. Quien no lo
  desee, lo desactiva en los ajustes bajo „Reconocimiento" („Mostrar el
  resultado después en la ventana de retoque").

### Mejorado

- **La selección de país pasa ahora a „automática".** Hasta ahora regía
  de fábrica el ámbito lingüístico de la interfaz; en un equipo alemán,
  por tanto, también los documentos neerlandeses o franceses se limpiaban
  solo con los reconocedores de DACH, y una dirección como
  „Universiteitslaan 1" quedaba sin tocar (hallado en actas municipales
  públicas reales). Ahora la selección de país se orienta por el idioma
  del documento; quien haya hecho una selección fija en los ajustes, la
  conserva.

- **Menos tachados por error.** Se elimina una serie de desaciertos,
  medidos con el corpus de verificación y con actas de sesión reales en
  seis idiomas: los nombres de empresa con forma jurídica („Musterfirma
  GmbH") ya no se consideran persona o lugar, sino organización; las
  fórmulas de despedida y los tratamientos sueltos („Saygılarımızla",
  „Buenas tardes", un „Frau" aislado) ya no son nombres; los cargos
  („Bürgermeister", „Sindaco", „Alcalde") se mantienen; los números de ley
  y de resolución („39/2015") y los importes con punto de miles
  („330.000") ya no son números de teléfono; los inicios de frase como
  „Envíame" o „Estarei" ya no caen como nombre; un hallazgo que atraviesa
  una línea vacía ya no cuenta como nombre. El número de factura de una
  factura se conserva como dato de comprobante; el número de cliente y el
  número de expediente siguen cayendo.

- **Antes de cargar el modelo de IA ahora consta para qué sirve.** El
  diálogo de recarga nombra las tareas del modelo (evaluar hallazgos
  límite, encontrar nombres adicionales, proponer reglas y perfiles) y
  dice abiertamente que no es un asistente de chat. Las preguntas
  frecuentes responden la misma pregunta en detalle („¿Qué puede hacer el
  nivel de IA, y qué no?"), en todas las versiones de idioma.

### Corregido

- **Los PDF de informe de verificación desde la línea de comandos ahora
  se pueden buscar en su interior.** En Windows, la vía de PDF sin
  interfaz arrancaba sin una sola fuente; cada carácter se dibujaba como
  un recuadro sustituto, y la hoja no llevaba texto legible: quien
  quisiera buscar algo ahí o copiarlo, no encontraba nada. Ahora, en ese
  caso, el informe recarga las fuentes del sistema; el texto está
  incrustado y es legible. Los informes generados desde la ventana nunca
  se vieron afectados.

- **„Recuperar original" sobre varias líneas de un escaneo dejaba franjas
  negras entre las líneas.** En una página convertida en imagen, el marco
  solo limpiaba las propias bandas de línea; los restos del tachado
  anterior quedaban en los huecos intermedios. Ahora el marco trazado se
  reparte por completo entre las líneas.

- **Un segundo marco sobre un marcador dejaba un resto rojo.** El
  marcador casi siempre es más ancho que la palabra que representa; quien
  tachaba después sobre el mismo lugar solo alcanzaba su inicio, y quedaba
  un fragmento como „RIFF_1]" en mitad de la frase, y la recuperación
  colocaba después el texto original en su lugar en vez de en el de la
  palabra. Un marcador recortado ahora siempre cae por completo.

- **En una página girada, tachar sobre un marcador borraba una frase
  ajena.** El marcador dibujado posteriormente se confundía al eliminarlo
  con el texto anterior: él mismo permanecía, aparecía el aviso „todavía
  está en el documento", y en otro lugar de la página desaparecía sin
  sustituto una frase que no tenía nada que ver con el marco. Un marcador
  ahora se vuelve a encontrar por su texto literal; con ello, la cadena
  „sustituir, tachar, recuperar" también funciona en páginas introducidas
  en horizontal.

- **El manual seguía recomendando `python3-tk` en diez idiomas.** En la
  resolución de problemas figuraba que bajo Linux quizá faltaba tkinter,
  un consejo de la época anterior a la interfaz Qt que ya no ayuda a
  nadie. Ahora en todas las versiones figura el mismo párrafo que en
  alemán: faltan las bibliotecas del sistema que Qt necesita para la
  representación.

- **El capítulo de licencias del manual estaba desactualizado en las
  dieciséis traducciones.** En diez idiomas todavía se leía que Windows
  Server necesita una licencia empresarial con acceso de servidor y que
  ahí no hay período de prueba ni nivel gratuito; desde que un puesto
  cuenta a una persona y no una máquina, ambas cosas son falsas. Además
  faltaban en todas partes las indicaciones de cuándo se libera un puesto
  ocupado, de que la licencia se confirma con regularidad y qué se
  transmite entonces, y la activación sin internet figuraba solo como
  resumen sin los tres pasos y sin la indicación de que el equipo trabaja
  después un año sin conexión.

- **Faltaban siete párrafos sobre el retoque en diez idiomas.** Quien leía
  la ayuda en danés, finés, francés, italiano, neerlandés, noruego,
  polaco, portugués, sueco o español no encontraba ni la vista de páginas
  para archivos de Office, ni „Tachar a mano", ni toda la sección sobre
  cómo el programa aprende de una corrección, incluida la tabla con los
  tres niveles. En „Qué se reconoce" faltaba en esas mismas diez versiones
  el camino a través del rótulo en el documento.

- **Con una licencia leída, el programa dejaba de iniciarse.** En lugar
  de la ventana aparecía „El programa no se pudo iniciar", y eso con
  cualquier licencia, sin importar cuál. La causa era la línea de la
  visualización de licencia que avisa poco antes de que expire el plazo
  de verificación; accedía a algo que ahí no estaba disponible. Sin
  licencia, en el período de prueba y en el nivel gratuito, el error no
  se producía, por eso solo ahora se ha notado.

- **En el formulario se mantienen los nombres de campo.** „Geburtsdatum"
  y „Anschrift" desaparecían junto con su valor: el marcador aparecía
  pequeño y rojo en el lugar del *nombre del campo*, y el campo debajo
  quedaba vacío. El nombre del campo no forma parte de los datos; ahora se
  mantiene, y el marcador aparece donde estaba el valor.

- **Los títulos de documento en idiomas extranjeros ya no se confunden con
  nombres.** Sobre un formulario italiano ponía „FATTURA", sobre uno
  español „PERMISO PARENTAL"; ambos se sustituían. La lista de palabras de
  documento solo conocía los equivalentes alemanes.

- **De una factura ya no desaparece ninguna posición.** „Materialaufschlag
  1  84,00" se tomaba por una dirección y se sustituía por un marcador de
  lugar; al comprobante le faltaba después una línea. Una línea que
  termina en un importe es una posición y no una dirección; las
  direcciones reales („Hauptstraße 1  120,00") permanecen intactas.

### Modificado

- **„Vigilar carpeta…" y la línea de comandos quedan retirados por
  ahora.** Ambos caminos están construidos y funcionan, pero ninguno de
  los dos está probado en la práctica: la vigilancia de carpetas nunca ha
  pasado por una prueba en Windows, y la línea de comandos pone en manos
  de un script dos docenas de opciones que nunca ha usado ningún usuario.
  Lo que modifica documentos sin supervisión no debe hacerlo sin haberse
  comprobado; por ello se retiran hasta que se recupere esa prueba. La
  entrada de menú falta, y `--wache` ya no aparece en `maskuro --help`.

- **Queda disponible lo que solo lee y lo que de todos modos se
  necesita.** El barrido de búsqueda (`--suchlauf`) y la verificación
  posterior (`--nachpruefen`) siguen funcionando en la línea de comandos;
  no modifican ningún archivo. Igual el inicio desde el Explorador, el
  menú contextual, el portapapeles y la ventana; en eso no cambia nada.

- **„Obtener del escáner" tiene ahora su propio capítulo en el manual.**
  Hasta ahora estaba al final de „Vigilar carpeta". En el Mac, el consejo
  ahí era dejar vigilar una carpeta; ahora es arrastrar las páginas
  leídas a la ventana.

### Corregido

- **„Recuperar original" sobre varias líneas destruía la estructura.** Un
  marco sobre un marcador, un título de puesto sin cambios y una segunda
  sustitución colocaban toda la zona de nuevo como **una** sola línea; de
  tres líneas salía una, y lo que ya no cabía se convertía en una barra.
  Ahora cada línea se recupera por separado.

- **Y el texto sin cambios permanece intacto con ello.** Quien arrastra
  sobre una sustitución *y* texto normal solo recupera la sustitución; el
  resto no se toca. También desaparece con ello el último resto del
  marcador antiguo; antes quedaba su corchete de cierre en mitad de la
  frase.

- **Al sustituir ya no quedan restos del texto antiguo.** En un
  encabezado en negrita aparecía después „1. R[BEGRIFF_2]ige [BEGRIFF_1]
  … che": el marcador estaba ahí, pero al lado, sílabas del original.
  Ahora se limpia la zona que usted enmarca, no solo las cajas de las
  palabras dentro de ella.

- **Un marcador anónimo ya no se recupera.** Al anonimizar, cada nombre
  lleva el mismo `[NAME]`. La recuperación tomaba la primera entrada que
  encontraba y la escribía en cada hallazgo; de „Georg Aigner" salía
  „Anna Musterfrau", es decir, un nombre falso en el documento. Ahora
  indica que ya no se puede decir a qué dato se refería; el documento
  queda intacto.

### Nuevo

- **„Recuperar original" ahora también actúa sobre una página
  rasterizada.** Si una página se había convertido en imagen, hasta ahora
  aparecía una negativa: el texto recuperado quedaría bajo la imagen de
  la página. Ahora se limpia el lugar en la imagen y se escribe el texto
  encima, como un marcador sobre un escaneo. El contenido procede en este
  caso del archivo original, que no está rasterizado.

- **„Recuperar selección" aparece ahora como botón propio.** Ya era
  posible antes, pero solo si por casualidad se marcaba un marcador y se
  pulsaba „Sustituir selección"; una función que solo se encuentra por
  casualidad no existe para el usuario.

### Modificado

- **En texto plano, CSV y mensajes de Outlook ya no hay „Tachar
  selección".** Estos formatos no pueden llevar una barra; el botón ahí
  colocaba un marcador y también lo decía, pero un botón que hace algo
  distinto de lo que dice su nombre no pertenece ahí.

- **Una herramienta ahora dice cuando no puede hacer nada en ese lugar.**
  Un marcador no se puede volver a sustituir, sobre un tachado no se
  coloca ningún marcador, y donde ya está el original no hay nada que
  recuperar. Hasta ahora estas acciones hacían algo que parecía tener
  efecto, pero no lo tenía.

## 0.10.29-alpha.20260817 – 17 de agosto de 2026

### Corregido

- **En la ventana de retoque ahora surte efecto cada marco que se
  arrastra.** Quien trabajaba dos veces en el mismo lugar —primero
  sustituir, luego tachar, luego restaurar el original— veía que su
  segundo y tercer movimiento se perdían sin más: el marco todavía
  manipulable del movimiento anterior lo interceptaba. Lo mismo ocurría al
  cambiar de herramienta, donde incluso la herramienta anterior seguía
  actuando en silencio.
- **Un marco arrastrado demasiado estrecho avisa de que es demasiado
  estrecho.** Hasta ahora la vista previa encendía en rojo una palabra, y al
  soltar no ocurría nada, sin ningún aviso.

- **Los mensajes de Outlook por fin se pueden retocar.** Un archivo `.msg`
  mostraba en la ventana de retoque «Este formato no se puede visualizar
  aquí»; era el único formato compatible sin ninguna vía para retocarlo a
  mano. Ahora el remitente, el destinatario, el asunto y el cuerpo del
  mensaje aparecen identificados en la vista y pueden marcarse y sustituirse
  como en cualquier otro formato de texto.

- **«Sustituir selección» se mantiene, en un correo electrónico, dentro de
  la selección.** Quien marcaba un nombre en el cuerpo del texto perdía con
  ello también el remitente y el destinatario de las cabeceras, y el
  mensaje nombraba un marcador de posición distinto del que aparecía en el
  texto. Ahora el valor marcado se sustituye en todas partes —también en el
  remitente, si figura allí— y nada más se toca.

- **Un marco sobre varias líneas ya no destruye el texto.** Hasta ahora se
  generaba un único marcador de posición en un solo lugar: de la palabra
  cortada quedaba un resto pegado, y de la segunda línea el texto
  desaparecía sin sustituto alguno: ni marcador de posición, ni barra, solo
  un hueco. Ahora cada línea recibe su propio marcador de posición con el
  valor que realmente figuraba allí.

- **«Restaurar original» ahora surte efecto también después de un
  tachado.** La ventana anunciaba éxito, y el texto nunca volvía a
  aparecer: la barra negra contaba como obstáculo, de modo que ya no
  quedaba sitio para el texto restaurado. Ahora la barra cede, y el texto
  restaurado aparece en negro como texto normal, no en rojo como un
  marcador de posición.

- **«Restaurar original» en un lugar no modificado ya no hace nada.**
  Quien arrastraba el marco sobre un texto en el que no se había cambiado
  absolutamente nada, obtenía el texto eliminado y reinsertado más pequeño
  y desplazado, y se anunciaba éxito. Ahora aparece el aviso de que no hay
  nada que restaurar.

### Novedades

- **También en Word, Excel, PowerPoint, OpenDocument y texto se puede
  tachar.** Hasta ahora allí solo existía «Sustituir selección»; una barra
  estaba reservada a la vista PDF sin que hubiera ningún motivo para ello.
  Donde una barra no se puede representar —en texto plano y en un mensaje
  de Outlook— el valor se sustituye como antes por un marcador de
  posición, y así consta también en el mensaje.

- **Marcar un marcador de posición lo restaura.** En la vista de texto
  (Word, Excel, PowerPoint, OpenDocument, texto) ahora basta con marcar el
  marcador de posición y pulsar «Sustituir selección»: el valor original
  vuelve. Hasta ahora, para eso, la ventana remitía al panel de
  resultados.

- **Los interlocutores en un acta de reunión se reconocen ahora también
  cuando su nombre es a la vez una palabra corriente.** «Gruber: La
  recepción se realiza la próxima semana.» se sustituía; «Bauer: Estoy de
  acuerdo.» quedaba sin tocar: el apellido parece para la detección un
  sustantivo común. Las líneas de aviso de la misma forma quedan intactas:
  de «Atención: la instalación debe apagarse.» no resulta ningún nombre.

- **Se decía «Está usando la versión más reciente» incluso cuando ni
  siquiera se había podido comprobar.** Si el servidor de actualizaciones
  rechazaba la consulta —porque llegaban demasiadas solicitudes desde la
  misma dirección de internet o porque él mismo estaba temporalmente
  averiado—, entonces el programa se quedaba parado en su versión antigua y
  afirmaba que era la más reciente. Exactamente eso ocurrió el 17 de agosto
  en un Mac: la 0.10.25 se quedó estancada mientras la 0.10.28 llevaba
  horas disponible.

  Ahora la ventana dice lo que ocurre, indica la hora de la próxima
  consulta, y advierte expresamente de que **no** está establecido si la
  propia versión es la más reciente.

  Casi nunca es culpa del propio equipo: en muchas conexiones, numerosos
  clientes comparten la misma dirección de internet, y el servidor los
  cuenta juntos. Por eso, en ese caso, Maskuro busca la lista de versiones
  por una **segunda vía** y casi siempre encuentra igualmente las versiones
  nuevas. Si persiste el rechazo, el servidor se deja en paz hasta la hora
  indicada, aunque se vuelva a pulsar el botón; insistir solo prolonga el
  bloqueo.

- **Las cantidades ya no se confunden con nombres de lugar.** En un
  contrato de servicios, «Vier-Tage-Woche» desaparecía tras un marcador de
  posición de lugar, justo en medio del objeto del contrato. Este tipo de
  combinaciones de palabras formadas por número y guion («Drei-Punkte-Plan»,
  «24-Stunden-Dienst») ahora se mantienen sin tocar. Las direcciones
  quedan excluidas de esto: un «Zwei-Brüder-Weg» se sigue sustituyendo.

## 0.10.28-alpha.20260817 – 17 de agosto de 2026

### Modificado

- **Los puestos de licencia ahora se cuentan de verdad.** Hasta ahora
  ningún puesto de trabajo se registraba jamás en el servicio de licencias;
  una licencia de diez puestos funcionaba en cualquier cantidad de equipos
  sin que nadie se enterara. Novedad: el equipo que inicia el programa
  ocupa un puesto; un puesto queda libre por sí solo tras **siete días sin
  inicio**, de modo que un equipo averiado o un empleado que se ha
  marchado no bloquean nada de forma permanente.

  Un pequeño exceso solo se **muestra y no se bloquea**: hasta un diez por
  ciento por encima del número comprado, todos siguen trabajando; el
  portátil nuevo junto al viejo que todavía sigue registrado no debe ser
  un caso para la línea de soporte. Quien se suma más allá de eso cae al
  nivel gratuito y se le informa de ello; los equipos que llegaron primero
  no notan nada.

- **Una licencia comprada se confirma con regularidad.** Si eso no se
  logra durante **30 días**, se aplica el nivel gratuito hasta que vuelva
  a lograrse. No se desactiva nada, y a partir de una semana antes aparece
  el aviso en la ventana. En cuanto el equipo vuelve a tener acceso a
  internet, esto se resuelve por sí solo. El período de prueba y el nivel
  gratuito siguen sin comunicar nada en absoluto; quien nunca compra,
  nunca llama.

- **„Activar sin internet" por fin funciona.** La activación se verificaba
  y se guardaba hasta ahora, pero después nadie volvía a leerla; no
  cambiaba nada en los derechos. Ahora es la salida para equipos sin
  acceso a la red: es válida durante **un año**, después se obtiene una
  nueva con un código de solicitud reciente. Para ello se necesita un
  dispositivo con internet una vez al año; el propio equipo permanece
  desconectado de forma permanente.

- **La activación ahora también se hace desde la cuenta de cliente**, en
  „Mis licencias" en el sitio web. Allí también figura qué equipos están
  vinculados a su licencia y cuándo se liberan de nuevo sus puestos; hasta
  ahora eso no se veía en ninguna parte. La página sin inicio de sesión
  sigue disponible para quienes no tienen acceso a la tienda; para ello
  exige además la dirección de correo del pedido, de modo que la clave de
  licencia sola no basta.

- **Y en la ventana ahora consta adónde llevar el código de solicitud.**
  El texto en papel decía „introducir en un dispositivo con conexión a
  internet" y no daba ninguna dirección; la página de activación existía
  desde hacía tiempo, pero no estaba enlazada desde ningún sitio. Ahora
  aparece **maskuro.com/lizenz-freischalten** en el diálogo, en el manual
  y en las preguntas frecuentes, y en el sitio web debajo de la clave de
  licencia.

- **El botón „Activar sin internet…" permanece visible**, incluso cuando
  la licencia no es válida en ese momento. Antes desaparecía junto con
  ella, justo cuando se necesita.

- **„Todos los puestos ocupados" ahora dice la verdad.** El aviso
  terminaba con „El programa sigue funcionando sin cambios"; eso ya no es
  cierto cuando no se ha asignado ningún puesto. Ahora indica que, hasta
  nuevo aviso, se aplica el nivel gratuito.

### Nuevo

- **Al activar la limpieza del portapapeles ahora se indica que hay que
  revisar.** El aviso menciona desde entonces la misma frase que aparece
  en el resultado de un archivo: Maskuro no reconoce en todos los casos
  todos los datos personales.

  Aquí pesa más que en otros lugares. Con un archivo se ve el resultado
  antes de compartirlo. Con el portapapeles no: se copia, se pega, y el
  texto limpiado ya está en la ventana de correo. Por ello el aviso indica
  expresamente revisar el texto **pegado**.

  Aparece al activarlo, no en cada operación de copiar: lo que aparecería
  cincuenta veces al día, nadie lo lee después de la tercera vez.

- **„Copiar todo" bajo la lista, y „Eliminar todo" se aparta.** El nuevo
  botón coloca de una vez todos los resultados terminados en el
  portapapeles, para adjuntarlos a un correo o pegarlos en otro programa.
  Hasta ahora eso solo era posible por el menú, y también allí solo para
  las líneas **seleccionadas**; quien quería decir todas tenía que pulsar
  primero Ctrl+A.

  Con ello, la fila de botones se reordena: a la izquierda está lo que
  añade algo, a la derecha, tras un espacio, lo que quita algo. „Eliminar
  todo" estaba hasta ahora justo al lado de „Añadir…", y un descuido
  costaba la lista entera. La misma regla rige desde el 13 de agosto en
  cada línea terminada.

- **Los puestos de trabajo sin internet ahora reciben sus modelos de
  idioma desde la propia organización.** Limpiar siempre funcionó allí sin
  conexión; recargar un modelo de idioma no, y un modelo pesa varios
  cientos de megabytes.

  La administración reúne una vez los archivos en un equipo con conexión y
  los coloca en un recurso compartido, en el despliegue o en una memoria
  USB. El lugar se registra de forma centralizada (campo `modellquelle` en
  `vorgaben.json` o la variable de entorno `MASKURO_MODELLQUELLE`). A
  partir de ahí, cada recarga se sirve primero de allí (modelos de idioma,
  el diccionario japonés y el nivel alto) y solo va a la red si falta un
  archivo.

  Las sumas de comprobación siguen rigiendo sin cambios. Un recurso
  compartido de archivos en la propia organización suele ser más fácil de
  falsificar que una publicación en la red; no debe convertirse en el
  camino más cómodo hacia un modelo colado.

  Cómo se crea tal repositorio y cómo funcionan la licencia y la
  activación sin internet figura en `OFFLINE.md`.

- **„Recuperar original": un marco recupera lo que se eliminó de más.**
  En la ventana de retoque hay una nueva herramienta: arrastrar un marco
  sobre el lugar, y el texto vuelve a estar ahí tal como estaba en el
  original.

  Esto cierra la brecha que dejaba abierta el panel de hallazgos. Allí una
  sustitución solo se podía deshacer si su marcador era inequívoco, es
  decir, no al anonimizar, donde „[NOMBRE]" aparece en cada dato de este
  tipo, y en absoluto en lugares tachados, donde no queda ningún marcador.
  Precisamente ahí se acumulan los descuidos: „Usuario", „Número de
  inventario", „Firma" se toman con gusto por nombres.

  El marco no necesita el marcador: el **lugar** proviene del rectángulo,
  el **contenido** del archivo original, el mismo que muestra el
  conmutador antes/después. Anonimizado o seudonimizado ya no importa.

  El texto recuperado aparece en negro, no en rojo: vuelve a ser texto en
  claro y no un marcador. Una entrada desaparece de la lista de hallazgos
  solo cuando su marcador ya no aparece **en ningún lugar** del documento;
  si el mismo valor se sustituyó en varios lugares, permanece para los
  restantes.

  En una página que se convirtió en imagen, la herramienta se niega y
  explica por qué: el texto recuperado quedaría bajo la imagen de la
  página y no sería visible.

### Corregido

- **Al contraer „Detalles" y „Cifras" quedaban restos de imagen en la
  pantalla.** Al contraer, una parte del contenido se desplazaba bajo el
  borde inferior de la ventana y permanecía ahí sobre el fondo, hasta que
  algo distinto se dibujaba encima.

  Ambas zonas tienen una altura mínima para ser utilizables cuando están
  abiertas. Pero el movimiento al contraer solo reducía la altura máxima,
  y una zona no se encoge por debajo de su altura mínima. El contenido
  seguía teniendo así 200 puntos de alto, mientras la ventana ya se
  reducía a 24; la diferencia quedaba bajo el borde. Ahora la altura
  mínima cede durante la duración del movimiento y vuelve después.

- **La ventana se volvía cada vez más pequeña al contraer y expandir
  repetidamente.** Al expandir, crece como máximo hasta el 92 % de la
  altura de pantalla; si el espacio es escaso, crece por tanto menos de lo
  necesario. Al contraer, sin embargo, restaba el importe completo de
  todos modos. Ahora se devuelve exactamente lo que costó expandir.

- **Un resto de un dato tachado podía quedar visible.** En un currículum
  quedaron legibles en el resultado los caracteres „*30.1" de
  „*30.12.1991", es decir, el día y el inicio del mes de la fecha de
  nacimiento. El programa incluso había detectado el resto y por ello
  había convertido la página en imagen; precisamente eso lo empeoraba,
  porque con ello el resto ya no era buscable, pero seguía siendo legible,
  y ya no se podía corregir.

  La causa estaba entre dos verificaciones. La más estricta de las dos
  comprueba si en la zona de un dato eliminado todavía hay algo que no
  debería estar ahí; comunica su hallazgo como un conjunto de caracteres,
  porque el orden de lectura se desplaza al sustituir. El recurso de
  respaldo, que cubre esos lugares antes de convertir, buscaba ese
  conjunto de caracteres como texto en la página, y nunca lo encontraba.
  Por eso no se cubría nada. El lugar se conocía todo el tiempo y ahora se
  transmite en lugar de volver a buscarse.

  Se veía afectada toda página cuyo resto solo fuera detectado por esta
  verificación, independientemente del tipo de archivo y del idioma.

- **En un escaneo introducido en horizontal, el reconocimiento de texto
  no encontraba nada.** Quien coloca una hoja de lado en el alimentador
  obtiene un archivo en el que la escritura está girada 90 grados. Hasta
  ahora Maskuro no leía en él **ni un solo** dato, y el archivo parecía
  después normal: no se encontró nada, así que no se comunicó nada, y la
  dirección seguía siendo legible en la imagen. Ahora el reconocimiento de
  texto endereza la página por sí mismo; en la imagen de verificación
  vuelven a caer todos los datos.

  Dos límites se mencionan abiertamente: una hoja **cabeza abajo** (180
  grados) sigue sin leerse, y en un escaneo muy deficiente el enderezado
  no ayuda; ahí hay demasiado poco legible para determinar siquiera la
  orientación. Cada imagen necesita para ello alrededor de una quinta
  parte más de tiempo.

### Modificado

- **„Instalar automáticamente" ahora significa lo que hace.** La casilla
  en los ajustes prometía más de lo que cumplía: descarga la nueva versión
  por sí sola e inicia la instalación, pero esta se ejecuta de forma
  **visible** y requiere confirmación, en Windows incluida la consulta del
  control de cuentas de usuario. Quien leía „automáticamente" contaba con
  un equipo que se actualiza solo durante la noche, y por la mañana se
  encontraba con el asistente de instalación. La casilla ahora se llama
  „Cargar actualizaciones automáticamente e iniciar la instalación", con
  una frase debajo que explica lo que eso significa. El comportamiento no
  cambia: que Maskuro no se sustituya a sí mismo sin avisar es
  intencionado y sigue siendo así.

## 0.10.27-alpha.20260817 – 17 de agosto de 2026

### Nuevo

- **Nuevo: `--ersetzen` para la conexión con un programa de gestión de
  bufetes.** El resultado ocupa el lugar del archivo de origen, en vez de
  crearse junto a él. Así funciona el registro de salida y entrada de un
  programa de gestión de bufetes ("Abrir y editar" en el expediente
  electrónico) sin ninguna interfaz: el programa entrega el archivo y lo
  recupera limpio en el mismo lugar.

  **Este interruptor anula el primer principio**, y por eso solo existe en
  la línea de comandos —no en la ventana— y solo si su administración lo
  autoriza (entrada `ersetzen` en el archivo de valores predeterminados).
  Sin autorización, la llamada se interrumpe e indica por qué; crear
  silenciosamente un segundo archivo sería el error más grave, porque
  entonces se volvería a registrar la versión sin depurar.

  Primero se escribe un archivo vecino; solo cuando está terminado ocupa el
  lugar del original. Una interrupción o un error dejan así el original
  **byte por byte sin modificar** y no deja ningún fragmento. En el
  protocolo de verificación la sustitución figura como campo propio —un
  verificador debe saber que la versión no depurada ya no está aquí.

- **El manual ahora explica la advertencia de Windows en el primer
  inicio.** Nueva primera sección "Windows advierte en el primer inicio: qué
  hacer", con dos imágenes y tres pasos: "Más información" es un pequeño
  enlace, no un botón —justo ahí se atasca la mayoría—, luego "Ejecutar de
  todas formas".

  Que allí figure "Editor desconocido" es todo el mensaje de la advertencia:
  los paquetes se distribuyen por ahora sin certificado. Nos parece más
  correcto explicarlo que ocultarlo.

- **La ruta de retorno ahora detecta cuándo el texto y la asignación no se
  corresponden.** Quien pegaba la respuesta en otro caso recibía hasta ahora
  nombres ajenos en el texto correcto —sin error, sin aviso, solo
  incorrecto. Maskuro ahora recuerda qué marcadores generó realmente la
  última ejecución y avisa de cada uno que no pertenece a ella. Si ninguno
  proviene de la última ejecución, no se inserta nada y la ventana explica
  por qué —en lugar de suponer, como hasta ahora, un plazo vencido.

  **Queda un límite, y también figura en el manual:** los marcadores se
  numeran por ejecución, así que el primer nombre se llama `[NAME_1]` en
  cada documento. Si el texto ajeno contiene solo esos marcadores, la
  confusión no se puede detectar.

- **El PDF ahora puede generarse en blanco y negro.** Una casilla en el
  modo de funcionamiento convierte cada página en una imagen en blanco y
  negro —con una capa de texto invisible debajo, por lo que sigue siendo
  legible y buscable. Para el envío por beA y vías similares con límites de
  tamaño estrictos: según nuestro corpus de medición, en promedio **68 %
  más pequeño** (línea de comandos: `--monochrom`).

  **Cuánto se gana depende del documento** —y eso también figura junto a la
  casilla: lo escaneado y lo que contiene imágenes se reduce mucho, un
  documento de texto ligero sin fuentes incrustadas puede incluso volverse
  más grande. Pruébelo con un archivo antes de activarlo para un lote.

  El precio: cada página se recalcula —con mil páginas eso tarda minutos. Y
  las ilustraciones pierden todo lo que hay entre el negro y el blanco;
  para texto es indiferente, para una fotografía no.

- **La lista de coincidencias en la ventana de revisión ahora lleva la
  cuenta.** Sobre la lista figura "5 coincidencias", y en cuanto filtra, "1
  de 5 coincidencias". Esa es la diferencia entre "he filtrado" y "son
  cinco, y las he visto todas" —el gesto con el que se comprueba si un
  nombre realmente se sustituyó en todas partes.

- **El protocolo de verificación ahora se puede buscar y filtrar.** La
  vista bajo "Archivo → Protocolo de verificación" tenía hasta ahora una
  tabla y nada más —con un mes de tres mil ejecuciones se veía que había
  pasado mucho, pero no qué.

  Nuevos son un **campo de búsqueda**, **tres filtros** (procedimiento,
  resultado, tipo) y la **paginación**, además de tres columnas que antes no
  existían: **procedimiento** (tachado o sustituido), **confianza** y
  **duración**. Sobre la lista figura cuánto se ve en este momento y cuánto
  oculta el filtro.

  "Guardar como CSV…" ahora exporta **lo que se muestra**: quien ha
  filtrado recibe lo filtrado, y el mensaje indica la cantidad.

  Un guion en confianza o duración significa que para esa fila no se midió
  nada —por ejemplo, porque es anterior a esta función. Estos valores
  **no** se calculan a posteriori. Sigue sin existir un filtro por usuario;
  aun así, la búsqueda encuentra una fila individual.

### Eliminado

- **La nota de transparencia en la ventana "Acerca de este programa" ha
  desaparecido de nuevo.** Figuraba allí desde 0.10.22-beta.1 e indicaba que
  la aplicación se desarrolló con apoyo de inteligencia artificial. No es
  obligatoria en ninguna parte, y precisamente en una aplicación de
  protección de datos, algunos la leyeron como una afirmación sobre el modo
  de funcionamiento —como si los documentos fueran a un servicio en la
  red. La depuración sigue realizándose exclusivamente en el propio
  ordenador; eso figura donde corresponde, en la pestaña "Privacidad".

### Corregido

- **El programa sustituía su propio icono por uno peor.** Quien registraba
  el menú contextual desde el programa tenía después un icono distinto en
  la barra de tareas al que quedaba tras la instalación —parecido, pero con
  barras alineadas a la izquierda en vez de centradas y visiblemente más
  tosco. Detrás había una solución de emergencia: si el programa no
  encuentra la plantilla del icono, se dibuja uno él mismo. Estaba pensado
  para el caso de que **no** hubiera ningún icono; en realidad dibujaba
  también cuando los incluidos ya estaban presentes —y los sobrescribía. En
  una versión instalada desde el instalador no existe plantilla, así que
  allí afectaba a todos. Los iconos existentes ahora permanecen intactos.

  **Las instalaciones ya afectadas no recuperan el icono correcto por sí
  solas** —para eso hay que reinstalar una vez.

- **"Identificación de objeto: OB-4711-22" se consideraba nombre de
  usuario.** El reconocedor de nombres de usuario comprobaba sus
  etiquetas sin límite de palabra delante —así que capturaba **cualquier**
  palabra que terminara en una de ellas: identificación de objeto,
  identificación de vehículo, identificación de dispositivo. El valor
  detrás se eliminaba aunque no tuviera nada que ver con un nombre de
  usuario.

  Las composiciones que realmente se querían capturar —"identificación de
  usuario", "identificación de acceso"— figuran individualmente en la lista
  y se siguen encontrando.


- **En inglés, griego, japonés y coreano, dieciséis marcadores aparecían en
  alemán en el resultado.** Quien había puesto la interfaz en uno de estos
  cuatro idiomas recibía, para los tipos de datos más recientes, las
  etiquetas alemanas escritas en el documento —de una contraseña resultaba
  `[ZUGANGSDATEN_1]` en vez de `[CREDENTIALS_1]`, de una clave de
  diagnóstico `[DIAGNOSESCHLUESSEL_1]` en vez de `[DIAGNOSIS_CODE_1]`.
  Afectados: salud, diagnóstico, medicación, claves de diagnóstico y de
  medicamento, religión, sindicato, opinión política, derecho penal,
  credenciales, nombre de usuario, datos de tarjeta, coordenadas,
  profesión, importe y característica.

  Los otros 44 idiomas nunca tuvieron el error: obtienen sus etiquetas de
  los archivos de idioma, donde estos tipos figuraban desde el principio.
  Precisamente estos cuatro idiomas llevan tablas propias por otro
  motivo —su escritura no sobrevive al juego de caracteres del PDF, por lo
  que allí figuran etiquetas latinas—, y en esas tablas faltaban
  sencillamente los tipos nuevos.

  Se detectó al traducir la página del catálogo: el sitio web prometía a
  los lectores en inglés etiquetas que el programa no escribía. Una prueba
  automática ahora contrasta las cuatro tablas con la lista de todas las
  etiquetas que pueden llegar a generarse.

- **La ventana de reglas ya no se abre demasiado pequeña para su
  contenido.** En la pestaña "Patrones de búsqueda propios", la línea
  explicativa del asistente ("Se busca: …") quedaba medio oculta detrás del
  campo "Texto de prueba" —precisamente la frase con la que, sin
  conocimientos de expresiones regulares, se comprueba si la regla propia
  busca lo correcto. La ventana tenía un tamaño mínimo fijo de una época
  con menos pestañas y por eso se podía reducir por debajo de lo que cabía.
  Ahora se ajusta a su contenido y solo se hace tan pequeña como para que
  todo siga siendo legible.

- **Los nombres en fórmulas de tablas ya no permanecen.** Una celda tiene
  más de un lugar para el texto, y hasta ahora solo se despejaba uno. Si
  había un nombre en una fórmula —`="Frau "&"Sieglinde Ortner"`— o era el
  último resultado calculado de una fórmula, permanecía sin cambios en el
  libro, aunque la misma persona estuviera sustituida en la celda vecina.
  Quien hacía clic en la celda lo leía en la barra de edición.

  Ambos casos se sustituyen ahora. Solo se toca lo que está entre comillas:
  las referencias de celda, los nombres de función y los nombres de hoja
  permanecen intactos, `=SUMME(K2:K6)` sigue calculando. Como el mismo
  nombre recibe en todas partes el mismo marcador, `=SUMMEWENN(A:A;"Huber";B:B)`
  también sigue encontrando sus filas.

- **Los gráficos ya no muestran nombres.** Un gráfico guarda una copia
  propia de las etiquetas de sus ejes —sigue dibujando incluso cuando las
  celdas de origen ya están vacías. Debajo de las barras seguían figurando
  cinco nombres de personas, mientras la tabla de encima estaba limpia.
  Vale tanto para hojas de cálculo **como** para presentaciones.

- **Los rangos con nombre que contienen texto fijo se despejan.** Un rango
  con nombre puede contener texto fijo en vez de una referencia de celda;
  si allí había un nombre, permanecía. El **nombre** del rango sigue
  permaneciendo —a él hacen referencia las fórmulas, y un cambio de nombre
  provocaría un error de referencia. Al igual que con el nombre de la hoja,
  se notifica, no se sustituye.

- **Una fecha de nacimiento reconocida una vez desaparece en todo el
  documento.** Una fecha por sí sola no dice nada —solo una palabra clave
  la convierte en fecha de nacimiento, y precisamente por eso una fecha de
  factura permanece intacta. Pero si el mismo dato figuraba una segunda vez
  en el mismo documento sin esa palabra —en el título de una imagen, en un
  campo de formulario rellenado—, permanecía allí, aunque unas líneas más
  arriba "nacido el …" se hubiera reconocido sin lugar a dudas. Solo se
  traslada lo que en **este** documento ya se reconoció como fecha de
  nacimiento; sigue sin adivinarse nada.

- **Los datos estructurados en páginas web revelan la fecha de
  nacimiento.** En el bloque JSON-LD para motores de búsqueda, la fecha
  figura bajo la clave `birthDate` —la clave indica qué es, igual que en
  otros casos el encabezado de columna. Ahora se lee también; "Birthday" y
  "Birthdate" valen así también en formularios como designación de campo.

- **La fecha de nacimiento y el número de personal también se encuentran
  en tablas.** En una celda solo figura el valor desnudo —`14.03.1988`. Lo
  que significa lo indica solo el encabezado de columna, y este está muchas
  filas más arriba. En Excel ya se leía; en las hojas de cálculo de
  LibreOffice y en archivos CSV no, y por eso allí la fecha de nacimiento
  permanecía.

  Ambos leen ahora también el encabezado —**pero solo si él mismo es una
  designación de campo**. Bajo "Fecha de nacimiento" la fecha cae; bajo
  "Fecha de factura" o "Fecha de entrega" no. Esa es deliberadamente la
  interpretación prudente: un encabezado como "Nombre" sobre una
  observación cualquiera ya habría colocado una vez un marcador sobre una
  frase en la que no aparece ninguna persona.

### Corregido

- **Un CSV depurado sigue siendo una tabla.** El reconocimiento lee una
  línea CSV como una frase y por eso a veces colocaba sus hallazgos también
  a través de un punto y coma. El marcador se tragaba el separador, la
  línea tenía después una columna menos, y el archivo ya no se podía abrir
  como tabla. Los hallazgos ahora terminan en el límite de celda, y las
  comillas del enmascarado permanecen. Las celdas afectadas se vuelven a
  leer después por separado —de lo contrario la celda vecina quedaría sin
  depurar, oculta por el hallazgo demasiado largo.

- **Comentarios en presentaciones.** La nota al margen de una diapositiva
  —a menudo justo el lugar donde figura "Por favor, llamar a la Sra. …
  antes de la reunión"— permanecía intacta, junto con el nombre de quien la
  escribió. En Excel ya se había despejado; PowerPoint guarda el texto del
  comentario y el autor de otra manera, y eso se había pasado por alto.
  Afecta a ambos formatos: el más antiguo y el que PowerPoint escribe desde
  2019 —allí también la dirección de correo corporativa vinculada al
  autor. Las iniciales que PowerPoint muestra en el globo de comentario
  también se eliminan.

- **Archivos de LibreOffice: fórmula, campo de usuario, autor de nota.** Lo
  que ya se había despejado en Excel permanecía en la hoja ODS —allí la
  fórmula no figura como elemento propio, sino como propiedad de la celda,
  y el nombre en ella sobrevivía. Al abrir de nuevo, LibreOffice lo volvía
  a calcular.

  Además, otros tres puntos: el valor de un **campo de usuario** figura en
  OpenDocument una vez arriba en la declaración y en el texto solo se
  invoca —hasta ahora solo se sustituía la invocación, de modo que al abrir
  volvía el valor antiguo. El **autor de una nota** y de un cambio
  rastreado permanecía. Y en una **hoja de cálculo** el seguimiento de
  cambios no se despejaba en absoluto —a diferencia del documento de
  texto—, de modo que el contenido de celdas eliminado, junto con el
  nombre del editor, se conservaba. Las referencias de celda y las
  fórmulas de suma permanecen intactas.

- **Las páginas web guardadas revelan sus atributos.** Una página no
  muestra ni de lejos todo lo que contiene. Un campo de formulario
  rellenado lleva la entrada en `value`, una interfaz JavaScript guarda su
  conjunto de datos en `data-…`, y el bloque para motores de búsqueda
  (JSON-LD) lo repite completo y bien formado: nombre, fecha de
  nacimiento, dirección, teléfono. El texto visible estaba depurado, todo
  eso seguía ahí.

  Ahora también se despejan estos lugares, además `aria-…` (lo que se lee
  al lector de pantalla), `placeholder`, `summary` y el nombre de archivo
  sugerido de un enlace. El bloque JSON-LD se lee como datos y permanece
  válido —sus claves y su vocabulario permanecen, solo desaparecen los
  valores. El JavaScript común sigue sin tocarse.

- **Las imágenes pierden sus metadatos también sin EXIF.** Una fotografía
  lleva anotados el nombre del fotógrafo, la hora de la toma y las
  coordenadas GPS del lugar —en un anuncio de vivienda eso revela la
  dirección, aunque en el texto no figure ninguna. Eso se eliminaba
  mientras la imagen tuviera EXIF. Pero si los datos estaban depositados
  **solo** como XMP (así lo guardan Lightroom y Photoshop) o como bloque
  de texto en un PNG (`Author`, `Comment`), la imagen quedaba totalmente
  intacta. Ambos casos se reconocen y eliminan ahora —también en imágenes
  que están dentro de un documento y se conservan en él. La orientación
  sigue conservándose, y una imagen sin metadatos no se vuelve a guardar
  innecesariamente.

- **Destinos de enlaces en hojas de cálculo, presentaciones y documentos de
  Word.** Adónde lleva un enlace no figura en el texto, sino en un
  almacén propio del archivo. Una dirección de correo detrás de "Escribir
  correo" sobrevivía por eso intacta a la depuración, mientras la misma
  dirección en el texto estaba sustituida. `mailto:` y `tel:` se despejan
  ahora allí igual que en las páginas web guardadas.

### Nuevo

- **Las cartas médicas ya no vuelven dañadas.** Hasta ahora el
  reconocimiento de nombres confundía sustancias farmacéuticas con nombres
  de personas: de "Metoprololsuccinat" resultaba `[NAME]`, de "Ramipril"
  resultaba `[ORT]`. El plan de medicación quedaba después inutilizable
  —mientras los diagnósticos permanecían intactos, es decir, exactamente al
  revés. Medido, esto afectaba al **63 % de los principios activos** y al
  **53 % de los términos técnicos clínicos**, y no solo en alemán: en siete
  idiomas, el 74 %; en italiano, todos los casos examinados.

  Maskuro ahora conoce el vocabulario médico y lo deja en paz. Queda un 6 %
  en vez de un 43 % (alemán) y un 1 % en vez de un 74 % (en los distintos
  idiomas). Donde precede un tratamiento —"Estimada Sra. …"— el nombre
  sigue siendo un nombre, aunque por casualidad se llame como una
  sustancia farmacéutica.

- **Las enfermedades y los medicamentos se pueden eliminar, si usted lo
  desea.** Nueva casilla en los ajustes: "Eliminar también enfermedades y
  medicamentos" (línea de comandos: `--mit-diagnosen`). Para expedientes
  de personal, despidos y peritajes, donde el diagnóstico no incumbe a
  nadie.

  **Desactivada de forma predeterminada**, y a propósito: una carta médica
  *consiste* en diagnósticos y principios activos. Quien anonimiza una
  —para investigación, para una formación, para una herramienta de IA—
  quiere conservar casi siempre precisamente ese contenido y solo eliminar
  a quién concierne. El diagnóstico es ahí la carga útil, no la
  identificación.

  El reconocimiento encuentra las designaciones habituales y no sustituye
  la revisión: una lista de enfermedades nunca es completa, porque el
  médico escribe "abuso de C2" donde la clasificación dice "trastornos por
  consumo de alcohol".

- **Se encuentran claves de diagnóstico y de medicamento.** CIE-10
  (`I48.2`), ATC (`A10BA02`) y el número central farmacéutico son datos de
  salud como cualquier diagnóstico escrito —en informes de alta y
  documentos de facturación, incluso la forma más frecuente. Están
  activados de forma predeterminada, como las demás categorías especiales
  según el art. 9 del RGPD.

  Una clave de diagnóstico solo se reconoce con respaldo: con "CIE" delante
  o entre paréntesis detrás de la línea de diagnóstico. Sin esta
  condición, el programa tomaría la tecla de función **F10** por un
  diagnóstico de adicción —en la clasificación, F10 es exactamente eso.

- **El archivo terminado ya se puede copiar.** En cada línea terminada,
  junto a "Ver", "Revisar" y "Mostrar en la carpeta" hay un cuarto botón:
  **Copiar**. Coloca el archivo depurado en el portapapeles —desde ahí pasa
  con Ctrl+V (Mac: ⌘V) a un correo, una ventana de chat o una herramienta
  de IA, sin el rodeo por la carpeta.

  Se copia el **archivo**, no su texto: el diseño de página, las imágenes y
  las barras de tachado se conservan. Desde el menú contextual de la lista
  también pasan al portapapeles varios resultados seleccionados a la vez,
  y en el menú "Archivo" figura la misma opción como **"Copiar
  resultado"** para quienes prefieren usar el teclado.

- **La selección de país ahora puede seguir al documento.** Los números de
  identificación, de seguridad social y fiscales varían de un país a otro,
  y qué países se comprueban estaba hasta ahora fijado para toda la
  sesión —derivado del idioma de la interfaz. Quien trabaja en alemán y
  depura un escrito en francés buscaba en él, por tanto, identificaciones
  fiscales alemanas y no el número de seguridad social francés.

  En la ventana de reglas figura ahora para eso **"Automáticamente según el
  idioma del documento"**. La selección fija sigue existiendo junto a
  ella, y a propósito: el reconocimiento de idioma no es infalible —si
  reconoce mal, se aplica la selección de país equivocada. Quien solo
  trabaja con expedientes de un país va más seguro con la lista fija.

  Los patrones **alemanes** (identificación fiscal, matrícula, extensión)
  no se ven afectados por esto: dependen del idioma, no de la selección de
  país, y se siguen aplicando incluso cuando un texto alemán corto se
  clasifica como inglés.

- **Ahora se encuentran contraseñas, claves y nombres de usuario.** Quien
  copia un mensaje de error, un registro o un fragmento de un archivo de
  configuración en una ventana de IA tiene casi siempre una clave de acceso
  dentro —y hasta ahora permanecía sin cambios.

  Se reconocen ambas formas: las formas de clave comunes que hablan por sí
  mismas (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token, la
  cabecera de una clave privada) y la forma etiquetada —"Contraseña:",
  "API-Key =", "Token:", "Nombre de usuario:". Solo se sustituye el valor,
  nunca la etiqueta: "Contraseña: [ZUGANGSDATEN_1]" sigue siendo legible, y
  quien revisa el resultado ve que allí había una contraseña.

  Nombre de usuario y contraseña son dos tipos separados. Quien solo quiere
  eliminar contraseñas desactiva uno y conserva el otro.

- **Los códigos de barras y QR en imágenes se vuelven irreconocibles.** En
  una resolución escaneada casi siempre hay pegado un código, y en él
  figura el número de expediente —el mismo número que se elimina en el
  texto de al lado. Hasta ahora permanecía la versión legible por máquina:
  la barra sobre el número no sirve de nada si dos centímetros más allá un
  dispositivo la lee en un segundo.

  Se reconocen código QR, Data Matrix, Aztec, Code 128, EAN y las demás
  formas habituales. Irreconocible significa pixelado, y más grueso que en
  el caso de los rostros: la corrección de errores de un código recupera
  sorprendentemente mucho a partir de pocos campos conservados, un velo a
  medias no sería una eliminación.

  La opción figura junto a "Hacer irreconocibles los rostros" y está
  **activada de forma predeterminada** igualmente. Incluso con la opción
  desactivada, el informe indica cuántas imágenes llevan un código —un
  rostro se ve al hojear, un código se toma por adorno.

- **Se encuentran el código de verificación de tarjeta, el PIN y la fecha
  de caducidad.** El número de tarjeta de crédito ya lo encontraba el
  programa; solo con los tres datos adicionales es utilizable, y en cada
  comprobante de liquidación figuran juntos. Los tres solo detrás de su
  etiqueta —"123" solo puede ser un número de calle, un número de página o
  una cantidad.

- **Se encuentran coordenadas en el texto.** De las imágenes, Maskuro ya
  eliminaba el lugar de la toma; si el mismo dato figuraba como texto en el
  peritaje o en el parte de intervención, permanecía. Se reconocen los
  grados decimales y la notación de grados-minutos-segundos. Con grados
  decimales debe haber cerca una palabra como "ubicación", "lugar del
  hallazgo" o "coordenadas" —de lo contrario, cualquier serie de medición
  con dos decimales sería una ubicación.

- **Los importes de dinero ahora se pueden eliminar también.** Nueva
  casilla "Eliminar también importes de dinero", **desactivada de forma
  predeterminada** como las fechas de arriba: en un contrato, el importe
  es el contenido, y quien tacha todo no protege a nadie. En una nómina, una
  propuesta de conciliación o un extracto de cuenta, en cambio, es
  precisamente el dato que dice más sobre la persona que el nombre de al
  lado —eso solo lo sabe quien tiene el documento delante.

  Se reconoce un importe **solo con indicación de divisa**: "4.250,00" por
  sí solo es una cantidad, solo "4.250,00 EUR" es dinero. Cuentan el
  símbolo de divisa, la sigla y el nombre escrito, tanto delante como
  detrás, incluida la notación "990,– CHF".

- **Se reconocen las categorías especiales según el art. 9 del RGPD.**
  Confesión religiosa, afiliación sindical, convicción política, datos de
  salud —y junto a ellos los datos penales según el art. 10. Son los datos
  cuyo tratamiento el reglamento **prohíbe** en principio; por eso son el
  único grupo nuevo que está activado **por defecto**. Quien quiera
  conservarlos, lo decide él mismo.

  Se reconoce la forma en que figuran en la práctica: el campo de
  formulario en la ficha de personal —"Confesión religiosa: católica",
  "Sindicato: ÖGB", "Grado de discapacidad: 50", "Antecedentes penales:
  ninguno"—, tanto con dos puntos al lado como con el encabezado encima,
  tal como lo entrega una hoja rellenada.

  **El texto corrido pertenece a la etapa de IA.** "Se compromete desde
  hace años con el sindicato" es el mismo dato, y ningún patrón de
  búsqueda lo encuentra de forma fiable. Desde esta versión, la etapa de
  IA busca expresamente también estas categorías; quien necesite el texto
  corrido, la activa.

- **Rasgos personales y profesión: los datos que también sin nombre
  muestran de quién se trata.** Sexo, estado civil, estatura, color de
  ojos y de cabello se eliminan a partir de esta versión; profesión,
  función y departamento a voluntad, mediante una casilla propia
  ("Eliminar también profesión y departamento") o `--mit-berufen`.

  **Por qué uno está activado y el otro no:** "La jefa del departamento de
  Compras" designa en una empresa exactamente a una persona, aunque el
  nombre de al lado esté tachado —en un peritaje o un despido eso debe
  eliminarse. Un listado de personal, en cambio, *consiste* en
  denominaciones de puesto; quien lo eliminara por defecto devolvería una
  hoja vacía. Solo quien tiene el documento delante sabe qué caso se da.
  Los rasgos de arriba figuran casi siempre solo en campos de formulario,
  son raros y nunca constituyen el contenido —así que no cuestan nada.

- **Comprobar un archivo ajeno.** "Archivo → Comprobar archivo…" vuelve a
  leer un documento ya tachado y notifica lo que todavía contiene —y **en
  qué lugar**: página y línea, tipo y longitud. Para el caso de que alguien
  compruebe el trabajo de otro: un expediente del bufete, una respuesta de
  la administración, la propia correspondencia saliente antes del envío.

  **El valor en sí no figura en el informe.** Quien abre el lugar lo ve de
  todos modos —y por eso el informe se puede guardar y compartir sin ser
  él mismo una colección de datos personales.

  **Y el informe siempre indica lo que no pudo ver.** Las imágenes no se
  leen; en un escaneo sin capa de texto, "ningún hallazgo" significa *no
  comprobado*, no *limpio*. En la línea de comandos eso lo distingue el
  valor de retorno: `--nachpruefen` entrega 0 para comprobado y limpio, 4
  para hallazgos y 5 para no comprobable. Así se puede retener
  automáticamente la correspondencia saliente, en vez de dejarla pasar.

- **Informe de verificación: una hoja por depuración.** "Archivo → Guardar
  informe de verificación…" —o `--pruefbericht <carpeta>` en la línea de
  comandos— escribe un PDF de una página (opcionalmente CSV o texto) con
  los datos de la ejecución, los tipos encontrados junto con su cantidad,
  dos indicadores y una nota de verificación. Para la carpeta del
  expediente y para la supervisión: el protocolo de verificación es la
  prueba sólida, pero nadie presenta un archivo JSON Lines.

  **Nuevos son dos números** que hasta ahora no se veían en ningún sitio:
  la *confianza media* —qué tan segura estuvo la detección en lo que
  encontró— y la *tasa de enmascaramiento*, la proporción de caracteres
  sustituidos respecto al texto. Ambos figuran con su límite: la confianza
  **no** dice nada sobre lo pasado por alto, y junto a ella siempre figura
  sobre cuántos hallazgos se calcula; la tasa no cuenta las imágenes y
  resulta demasiado alta en un documento con muchas imágenes.

  **Los valores encontrados no figuran en la hoja** —el mismo límite que
  en el protocolo y en la búsqueda. Abajo hay dos líneas que no dicen lo
  mismo: la suma de verificación muestra que la hoja no se ha modificado;
  la línea de protocolo —solo con protocolo activo— remite a la línea
  **firmada** que acredita la ejecución. Solo ella demuestra la
  procedencia.

- **"¿Qué tan seguro era eso?": los indicadores en el resultado.** Un
  botón "Indicadores" bajo el resultado despliega lo que hasta ahora no se
  veía en ningún sitio: hallazgos, palabras y caracteres, la distribución
  por tipo como fila de barras, además de la confianza media y la tasa de
  enmascaramiento. Los mismos números que en el informe de verificación,
  solo que al instante y sin impresión.

  **Con su reserva en la misma superficie:** junto a la confianza figura
  sobre cuántos hallazgos se calcula, y debajo la frase de que **no** dice
  nada sobre lo pasado por alto. Un porcentaje sin esa frase se lee como
  una tasa de acierto —y quien lo entiende así está peor que sin el
  número.

  Se calcula solo al desplegar: el denominador de la tasa de
  enmascaramiento cuesta una lectura por archivo, y eso no debe pagarlo
  quien ni siquiera mira los números.

- **Construir patrones de búsqueda propios sin escribir uno.** La pestaña
  "Patrones de búsqueda propios" guía ahora en tres pasos por el asunto:
  *¿Qué busca? → ¿Cómo se ve ese dato en su caso? → Nombrar y guardar.*
  Usted escribe un ejemplo —por ejemplo `KD-004711`—, el programa deriva de
  ahí la regla y describe en palabras qué busca. Una vista previa con
  contador de coincidencias comprueba con cada pulsación de tecla.

  **Ninguna expresión regular aparece en esto.** La capacidad nunca fue el
  problema: los patrones propios existen desde hace tiempo, solo que
  exigían una expresión como `\bKD-\d{6}\b`, y eso no lo escribe nadie en
  un bufete o un departamento de personal. Quien *quiera* escribir una,
  despliega el modo experto.

  **El catálogo de plantillas está reordenado:** trece tarjetas con
  nombre, explicación y valor de ejemplo, filtradas por etiquetas de
  categoría: finanzas, administración, contacto, personal, medicina.

  Y si el patrón derivado abarca demasiado, el programa lo dice por sí
  mismo: un ejemplo compuesto solo de cifras coincide con cualquier año y
  cualquier importe, y quien no sepa leer la expresión no podría notarlo
  de otro modo.

- **Siete etiquetas en vez de cincuenta y seis casillas.** Una nueva
  pestaña "Qué se busca" agrupa todos los tipos reconocibles en siete
  grupos: persona, contacto y lugar, identificadores, finanzas, técnica,
  categorías especiales, empresas y propios. Una etiqueta activa su grupo,
  "Todo activado" y "Todo desactivado" toda la lista; debajo cada tipo se
  puede seguir marcando individualmente.

  **Por defecto todo está activado, y así se mantiene.** Lo que aquí se
  desactiva ni siquiera se busca —la intervención más drástica que permite
  la ventana de reglas, y afecta a cada documento. Por eso, debajo de la
  lista figura en todo momento cuántos tipos están desactivados, y solo se
  guarda lo desactivado: un tipo nuevo está así activado también en un
  archivo de reglas de anteayer, en vez de quedar excluido en silencio.

- **Transferir un marco a todas las páginas.** En la ventana de revisión,
  el botón **Transferir a todas las páginas** toma el marco dibujado por
  última vez y tacha el mismo lugar en cada página adicional —para
  membrete, pie de página y campo de número de expediente. En un
  expediente escaneado de ochenta páginas, eso convierte veinte minutos en
  dos.

  **"El mismo lugar" significa el mismo lugar *relativo* en la hoja.** En
  un lote del alimentador de papel, regularmente una página está apaisada,
  otra es A3, una tercera está girada; un rectángulo transferido de forma
  absoluta acabaría junto al membrete —y se vería una barra y se daría el
  asunto por resuelto.

  **Se tacha, no se sustituye**, aunque el marco de origen fuera un
  marcador: bajo el mismo rectángulo, en la página cuarenta hay algo
  distinto que en la página uno, y un marcador con el mismo número
  afirmaría una igualdad que no existe.

- **Una nota en la barra de tachado.** En el derecho de acceso al
  expediente, junto a cada tachadura figura por qué se tachó. El nuevo
  campo **Nota en la barra** en los ajustes —o `--balkenvermerk`— escribe
  un texto breve en cada barra: "§ 203 StGB", "RGPD", "confidencial". Para
  un documento que expide una administración, eso marca la diferencia: el
  destinatario ve el motivo sin tener un protocolo que de todos modos
  nunca recibirá.

  **Vacía por defecto**, porque la nota es visible en el documento
  entregado y constituye ella misma un dato: le dice al destinatario bajo
  qué título se retiene algo. Solo actúa en el **tachado**; donde hay un
  marcador, no hay barra. En una barra demasiado pequeña para texto
  legible, se omite —una nota ilegible parece un error.

- **Activación sin conexión a internet, ahora completa.** En la ventana de
  licencia ya existía desde hace tiempo "Activar sin internet": arriba un
  código de solicitud para llevarse, abajo el campo para la activación que
  se recibe de vuelta. Solo que hasta ahora **nadie podía emitirla** —
  faltaba la herramienta para ello, y el código quedaba en el vacío. Eso
  está corregido.

  Para administraciones y bufetes con ordenadores aislados, esto no es un
  caso especial, sino el caso normal —y es precisamente el grupo objetivo
  para el que más pesa la promesa "sus documentos nunca salen del
  ordenador". El código no revela nada sobre documentos: contiene el
  identificador de licencia y un valor hash del ordenador, nada más.

- **Obtener del escáner.** "Archivo → Obtener del escáner…" lee
  directamente un lote y coloca las páginas en la lista —para una oficina
  de correspondencia, la diferencia entre dos pasos de trabajo y uno. Un
  alimentador de hojas se vacía hasta la última página; el dispositivo, la
  resolución y el color los elige el diálogo del sistema del escáner, que
  usted ya conoce.

  **No se depura automáticamente.** Primero ve lo que ha entrado y luego
  pulsa "Depurar" como con cualquier otro archivo —un escaneo que se
  procesara de inmediato le quitaría la posibilidad de ver un lote
  introducido torcido.

  **Esto solo existe en Windows**, y la entrada del menú también lo dice
  en el Mac: allí el software de su escáner escribe en una carpeta, y
  "Vigilar carpeta…" depura todo lo que llega allí.

### Otros

- **La lista de todos los datos encontrados ahora se incluye** y se genera
  a partir del código fuente (`hilfe/GEFUNDENE-ANGABEN.md`): 177 tipos en
  35 países, 23 de ellos con cálculo de dígito de control. También indica
  cómo se contó: contamos `[NAME]` una vez, donde otros cuentan nombre de
  pila, segundo nombre y apellido como tres entradas.

- **El tachado ahora también existe en Word, PowerPoint, OpenDocument y
  HTML.** La elección entre marcador y tachado hasta ahora solo existía
  para archivos PDF. Ahora también pueden los demás: el hallazgo se
  elimina, y en su lugar queda una barra negra —en el propio documento, no
  como imagen encima. Quien reenvía el archivo entrega un expediente
  tachado y no uno en el que lo tachado sigue estando como texto debajo.

  **Se decide por separado**, en dos campos de selección: "Para PDF" y
  "Para Word, PowerPoint, OpenDocument y HTML". Se quiere de forma
  distinta: el PDF tachado va a la administración, el mismo asunto como
  archivo Word sigue circulando por la oficina y debe seguir siendo
  legible. En la línea de comandos, respectivamente `--pdf-modus` y
  `--office-modus`; un "tachado" guardado de versiones anteriores sigue
  aplicándose al PDF.

  En hojas de cálculo, texto plano, CSV y correo electrónico no funciona
  la barra —allí falta la superficie sobre la que colocarla. Se sigue
  insertando un marcador, y el resultado **lo indica ahora**, en vez de
  hacerlo en silencio.

- **Nuevo: "Eliminar": el hallazgo simplemente queda vacío.** El tercer
  modo de funcionamiento junto a marcador y tachado, y el único que
  funciona en **todos** los formatos: omitir algo no necesita ninguna
  superficie. En el PDF no se dibuja nada, en Word y HTML el lugar queda
  vacío, en una hoja de cálculo igual.

  Es el más discreto de los tres: quien lee el resultado no ve que allí
  hubo algo alguna vez —tampoco se delata ya la longitud del valor. Para
  un documento que alguien debe revisar, el marcador suele seguir siendo
  la mejor opción.

  En imágenes no rige ninguna de las tres opciones: los píxeles no se
  pueden sustituir por un marcador ni omitir. Lo que el reconocimiento de
  texto encuentra allí se sigue repintando siempre.

- **La ventana de revisión ya no afirma sustituciones que no existen.** A
  la derecha figuraba junto a cada valor un marcador —también en un
  archivo tachado, en el que no aparece ninguno. Un clic en esa línea no
  marcaba nada, y "Deshacer" quedaba en el vacío. Ahora figura allí
  "tachado" o "eliminado", y esas líneas ni siquiera se pueden deshacer:
  el texto ha desaparecido, no hay nada que recuperar. Esto valía para
  archivos PDF tachados, para Word y OpenDocument y para todo lo
  encontrado en imágenes.

- **La vista de texto ahora muestra las barras como barras.** Un archivo
  Word tachado se veía **vacío** al revisarlo: en los lugares tachados
  había huecos, como si el programa se hubiera tragado el texto. La causa
  era la visualización, no el resultado —en el propio documento la barra
  estuvo bien todo el tiempo. Ahora también figura así en la vista, negra
  como en el resultado, en Word, PowerPoint, OpenDocument y HTML.

- **Los mensajes de Outlook (`.msg`) ahora se depuran.** `.eml` existía
  desde hace tiempo —pero en las empresas alemanas, Outlook es el correo
  electrónico, y allí un mensaje guardado se llama `.msg`. Con esto, el
  formato con más datos personales queda cubierto también en su forma de
  almacenamiento más extendida: asunto, remitente, líneas de
  destinatarios, texto del mensaje, versión HTML, lista de destinatarios y
  adjuntos —estos últimos por las vías ya existentes y con los mismos
  marcadores que el texto del correo.

  **Un `.msg` lleva el mismo texto varias veces**, y ahí está la trampa:
  como texto plano, como HTML **y** como RTF. Quien depura solo el texto
  plano no ha hecho nada —Outlook muestra preferentemente el RTF. Por eso,
  la versión RTF se elimina por completo, al igual que las cabeceras de
  internet con su cadena Received y las claves de búsqueda binarias, que
  sobreviven a cualquier depuración de texto con nombres y direcciones. El
  resultado se sigue abriendo en Outlook y muestra el texto sin formato
  tipográfico; el informe lo indica expresamente.

- **Describir reglas con sus propias palabras, en vez de escribir regex.**
  La ventana de reglas puede mucho y para ello exigía un patrón de
  expresión regular —el punto en el que la mayoría se detiene. Ahora basta
  una frase: "Nuestros números de expediente con la forma 12 C 345/26
  deben permanecer." La etapa de IA propone a partir de ahí términos y
  patrones de búsqueda.

  **Solo se aplica lo que usted marca, y por defecto no hay nada
  marcado.** Junto a cada propuesta figura una frase de lo que significa,
  y el número de sus coincidencias en un texto de ejemplo que usted puede
  aportar. Lo que **quita** protección está señalado como tal: "eliminar
  siempre este término" y "no eliminar nunca este término" se verían
  igual en una lista si no. Las propuestas que coincidirían con todo ni
  siquiera se muestran.

- **El protocolo de verificación ahora suma en todos los puestos de
  trabajo.** Si una organización guarda los protocolos mediante
  `protokoll_pfad` en una unidad compartida, cada puesto escribe allí su
  propio archivo mensual —hasta ahora un responsable de protección de
  datos con treinta puestos tenía que revisar treinta archivos por
  separado. Sobre la lista figura ahora una línea con las sumas del mes, y
  **notifica cadenas rotas con nombre**: una modificación posterior solo
  se nota si alguien la revisa, y en treinta archivos nadie lo revisa a
  mano.

  **Ningún desglose por persona** —tampoco en esta vista. Un ranking de
  "quién depuró cuánto" serviría para el control de comportamiento y
  rendimiento, y en materia de codeterminación eso es lo que cuenta, no la
  intención. Se cuentan ejecuciones, archivos y hallazgos a nivel de toda
  la organización.

- **"Proponer perfil a partir de un documento": preguntar a las reglas una
  vez en vez de repasar cuarenta y cuatro tipos.** En la ventana de reglas
  hay un botón nuevo: muestra a la etapa de IA un documento, determina de
  qué se trata —carta médica, solicitud de empleo, contrato, factura,
  resolución— y propone las estrategias adecuadas. En una carta médica,
  por ejemplo, las fechas se desplazan en vez de sustituirse, porque en un
  historial clínico la cronología es el contenido.

  **Los perfiles están en el programa, el modelo solo elige entre
  ellos** —las reglas de tachado no dependen de lo que un modelo de
  lenguaje considere una buena idea. Cada punto se propone individualmente
  y con justificación; no se aplica nada sin confirmación, y lo que usted
  mismo ha fijado permanece intacto. Sin la etapa de IA, se mantiene el
  valor predeterminado seguro: marcador para todo.

- **Nueva estrategia "inventar": un valor falso plausible en vez de un
  marcador.** "La Sra. Berger escribió al Sr. Doppler en Fulda" en vez de
  "[NAME_1] escribió a [NAME_2] en [ORT_1]" —para material de formación,
  expedientes de demostración, conjuntos de datos de prueba y todo lo que
  después se presenta a una IA. El tratamiento, la construcción de la
  frase y la legibilidad se conservan.

  El mismo valor recibe el mismo valor falso, en todos los archivos de un
  caso y en cada ordenador con el mismo archivo de reglas —**sin que en
  ningún sitio se guarde una asignación** (el mismo mecanismo que en el
  hash). Las direcciones de correo se sitúan en dominios de ejemplo
  reservados, los números de teléfono en el rango reservado para ello, los
  IBAN inventados llevan un dígito de control calculado correctamente.
  Posible para nombres, lugares, direcciones, empresas, correo, teléfono e
  IBAN; para otros tipos la regla se rechaza, en vez de quedar sin efecto.

  **El informe indica expresamente que se inventó.** Un documento así
  depurado se lee como uno real y no lo es —no sirve como prueba y no debe
  entregarse como original.

- **La contraprueba: "¿Quién sigue siendo reconocible?"** Una nueva
  casilla bajo la etapa de IA presenta de nuevo el **resultado
  terminado** al modelo de lenguaje y pregunta quién, pese a la depuración,
  sigue siendo reconocible. Se trata del caso que ningún reconocimiento
  del mundo encuentra, porque allí no figura ningún nombre: "la única
  comadrona del distrito", "el compañero que dimitió en marzo tras el
  incendio". Ningún patrón se aplica, y en el lugar todos saben de todos
  modos de quién se trata.

  **En esto no se elimina nada.** Los lugares figuran en el informe con
  una frase de justificación, y se decide a mano —un programa que por su
  cuenta tomara frases de un documento porque le parecen reveladoras
  convertiría una depuración en una reescritura, y nadie vería qué falta.
  Como máximo cinco lugares por archivo; lo que el modelo no puede
  acreditar literalmente se descarta. En la línea de comandos:
  `--restrisiko` junto con `--ki`.

- **El camino de vuelta desde la IA: "Retraducir respuesta".** Hasta ahora
  solo estaba construida la mitad del ciclo: copiar texto, pegarlo
  depurado, presentarlo a la IA. La respuesta volvía con `[NAME_1]`, y
  quien la necesitaba volvía a poner a mano lo que había quitado a mano.
  Ahora el camino de vuelta figura en el menú "Programa": copiar la
  respuesta, hacer clic en la entrada, los nombres reales vuelven a estar
  ahí.

  La asignación para esto reside **solo en la memoria de trabajo**, vale
  siempre solo para el último lugar depurado y caduca al cabo de una hora;
  quien desactiva el vigilante del portapapeles la pierde de inmediato.
  Solo se puede recuperar lo que se sustituyó —lo tachado, lo enmascarado
  y lo con hash no es reversible, y el programa indica cuántos lugares
  tuvo que dejar así por ese motivo. Las instalaciones gestionadas
  desactivan el camino de vuelta por completo mediante el valor
  predeterminado `rueckweg`.

- **Vigilar carpeta: lo que se coloca dentro aparece poco después depurado
  en la salida.** Para una oficina de correspondencia, un equipo de
  correo o una carpeta de escaneo —se configura una vez, después ya nadie
  hace clic. Se encuentra en "Archivo → Vigilar carpeta…", en la línea de
  comandos mediante `--wache <carpeta>`.

  El original permanece donde estaba; si se desea, pasa sin modificar a la
  subcarpeta "Hecho", sin sobrescribir nunca nada. Un archivo se toca solo
  cuando está completamente escrito —de lo contrario, un archivo aún
  copiándose por la red se leería a medias y se notificaría como depurado.
  Lo que falla queda ahí y se comunica, en vez de repetirse sin fin. Y el
  vigilante recuerda lo hecho sin usar nombres de archivo: lo que hay en
  una carpeta de entrada a menudo ya revela en el nombre de qué se trata.

  **Vigilar una carpeta fuera del propio perfil de usuario —por ejemplo en
  una unidad de red— requiere una licencia de automatización.** Una
  carpeta a la que acceden varias personas es un servicio y no un puesto
  de trabajo; en el propio perfil y durante el período de prueba, esta
  restricción no se aplica.

### Corregido

- **Los ajustes quedaban cortados por la derecha.** La ventana se abría
  con un tamaño fijo, y este solo alcanzaba para el tamaño de fuente con
  el que se desarrolló: en el Mac, "Comprobar ahora", "Cambiar…" y las
  indicaciones de al lado quedaban a medias fuera. Ahora se abre tan ancha
  como lo necesitan sus páginas —en cada idioma y con cada tamaño de
  fuente, limitada solo por la pantalla.

- **"Comprobar ahora" ahora responde de forma visible.** El resultado
  figuraba en la barra de estado de la ventana principal —es decir,
  detrás de la ventana de ajustes desde la que se había preguntado. Quien
  comprobaba no veía nada. Ahora la respuesta llega como mensaje sobre los
  ajustes, y si hay una versión nueva disponible, lleva directamente a la
  instalación. Al iniciar el programa se mantiene como hasta ahora en la
  barra de estado, ninguna ventana se abre sin que se pida.

- **Los archivos copiados no llegaban al portapapeles en el Mac.** El
  hecho de colocar archivos depurados en el portapapeles notificaba éxito
  y sin embargo no dejaba nada utilizable —pegar no daba resultado.
  Afectaba a todo lo que escribe archivos en el portapapeles.

- **Y del portapapeles, en el Mac, solo se leía el primer archivo.** Quien
  copiaba tres archivos en el Finder y elegía "Depurar portapapeles ahora"
  recibía dos de ellos sin depurar —sin que nada lo indicara. Ahora llegan
  todos.

- **"Comprobar archivo" ahora también acepta archivos arrastrados** —igual
  que la ventana principal. Lo soltado se añade, en vez de descartar la
  selección anterior; soltar lo mismo dos veces no cambia nada, y lo que
  el programa no puede leer se comunica en vez de ignorarse.

- **Y la ventana indica que está esperando algo de usted.** Se abría con
  un recuadro vacío y un botón gris "Comprobar" —eso parece que no hay
  nada, no que falta la selección. Ahora figura allí "Todavía no se ha
  elegido ningún archivo: arrástrelo aquí o elíjalo abajo mediante
  'Seleccionar archivos…'."

- **Una ejecución larga ahora indica que está en marcha.** "Cargando
  modelo adicional para un reconocimiento más preciso: un momento…" se
  quedaba fijo mientras el reconocimiento calculaba: en un archivo de 47
  500 palabras, dieciocho minutos, aunque la carga había terminado a los
  nueve segundos. Quien ve eso considera que el programa se ha quedado
  colgado. Ahora le sigue "El reconocimiento más preciso está en marcha:
  esto tarda varios minutos en textos largos", y la barra de estado cuenta
  a la vez: "Reconocimiento más preciso (7/312)". Se notifica desde el
  bucle del modelo —cada 250 palabras, es decir, cada seis segundos
  aproximadamente—, no por bloque de texto: un bloque de texto lleva doce
  mil palabras y necesita minutos.

- **Una ejecución cancelada ahora indica que se canceló.** Quien pulsaba
  "Cancelar" leía después "0 de 1 archivo(s) depurado(s)." —contado
  correctamente y aun así la información equivocada. El mensaje de qué
  archivo se vio afectado fue sobrescrito en el mismo instante por el
  mensaje de recuento. Y en la lista de archivos seguía figurando "en
  curso…", aunque ya no se ejecutaba nada; ahora figura "cancelado".

- **La frase sobre la privacidad estaba cortada.** "… sin nube, sin
  subida. Más en la protec" —con el ancho de ventana con el que arranca el
  programa, terminaba en medio de una palabra. Ahora ocupa todo el ancho.

- **El servicio de licencias podía comunicar algo, y nadie escuchaba.**
  Cuando todos los puestos de licencia están ocupados, la licencia ha
  caducado, la clave es desconocida o la gestión de licencias está
  desactivada en el proveedor, el servicio envía precisamente para eso un
  motivo —estaba previsto desde el principio que se le explicara **una
  vez**. Nunca se mostraba. Ahora aparece un aviso que primero dice que el
  programa sigue funcionando sin cambios, y después de qué se trata. Una
  vez por motivo: quien lo cerró no lo vuelve a ver en la comprobación
  diaria —salvo que el motivo cambie.

- **Una licencia multipuesto comprada en la tienda mostraba "1 puesto".**
  La tienda distribuye claves preparadas y conserva ella misma el número
  de puestos comprado; pero se mostraba el número contenido en la propia
  clave, y este es de un puesto en cada clave de reserva. Quien había
  comprado ocho puestos leía "1 puesto" —y a partir del segundo ordenador
  registrado, la indicación aparecía en rojo junto con "Consulte a su
  administración". Ahora se aplica el número que el servicio comunicó por
  última vez; sin respuesta, se mantiene el de la clave, y nunca será
  menor que el volumen comprado. Lo mismo vale para compras adicionales y
  renovaciones: estas cambian el número de puestos en el proveedor, no su
  clave.

- **Tras la compra figuraba "Licenciado para Maskuro Privatlizenz".** No
  es un nombre, sino el marcador bajo el cual se preparan las claves —su
  nombre no puede figurar allí, porque la clave ya se firma antes de la
  compra. En vez de mostrarle un nombre ajeno como si fuera el suyo, ahora
  figura simplemente "Licencia personal" y el número de puestos. En una
  licencia expedida a su nombre, su nombre sigue figurando sin cambios.

- **En el menú de ayuda figuraba "Ayuda _FAQ".** El signo "y" comercial se
  había convertido en un guion bajo, porque Qt lo interpretaba como marca
  de una letra de acceso rápido. Ahora figura "Ayuda y FAQ".

- **La ventana de ajustes permanecía abierta cuando el programa
  desaparecía al icono** —e incluso cuando se cerraba la ventana
  principal. Ahora la acompaña. (Afecta solo a esta versión; la ventana
  propia es nueva.)

- **Una solicitud de licencia rechazada ahora indica la causa.** Si el
  servicio de licencias rechazaba una solicitud sin enviar un motivo, en
  la ventana de licencia figuraba en rojo "Respuesta desconocida." —una
  frase con la que ni usted ni el soporte pueden hacer nada y que le hace
  buscar el error en su propia clave. Ahora figura lo que realmente
  ocurrió: que el servicio rechazó sin justificarlo, y a quién dirigirse.
  Si la gestión de licencias está temporalmente desactivada en el
  proveedor, también se indica —junto con la advertencia de que su clave
  no se ve afectada por ello.

- **En el Mac, los idiomas ya configurados de repente se consideraban
  ausentes.** Al iniciar, el programa notificaba "No hay ningún modelo de
  idioma instalado" y ofrecía la configuración inicial, aunque los idiomas
  ya estaban cargados desde hacía tiempo —quien revisaba en "Idiomas de
  los documentos" los encontraba todos completos. El programa los buscaba
  en dos lugares distintos según la vía de inicio: si se iniciaba desde la
  carpeta de programas, los encontraba; si la misma compilación se
  iniciaba como una simple carpeta, los buscaba junto a sí misma, donde no
  hay ninguno. Desde ahora, en el Mac rige sin excepción el mismo lugar en
  el perfil de usuario, sea cual sea el empaquetado del programa. No hace
  falta volver a cargar nada.

- **"Qué hay de nuevo" mostraba la mitad de la lista.** La ventana tras una
  actualización se interrumpía en mitad de una frase, y los puntos
  restantes figuraban como viñetas vacías. La culpa era de un marcador
  entre corchetes angulares —por ejemplo `<archivo>.docx`— que la
  visualización tomaba por marcado y a partir del cual descartaba todo lo
  siguiente. Precisamente las novedades de seguridad se veían afectadas.
  La ayuda siempre mostró correctamente esos marcadores; esta ventana
  ahora también lo hace.

- **Pellizcar con dos dedos ahora hace zoom en la ventana de revisión.**
  En el panel táctil, ese es *el* gesto de zoom —en el editor hasta ahora
  no hacía nada, y quien quería ver un lugar más de cerca tenía que
  recurrir al control deslizante o a Ctrl+rueda del ratón. La página sigue
  el gesto de inmediato y se vuelve a dibujar con nitidez al soltar.

- **El zoom se centra en el lugar que se está mirando.** Pellizcar amplía
  alrededor del punto entre los dedos, Ctrl+rueda del ratón alrededor del
  punto bajo el cursor. Los botones, los atajos de teclado y el control
  deslizante de zoom mantienen fijo el centro —a ellos no pertenece ningún
  lugar señalado. Antes, en todos los casos solo se conservaba el valor de
  desplazamiento: desde una página ajustada, eso mantenía el borde
  superior, y todo lo demás se salía de la imagen al acercar el zoom.

- **"Antes/Después" era un botón muerto en la vista de páginas.** Mientras
  la vista de páginas estaba activa, se podía pulsar —y cada vez notificaba
  que el original no se podía abrir. Tampoco hay nada que comparar allí:
  la vista de páginas es una representación de la versión depurada, no
  existe una contraparte del original. El botón ahora está bloqueado y, al
  pasar el cursor por encima, indica el motivo junto con la alternativa
  (la vista de texto). Su descripción, además, prometía expresamente que
  la comparación funcionaba "independientemente de si la vista de texto o
  la de páginas está activa" —eso nunca fue cierto.

- **La vista de páginas hacía que LibreOffice se cerrara
  inesperadamente.** Si se generaban dos vistas de páginas al mismo
  tiempo —por ejemplo "Tachar como PDF" mientras la vista previa aún
  calculaba—, el sistema notificaba un cierre inesperado de LibreOffice,
  aunque las páginas al final sí aparecían: ambas ejecuciones accedían al
  mismo espacio de trabajo de LibreOffice, algo que este no tolera. Ahora
  solo una ejecución lo recibe siempre; las demás recurren a uno propio.
  Eso les cuesta unos segundos más, pero a cambio ya no aparece ningún
  mensaje de error, y ninguna de las ejecuciones se queda sin resultado.
  Además, un segundo encargo de renderizado junto a uno en curso ya ni
  siquiera se acepta.

- **"Mostrar original" podía cerrar el programa.** Si el original no se
  podía abrir —porque se había movido, renombrado, protegido con
  contraseña o estaba en una unidad desconectada—, la ventana de revisión
  se cerraba sin previo aviso, y las copias de trabajo abiertas se
  perdían. Ahora aparece un aviso, el interruptor vuelve a su posición
  anterior, y la versión depurada permanece. Donde el original en
  principio no encaja —por ejemplo en una vista de páginas PDF generada a
  partir de un archivo Word—, el interruptor está bloqueado desde el
  principio e indica el motivo al pasar el cursor, en vez de mostrar el
  mismo aviso en cada pulsación.

- **Los informes de error nunca llegaban.** Quien quería notificar un
  error recibía "La contraparte rechazó el informe" —y nadie lo había
  visto jamás. Dos causas, ambas en el camino: el programa no se
  identificaba ante el servidor y por eso era rechazado por la protección
  contra accesos masivos, y la dirección remitía a un segundo nombre que
  el programa no seguía. Ambas están corregidas; un informe vuelve a
  salir. **Lo mismo afectaba a la activación de licencias**: iniciar
  sesión, cerrar sesión y las consultas tampoco llegaban al servicio —allí
  solo de forma discreta, porque una solicitud sin respuesta
  deliberadamente no cambia nada en su licencia. Y si un rechazo sigue
  siendo inexplicable alguna vez, ahora figura junto a él su número
  técnico, en vez de que cada causa se vea igual.

- **Un clic en "Mostrar original" podía cerrar el programa.** Si el
  original no se podía abrir —movido, renombrado, en una unidad de red
  desconectada, protegido con contraseña o dañado—, la ventana de revisión
  desaparecía junto con todas las copias de trabajo abiertas. Ahora el
  interruptor permanece en la versión depurada, y un recuadro indica qué
  ocurre; el motivo técnico figura en los detalles, por si desea
  notificarlo. Lo mismo vale para un resultado que no se puede mostrar: la
  ventana se abre y lo indica, en vez de desaparecer.

- **La pregunta sobre un cierre inesperado aparecía con demasiada
  frecuencia, y borraba la huella que preguntaba.** Aparecía también
  cuando no había ocurrido ningún cierre: la nota se genera en cuanto
  ocurre en algún lugar una interrupción inesperada, incluso si el
  programa la soporta y después termina con total normalidad; nunca se
  eliminaba. Y quien respondía "No" destruía los únicos detalles del
  incidente —la nota desaparecía ya al *mostrarse* la pregunta. Ambos
  casos están corregidos: un cierre ordenado elimina la nota, solo se
  pregunta ante un cierre inesperado real, y solo se marca tras su
  respuesta. Los detalles figuran de todos modos en el registro de errores
  del propio ordenador —quien no quiere enviar nada no pierde nada por
  ello. Se sigue enviando únicamente lo que usted ha visto completo de
  antemano y ha autorizado usted mismo.

- **"Depurar" podía quedar bloqueado en silencio.** Si los modelos de
  idioma se quedaban colgados al cargar, el botón permanecía
  desactivado —sin explicación. Un clic sobre él no hacía nada, y la barra
  de estado seguía indicando sin cambios "Cargando modelos de idioma…",
  incluso después de diez minutos. La causa: las interrupciones en
  procesos en segundo plano iban a un lugar que nadie ve al iniciar desde
  el explorador de archivos; quedaba una ventana que parecía lista para
  trabajar y no reaccionaba a ningún clic. Ahora esas interrupciones
  acaban en el registro de errores, la carga de los modelos de idioma
  notifica su fallo en todos los casos en vez de rendirse en silencio, y
  si aun así queda en silencio, la aplicación indica al cabo de tres
  cuartos de minuto que algo no va bien, con un consejo en los detalles.
  El botón bloqueado indica su motivo al pasar el cursor. Una primera
  carga larga no cuenta como silencio: mientras se notifique progreso,
  todo sigue tranquilo. Nada de esto cuenta como cierre inesperado: la
  aplicación sigue funcionando, y por eso tampoco se pregunta al
  siguiente inicio.

- **En el Mac, el programa ya no encontraba actualizaciones, y decía que
  estaba en la versión más reciente.** La versión para Mac no incluía un
  directorio de certificados raíz; lo buscaba en un lugar que solo existe en
  el equipo en el que se compila. Con ello no podía verificar ante ningún
  servidor con quién hablaba, e interrumpía cada conexión: sin
  actualizaciones, sin activación de licencia, sin recarga de modelos de
  idioma, sin informe de errores. Las versiones anteriores convertían eso
  en silencio en el mensaje „Está utilizando la versión más reciente". Los
  certificados están ahora en el propio programa; si no encuentra ninguno
  ahí, toma los del sistema y, en el Mac, en caso necesario los del
  llavero; y si no hay ninguno en absoluto, lo dice, en vez de afirmar que
  es la versión más reciente. La propia verificación nunca se desactiva
  con esto.

  Esta única actualización todavía la deben instalar a mano los usuarios
  de Mac: una versión que no alcanza el servidor tampoco puede
  actualizarse a sí misma.

### Modificado

- **La ventana principal se ha ordenado.** Abajo había seis botones del
  mismo tamaño uno junto al otro („Acerca de…", „Manual" y „Ayuda y
  preguntas frecuentes" entre ellos), aunque esos mismos tres caminos ya
  estaban en el menú Ayuda de arriba. Ahora están reunidos en un botón
  „Ayuda" que los despliega; no se pierde ninguno. Abajo quedan los dos
  caminos con los que realmente se empieza: „Limpiar" y „Tachar a mano…".

- **Lo que el programa está haciendo en ese momento ahora tiene un lugar
  fijo.** El mensaje („Cargando modelos de idioma…", „(3 / 7)
  brief.pdf", „5 de 7 archivo(s) limpiado(s).") colgaba hasta ahora como
  texto gris entre dos filas de botones. Ha recibido una superficie
  propia, con un punto coloreado delante: gris mientras nada se ejecuta,
  azul durante el trabajo, verde tras una ejecución sin incidencias y
  amarillo cuando han surgido avisos. El punto no dice nada que no esté
  al lado; solo lo dice más rápido.

- **Los ajustes se han convertido en una ventana propia.** Hasta ahora
  estaban en la ventana principal, un recuadro con cuatro pestañas que se
  desplegaba bajo „Más ajustes" y que después resultaba demasiado
  pequeño para su contenido: siempre había una barra de desplazamiento
  dentro, y la elección entre anonimizar y seudonimizar quedaba medio
  fuera de la imagen. El botón ahora se llama „Ajustes…" y abre una
  ventana con una barra lateral; cada una de las cuatro páginas cabe por
  completo. La ventana principal ya no salta al abrirla, y se puede ver
  la lista de archivos al lado. Solo ha cambiado dónde están los
  ajustes; cuáles hay y qué hacen sigue igual.

- **„Detalles" se despliega en vez de saltar.** La ventana crecía hasta
  ahora de golpe, y había que buscar después qué había cambiado. Ahora
  se mueve hacia allí.

- **Los tamaños de fuente y los espacios siguen la misma medida en toda
  la ventana.** Los encabezados tenían tamaños distintos en dos lugares,
  y las líneas del mismo rango estaban separadas de forma distinta.
  Esto se nota como calma, no como un cambio concreto.

- **Anonimizar es ahora el valor predeterminado.** Hasta ahora,
  seudonimizar venía configurado por defecto: las mismas personas
  recibían el mismo número (`[NAME_1]`, `[NAME_2]`), las referencias se
  mantenían legibles, pero jurídicamente seguían siendo **datos
  personales**. Quien no configure nada obtiene ahora el procedimiento
  que saca los datos del RGPD: todos los hallazgos de un tipo se llaman
  igual (`[NAME]`). La numeración sigue siendo una opción, está sin
  cambios en la misma ventana; los ajustes existentes se mantienen como
  están. En la línea de comandos, `--pseudonymisieren` (también
  `--mit-nummerierung`) restablece el otro modo.

- **Los marcadores anonimizados ya no se pueden deshacer
  individualmente.** Quien anonimiza obtiene para cada persona el mismo
  marcador, y con ello ya no hay un lugar individual que pertenezca a un
  nombre concreto. La ventana de retoque ofrecía pese a ello „Deshacer
  sustitución": un clic habría colocado *uno* de los valores en *todos*
  los lugares. Las líneas ahora aparecen atenuadas como con los datos
  tachados, el clic indica el motivo, y un hallazgo corregido a mano ya
  no recibe un número que no está en ningún otro sitio del documento.

  Por el mismo motivo, tras una ejecución anonimizada ya no existe
  „Retraducir respuesta"; antes habría colocado un nombre ajeno en el
  lugar de cada persona. Quien necesite ese ciclo elige „Seudonimizar";
  la aplicación ahora también lo dice así, en vez de remitir a una
  asignación caducada.

  En la línea de comandos, `--zuordnung` ahora se interrumpe al
  anonimizar, en vez de escribir un archivo que no es una retraducción;
  en la ventana, la casilla ya estaba bloqueada desde hace tiempo. O
  bien se añade `--pseudonymisieren`, o se omite `--zuordnung`; el
  mensaje lo indica. El resultado ni siquiera se genera en ese caso,
  para que un script no se quede con trabajo a medias.

- **El canal de actualización pasa a „Estable" por defecto.** Sin
  elección propia, el canal se orientaba hasta ahora según de qué
  compilación procedía la versión en uso; quien probó una vez una
  versión de prueba recibía desde entonces de forma permanente versiones
  de prueba. Un cambio de canal es una decisión y debe seguir siéndolo;
  por eso el valor predeterminado es „Estable". Los canales configurados
  permanecen intactos.

### Mejorado

- **„Beschwerdevorgang" ya no se considera un nombre de lugar.** En el
  encabezado „Aktennotiz – Beschwerdevorgang 12 C 345/26", el programa
  tachaba también el trámite: el modelo de lenguaje lo consideraba un
  lugar, independientemente del contexto. Lo que se ha añadido no es la
  palabra individual, sino la **palabra base** del compuesto; „vorgang"
  y „notiz" cubren así también trámite comercial, contable y de pago, o
  la nota telefónica. De treinta términos administrativos comprobados,
  antes tres provocaban una falsa alarma, ahora ninguno; se sigue
  encontrando todo lo que está al lado („Beschwerdevorgang: Bernd
  Meisinger" pierde el nombre, no el encabezado).

- **Anonimizar vuelve a llevar registro, para el ajuste posterior y el
  protocolo.** En el modo de funcionamiento anonimizador, el programa no
  recordaba los valores encontrados. Con ello quedaban mudas dos cosas:
  el ajuste de consistencia a nivel de documento (un apellido que
  aparece después solo, quedaba sin tocar) y la lista de sustituciones
  en el registro de verificación. Mientras anonimizar era la opción
  menos frecuente, apenas se notaba; como valor predeterminado se habría
  convertido en el caso normal. En el documento no cambia nada: el
  marcador se mantiene sin número.

- **„Ningún dato personal" ahora se llama „ningún dato de carácter
  personal".** En el diálogo de recuperación y en el aviso de rostros
  aparecía el término jurídico *dato*, en singular; se leía como un día
  del calendario, sobre todo porque la aplicación en otro lugar ofrece
  „eliminar también las fechas". Ahora se llama en todas partes „dato",
  igual que en los cuatro motivos de arriba en la misma ventana.

- **La línea de procedencia solo está ya en la ventana „Acerca de".**
  „Made with ♥ in Austria" estaba abajo en la ventana principal, en
  mitad de la fila de botones, y ahí se leía como un botón más. Sigue
  estando en la ventana „Acerca de", donde se busca.

- **La zona de depósito ahora tiene un borde visible.** Su borde
  discontinuo era tan pálido que apenas se distinguía de la ventana; eso
  daba igual mientras la zona era solo una superficie. Desde que es un
  botón al que se puede saltar con la tecla Tab, ese trazo es lo único
  que la muestra como elemento de control; por eso se ha elevado al
  valor que exige la norma para ello.

## 0.10.22-beta.1 – 15 de agosto de 2026

### Nuevo

- **Si se desactiva la vigilancia del portapapeles, queda realmente
  desactivada.** El vigilante mantiene los últimos contenidos en la
  memoria de trabajo para poder restaurar el original; hasta ahora también
  cuando usted había desactivado la vigilancia. Ahora el historial se
  olvida al desactivar. Esto cuesta la restauración tras la desactivación,
  y así está pensado: desactivado significa desactivado.
- **El registro de errores ya no contiene rutas de archivo.** Solo estaba
  en su equipo y nunca se enviaba por sí solo, pero llevaba rutas en texto
  claro, y un nombre de archivo a menudo revela más que el contenido. De
  „…/Divorcio_Mueller_Acuerdo.docx" se pasa ahora, al escribir, a
  `<archivo>.docx`; la extensión se mantiene porque cuenta a la hora de
  buscar el error. Lo mismo vale para la nota tras un cierre inesperado.
- **La lista de sustituciones ahora advierte en sí misma.** Es el único
  archivo en el que sus datos originales están en texto claro, y se
  encuentra junto al resultado; quien comparte una carpeta la comparte a
  ella también. Ahora la advertencia aparece como primera línea **dentro**
  del archivo, el área de salida nombra la ruta completa en lugar de solo
  el nombre del archivo, y en la línea de comandos el archivo se menciona
  siquiera: hasta ahora ahí no se sabía en absoluto que se había creado.
- **Anonimizar o seudonimizar es ahora una elección con nombre propio.**
  En ese lugar había hasta ahora una casilla „Nombrar igual los mismos
  nombres; la IA sigue reconociendo entonces quién es quién". Eso
  describía la utilidad y callaba la consecuencia: los marcadores
  numerados (`[NOMBRE_1]`, `[NOMBRE_2]`) son **seudonimización**, y los
  datos seudonimizados siguen siendo datos personales; quien creía haber
  anonimizado así, se equivocaba. Ahora ambos procedimientos aparecen uno
  junto al otro, cada uno con su precio. El valor predeterminado sigue
  siendo seudonimizar, porque un documento que después se sigue leyendo o
  que procesa una IA necesita sus referencias. Al anonimizar, la lista de
  sustituciones queda bloqueada: volvería a hacer el resultado
  reconducible. El manual y las preguntas frecuentes explican la
  diferencia en los 18 idiomas; en la línea de comandos el modificador se
  llama ahora también `--anonymisieren`.
- **La línea sobre la zona de depósito ahora dice lo que realmente es
  cierto.** Prometía „100 % de procesamiento local, sin nube ni cuenta,
  conforme al RGPD". Para sus documentos eso es cierto, para el programa
  no con esa generalidad: busca actualizaciones, comunica errores si se
  desea, recarga modelos y registra puestos de trabajo comprados. Ahora
  aparece ahí la afirmación más estricta y sostenible: sus documentos no
  salen del equipo.
- **En el resultado ahora siempre consta que hay que revisarlo.** Hasta
  ahora Maskuro comunicaba, tras una ejecución sin incidencias, „12
  dato(s) eliminado(s)" en verde y nada más; eso se lee como una garantía
  de haberlo encontrado todo. Los avisos solo aparecían cuando algo
  concreto no se pudo comprobar (imágenes, adjuntos desconocidos). Ahora,
  bajo cada resultado aparece de forma bien visible que no en todos los
  casos se reconocen todos los datos personales, que la revisión es cosa
  del usuario y que lo que falte hay que completarlo a mano; en la
  ventana, en el área de salida y en la línea de comandos. Sin ventana de
  aviso para cerrar de un clic: la frase queda ahí de forma permanente. La
  guía rápida lo dice ahora con las mismas palabras.
- **Tras una actualización, al iniciar aparece qué ha cambiado.** Hasta
  ahora una actualización se ejecutaba en silencio y no se distinguía de
  un reinicio. Ahora aparece una vez „Qué hay de nuevo", y quien se saltó
  una versión ve también lo intermedio. No en el primerísimo inicio: ahí
  sigue introduciendo la guía rápida.
- **Chino y japonés ahora encuentran nombres.** Hasta ahora no encontraban
  **ninguno**, no pocos, ninguno. A ambos modelos de idioma les faltaba la
  segmentación de palabras, sin la cual una frase sin espacios se
  considera una sola palabra; el programa recurría en silencio al modelo
  sustituto multilingüe. Ambos idiomas reconocen ahora personas y lugares
  como los demás. El diccionario japonés se carga junto con el idioma y no
  está en el programa; él solo pesaría unos 200 MB que de otro modo todos
  tendrían que cargar.
- **Rumanía se puede elegir como país.** Hasta ahora faltaba por completo.
  Con ello se reconocen direcciones rumanas („Strada Victoriei 30"),
  códigos postales con localidad („010061 București") y el Cod Numeric
  Personal, este último solo con dígito de control correcto, para que no
  se marque cualquier número de trece cifras en una factura. Hasta
  entonces, en los documentos rumanos el código postal quedaba legible
  junto al nombre de lugar tachado.
- **„Rasterizar página" en el editor.** Si no se puede eliminar texto de
  un PDF, algo que ocurre con archivos de generadores externos, ahora la
  página se puede sustituir, si se desea, por su imagen: el texto
  desaparece así de forma irrevocable, la página sigue siendo legible y
  buscable. El aviso que comunica el caso ofrece el paso directamente como
  botón; también se llega a él por „Herramientas → Rasterizar página".
  Deshacer recupera la página.
- **La interfaz ahora también está en croata, griego, lituano, esloveno,
  japonés y coreano.** Con ello son dieciocho idiomas. El manual, las
  preguntas frecuentes y los textos legales están completos en los seis.
  Los rótulos en el documento limpiado siguen a la interfaz: de
  `[NAME_1]` pasa a `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` o `[氏名_1]`.
  **En griego, japonés y coreano los rótulos están en caracteres
  latinos**: `[ONOMA_1]`, `[SHIMEI_1]`, `[IREUM_1]`. La interfaz permanece
  en su propia escritura; solo lo que se escribe en el documento es
  latino. La razón es el juego de caracteres del PDF: ahí los rótulos
  griegos y japoneses llegaban antes como `[??_1]`, con lo que ya no se
  podía distinguir nombre de lugar.
- **Se añaden nueve países, y siete existentes quedan completos.** Se
  reconocen de nuevo números de documento de identidad, fiscales y de
  seguridad social junto con direcciones para **Croacia, Eslovenia,
  Grecia, Lituania, Macedonia del Norte, Rusia, Ucrania, China y Japón**.
  En los países existentes se cerraron lagunas que pesaban más: para
  **los Países Bajos** y **Portugal** hasta ahora no existía ningún número
  de persona; el BSN neerlandés y el NIF portugués no se reconocían,
  aunque figuran en prácticamente cualquier documento de esos países.
  Polonia obtiene el número fiscal NIP, Dinamarca, Noruega y Finlandia sus
  direcciones, Canadá su código postal. Con ello son **35 países**.

### Eliminado

- **Para Linux no hay por ahora ningún paquete.** El código fuente
  funciona ahí, pero faltan tres cosas que esta guía promete bajo Linux:
  inicio automático, atajos de teclado globales y, según el entorno de
  escritorio, el icono en la barra. Entregar un paquete que puede menos de
  lo descrito sería el camino equivocado. Windows y macOS no se ven
  afectados.

### Mejorado

- **Los números de expediente ahora se encuentran en todos los idiomas.**
  „Aktenzeichen 12/2026-AB" se eliminaba, „File reference 12/2026-AB" o
  „Sygnatura 12/2026-AB" quedaban sin tocar: las palabras de campo por las
  que Maskuro reconoce ese tipo de número solo existían en alemán. Ahora
  conoce los equivalentes en doce idiomas, y como hasta ahora solo se
  sustituye el número; el rótulo delante queda, para que en el resultado
  se reconozca qué se eliminó ahí.
- **Maskuro ocupa en reposo unos medio gigabyte menos.** Al iniciar se
  cargaba hasta ahora también el modelo adicional del reconocimiento más
  preciso, para que la primera limpieza no tuviera que esperarlo. Medido,
  eso costaba 648 MB de memoria de trabajo y ahorraba 1,9 segundos, y lo
  costaba también cuando usted solo abría la ventana y volvía a cerrarla.
  El modelo se carga ahora la primera vez que se necesita; la línea de
  estado lo indica. El modelo de idioma se sigue cargando al iniciar: eso
  lo necesita de inmediato la vigilancia del portapapeles.
- **La zona de depósito ahora también se maneja sin ratón.** „Arrastre los
  archivos aquí" era una zona que reaccionaba a clics; con el teclado no
  se llegaba a ella, y un lector de pantalla la leía como un marco con
  texto dentro, no como lo que es. Ahora es un botón: la tecla Tab salta a
  él, las teclas de espacio e Intro abren el selector de archivos, y quien
  ha llegado a él lo ve por el borde. Por el menú „Archivo → Seleccionar
  archivos" ya se llegaba antes, pero había que saberlo.
- **El nombre del archivo limpiado ahora también se lee en voz alta.** En
  la lista de archivos aparece como segunda línea, más pequeña, bajo el
  original, pero solo estaba dibujado ahí, y un lector de pantalla
  nombraba solo el original. Precisamente esta línea está construida
  contra el error de creer que una ejecución no tuvo efecto porque en la
  carpeta está el original intacto. La línea dice ahora, leída en voz
  alta, „rechnung.pdf, resultado: rechnung_bereinigt.pdf".
- **Los elementos de control sin rótulo ahora dicen para qué sirven.** Los
  botones de icono en la lista de archivos, los botones de dibujo en la
  ventana de retoque y todos los campos de selección y entrada carecían
  de nombre para los lectores de pantalla; se anunciaban como „botón" y
  „cuadro combinado", sin decir de qué. Los botones de una línea mencionan
  además el archivo: en una lista de veinte entradas, si no, se oía veinte
  veces la misma frase.
- **Quien maneja el programa con el teclado vuelve a ver dónde está.** El
  botón „Limpiar" y los botones de icono en la lista de archivos están
  diseñados en color, y con ello el marco que el sistema suele poner
  alrededor del elemento de control activo dejaba de verse; al tabular, la
  mirada caía en el vacío. Ambos tienen ahora su propio marco en cuanto
  les toca el turno. Los botones no cambian de tamaño con ello.
- **Siete colores de texto eran demasiado pálidos, en ambas apariencias.**
  Medidos según la norma habitual (WCAG 2.1), las líneas de aviso pálidas,
  los textos secundarios en la zona de depósito, los puntos de la guía y,
  en la imagen oscura, además el azul y el rojo, quedaban por debajo del
  umbral de 4,5:1: legibles con buena luz y buena vista, si no, no. Todos
  se han elevado; la gradación se mantiene, los textos se siguen leyendo
  como textos secundarios. Otros tres, los colores en que se comunican
  avisos y éxito, mantenían el umbral por poco y se han ajustado también:
  quien no los lee, no lee la información de si algo salió mal.
  Visiblemente solo ha cambiado el botón „Limpiar" en la imagen oscura:
  ahora lleva texto oscuro en vez de blanco, como también los botones de
  acento de Windows 11.
- **Cada línea de la lista de archivos tiene ahora su propia cruz.**
  Hasta ahora había que seleccionar primero la línea y luego pulsar
  „Eliminar", dos pasos para una pequeñez. La cruz está a la derecha en la
  línea y basta con ella. El botón „Eliminar" de debajo ha desaparecido
  con esto; quien quiera deshacerse de varias líneas a la vez las
  selecciona y usa la entrada del menú contextual, que también indica
  cuántas son. „Eliminar todo" se mantiene. De la lista solo se quita
  siempre la línea, nunca un archivo del disco.
- **Antes de la verificación con IA ahora se indica si este equipo sirve
  para ello.** Hasta ahora en la ventana solo constaba cuán grande es el
  modelo. Quien lo activaba en un equipo débil solo notaba, con el primer
  documento, que tardaba muchísimo, tras 5,4 GB de descarga. Ahora la
  ventana indica **antes** la memoria de trabajo y el espacio libre y dice
  qué significa eso; **después** se mide la velocidad y se expresa en el
  tamaño del que se trata: „En este equipo, un documento de diez páginas
  tarda unos 12 minutos". Si es demasiado lento, el programa lo
  desaconseja y ofrece volver a desactivar el nivel; no prohíbe nada.
- **La medición de velocidad ahora se ejecuta en todos los equipos.**
  Hasta ahora solo aparecía si además se había configurado la aceleración
  gráfica, que solo existe en Windows. En todos los demás equipos el
  programa estimaba por ello la duración a partir de un equipo ajeno, y
  precisamente donde es lento, la estimación fallaba.
- **Las direcciones turcas también se encuentran en el escaneo.** En un
  membrete escaneado quedaba legible „34710 İstanbul", mientras el mismo
  dato desaparecía en el texto de al lado: el reconocimiento de texto lee
  la İ turca sin su punto, y el patrón esperaba una letra mayúscula. Lo
  mismo valía para „Bağdat Caddesi".
- **Se encuentran direcciones españolas sin nombre de calle propio.**
  „Gran Vía 5" quedaba sin tocar porque el patrón esperaba tras el tipo de
  vía otra palabra de nombre; en „Calle Mayor" hay una, en „Gran Vía" el
  tipo mismo ya es el nombre. Lo mismo vale ahora para „La Rambla" y
  „Castellana".
- **En la ventana „Acerca de este programa" ahora hay un aviso de
  transparencia** sobre que la aplicación se desarrolló con apoyo de
  inteligencia artificial. Se refiere a la creación del programa, no a su
  forma de trabajar: la limpieza se sigue haciendo exclusivamente en el
  propio equipo.
- **„Gestionar idiomas" muestra ahora primero los idiomas utilizables.**
  Para la mitad de los 48 idiomas no hay un modelo de idioma propio; ahí
  un modelo sustituto multilingüe reconoce nombres solo débilmente, en
  algunas escrituras nada en absoluto. Uno junto a otro en una lista,
  todos parecían equivalentes. El valor predeterminado muestra ahora solo
  los idiomas con modelo propio; mediante „Mostrados" los demás se pueden
  visualizar en cualquier momento, con una frase sobre lo que pueden y lo
  que no. No desaparece nada, y quien haya configurado un idioma limitado
  lo conserva.
- **La pregunta sobre un idioma faltante ahora indica la salida.** Cuando
  se reconoce un idioma para el que aún no hay nada configurado, el
  programa ofrecía hasta ahora solo „Cargar" o „Continuar sin él". Pero el
  reconocimiento puede equivocarse; en formularios cortos y listas con
  poco texto corrido, unas pocas palabras deciden. Por ello, en la ventana
  ahora consta que se puede cancelar y elegir a mano el idioma correcto,
  en vez de usar „Reconocer automáticamente". Esto ahorra, en caso de
  duda, una descarga de varios cientos de megabytes para un idioma que no
  se necesita en absoluto.
- **Los rótulos de marcador ahora hablan el idioma de la interfaz.**
  „[NAME_1]", „[ADRESSE_2]" y compañía estaban hasta ahora siempre en
  alemán, sin importar qué idioma estuviera configurado o en qué idioma
  estuviera redactado el documento. Ahora siguen el idioma de la
  interfaz; en inglés, por ejemplo, „[NAME_1]", „[ADDRESS_2]". No el
  idioma del documento: este se adivina con „reconocer automáticamente" y
  a veces está equivocado; el idioma de la interfaz nunca lo está.
- **Menos preguntas al retocar.** Dónde se guarda el resultado ahora
  consta de forma permanente abajo en la barra („→ vertrag_bereinigt.pdf",
  la carpeta en la información sobre herramientas); un clic ahí elige otro
  lugar sin guardar de inmediato. Con ello desaparece la pregunta al
  guardar por primera vez. La pregunta „¿ya editado, empezar de nuevo?" se
  puede recordar para la sesión, y dos ventanas de aviso que solo daban
  una información ahora están en la línea de estado. Se mantienen las
  preguntas que evitan un daño irreversible: el trabajo sin guardar al
  cerrar y la advertencia sobre texto no eliminado.
- **El resultado ahora indica dónde el propio escaneo no era legible.**
  En un documento escaneado, el reconocimiento de texto del dispositivo no
  lee todo correctamente; de „Solarstraße 9" sale entonces, por ejemplo,
  „Solaret^aß« B". Lo que se leyó mal así, ninguna verificación puede
  volver a encontrarlo: para cualquier patrón de búsqueda parece una
  ensalada de letras. El programa no puede cambiar nada al respecto, pero
  ahora nombra esos lugares con número de página; ahí suelen encontrarse
  sellos, membretes o añadidos manuscritos. Un aviso, no una advertencia:
  en un documento compuesto tipográficamente no aparece.
- **La lista de archivos ahora muestra cómo se llama el resultado.** Bajo
  el nombre del archivo aparece, tras la ejecución, el nombre del archivo
  limpiado („→ vertrag_bereinigt.pdf"). Hasta ahora solo constaba en el
  registro tras „Detalles", y quien miraba en la carpeta encontraba el
  original intacto. El nombre de la fuente se mantiene; de lo contrario ya
  no se vería de qué archivo procede un resultado.
- **Los botones de una línea terminada son más grandes y claros.** Ver,
  Retocar y „Mostrar en la carpeta" eran iconos planos sin superficie y se
  perdían en la lista, siendo justamente lo único que se sigue pulsando
  tras la ejecución.

### Corregido

- **En la interfaz en un idioma extranjero, las reglas propias de tachar,
  enmascarar y aplicar hash se pasaban por alto en silencio.** Quien había
  establecido que los nombres se tacharan en lugar de sustituirse, los
  obtenía de todos modos sustituidos, en cuanto el programa no se manejaba
  en alemán o inglés. El ajuste estaba ahí, simplemente no surtía efecto,
  y en el resultado no se veía la diferencia. Se veían afectados nueve de
  los doce idiomas de interfaz.
- **El ajuste „Idioma de los rótulos" no tenía efecto fuera de alemán e
  inglés.** Se podían elegir „Alemán" e „Inglés", pero en el documento
  seguía apareciendo el idioma de la interfaz. Ahora las tres
  posibilidades funcionan; el valor predeterminado „como la interfaz"
  sigue dando lo mismo que hasta ahora.
- **En fragmentos de texto cortos quedaban nombres sin tocar, por ejemplo
  en una cita de correo copiada.** Quien limpiaba un fragmento por el
  portapapeles a menudo solo veía tachada la dirección de correo, pero no
  el nombre debajo. Lo decisivo era el mero número de líneas: a partir de
  seis líneas el programa reconocía el fragmento como una relación y
  encontraba los nombres; por debajo, no; una cita de correo copiada tiene
  cinco. Una línea adicional cualquiera, por ejemplo un asunto, volcaba el
  resultado. Ahora bastan cuatro líneas, y en la medición desaparecen
  todos los nombres comprobados en lugar de un tercio. Esto no afecta a
  documentos más largos ni a texto corrido.
- **La aceleración gráfica de la verificación con IA se volvía a
  desactivar en cuanto se había configurado.** Tras la configuración, el
  programa mide si la gráfica en este equipo es realmente más rápida que
  el procesador; esa medición fallaba sin embargo siempre sin decirlo, y
  el resultado „ambos igual de rápido" decidía a favor del procesador.
  Quien había cargado los 65 MB obtenía después menos que antes. La
  medición ahora se ejecuta; si falla, ya no cambia nada.
- **La estimación de tiempo calculaba en cada equipo con una velocidad
  ajena.** Se basa en la misma medición; mientras esta no se ejecutaba,
  regía el valor del equipo de desarrollo. „Unos dos minutos" podía
  significar así media hora en un equipo lento.
- **El nivel de IA trabaja con un modelo de lenguaje nuevo, claramente
  mejor** (Qwen3.5-9B en lugar de Qwen3-4B) y ya no está limitado a alemán
  e inglés, sino que trabaja en doce idiomas. Medido con el corpus de
  verificación: la misma cantidad de datos encontrados que sin el nivel,
  pero menos de la mitad de tachados superfluos (75 → 31). El modelo es
  más grande (5,4 en vez de 2,4 GB) y necesita aproximadamente el doble de
  tiempo de cálculo; al activarlo se carga una vez, eliminando el antiguo.
- **Las direcciones en francés, italiano, español, portugués, polaco,
  turco y sueco ahora se eliminan por completo.** Hasta ahora solo
  desaparecía ahí el nombre de calle y de lugar; el número y el código
  postal quedaban legibles („[ORT_1] 28, 28013 [ORT_2]"). Para estos
  idiomas no había patrones de dirección propios; ahora están añadidos.
- **Griego y coreano no encontraban ningún nombre en absoluto.** En griego
  se debía al modelo sustituto; con el modelo propio, que ahora se puede
  cargar, se reconocen limpiamente nombres y lugares. En coreano se debía
  al programa: suponía que un nombre empieza con mayúscula, y el hangul no
  conoce mayúsculas. Se veían afectadas sobre todo unidades cortas: celdas
  de tabla, campos de formulario, entradas de lista.
- **Un modelo de idioma que no se podía cargar interrumpía la limpieza.**
  En vez de un mensaje de error, ahora interviene el modelo multilingüe, y
  el resultado indica que se trabajó con el reconocimiento más débil.
  Afecta actualmente a chino y japonés, cuyos modelos necesitan una
  separación de palabras que el programa aún no incluye.
- **Un idioma con modelo propio se consideraba instalado en cuanto
  cualquier otro estaba cargado.** Quien configuraba, por ejemplo, turco,
  obtenía con ello el modelo sustituto multilingüe, y chino, japonés,
  coreano o griego aparecían entonces con la casilla marcada y „0 MB" en
  la lista, aunque su propio modelo faltaba. Por ello nunca se podían
  recargar y trabajaban de forma permanente con el sustituto más débil.
  Ahora la lista muestra el estado real junto con el tamaño de carga.
- **Un nivel de reconocimiento fallido guardaba silencio.** Si estaba
  activado „Reconocimiento avanzado" o „Reconocimiento máximo (IA)", pero
  el modelo no se podía ejecutar, el programa seguía trabajando sin ese
  nivel, sin decir una palabra al respecto. El resultado tenía el mismo
  aspecto que cualquier otro, y el interruptor seguía en „activado": se
  tomaba entonces el resultado del nivel básico por lo mejor que se podía
  obtener. El resultado lo dice ahora y menciona ambas cosas: qué no se
  comprobó y cómo se puede volver a cargar el modelo. El caso no es raro:
  en algunos equipos el nivel de IA falla al cargar cuando falta la
  aceleración gráfica.
- **Un error al cargar el modelo adicional interrumpía toda la
  limpieza.** En „Reconocimiento avanzado" solo estaba protegida la
  evaluación del modelo, no su lectura, y precisamente ahí falla cuando el
  archivo está dañado o no encaja con el equipo. En vez de un mensaje de
  error, ahora hay un resultado del nivel básico junto con un aviso.
- **Un idioma dejaba de poder eliminarse, y con ello tampoco recargarse.**
  Quien en „Gestionar idiomas" quitaba la marca y aplicaba el cambio, leía
  „Alemán eliminado", pero veía la marca puesta de nuevo de inmediato. La
  causa era la toma desde la carpeta del programa: en una instalación para
  todos los usuarios, los modelos de idioma están protegidos contra
  escritura en la carpeta del programa, y el programa toma de ahí los que
  faltan en vez de recargar cientos de megabytes. Esta toma se ejecutaba
  en cada acceso, y volvía a copiar el idioma recién eliminado en el mismo
  instante. Ahora ocurre una sola vez; los modelos de idioma recargados se
  conservan con ello. Además, el programa comprueba después de eliminar:
  lo que no se pudo eliminar se comunica ahora como fallo en vez de como
  „eliminado".
- **En una instalación para todos los usuarios no se podía depositar lo
  recargado.** Quien instala el programa para todos los usuarios lo tiene
  en „Programas", y ahí no se puede escribir nada sin derechos de
  administrador. Para los modelos de idioma ya había desde hacía tiempo un
  lugar alternativo previsto, para lo demás no:
  - El **componente de vista de páginas** se descomprimía, tras 290 MB de
    descarga, en la carpeta del programa y fallaba ahí, sin dar ningún
    motivo. Ahora está junto a los modelos de idioma, donde según la
    intención siempre debió estar.
  - La **aceleración gráfica** no puede evitarlo: intercambia bibliotecas
    en el propio programa. En vez de cargar primero y fallar en silencio
    después, el programa ahora dice de antemano que aquí no funciona y
    qué significa eso; el reconocimiento máximo sigue trabajando, solo
    que mediante el procesador.
  - Un **idioma de reconocimiento de texto** incluido no se podía
    eliminar: se restauraba de inmediato desde la carpeta del programa.
    Misma causa que en los modelos de idioma, misma solución.
  - Al eliminar un idioma se podían borrar **datos de idioma de una
    instalación ajena de Tesseract**. Ahora solo se toca la propia
    carpeta.
  - El lugar alternativo solo era válido hasta ahora en Windows. Un
    archivo Linux hacia `/opt` tenía la misma necesidad sin la misma
    salida.
- **Al retocar desaparecía una línea entera, aunque solo se había
  enmarcado una palabra.** Quien tachaba un marcador en un archivo ya
  limpiado perdía la línea en la que estaba: de „Sehr geehrte Frau Doktor
  [NAME_1]" no quedaba nada, y el mensaje decía „se eliminó una palabra
  del documento". Se veía afectado cualquier archivo que ya hubiera pasado
  una vez por el programa, precisamente el caso para el que existe el
  retoque. El resto del texto ahora se mantiene, en su lugar original.
- **„EMPLOYEES" sobre una lista de nombres se tachaba a sí mismo.** El
  mismo caso que „MITARBEITER" en la 0.10.19, solo en inglés, donde había
  quedado pendiente. En versales, al modelo de lenguaje le falta el rasgo
  distintivo, y el encabezado está sobre puros nombres reales. Los nombres
  debajo siguen encontrándose. No se incluyó „staff": es un apellido
  existente, y la entrada arrastraría a cualquier „John Staff", la misma
  ponderación que en su momento con „Arbeiter".
- **La forma jurídica se sustituía una segunda vez.** En un membrete
  escaneado, el modelo de lenguaje leyó „GmbH", la dirección y el código
  postal como **un solo** lugar. La dirección y el código postal recortaban
  después sus propias partes, y quedaba la forma jurídica como hallazgo
  propio: en el resultado aparecía „[ORT_1] [ORT_2]", donde se quería
  decir „[ORT_1] GmbH". El nombre de la empresa se sigue sustituyendo;
  solo el añadido desnudo se mantiene ahora, y el resultado se lee como un
  membrete en vez de como un ejercicio de rellenar huecos.
- **Un hallazgo recortado no se volvía a verificar.** La causa del caso
  anterior, y va más allá: los filtros contra hallazgos adivinados
  funcionaban sobre lo que los reconocedores **comunican**, no sobre lo
  que queda tras la resolución de solapamientos. Si un hallazgo largo se
  recorta en un reconocedor más fuerte, el fragmento es un texto distinto
  del evaluado, y nadie volvía a mirarlo. Ahora sí.
- **„Está utilizando la versión más reciente", aunque no se pudo
  comprobar en absoluto.** Quien había configurado como canal de
  actualización „Vista previa (Beta)" o „Estable, recomendado" recibía
  esta información, aunque en esos canales hasta ahora no había aparecido
  nada en absoluto. Ahora el programa dice exactamente eso, y sugiere
  elegir otro canal en los ajustes.
- **Cerrar la ventana durante la carga hacía fallar un hilo.** Quien
  iniciaba Maskuro y volvía a cerrar la ventana de inmediato, mientras los
  modelos de idioma todavía se cargaban, obtenía en el registro un informe
  de error: el proceso de carga se dirigía a una ventana que ya no
  existía. No tenía consecuencias visibles, pero en el registro aparecía
  un fallo donde solo alguien había sido más rápido que el programa.
- **El resultado ahora se mira, no solo se relee.** Hasta ahora una
  página se consideraba limpia cuando el valor ya no estaba en el texto.
  En un escaneo eso no es prueba de nada; ahí el texto visible es una
  imagen. Por ello, al final se comprueba si la zona en el resultado está
  realmente tachada; si ahí todavía hay papel claro, el informe lo dice
  expresamente en vez de comunicar „sustituido".
- **Un dato sustituido permanecía en la imagen.** Si el valor estaba en
  una imagen, un membrete escaneado, un sello, una página escaneada
  entera, se eliminaba del texto del documento, pero seguía siendo
  **visible**: lo que lee el ser humano ahí son píxeles. El informe
  comunicaba de todos modos „sustituido". Ahora la zona en la imagen se
  tacha, sea cual sea la estrategia configurada, y el marcador aparece
  claro sobre ese fondo, feo, pero honesto, y la asignación se conserva.
  Si un formato de imagen no se puede editar, el resultado ahora lo dice
  expresamente en vez de tener buen aspecto.
- **En un escaneo faltaba por completo el marcador.** La capa de texto de
  una página escaneada se dibuja invisible, y un marcador que se insertó
  en ella lo heredaba: puesto, pero no visible. En el lugar del hallazgo
  no quedaba nada después.
- **Un reconocimiento de texto que no podía ejecutarse en absoluto se
  consideraba aprobado.** Si faltaba el archivo de idioma o el motor de
  reconocimiento fallaba, el informe comunicaba „Imagen(es) … se
  verificaron mediante reconocimiento de texto (0 hallazgo(s))", es decir,
  una verificación que nunca tuvo lugar. En un escaneo esa es la única
  verificación posible: un contrato con una dirección legible en la
  imagen de página se consideraba así terminado. Ahora el informe dice que
  no se verificó nada, y por qué.
- **El archivo de idioma se buscaba en la carpeta equivocada.** Si en el
  propio directorio de idiomas había otros idiomas distintos al del
  documento, el motor de reconocimiento recibía precisamente ese
  directorio y fallaba, aunque el idioma correcto estaba justo al lado.
  Ahora se busca el **idioma**, no la carpeta.
- **La advertencia sobre texto no eliminado aconsejaba algo que no
  existe.** Remitía a „Tachar como PDF", pero eso genera una vista PDF de
  archivos de *Office* y no está disponible en absoluto para un PDF. Quien
  quería seguir la advertencia buscaba en vano. Ahora ahí está el botón
  que resuelve el asunto.
- **En el editor, las barras y los marcadores quedaban junto al lugar
  marcado.** Se veía afectado cualquier PDF en el que una línea termina en
  un guion y la palabra continúa en la siguiente; en los escaneos esto
  llama especialmente la atención porque los textos de contrato están
  divididos de forma continua. Las dos mitades de línea se consideraban
  *una* palabra que se extiende a lo ancho de la caja de texto, y cualquier
  marco cerca de ella heredaba esa extensión. El reconocimiento en sí no
  cambia con ello: el corpus de medición da el mismo resultado que antes.
- **El editor advertía que el texto „todavía está en el documento",
  aunque se había eliminado.** Si la misma palabra aparecía varias veces
  en una página, la norma en los contratos, la autoverificación
  comunicaba un fallo tras cada intervención. Ahora cuenta las apariciones
  en vez de solo comprobar si la palabra sigue apareciendo en algún sitio.
  Ante un fallo real, sigue advirtiendo sin cambios.
- **El archivo de resultado se llamaba „_bereinigt" en todos los
  idiomas.** Se quería siempre que el añadido al nombre siguiera el idioma
  de la interfaz; en inglés lo hacía („_cleaned"), en los otros dieciséis
  idiomas no. Quien usaba el programa en finés obtenía
  „asiakirja_bereinigt.pdf". Ahora el archivo se llama
  „asiakirja_puhdistettu.pdf", en japonés „書類_除去済み.pdf" y así
  sucesivamente, cada uno con la palabra que esa misma interfaz usa en su
  mensaje de finalización. Quien haya configurado un añadido propio lo
  conserva.
- **„Gestionar idiomas" se rotulaba siempre en alemán.** En la lista de
  los 48 idiomas de documento aparecían los nombres alemanes, sin importar
  qué interfaz estuviera configurada: un usuario finlandés leía
  „Chinesisch". Ahora aparece ahí el nombre en su idioma y, detrás, el
  nombre propio: „Kiina (中文)". El nombre propio es intencionado: quien
  reconoce el idioma por su propio nombre lo encuentra también cuando la
  palabra finlandesa no le dice nada.

## 0.10.19 – 12 de agosto de 2026

### Mejorado

- **La entrada en el menú contextual ahora habla su idioma.** Hasta ahora
  aparecía allí el texto en alemán en todos los sistemas, incluso en un
  Windows en inglés. Ahora sigue el idioma de interfaz configurado, y quien
  cambia el idioma ve la entrada renombrada de inmediato, sin necesidad de
  reinstalar. (Windows; en macOS y Linux el nombre del menú es a la vez un
  nombre de archivo, eso llegará más adelante.)
- **El editor recuerda en qué vista trabajó por última vez.** Quien usa la
  vista de páginas la obtiene automáticamente en el siguiente documento,
  sin tener que activarla cada vez. Quien nunca la ha usado no nota nada:
  solo se restaura si el componente necesario ya está cargado, nunca se
  carga nada adicional para ello.

### Corregido

- **„EMPLEADOS" sobre una lista de nombres se tachaba a sí mismo.** En
  directorios de empleados y organigramas, el encabezado desaparecía como
  supuesto nombre; está ahí sobre puros nombres reales, y en mayúsculas al
  modelo de lenguaje le falta el rasgo distintivo. Los nombres debajo
  siguen encontrándose.
- **Las cantidades se confundían con direcciones.** En facturas,
  albaranes y listas de almacén desaparecían datos como „3390 Protocolo",
  „1030 Importe" o „3390 Almacén" como supuesto código postal con
  localidad: cualquier cifra de cuatro dígitos parece un código postal
  austríaco. Si tras el número hay una palabra que la aplicación reconoce
  como sustantivo, departamento, actividad o etiqueta de campo, ahora se
  mantiene. Las direcciones reales quedan intactas, incluso las que a la
  vez son una de esas palabras („4692 Lugar"). Lo que no queda resuelto es
  el caso de que tras el número haya una palabra totalmente corriente
  („3390 Estante"); para eso hace falta un listado de códigos postales.
- **La ayuda mencionaba una opción de menú que no existe.** El manual, la
  imagen y el mensaje al final de la instalación hablaban de „Limpiar
  documento para IA"; pero la entrada del menú contextual se llama
  „Eliminar datos personales". Quien seguía la ayuda buscaba en vano. Los
  tres lugares nombran ahora la opción de menú tal como se llama
  realmente.
- **„Iniciar con el sistema" no se podía desactivar.** Quien había
  marcado „Iniciar con Windows" durante la instalación veía, pese a ello,
  una casilla vacía en los ajustes, y más grave aún: activar y desactivar
  en la aplicación no tenía efecto, el programa seguía iniciándose con
  Windows. La causa eran dos lugares donde Windows busca programas de
  inicio; la aplicación solo conocía uno de ellos. Ahora cuentan ambos, el
  interruptor muestra el estado real y actúa en ambas direcciones. También
  se tuvo en cuenta: quien desactiva la entrada en el Administrador de
  tareas lo ve ahora en la aplicación, y quien la vuelve a activar allí
  anula con ello la desactivación.
- **Los encabezados sobre listas de nombres se tachaban.** „LISTA DE
  PARTICIPANTES REUNIÓN DE TALLER" o „RESUMEN DE PERSONAL ADMINISTRACIÓN"
  sobre una lista de personas desaparecían como supuesto nombre. En
  mayúsculas, al modelo de lenguaje le falta su mejor rasgo de
  reconocimiento, y en alemán cada sustantivo se escribe con mayúscula
  inicial: „Teilnehmerliste Werkstattgespräch" parece entonces „Anna
  Huber". Las composiciones en `-liste`, `-dienst`, `-gespräch`,
  `-sitzung` y `-besprechung` ahora se mantienen. Las palabras base solas
  siguen considerándose nombres: *Liste* y *Dienst* son apellidos
  existentes, *Teilnehmerliste* no lo es.
- **Los datos escritos en vertical recibían un marcador ilegible.**
  Números de expediente al margen de la página, iniciales del gestor
  junto al lomo, encabezados de tabla en vertical: esos datos se
  encontraban y eliminaban, pero el marcador salía atravesado sobre el
  texto, comprimido a uno o dos puntos y a veces fuera del borde del
  papel. Ahora sigue al texto: en vertical, en tamaño legible y en la
  misma dirección en que estaba el dato. Lo mismo ocurría en páginas
  giradas posteriormente (texto escrito en horizontal con una rotación de
  página registrada, como la entregan algunos programas de salida);
  también ahí el marcador queda ahora tal como se ve la página. „Sehr
  geehrte Frau Doktor Anneliese Berger" solo daba „Anneliese" como
  nombre; „Berger" quedaba en el documento. Lo mismo afectaba a cualquier
  nombre con segundo nombre („Frau Anna Maria Berger"). La causa era la
  regla para el nombre tras un tratamiento: tenía dos posiciones de
  palabra, y un título o un segundo nombre consumía la primera. Con „Dr."
  nunca se notaba, el punto rompe la regla y el modelo de lenguaje
  capturaba el nombre completo. Ahora los títulos se saltan sin consumir
  una posición, y el nombre puede constar de tres partes. Un cargo
  **después** del nombre sigue sin funcionar: „Frau Anna Huber
  Geschäftsführerin" reemplaza el nombre, no el cargo.
