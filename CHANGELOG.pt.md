O que muda de versão para versão – descrito do ponto de vista da aplicação,
não das suas entranhas. Quem quiser saber *do que* ela é feita encontra isso em
[LIZENZEN.md](LIZENZEN.md); aqui está o que muda para o trabalho com ela.

A numeração segue a contagem habitual: o **primeiro** número muda quando algo
deixa de funcionar como antes, o **segundo** com novas funcionalidades, o
**terceiro** com correções de erros.

## 0.10.50-alpha.20260903 – 3 de setembro de 2026

- Marcas de empresa recorrentes em PDFs são limpas de forma consistente,
  mesmo quando o reconhecimento de texto lê o logótipo de forma diferente
  numa página ou omite por completo o selo redondo. Uma desmarcação
  expressa na pré-visualização mantém-se vinculativa e não pode ser
  anulada por nenhum ajuste posterior.
- Preços sem moeda em tabelas digitalizadas são agora ocultados na
  íntegra mesmo quando o cabeçalho da tabela e os valores estão em
  imagens de PDF diferentes e sobrepostas. Quantidades, horas, pesos e
  percentagens permanecem; números muito distantes entre si deixam de ser
  ligados por engano a um montante.
- A pesquisa de assinaturas capta agora também traços azuis fracos
  comprovados e siglas de assinatura vermelhas estreitas. Diagramas
  pontilhados, curvas de medição, carimbos, logótipos e marcações de
  edição vermelhas largas ficam excluídos deste ajuste rigoroso.
- As ocultações em imagens de PDF rodadas, espelhadas, distorcidas ou
  recortadas atingem agora o verdadeiro polígono da imagem. Cargos
  técnicos em posições de prestação, valores técnicos de veículo e pneu,
  bem como „compensação" técnica, são simultaneamente delimitados de
  forma mais rigorosa contra falsos resultados; cargos de contacto e
  números de telefone expressamente identificados permanecem protegidos.
- A verificação visual antes de guardar um PDF deixa de bloquear a
  janela: em documentos grandes com muitos resultados, ficava até agora
  vários segundos sem resposta; agora um aviso indica que está a ser
  verificado, e a janela continua a desenhar-se.
- A recuperação de um valor a partir de uma imagem no editor de correção
  só lê agora cada imagem original uma vez por reconhecimento de texto;
  até agora corria de novo a cada recuperação adicional para as mesmas
  imagens.
- O carregamento posterior do nível avançado e do modelo de assinaturas
  precisa de quase nenhuma memória: o pacote de 596 MB era até agora
  mantido, verificado e descompactado por completo na memória – mais de
  um gigabyte de pico com o programa em execução, em computadores com
  8 GB o momento em que tudo começava a engasgar. Agora flui em blocos
  para o disco, sendo aí verificado e descompactado.
- A pesquisa no editor de correção deixa de bloquear PDFs grandes: a
  primeira letra no campo de pesquisa lia até agora todas as páginas de
  uma vez – com 200 páginas, a janela ficava dois segundos parada, e
  outra vez depois de cada ocultação. As páginas são agora lidas aos
  poucos; até lá, „A ler…" aparece no contador, o resultado é o mesmo.
- As páginas de PDF rasterizadas – depois de um reconhecimento de texto
  ou quando um texto não pôde ser removido de forma limpa – são
  guardadas significativamente mais pequenas e sem perda de imagem: em
  vez de sempre como JPEG, cada página é também codificada sem perdas, e
  a versão mais pequena vai para o ficheiro. Uma digitalização limpa
  encolhe assim de 248 para 48 KB, o documento de exercício com
  reconhecimento de texto de 913 para 702 KB; o texto mantém-se
  perfeitamente nítido.
- Os modelos carregados posteriormente (nível avançado, assinaturas,
  rostos, segundo reconhecimento de texto) são libertados da memória ao
  fim de dez minutos sem limpeza. Até agora permaneciam carregados até
  ao fim do programa – quem tivesse usado uma vez a pesquisa de
  assinaturas e o nível avançado mantinha permanentemente mais de dois
  gigabytes. A próxima execução volta a carregá-los em um a dois
  segundos; a barra de estado avisa.
- PowerPoint: os nomes genéricos de esquemas de diapositivo e diapositivos
  mestre („Vazio", „Diapositivo de título") deixam de ser substituídos
  como indicação. „Vazio" também é um local e era ocultado por engano em
  todas as apresentações em alemão e inglês; agora só são limpos os
  nomes atribuídos manualmente dos próprios diapositivos.
- Em PDFs, o alisamento de linhas deixa de arrastar o início da linha
  seguinte para um resultado: o número do ponto de lista seguinte a
  seguir a uma data valia como número de telefone, um cabeçalho de campo
  como „Código" ou „Número de encomenda" a seguir a um número valia como
  código postal com localidade, e a linha de localidade sob a morada
  duplicava a localidade. O resultado correto e mais curto era, com
  isso, suprimido. Em 132 PDFs de corpus, dos 24 resultados adicionais de
  alisamento mantêm-se os dois reais; no corpus de prática, os falsos
  alarmes descem de 29 para 21 com a mesma taxa de deteção.
- „Pesquisar e ocultar pasta de PDFs" no editor de correção deixa de
  bloquear a janela: a execução corre em segundo plano, o progresso e o
  botão de cancelar respondem, e os menus ou separadores deixam de poder
  ser acionados a meio de um ficheiro por concluir.
- As páginas digitalizadas com resultados são agora reescritas apenas
  uma vez ao ocultar, em vez de duas: até agora, o programa preenchia as
  caixas dos resultados e as das justificações em duas passagens, e a
  segunda comprimia mais uma vez a imagem de digitalização acabada de
  guardar. Isto poupa tempo em grandes digitalizações e uma perda de
  qualidade na imagem.
- Folhear, ampliar e as miniaturas no editor de correção respondem mais
  depressa: cada página renderizada passava até agora por uma compressão
  como PNG e voltava logo a seguir, só para ser mostrada – em ecrãs de
  alta resolução, cerca de um décimo de segundo por página. A imagem
  chega agora diretamente, pixel a pixel igual.
- A verificação visual antes de guardar um PDF („prova de saída") é cerca
  de três vezes mais rápida, com o mesmo resultado.
- A janela principal fica pronta mais um quarto de segundo antes: a
  verificação de se o reconhecimento de texto está pronto neste
  computador corria durante a construção da janela – no Mac incluindo um
  pedido de teste ao reconhecimento do sistema –, e a página de
  definições dos componentes adicionais consultava para isso o estado
  dos 48 idiomas. Ambos acontecem agora em segundo plano, ou só quando a
  lista de idiomas é realmente aberta; até lá consta „A verificar
  reconhecimento de texto…".
- Depois de uma pesquisa de assinaturas, o programa ocupa cerca de
  300 MB menos de memória: o modelo de deteção estava até agora
  duplicado na memória – uma vez para verificar a sua autenticidade, uma
  vez para calcular. Continua a ser verificado, apenas sem a segunda
  cópia.
- O reconhecimento de texto em PDFs tornou-se visivelmente mais rápido:
  para cada cabeçalho de campo de uma página („Data de nascimento:",
  „Número fiscal:") era até agora enviado um teste próprio por tipo de
  indicação através do reconhecimento – de novo em cada página, mesmo
  que o mesmo cabeçalho já constasse dez páginas antes. A resposta é
  agora memorizada; um caderno de encargos de duas páginas fazia assim
  324 perguntas, agora apenas as diferentes. Os resultados são os
  mesmos.
- Tabelas grandes voltam a ser limpas em segundos em vez de minutos: no
  modo anonimizador – o padrão –, a comparação de valores já conhecidos
  com cada célula adicional ficava mais lenta, porque uma memória
  intermédia era descartada e reconstruída a cada resultado. 5.000
  células precisavam para isso de cerca de 18 segundos, agora meio
  segundo; o resultado é carácter por carácter o mesmo.
- A janela principal aparece, mais uma vez, visivelmente mais depressa: a
  lista de países das definições puxava, ao construir a janela, toda a
  biblioteca de deteção para primeiro plano – cerca de 0,7 segundos no
  Mac, correspondentemente mais no Windows –, apesar de para isso só
  serem necessários os nomes dos países. A lista vem agora de um
  catálogo leve; a biblioteca carrega, como previsto, em segundo plano,
  enquanto a janela já está pronta. Isto aplica-se também depois de cada
  mudança de idioma ou de aparência que reinicie o programa.
- O laboratório de documentos processa agora integralmente cabeçalhos de
  campo cortados, sombras locais de valor e recortes de digitalização
  acentuados através de contentores PDF, DOCX e ODT. A matriz abrange
  680 ficheiros de 40 famílias de documentos e 17 eixos de contentor. O
  Maskuro remove, nos novos perfis básico e de características, bem como
  nos completos, todos os valores de referência, sem falso alarme
  medido, valor de preservação danificado ou interrupção.

- As digitalizações usadas várias vezes são agora verificadas e limpas
  em cada posicionamento visível: o laboratório de documentos partilha o
  mesmo objeto de imagem em várias páginas, tamanhos e orientações em
  PDF, e refere a mesma parte de imagem várias vezes em DOCX e ODT. Nomes
  técnicos de moldura ODT como „Digitalização de formulário pequena
  transversal" deixam de valer como pessoa; nomes e locais livres com
  início semelhante permanecem protegidos. Um palpite geral de
  formulário da execução final de páginas de PDF já não pode gerar um
  falso resultado grande de morada numa área de imagem já lida de forma
  independente. Os 120 novos contentores atingem, nos perfis básico e de
  características, todos os 813 e 840 valores de referência
  respetivamente, sem falso alarme, violação de preservação ou
  interrupção; a aceitação completa de características de 800 ficheiros
  confirma 5.600/5.600.

- O laboratório alemão de OCR abrange agora 560 digitalizações de 40
  famílias de documentos. Novas variantes cortam as margens do cabeçalho
  de campo e da página, ou colocam uma sombra diretamente sobre um
  valor. O Maskuro protege assim também nomes, moradas, datas de
  nascimento, códigos médicos e números de identificação legendados com
  legenda parcialmente danificada. Simultaneamente, restos de campo de
  formulário, cabeçalhos oficiais, bem como termos jurídicos e
  informativos objetivos, deixam de ser substituídos como pessoas ou
  locais. Os perfis completos básico e de características atingem
  3.794/3.794 e 3.920/3.920 valores de referência respetivamente, sem
  falso alarme medido ou interrupção.

- A seleção automática de imagens em PDF deixa de remover fotografias de
  produto de grande formato, etiquetas energéticas e séries de retratos
  apenas por começarem na margem superior da página. Imagens de
  cabeçalho/rodapé realmente planas e cabeçalhos de carta que arrancam
  na margem da folha continuam a cair. Em diretórios de colaboradores,
  os nomes são agora reconhecidos também a partir de entradas
  estruturalmente repetidas, mesmo quando o título visível do documento
  existe apenas como imagem. A deteção deixa de estar limitada a duas
  palavras de cargo concretas e à sigla „DW": uma a quatro funções com
  quebra de linha, bem como „Extensão", „Ramal", „Ext." e „Extension",
  são deduzidas a partir da estrutura comum. Cargos e cabeçalhos de
  secção permanecem, mesmo quando o modelo de linguagem, depois da
  resolução de sobreposição, só deixa um adjetivo de cargo. Grelhas
  horizontais de cargo deixam de valer, por engano, como colunas de
  nomes. Se o OCR de página colar vários cartões numa palavra
  extremamente larga com maiúsculas internas, uma contraverificação
  local estreita separa as caixas de palavra reais; com isso não fica
  nem um nome isolado nem uma barra de erro larga. Logótipos de empresa
  de várias linhas repetidos são ocultados com base num modelo de pixel
  idêntico já confirmado, também em páginas sem texto OCR utilizável e
  com até dois pixels de desvio de posição; segundas leituras locais
  mais curtas do OCR deixam, ao mesmo tempo, de poder acrescentar uma
  área de cabeçalho maior como nome inventado. Números de página antes
  de um cabeçalho de carta de empresa deixam de pertencer ao nome da
  organização, nomes de marca reais que começam por números permanecem
  protegidos. Vários termos medidos de produto, técnicos e de formulário
  deixam de ser sugeridos como pessoas.

- A pesquisa de assinaturas em PDFs só corre agora depois da limpeza de
  imagem por OCR, visita também páginas sem resultado de texto comum e
  recalcula corretamente as caixas de resultado de páginas rodadas de
  volta ao espaço do documento. Fotografias de produto densas deixam de
  ser ocultadas como assinatura. Sobre campos de assinatura claramente
  legendados, um mecanismo de recurso estreito de traço fecha pequenas
  lacunas do modelo; linhas vazias com data pré-impressa não o
  desencadeiam. Digitalizações puras com apenas resultados de OCR/
  assinatura deixam de falhar nesta fase por causa de um ocultador de
  imagem só carregado no ramo de texto.

- Muitos documentos abertos em simultâneo permanecem distinguíveis no
  editor de correção: os separadores deixam de encolher até um mero
  sinal de reticências, e um botão de lista à direita mostra todos os
  nomes completos de ficheiro uns sob os outros. Os separadores podem
  ser reordenados por arrasto e removidos com a sua cruz na mesma lista
  que na janela principal; trabalho ainda não guardado continua a ser
  esclarecido primeiro. Um clique direito oferece ainda „Fechar",
  „Fechar outros separadores" e „Fechar separadores à direita".

- Um bloqueio breve do Windows por antivírus ou índice de pesquisa deixa
  de fazer falhar, com „Acesso negado", a pasta de modelo de idioma ou
  dicionário já carregada, na sua colocação final. O Maskuro tenta agora
  repetir esta última mudança de pasta por um curto período.

- O laboratório de documentos alemão verifica agora contentores também
  com rotação variável de página de PDF, imagens de PDF rodadas de forma
  independente, bem como imagens de tabela dimensionadas e recortadas em
  DOCX e ODT. Valores de campo em imagens visivelmente rodadas voltam a
  ser totalmente reconhecidos, identificadores técnicos de coluna deixam
  de ser substituídos como locais, e nomes com apelido comum deixam de
  ser divididos em resultados parciais duplicados pela verificação de
  consistência posterior. A matriz, duplicada para 320 ficheiros, atinge,
  com deteção de data, dinheiro e medicina ativada, 2.240/2.240 valores
  de referência, sem falso alarme medido ou interrupção.

- PDFs de imagem de várias páginas, PDFs mistos de texto/imagem e
  digitalizações incorporadas em DOCX ou ODT são agora verificados num
  laboratório próprio de 160 ficheiros, abrangendo todas as 40 famílias
  de documentos alemãs. Nomes técnicos de moldura ODT e códigos de
  aparelho legendados deixam de ser substituídos como locais; nomes,
  locais e moradas reais nas mesmas estruturas permanecem protegidos.
  Com a deteção médica ou de dinheiro ativada, uma dosagem diretamente a
  seguir ou um intervalo de pagamento são também removidos por completo.
  As execuções de contentor, base de texto, características de texto e
  características de OCR atingem, em conjunto, os respetivos totais
  completos, sem falso alarme medido ou interrupção.

- A verificação de segurança antes de guardar mostra agora os locais de
  PDF suspeitos como lista selecionável individualmente. „Verificar no
  editor" abre exatamente a página escolhida e marca a área; resultados
  parciais sobrepostos no mesmo local aparecem agora apenas uma vez. Os
  novos textos de interface estão completos nos 17 idiomas de interface
  traduzidos.

- Os ficheiros Markdown mantêm, ao substituir, a sua sintaxe de
  referência, destaque e nota de rodapé. Para isso, o Maskuro lê uma
  versão de comprimento idêntico em carateres, sem marcações Markdown;
  travessões em endereços de e-mail, asteriscos de cálculo e referências
  comuns sem indicação pessoal permanecem inalterados.

- Várias entradas manuscritas na mesma página de PDF são agora
  procuradas em até três passagens. Traços já encontrados são apenas
  ocultados na imagem de trabalho, para deixarem de suprimir assinaturas
  mais fracas; em páginas rodadas, as áreas de ocultação voltam a ficar
  no local visível encontrado. Preenchimentos de imagem de fases de
  segurança anteriores mantêm-se na reescrita posterior.

- „Repor todas as definições" abrange agora também „Texto em imagens".
  Se o componente de OCR não estiver disponível, o interruptor
  permanece tecnicamente desligado, sem ser marcado por engano como
  divergente do estado de fábrica.

- Grandes fragmentos de imagem na margem superior da página deixam de
  valer como cabeçalho apenas pela sua posição. Com isso, mantêm-se
  sobretudo descrições de artigo e conteúdos de tabela baseados em
  imagem. Resultados de e-mail e formulário recém-reconhecidos e exatos
  por tipo deixam também de ser filtrados da verificação visual final
  numa área de imagem já verificada.

- Linhas técnicas de posição e artigo em propostas de climatização e
  eletricidade são distinguidas de forma mais rigorosa de pessoas,
  locais e organizações. Isto afeta, entre outros, tipos de cabo,
  alimentação AC, números de posição, bem como códigos de produto em
  maiúsculas; nomes e moradas reais permanecem protegidos.

- A verificação de PDFs limpos reais deixa de confundir componentes de
  preço como `1 699,59` com números de telefone e deixa de recortar de
  uma data completa como `08.05.2025` uma suposta indicação de cartão.
  Nomes a seguir a uma saudação terminam na quebra de linha em vez de na
  rua seguinte; nomes de local em nomes de ficheiro de anexo são
  limitados ao local real. Cores de veículo, valores técnicos de estado,
  designações de atividade comercial e formas jurídicas de produto
  também se mantêm. Leituras danificadas de marcador como `|PLLZ`
  deixam de ser tratadas de novo como indicação pessoal numa segunda
  passagem de OCR.

- As imagens de PDF guardadas lateralmente recebem, na verificação
  visual final, um olhar adicional na sua posição de imagem inalterada.
  Este só pode ocultar adicionalmente valores que o Maskuro já tenha
  reconhecido com segurança na mesma página. Assim, por exemplo, um
  pequeno carimbo de morada rodado é totalmente coberto, sem inventar
  novas palavras como indicações pessoais a partir de títulos de imagem
  ou desenhos técnicos.

- Em textos OpenDocument, as iniciais do autor de uma nota (comentário)
  são agora limpas em conjunto com o autor. O LibreOffice regista-as ao
  lado do nome completo como forma curta própria e mostra exatamente
  essa na margem da página; até agora ficava ali „SO", enquanto
  „Sieglinde Ortner" ao lado já era há muito um marcador. Só é limpo
  quando o autor foi efetivamente substituído – a nota de um
  departamento mantém a sua identificação.

- Em cartas comerciais italianas, as fórmulas padrão no início de frase
  deixam de valer como nome ou local: „Restiamo a disposizione",
  „Rimaniamo", „Attendiamo", „Alleghiamo", „Comunichiamo" e „Auguriamo
  buon lavoro" ficavam até agora presas como suposta pessoa ou
  indicação de local. Nomes reais no mesmo local („Rossi Mario")
  continuam a ser reconhecidos.

- Digitalizações de duas colunas protegem agora identificações e
  indicações de local legendadas mesmo quando o reconhecimento de texto
  fornece primeiro todos os cabeçalhos de campo e só depois todos os
  valores. A atribuição segue a linha de pixel visível e funciona também
  em páginas rodadas 90 graus. Partes estreitamente separadas de uma
  identificação de passaporte ou contrato são ocultadas em conjunto;
  datas de nascimento legendadas, códigos ICD e PZN também são
  cobertos, palavras técnicas seguintes permanecem. Nomes curtos e nomes
  de utilizador são protegidos em campos exatos; endereços de e-mail
  divididos em várias palavras de OCR só em proximidade estreita e com
  gramática de e-mail completa. Uma correção ligada a campo de
  carateres facilmente confundíveis, bem como a releitura local de um
  campo de pessoa ainda vazio, cobrem digitalizações danificadas e
  rodadas, sem alargar campos técnicos ou valores já atribuídos.
  Margens de segurança seguem o tamanho da palavra, e o perfil de
  características inclui unidades de dosagem e intervalos de pagamento
  diretamente vizinhos. Formulários digitalizados ligeiramente
  inclinados são reprojetados geometricamente a partir de várias linhas
  de OCR na mesma direção; ruído de arredondamento ou testemunhos
  contraditórios não bastam. Prefixos curtos de letras mantêm-se antes
  de uma identificação com hífen, e um resultado de morada legendado
  completo substitui apenas o seu resultado parcial de rua do mesmo
  tipo. Um cabeçalho de campo de cargo mal lido só cai numa coluna de
  formulário comprovada por pelo menos três cabeçalhos conhecidos; nomes
  de chat permanecem protegidos. Um corte de margem apertado e uma
  sobre-exposição local com reflexo de luz diagonal complementam a
  matriz de imagem. Resultados de pessoa, local e empresa que se
  estendem por várias linhas de formulário são limitados ao respetivo
  valor numa coluna de campo ocupada várias vezes. Um valor técnico de
  posição só cai com cabeçalho de posição e forma de identificação
  correspondente; nomes reais permanecem protegidos. Também valores de
  e-mail interrompidos pelo reflexo de luz são removidos atrás de um
  cabeçalho de campo de e-mail expresso com margem de imagem estreita e
  limitada pela vizinhança. Dois pares campo-valor da mesma linha
  visível são agora avaliados de forma independente; valores numa linha
  de base mais profunda só são associados após três testemunhos
  geométricos coincidentes. Assim, números de identificação, datas de
  nascimento e moradas permanecem totalmente protegidos mesmo em
  esquemas de formulário densos. Rua, código postal e localidade só são
  unidos dentro do mesmo campo de morada e com gramática postal
  correspondente. Campos técnicos delimitados de forma restrita para
  meios de trabalho/auxiliares e estado dentário deixam de gerar falsos
  alarmes de local ou diretório; nomes reais e campos com nomes
  semelhantes permanecem protegidos. O laboratório alemão de documentos
  abrange agora 440 digitalizações e atinge 2.981/2.981 no perfil básico
  e 3.080/3.080 no perfil de características. Todas as onze mutações de
  imagem e todas as 40 famílias de documentos estão em 100 por cento,
  continuando sem falso alarme medido, violação de preservação ou
  interrupção.

- Camadas de texto de PDF com separadores de célula perdidos limitam
  agora os resultados de organização, morada e local com base na
  estrutura repetida de campo-valor. Cabeçalhos de campo antes de
  valores de empresa e setas técnicas como `=>` ou `->` deixam de
  pertencer ao resultado. A vista adicional para quebras de linha suaves
  deixa de poder estender resultados de forma jurídica e local por várias
  linhas de tabela; uma morada já completa termina antes do cabeçalho de
  campo seguinte com o respetivo valor. A execução final sobre todos os
  1.600 documentos TXT, HTML, PDF e DOCX remove 10.840/10.840 valores de
  referência, com zero falsos alarmes, zero violações de preservação e
  zero interrupções.

## 0.10.44-beta.1 – 1 de setembro de 2026

- A construção de pacotes gera saídas separadas para Windows x64 e ARM64, macOS
  em Apple Silicon e Intel, bem como Linux x64 e ARM64. Nomes de pacote,
  seleção de atualização e lançamentos distinguem a arquitetura; uma
  publicação permanece bloqueada enquanto faltar um dos seis alvos ou o seu
  comprovativo de dependências. O Linux ARM64 exige, por causa do Qt, pelo
  menos glibc 2.39. Totalmente validados em hardware real estão, por agora,
  apenas Windows x64 e macOS em Apple Silicon; os restantes pacotes de
  arquitetura devem ser claramente identificados como versões prévias para
  teste, não para uso produtivo.

- Com vários ficheiros, a deteção continua agora a trabalhar enquanto uma
  pré-visualização espera revisão. Até três pré-visualizações preparadas são
  mostradas em sequência; ao mesmo tempo, continua a calcular apenas um
  documento, e um ficheiro de resultado só surge depois da sua aprovação.
  Uma exceção permanente escolhida na pré-visualização aplica-se também a
  documentos seguintes já preparados.

- Os certificados de redação podem agora ser verificados a qualquer momento
  diretamente no menu Ficheiro, contra o documento ocultado. O Maskuro
  distingue aí um ficheiro assinado correspondente, um comprovativo
  correspondente mas não assinado, uma assinatura inválida e um documento
  que não pertence ao certificado. Não é necessária uma licença nem a conta
  original do sistema operativo para a contraverificação.
  Para pontos de verificação automáticos, está disponível a mesma
  comparação via `--zertifikat-pruefen`; códigos de retorno distinguem
  correspondência, erro de utilização e comprovativo inválido.
  A contraverificação compara adicionalmente o ID Maskuro incorporado com o
  certificado; um ID alheio inserido livremente é assim detetado mesmo num
  comprovativo não assinado.
  Com assinatura válida, o resultado da verificação mostra também o editor
  ativado pela administração, com conta do sistema operativo, ID técnico de
  conta e plataforma. Indicações não confirmadas de comprovativos não
  assinados ou inválidos não são emitidas.

- Um novo laboratório de documentos alemão gera 160 documentos TXT, HTML, PDF
  e DOCX totalmente sintéticos de dez áreas e quatro variantes estruturais. O
  manifesto distingue agora expressamente entre indicações que têm de
  desaparecer e textos técnicos ou identificações objetivas que têm de ser
  mantidas; família de documento, mutação e fonte estrutural pública ficam
  registadas de forma rastreável.

- O laboratório de documentos alemão foi alargado para 280 ficheiros, sete
  formas estruturais, 1.540 valores de referência e 1.036 âncoras de
  preservação. São agora verificados adicionalmente formulários numerados,
  campos de PDF/máscara entre parênteses e atribuições técnicas `=>`. O
  estado completo alargado atinge, em TXT, HTML, PDF e DOCX, 100 por cento
  cada um, com zero falsos alarmes. Campos de data e número de identificação
  entre parênteses, separadores de seta e associações expressamente
  legendadas são agora reconhecidos estruturalmente.

- Uma segunda expansão do laboratório eleva o conjunto para 400 documentos,
  dez formas estruturais, 2.200 valores de referência e 1.480 âncoras de
  preservação. Valores-chave do tipo JSON, listas YAML e campos de
  formulário em maiúsculas atingem, juntamente com o conjunto anterior, 100
  por cento com zero falsos alarmes. Datas de nascimento e números de
  identificação citados, bem como cargos expressamente legendados como
  pessoas seguradas, candidatas, sujeitas a entrega ou com poder de
  representação, são agora reconhecidos também nestas formas de exportação.

- Um modo de OCR separado do laboratório de documentos alemão gera
  adicionalmente 200 digitalizações de imagem pura de todas as 40 famílias.
  Páginas limpas, de baixo contraste, de baixa resolução, com artefactos
  JPEG e rodadas 90 graus são remedidas com caixas de pixel exatas, sem
  alterar a base de texto comparável de 1.600 ficheiros. O manifesto separa
  características ativáveis de data, dinheiro e medicina do perfil base e
  conhece leituras de OCR comprovadas, sem as contar como locais de
  referência adicionais. A medição é discriminada por mutação e família de
  documento. Limites de campo estreitos impedem, entre outras coisas, que
  „Az" no nome de local „Graz" oculte uma data seguinte como referência de
  processo; a matriz base atual corre com zero falsos alarmes e zero
  interrupções.

- Cinco novas famílias de documentos alemãs para fatura/guia de remessa,
  banco/crédito, arrendamento/administração predial, escola/universidade e
  logística/alfândega alargam o laboratório para 600 ficheiros com 3.520
  valores de referência e 2.360 âncoras de preservação. Uma via estreita de
  tabela em PDF usa o cabeçalho expresso `Campo Indicação` quando a camada
  de texto perde separadores de célula; uma nova seleção `--familien`
  acelera medições parciais. Os 200 novos ficheiros atingem 1.320/1.320 com
  zero falsos alarmes e zero interrupções.

- Seguro/sinistro, trabalho/salário, medicina/laboratório, veículo/oficina e
  técnica/manutenção alargam o laboratório de documentos alemão para 800
  ficheiros com 4.960 valores de referência e 3.200 âncoras de preservação.
  São reconhecidas identificações de apólice, paciente, inspetor e veículo
  estreitamente legendadas, bem como novos campos de cargo, morada e
  organização. A nova matriz parcial e a matriz completa atingem 100 por
  cento com zero falsos alarmes e zero interrupções em TXT, HTML, PDF e
  DOCX.

- Construção/concurso, energia/ambiente, associação/sociedade,
  comunicação/calendário e hotel/evento elevam o laboratório de documentos
  alemão para 1.200 ficheiros com 7.920 valores de referência e 4.800
  âncoras de preservação. Novos campos de cargo, empresa, morada, registo,
  adjudicação, reserva e conta de utilizador são reconhecidos também em
  todas as formas de exportação. Números de contador mantêm-se como
  identificações objetivas. A matriz parcial e completa atingem 100 por
  cento com zero falsos alarmes e zero interrupções.

- Gastronomia/serviço de entrega, farmácia/receita, funerária/cemitério,
  desporto/associação e imobiliário/mediação alargam o laboratório de
  documentos alemão para 1.400 ficheiros com 9.360 valores de referência e
  5.640 âncoras de preservação. São reconhecidos novos cargos de pessoa,
  campos de morada e números de pedido de pesquisa. Nomes de empresa
  legendados com forma jurídica permanecem totalmente protegidos mesmo com
  uma quebra de linha automática; classes etárias e cabeçalhos técnicos
  deixam de ser substituídos por engano. A matriz parcial e completa
  atingem 100 por cento com zero falsos alarmes e zero interrupções.

- Tratamento dentário, escola de condução, bombeiros/intervenção,
  comunidade de energia e viagem organizada alargam o laboratório de
  documentos alemão para 1.600 ficheiros com 10.840 valores de referência e
  6.440 âncoras de preservação. São reconhecidos estruturalmente novos
  cargos, campos de morada, bem como identificações de tratamento,
  formação, intervenção, energia e contrato de viagem. A nova matriz
  parcial de 200 ficheiros atinge 1.480/1.480; a matriz completa atinge
  10.840/10.840. Ambas permanecem com zero falsos alarmes e zero
  interrupções.

- A medição completa do laboratório de documentos reduziu, através de
  formas oficiais objetivas e regras estruturais estreitas, as
  substituições desnecessárias de 68 para 0, as violações de preservação
  expressamente medidas de 23 para 0 e as interrupções de 3 para 0. A taxa
  de deteção subiu, ao mesmo tempo, de 91,1 para 100,0 por cento; TXT,
  HTML, PDF e DOCX atingem cada um 100 por cento. Cabeçalhos de tabela
  gerais como `Campo` só são travados na sequência comprovada
  `Campo`/`Indicação`; um apelido com o mesmo nome permanece protegido.
  Referências de processo judiciais com letra final, campos de sinal de
  igualdade, `Data de nascimento da criança` e vários nomes individuais
  legendados na mesma linha são totalmente reconhecidos. Tabelas Word e
  campos de linha anterior usam o seu cabeçalho de campo como contexto de
  deteção temporário; moradas de PDF legendadas permanecem totalmente
  protegidas mesmo com uma quebra de linha causada pela composição.

- Os campos alemães de características pessoais, profissão e medicina
  funcionam agora também com quebras de linha do Windows. Indicações de
  sexo de uma letra como `Sexo`/`f` são protegidas na forma de linha
  anterior. Campos objetivos `Artigo-PZN`, pelo contrário, não desencadeiam
  nem um resultado de código de medicamento nem de pessoa; indicações
  reais de PZN, ICD e ATC continuam reconhecidas.

- Os campos de formulário e número alemães são mais precisos: „DW." funciona
  agora também antes de uma quebra de linha suave, nomes expressamente
  legendados são removidos mesmo em minúsculas, e referências de processo
  puramente numéricas são atribuídas ao seu tipo correto de número de
  identificação. Inversamente, um número de fatura, comprovativo ou artigo
  que seja por acaso válido segundo Luhn deixa de valer como cartão de
  crédito. Provas sintéticas de saída em HTML e PDF confirmam remoção e
  preservação no documento final.
  Números de identificação e nomes de utilizador são também reconhecidos
  quando a sua legenda está na linha de tabela ou formulário imediatamente
  anterior; números de comprovativo objetivos permanecem visíveis também
  nesta forma.

- As palavras-passe são agora também reconhecidas atrás de um cabeçalho de
  campo isolado na linha anterior. Carateres especiais finais como `!` ou
  `#` pertencem, nesse caso, integralmente ao valor protegido. PINs de
  produto e artigo deixam, inversamente, de ser mascarados como PIN de
  cartão; campos expressos `PIN` e `PIN do cartão` permanecem protegidos.

- Valores de formulário em minúsculas são agora emitidos, em campos alemães
  inequívocos de morada e `Código postal/Localidade`, como morada ou como
  código postal com localidade, em vez de apenas como local genérico.
  Também valores de empresa em minúsculas como „beispiel service" atrás de
  um campo de empresa permanecem totalmente protegidos, sem cortar a
  palavra final como suposto próximo cabeçalho de campo.

- A ajuda, as perguntas frequentes, o texto de proteção de dados e o site
  explicam agora em conjunto o comprovativo de origem: ID Maskuro neutro no
  documento, atribuição opcional à conta real do sistema operativo apenas
  no registo de verificação local, mudança de utilizador via
  Windows/macOS/Linux, bem como o poder informativo do SHA-256 e da
  assinatura.

- Cadernos de encargos técnicos baseados em imagem são limpos de forma mais
  contida. Palavras técnicas inequívocas como „Abbruchhämmern",
  „Deckungsrücklass", „Positionsnummern", „Einbauplatine" ou
  „Terminsituation", bem como formas de OCR divididas a meio da palavra,
  deixam de valer como pessoa ou local. Uma proposta real de uma câmara
  municipal desceu assim de 140 para 90 substituições inequívocas, sem
  gerar novos resultados; nomes como Schneider, Lang, Bauer e Hahn
  permanecem expressamente protegidos.

- Mais falsos alarmes de propostas reais foram corrigidos: „Digital
  signiert" deixa de conter uma suposta pessoa, um BIC é reconhecido também
  sem dois pontos atrás da sua legenda, `15000 Alternativ` deixa de valer
  como código postal com localidade, e a citação da UE „(VO (EG)
  715/2007" deixa de gerar uma organização. Uma proposta fotovoltaica
  desceu assim de 26 para 16 ocorrências de substituição; nomes, locais e
  dados bancários reais mantiveram-se.

- Em organogramas de colaboradores, a abreviatura de suplente „Stv." e um
  título de secção „FACILITY" isolado deixam de ser substituídos como nome
  de pessoa. A contraverificação real de 13 páginas desceu de 878 para 875
  substituições; nomes, extensões e a designação da empresa permaneceram
  protegidos.

- Os ficheiros PDF, OpenDocument e Office limpos recebem uma identificação
  neutra `MASKURO-…` nas suas propriedades de documento. O relatório de
  verificação e o registo de verificação assinado registam a mesma
  identificação, bem como valores SHA-256 da origem e do resultado; o
  certificado de redação assume a identificação a partir do ficheiro
  concluído. Um nome de utilizador só é adicionado quando a administração
  ativa expressamente o campo de utilizador existente.

- A janela principal e as definições estão organizadas de forma mais calma:
  Guardar, Copiar, Detalhes, Indicadores e a eliminação de um perfil de
  deteção só aparecem quando a respetiva ação é possível. Siglas técnicas
  de idioma de OCR e exemplos longos ficam, quando necessário, no texto de
  ajuda em vez de permanentemente na área de trabalho. A página de deteção
  adapta-se melhor a janelas mais estreitas, sem explicações cortadas nem
  barra de deslocamento horizontal; o aviso sobre texto simples na lista de
  substituições permanece visível.

- A deteção abrange mais casos de contacto alemães e internacionais: os
  números de telefone são agora verificados para todas as regiões de país
  selecionáveis, os cargos contratuais húngaros e croatas abrangem também
  na íntegra apelidos homónimos de profissões, e listas numeradas de peças
  sobressalentes/materiais deixam de desencadear um falso alarme de pessoa
  por causa de „Mutter / Flach". Campos de pessoa com um valor objetivo
  claramente numérico deixam de ser assumidos como nome; a zona legível por
  máquina do passaporte (MRZ) pode também ser ligada e desligada em
  conjunto através do grupo „Identificações".

- As empresas sem forma jurídica são melhor distinguidas de pessoas atrás
  de campos de empregador ambíguos: nomes como „Huber Handel", „Müller
  Logistik" ou „Kowalski Handel" são reconhecidos por completo como
  empresa, enquanto „Arbeitgeber: Bauer Anna" continua a ser um nome de
  pessoa. A seleção automática de país continua a considerar, em
  documentos franceses, todo o espaço linguístico francês, incluindo o
  Luxemburgo.

- Assinaturas reconhecidas e texto pessoal dentro de uma imagem eram, até
  agora, sempre cobertos com um retângulo preto – mesmo quando estava
  definida uma cor diferente ou um padrão como „Arco-íris" para
  ocultações. Estas áreas de imagem assumem agora também a apresentação de
  ocultação escolhida; a área opaca continua a ser escrita diretamente nos
  pixels.

- A deteção em inglês foi remedida em onze documentos reais traduzidos
  manualmente e melhorada de forma direcionada: estado de inventário,
  campos técnicos de proposta e loja online, bem como cargos em diretórios
  de colaboradores, permanecem visíveis; „CV" deixa de ser lido, na frase
  padrão, como forma jurídica; tipos de letra citados mantêm-se; e nomes em
  cabeçalhos verticais de currículo, listas de colaboradores de várias
  páginas, atrás de „Account manager", bem como nomes de empresa que
  começam por dígito, são totalmente reconhecidos. Números de registo
  comercial austríacos funcionam agora também atrás de uma legenda em
  inglês; a forma curta „Customer:", números de registo EAR e números de
  entidade patronal trazem o seu valor. Cadeias de medidas, tipos de cabo,
  referências jurídicas da UE, datas de validade de proposta, locais de
  cumprimento, foros competentes, tribunais de registo, a sigla fiscal
  „NoVA", números técnicos em etiquetas de pneus, bem como referências
  normativas como „OVE R6-2" e „AStV", deixam de gerar falso alarme. Um
  IBAN legendado válido termina de forma limpa antes do campo de registo ou
  do título da linha seguinte; moradas com acrescento de zona comercial são
  totalmente reconhecidas também a partir de fluxos de texto de PDF com
  quebras de linha do Windows. Introduções de empresa em inglês e nomes
  estruturados de caixas económicas são totalmente delimitados. O país do
  documento de origem mantém-se nas versões de idioma para códigos postais
  e identificações específicas de país.

- Em linhas de cabeçalho de destinatário e mensagem, o modelo de linguagem
  podia unir os dois primeiros nomes de uma lista separada por vírgulas
  num único resultado („Bcc: Huber, Mayer"). Ambos os nomes são agora
  reconhecidos, substituídos e registados individualmente no relatório –
  também atrás de „Sent:", „Reply:" e „Fwd:".

- A zona legível por máquina de um passaporte ou cartão de identidade (MRZ)
  faltava no controlo de grupo „O que é procurado". Pertence agora a
  „Identificações" e pode ser ligada e desligada em conjunto com este
  grupo.

- Quem escolher o modelo „Arco-íris" para textos substitutos recebe agora
  também locais ocultados na mesma aparência; até agora, permaneciam
  surpreendentemente pretos clássicos. As áreas de ocultação continuam a
  poder ser mudadas de forma independente para outro modelo depois disso.

- O painel de páginas do editor de correção podia ficar vazio depois de
  restaurar uma divisão de janela guardada, até a sua largura ser alterada
  manualmente. As miniaturas são agora reordenadas depois da construção
  visível da janela e ficam imediatamente centradas no painel.

- As marcas coloridas de verificação à volta de textos substitutos em PDFs
  permaneciam pouco visíveis consoante a cor de categoria e de semáforo.
  Um contorno claro por baixo separa agora, de forma fiável, a moldura de
  verificação do marcador colorido e do fundo da página.

- Quem, no editor de correção, ocultasse uma linha cujo documento está
  composto com espaçamento de linha estreito (típico de propostas e
  cadernos de encargos), obtinha uma barra que ultrapassava para as
  ascendentes da linha por baixo – esta ficava depois só meio legível. A
  barra termina agora na letra realmente desenhada da linha vizinha; a
  própria linha ocultada permanece, com isso, totalmente coberta, incluindo
  as suas descendentes.

- O documento de exercício („Ajuda → Abrir documento de exercício", também
  no tour guiado) demonstra agora todos os tipos de deteção: à carta
  inventada juntam-se uma fotografia com rosto reconhecível, uma assinatura
  manuscrita, profissão e departamento, diagnóstico e medicamento – ao lado
  de nome de empresa, montante e data, que já lá estavam. O que o padrão
  deliberadamente deixa fica explicado na própria folha, com o interruptor
  que o remove; o rosto na fotografia é pixelizado de fábrica.

- Montantes monetários na grafia alemã habitual, com o símbolo depois do
  número („1.240,00 €"), nunca eram encontrados pelo interruptor „Remover
  também montantes monetários" – „1.240,00 EUR" e „€ 1.240,00" sempre
  foram. Agora as três grafias são reconhecidas.

- A pesquisa de assinaturas funciona agora também em ficheiros de imagem
  isolados: quem limpar uma digitalização como JPG ou PNG recebe
  assinaturas manuscritas ocultadas nela – a mesma deteção, a mesma
  mensagem no relatório que num PDF. Imagens incorporadas em ficheiros do
  Office continuam a não ser pesquisadas, porque a deteção ali trabalha,
  medidamente, de forma pouco fiável; a marcação chama-se por isso agora
  „PDF e ficheiros de imagem: Ocultar assinaturas manuscritas".

- Uma barra de ocultação podia, com espaçamento de linha estreito,
  ultrapassar visivelmente para as ascendentes da linha por baixo e
  torná-la parcialmente ilegível – a altura da barra vinha das métricas do
  tipo de letra, não do que realmente está no papel. A barra termina agora
  na tinta efetivamente desenhada da linha vizinha, tanto no editor de
  correção como na limpeza automática. A própria linha, incluindo
  descendentes, permanece sempre totalmente coberta; se as linhas se
  sobrepuserem mesmo, a barra prefere manter-se sobre a linha vizinha, em
  vez de libertar algo.

- Num diretório de colaboradores com cargo sob o nome, uma designação de
  chefia feminina („Anna Berger" com „Montageleiterin" por baixo) era
  arrastada para a substituição do nome – a forma masculina ao lado
  permanecia corretamente. As formas femininas „…leiterin" (de montagem,
  equipa, projeto, obra, departamento, operação, grupo, repartição) são
  agora tratadas, como os seus equivalentes masculinos, como designação de
  função; chefia de filial, pessoal e vendas passam a constar em ambas as
  formas.

- A deteção ativável de profissão não encontrava cargos de chefia
  femininos como „Projektleiterin", „Teamleiterin" ou
  „Abteilungsleiterin", mas já encontrava as suas formas masculinas. Ambas
  as formas contam agora igualmente.

- Na janela de pré-visualização, no Mac, a indicação de múltiplas ficava
  colada diretamente ao termo („Anna Musterfrau2ק em vez de „Anna
  Musterfrau 2ק). O espaço voltou a aparecer.

- A lupa de comparação tem um novo botão ao lado do cursor de zoom: coloca-a,
  com um toque, em largura total sobre o resultado – com meia altura, e o
  original na mesma escala do documento (o zoom da lupa salta para 100%
  nesse caso). Um segundo toque volta a ancorá-la, pequena, na coluna
  esquerda e restaura o zoom anterior da lupa. O círculo ao lado só repõe
  agora o zoom – o seu texto de dica afirmava até agora, erradamente, que
  também voltava a ancorar a janela.

- Na barra de ferramentas do editor de correção, volta a ser visível que a
  ferramenta escolhida está selecionada: o botão da ferramenta ativa traz
  uma área preenchida com contorno azul – tal como qualquer outro botão de
  alternância ativado da barra (por exemplo, lupa de comparação ou modo de
  aprendizagem). A marcação tinha-se perdido com o desenho próprio dos
  botões de 29 de agosto.

- Números de posição de um caderno de encargos („2.3.3.3, 2.3.3.4, 2.3.3.5"
  uns sob os outros) eram tomados por endereços IP e removidos do
  resultado; números de três níveis com um último elemento semelhante a um
  ano („2.3.19, 2.3.20") caíam como datas de calendário. Uma sequência
  numérica ascendente no início da linha vale agora como o que é – uma
  lista de posições; moradas reais (tabelas de rede com contexto técnico
  de palavras, números acima de 99) e datas reais continuam reconhecidas.

- Apelidos como „Müller", „Fischer", „Bauer", „Koch", „Wagner",
  „Schneider", „Weber", „Jäger", „Schmied", „Becker", „Schuster",
  „Schäfer" ou „Meister" permaneciam em texto simples em listas da forma
  „Apelido, Nome" (por exemplo, „Teilnehmer: Müller, Peter; Nowak, Anna"),
  porque são simultaneamente designações profissionais comuns. São agora
  reconhecidos de forma fiável.

- Ao ocultar um PDF, a barra podia levar consigo toda a célula em células
  de tabela estreitas: do resultado „D-LINK" num caderno de encargos
  resultava a remoção de toda a descrição de produto ao lado, apesar de a
  pré-visualização ter indicado apenas o resultado. A barra continua a
  cobrir linhas inteiras de bloco de morada e legendas de campo, mas
  engole, no máximo, tanto conteúdo não relacionado quanto cobre de
  conteúdo a proteger – a descrição ao lado do resultado permanece agora.

- Depois de „Repor vista" no editor de correção, o painel de páginas
  ficava vazio – as miniaturas das páginas só voltavam a ser visíveis
  depois de fechar e reabrir a janela. Agora ficam visíveis logo depois de
  repor, centradas como antes.

- O editor de correção tem uma quarta ferramenta: **Remover** retira o
  texto sob a moldura sem substituto – sem barra (ocultar) e sem marcador
  (substituir); o vazio permanece visível. Funciona exato à palavra; se
  houver uma imagem por baixo, o seu fundo é limpo a branco, e „Recuperar
  original" também anula uma remoção sem substituto. Símbolo próprio na
  barra e distintivo de mira (cruz), tecla mnemónica própria em todos os
  18 idiomas (alemão F de entFernen).

- Na barra de pesquisa de PDF, „Pasta…" fica agora à direita das opções de
  pesquisa. Desde que existe, além de ocultar, também a substituição de
  resultados, cinco botões deixaram de caber lado a lado na largura normal
  de janela – o primeiro ficava comprimido e o seu texto cortado.

- „Repor todas as definições" repõe agora também a marcação „Substituir
  vermelho/verde por outras cores" e assinala-a, como qualquer outra, com
  „alterado" quando divergir do estado de fábrica.

- Os textos substitutos em PDFs atuam agora de forma mais uniforme: onde o
  marcador completo ficaria claramente mais pequeno do que a sua linha (por
  exemplo, „[BEG16]" espremido numa palavra curta como „Das"), consta em
  vez disso uma forma curta no tamanho da linha („[B16]") – bem legível em
  vez de minúscula, e o número para recuperação traz ambas as grafias. Um
  marcador só fica minúsculo quando nem sequer a forma mais curta encontra
  espaço – isso continua a ser melhor do que uma barra sem qualquer
  informação.

- Um texto substituto composto por várias cores (gradiente ou arco-íris)
  num PDF só se mantinha intacto até à próxima intervenção: qualquer nova
  substituição ou ocultação na mesma página podia comprimir marcadores já
  definidos numa pilha de letras ilegível e espremida – quem substituísse
  palavra a palavra no editor via, em vez de „[BEG17]", apenas carateres
  impressos uns sobre os outros. Os marcadores já definidos permanecem
  agora como foram definidos.

- O interruptor para exceções permanentes na pré-visualização chama-se
  agora „Nunca remover" – como a lista em que regista; até agora constava
  „nunca mais". A linha de resultado ao lado está mais arrumada: o símbolo
  de informação „ⓘ" é maior e mais fácil de atingir, e a caixa, a marca de
  substituir e o botão têm uma altura comum. A frase à volta de um
  resultado usa agora efetivamente a largura anunciada – a indicação de
  largura anterior era, até agora, silenciosamente ignorada pela
  apresentação, e o excerto quebrava como uma faixa estreita.

- No editor, o cursor do rato diz agora qual a ferramenta ativa: uma mira
  para apontar, ao lado um pequeno sinal – barra para ocultar, setas de
  troca para substituir, seta de retrocesso para recuperar, grelha de
  pixels para pixelizar. Os antigos símbolos de mão deixaram de existir;
  uma mão significa, em qualquer outro local, „agarrar e arrastar". Tem
  agora uma tarefa adequada: sobre uma palavra ou barra realçada a
  vermelho, o cursor torna-se uma mão a apontar – aí basta um clique.

- „Deteção máxima (IA)" deixa de oferecer um modelo de linguagem local
  descarregável – o nível calcula agora exclusivamente através de uma IA
  própria configurada em „Ligar IA própria". Quem já tivesse ligado um
  servidor próprio não nota qualquer diferença.

- O tour guiado da pré-visualização explica agora também o símbolo de
  informação „ⓘ", que mostra a frase à volta de um resultado. E essa
  própria frase está mais legível: um tamanho de letra maior, mais
  espaçamento entre linhas, largura fixa em vez de uma quebra estreita e
  apertada.
- Também „Verificar ficheiro", „Regras de deteção e termos próprios",
  „Limpar texto" e „Limpar imagem" têm agora um tour guiado próprio –
  através de um novo botão „Tour guiado pela janela", já que estas quatro
  janelas não têm barra de menu própria.
- Nomes sob nove legendas ucranianas de cargo contratual permaneciam
  incompletamente reconhecidos quando ocorria um apelido homógrafo, se a
  legenda estivesse sozinha na sua linha: „Покупець"/„Продавець"
  (comprador/vendedor), „Поручитель"/„Боржник" (fiador/devedor
  principal), „Свідок" (testemunha), „Орендодавець"/„Орендар"
  (senhorio/inquilino) e „Спадкодавець"/„Спадкоємець" (autor da herança/
  herdeiro). Os nomes são agora totalmente reconhecidos.

- O comentário de um intervalo nomeado numa pasta de trabalho Excel (Gestor
  de Nomes, campo „Comentário") transportava, inalterado, um nome
  registado nele. É agora limpo tal como o resto do conteúdo da pasta de
  trabalho.

- Nomes sob sete legendas húngaras de cargo contratual permaneciam
  totalmente por detetar quando ocorria um apelido homógrafo:
  „Bérbeadó"/„Bérlő" (senhorio/inquilino), „Vevő"/„Eladó"
  (comprador/vendedor), „Kezes"/„Főadós" (fiador/devedor principal) e
  „Tanú" (testemunha). Os nomes são agora totalmente reconhecidos.

- Nomes sob a legenda checa de comprador „Kupující" permaneciam totalmente
  por detetar com um apelido homógrafo. O nome é agora totalmente
  reconhecido.

- Nomes sob a legenda russa de tutor „Опекун" permaneciam totalmente por
  detetar com um apelido homógrafo. O nome é agora totalmente reconhecido.

- Nomes sob seis outras legendas croatas permaneciam por detetar: „Jamac"
  (fiador), „Glavni dužnik"/„Dužnik" (devedor principal/devedor),
  „Ostavitelj" (autor da herança), „Nasljednik" (herdeiro) e „Vjerovnik"
  (credor). Os nomes são agora totalmente reconhecidos.

- Uma página HTML guardada com uma subpágina incorporada no atributo `src`
  de um `<embed>` (em vez de `data` num `<object>`) transportava indicações
  pessoais nela inalteradas. São agora limpas tal como em `<object>`.

- Nomes sob cinco legendas dinamarquesas de cargo contratual permaneciam
  incompletamente reconhecidos com um apelido homógrafo, quando a legenda
  estava com dois pontos antes do nome: „Arvelader"/„Arving" (autor da
  herança/herdeiro), „Befuldmægtiget"/„Fuldmagtsgiver" (procurador/
  outorgante) e „Værge" (tutor). Os nomes são agora totalmente
  reconhecidos; as legendas norueguesas correspondentes foram também
  acrescentadas por precaução.

- Os marcadores em ficheiros Word e PowerPoint têm agora a mesma cor que na
  aparência escolhida (uma cor, gradiente, arco-íris ou por categoria) –
  até agora permaneciam ali na cor de texto comum, mesmo quando os
  resultados de PDF já saíam coloridos há muito.

- „Copiar como texto" e „Copiar como Markdown" colocam o texto simples do
  resultado diretamente na área de transferência – para colar num chat,
  e-mail ou outro programa, sem abrir primeiro o ficheiro.

- Nomes sob cinco outras legendas eslovenas permaneciam por detetar:
  „Toženec" (réu), „Tožnik" (autor), „Zastavitelj" (dador do penhor),
  „Zastavni upnik" (credor pignoratício) e „Darovalec" (doador). Os nomes
  são agora totalmente reconhecidos.

- O nome do autor de uma alteração controlada de célula de tabela
  (célula inserida, apagada ou fundida no Word) permanecia no ficheiro,
  mesmo quando o mesmo nome, como autor de comentário, já tinha sido
  removido há muito. É agora também removido.

- Nomes sob nove outras legendas eslovenas permaneciam por detetar:
  „Najemodajalec"/„Najemnik" (senhorio/inquilino), „Zapustnik"/„Dedič"
  (autor da herança/herdeiro), „Upnik"/„Dolžnik" (credor/devedor),
  „Glavni dolžnik" (devedor principal) e „Skrbnik" (tutor/curador). Os
  nomes são agora totalmente reconhecidos.

- Nomes sob cinco legendas eslovenas permaneciam por detetar: „Izvedenec"
  (perito), „Kupec" (comprador), „Prodajalec" (vendedor), „Naročnik"
  (cliente) e „Izvajalec" (contratado). Os nomes são agora totalmente
  reconhecidos.

- Nomes sob cinco outras legendas lituanas permaneciam por detetar:
  „Užsakovas" (cliente), „Vykdytojas" (contratado), „Vežėjas"
  (transportador), „Siuntėjas" (remetente) e „Arbitras" (árbitro). Os
  nomes são agora totalmente reconhecidos.

- Nomes sob seis outras legendas lituanas permaneciam por detetar:
  „Įgaliotinis" (procurador), „Įgaliotojas" (outorgante), „Naudos gavėjas"
  (beneficiário, seguro), „Trečiasis asmuo" (interveniente/terceira parte
  em processo civil), „Ankstesnis nuomininkas" (inquilino anterior) e
  „Naujasis nuomininkas" (novo inquilino). Os nomes são agora totalmente
  reconhecidos.

- Um marcador em documentos ODT (`text:bookmark`) tem o seu nome atribuído
  livremente, muitas vezes conforme o local para o qual aponta (por
  exemplo, „Herr_Mueller_Unterschrift") – invisível para o leitor, mas
  literal no ficheiro. O nome é agora também limpo.

- Nomes sob oito outras legendas lituanas permaneciam por detetar:
  „Pareiškėjas" (requerente), „Suinteresuotas asmuo" (requerido em
  processo não contencioso), „Ekspertas" (perito), „Bankroto
  administratorius" (administrador de insolvência), „Valdybos narys"
  (membro do conselho fiscal), „Direktorius" (gerente), „Palikėjas"
  (autor da herança) e „Įpėdinis" (herdeiro). Os nomes são agora
  totalmente reconhecidos.

- Nomes sob sete outras legendas lituanas permaneciam por detetar:
  „Liudytojas" (testemunha), „Vertėjas" (intérprete/tradutor), „Notaras"
  (notário), „Dovanotojas" (doador), „Apdovanotasis" (donatário),
  „Pirkėjas" (comprador) e „Pardavėjas" (vendedor). Os nomes são agora
  totalmente reconhecidos.

- Nomes sob seis outras legendas lituanas permaneciam por detetar:
  „Globėjas" (tutor/curador), „Palikimo administratorius" (administrador
  da herança), „Laiduotojas" (fiador), „Pagrindinis skolininkas" (devedor
  principal), „Nuomotojas" (senhorio) e „Nuomininkas" (inquilino). Os
  nomes são agora totalmente reconhecidos.

- Um nome sob a legenda lituana „Ieškovas"/„Atsakovas" (autor/réu como
  parte processual) permanecia por detetar, independentemente de o
  apelido ser simultaneamente uma palavra comum (por exemplo, „Vilkas" =
  lobo) ou não. O nome é agora totalmente reconhecido.

- Uma entrada de índice de pessoas em documentos ODT (marcador para o
  índice remissivo) trazia o nome uma segunda vez na sua própria chave de
  ordenação – invisível no texto corrido, mas literal no índice gerado
  posteriormente. A chave é agora também limpa.

- O nome do diapositivo e o nome da secção de uma apresentação PowerPoint
  (visíveis na área de seleção ou na ordenação de diapositivos) não eram
  limpos, porque ambos são um atributo de um elemento que não é texto de
  diapositivo. Ambos são agora reconhecidos.

- Um nome duplo lituano com hífen como „Petraitis-Kazlauskas" perdia a sua
  segunda metade assim que qualquer texto corrido o precedesse (só no
  início do texto permanecia completo): o apelido é agora totalmente
  reconhecido também nesse caso.

- Um nome sob a legenda „Cesionar" (croata, cessionário na cessão de
  crédito) gerava um falso alarme, porque a própria legenda de campo era
  lida por engano como pessoa. Um nome sob a legenda russa „Цессионарий"
  (também cessionário), pelo contrário, permanecia totalmente por
  detetar. Ambos os casos estão agora corrigidos.

- Um nome sob a legenda „Zedent"/„Zessionar" (alemão, cessão de crédito)
  permanecia totalmente por detetar quando o apelido era simultaneamente
  uma palavra comum (por exemplo, „Bauer"). O nome é agora totalmente
  reconhecido.

- Um nome sob a legenda „Darczyńca"/„Obdarowany" (polaco, doador/donatário
  no contrato de doação) permanecia por detetar quando o apelido era
  simultaneamente uma palavra comum (por exemplo, „Wilk" = lobo). Da
  mesma forma, a legenda romena „Donatar" (donatário) ficava presa, com
  um apelido comum, mesmo como suposta parte do nome. Ambos os casos
  estão agora corrigidos.

- Um nome sob a legenda „Wierzyciel"/„Dłużnik" (polaco, credor/devedor de
  execução, ou credor/devedor em geral) permanecia por detetar quando o
  apelido era simultaneamente uma palavra comum (por exemplo, „Wilk" =
  lobo). O nome é agora totalmente reconhecido.

- Um nome sob a legenda „Poręczyciel"/„Dłużnik główny" (polaco,
  fiador/devedor principal em contratos de fiança) permanecia por detetar
  quando o apelido era simultaneamente uma palavra comum (por exemplo,
  „Wilk" = lobo). O nome é agora totalmente reconhecido.

- Um nome sob a legenda „Ubezpieczony"/„Ubezpieczający" (polaco, segurado/
  tomador do seguro em apólices) permanecia parcial ou totalmente por
  detetar quando o apelido era simultaneamente uma palavra comum (por
  exemplo, „Wilk" = lobo). Da mesma forma, um nome sob „Osiguranik"/
  „Osiguravatelj" (croata, os mesmos cargos), onde desaparecia por
  completo, incluindo o primeiro nome (por exemplo, „Golub" = pomba).
  Ambos os nomes são agora totalmente reconhecidos.

- Um nome sob a legenda „Pełnomocnik"/„Mocodawca" (polaco, procurador/
  outorgante em procurações) permanecia por detetar quando o apelido era
  simultaneamente uma palavra comum (por exemplo, „Wilk" = lobo). Da
  mesma forma, um nome sob „Opunomoćenik"/„Opunomoćitelj" (croata, os
  mesmos cargos), onde desaparecia mesmo por completo, incluindo o
  primeiro nome. Ambos os nomes são agora totalmente reconhecidos.

- Um nome sob a legenda „Pozwany" (polaco, réu como parte processual)
  permanecia por detetar quando o apelido era simultaneamente uma palavra
  comum (por exemplo, „Wilk" = lobo). O nome é agora totalmente
  reconhecido.

- Um nome sob a legenda „Najmoprimac"/„Najmodavac" (croata,
  inquilino/senhorio em contratos de arrendamento) permanecia por detetar
  quando o apelido era simultaneamente uma palavra comum (por exemplo,
  „Kovač" = ferreiro). O nome é agora totalmente reconhecido.

- Um nome sob a legenda „Pracodawca"/„Pracownik" (polaco, empregador/
  trabalhador como parte contratante em contratos de trabalho) permanecia
  parcialmente por detetar quando o apelido era simultaneamente uma
  palavra comum (por exemplo, „Krawiec" = alfaiate). O nome é agora
  totalmente reconhecido.

- A Hungria tinha, no catálogo de países, apenas as identificações de
  pessoa e o NIF: o número de registo comercial (Cégjegyzékszám) é agora
  reconhecido, desde que a palavra de campo „Cégjegyzékszám" ou a
  abreviatura „Cg." esteja imediatamente antes – o próprio número não tem
  dígito de controlo.

- A Estónia tinha, no catálogo de países, apenas o Isikukood: o
  Käibemaksukohustuslase number (NIF em qualquer fatura estónia) é agora
  reconhecido com dígito de controlo.

- A Letónia tinha, no catálogo de países, apenas o código pessoal: o PVN
  reģistrācijas numurs de pessoas coletivas (identificação de empresa em
  qualquer fatura letã) é agora reconhecido com dígito de controlo.

- Um e-mail com conteúdo encriptado (envelope S/MIME ou PGP/MIME,
  `multipart/encrypted`) era apresentado, sem qualquer aviso, como
  aparentemente totalmente verificado, apesar de o seu conteúdo real
  estar encriptado e, por isso, não verificado. Tais e-mails indicam-no
  agora como um anexo não verificado.

- Faltava Malta no catálogo de países: o NIF maltês (VAT number) é agora
  reconhecido.

- Faltava o Luxemburgo no catálogo de países: o NIF luxemburguês (n° TVA)
  é agora reconhecido.

- Um „Изчакайте" búlgaro („Espere!") no início de frase era comunicado
  como indicação de local – o mesmo limite de modelo que antes em formas
  de imperativo húngaras, polacas, checas e outras sem modelo de idioma
  próprio. O falso alarme deixa agora de ocorrer.

- Um nome sob a legenda „Zleceniodawca", „Zleceniobiorca" (polaco),
  „Prestator" (romeno), „Naručitelj" ou „Izvođač" (croata) permanecia
  parcial ou totalmente por detetar quando o apelido era simultaneamente
  uma palavra comum (por exemplo, „Wilk", „Vuk" = lobo, „Vulpe" = raposa,
  „Sokol" = falcão). O nome é agora totalmente reconhecido.

- Um nome sob a legenda „Nadawca" (polaco), „Afsender" (dinamarquês) ou
  „Pošiljatelj" (esloveno) permanecia parcial ou totalmente por detetar
  quando o apelido era simultaneamente uma palavra comum (por exemplo,
  „Sowa" = coruja, „Bager" = padeiro, „Volk" = lobo). O nome é agora
  totalmente reconhecido.

- Um nome sob a legenda „Gavėjas" (lituano) ou „Prejemnik" (esloveno)
  permanecia parcial ou totalmente por detetar quando o apelido era
  simultaneamente uma palavra comum (por exemplo, „Vilkas" = lobo). Como
  já em „Primatelj" (croata) e „Modtager" (dinamarquês), o nome é agora
  totalmente reconhecido.

- Um cabeçalho de circular como „To All Staff" ou „To All Employees" era
  reconhecido e removido por engano como nome de pessoa. Isso deixa agora
  de acontecer.

- Um nome sob a legenda „Primatelj" (croata) ou „Modtager" (dinamarquês)
  permanecia parcialmente por detetar quando o apelido era simultaneamente
  uma palavra comum (por exemplo, „Golub" = pomba, „Bager" = padeiro).
  Como já em „Odbiorca" (polaco) e „Destinatar" (romeno), o nome é agora
  totalmente reconhecido.

- Um nome completo na linha de assinatura de um documento dinamarquês,
  norueguês ou grego permanecia parcialmente por detetar quando a legenda
  „Underskrift" ou „Υπογραφή" estava sozinha acima do nome – no caso
  grego, o apelido era mesmo reconhecido como indicação de local em vez
  de nome. Como já em „Подпись" (russo), o nome é agora totalmente
  reconhecido.

- Texto numa fotografia de telemóvel guardada de lado (a gravação vertical
  habitual, só mostrada em pé através de uma marca de rotação de imagem)
  podia ser ignorado pelo reconhecimento de texto, porque este lia, até
  agora, os pixels brutos deitados. Tais fotografias são agora rodadas
  corretamente antes da leitura – tal como já antes no reconhecimento
  facial.

- Um nome completo na linha de assinatura de um documento russo, ucraniano
  ou lituano permanecia parcialmente por detetar quando a legenda
  „Подпись", „Підпис" ou „Parašas" estava sozinha acima do nome – o
  primeiro nome ou nome patronímico desaparecia. Como já em „Potpis"
  (croata), o nome é agora totalmente reconhecido.

- Um rosto numa fotografia de telemóvel guardada de lado (a gravação
  vertical habitual, só mostrada em pé através de uma marca de rotação de
  imagem) podia ser ignorado pelo reconhecimento facial, porque este
  verificava, até agora, os pixels brutos deitados. Tais fotografias são
  agora rodadas corretamente antes da pesquisa.

- Um nome completo na linha de assinatura de um documento croata
  permanecia parcialmente por detetar quando a legenda „Potpis" estava
  sozinha acima do nome ou com dois pontos antes – o primeiro nome
  desaparecia, quer numa linha própria quer em „Potpis: Primeiro nome
  Segundo nome Apelido". Como já em „Unterschrift" e „Signature", o nome
  é agora totalmente reconhecido.

- Um nome de casada atrás das abreviaturas de estado civil „verh."
  (casada/casado) e „verw." (viúva/viúvo) permanecia até agora totalmente
  por detetar, quer entre parênteses, atrás de vírgula ou colado sem
  espaço („Anna Meier (verh. Weber)", „Klaus Bauer (verw.Fischer)") –
  como já em „geb.", é agora reconhecido de forma fiável.

- Um nome atrás da assinatura de procuração „ppa." (por exemplo, na linha
  de assinatura de um e-mail ou carta comercial) permanecia até agora
  parcial ou totalmente por detetar com um apelido homónimo de profissão
  como „Bauer" ou „Koch" – como já em „gez.", é agora reconhecido de
  forma fiável.

- O número do bilhete de identidade polaco (dowód osobisty) só era
  reconhecido sem espaço entre a série e o número („ABS123456"). Mas o
  documento não imprime a indicação exatamente assim – oficialmente
  consta ali um espaço entre eles („ABS 123456"), e nesta grafia o número
  permanecia até agora por detetar.

- Um PNG animado (APNG, por exemplo, uma gravação de ecrã curta guardada
  como PNG em vez de GIF) era, até agora, verificado e limpo apenas com a
  sua primeira imagem, sem que isso fosse comunicado – como antes no WebP
  animado, o Maskuro comunica agora que cada imagem seguinte permanece
  não verificada no resultado.

- Uma imagem WebP animada (por exemplo, de uma ferramenta de captura de
  ecrã ou de uma aplicação de chat com várias imagens num ficheiro) era,
  até agora, verificada e limpa apenas com a sua primeira imagem, sem que
  isso fosse comunicado – como antes num TIFF de várias páginas, o
  Maskuro comunica agora que cada imagem seguinte permanece não
  verificada no resultado.

- Um primeiro nome duplo esloveno com hífen („Ana-Marija Novak") perdia a
  sua metade anterior assim que o precedia texto corrido – o mesmo erro
  de antes em polaco. „Ana-" permanecia sem cobertura em texto simples,
  enquanto o resto do nome já estava substituído.

- Um primeiro nome duplo polaco com hífen („Anna-Maria Kowalska") perdia
  a sua metade anterior assim que o precedia texto corrido ou uma
  preposição como „z"/„od" – o resto do nome era substituído, „Anna-"
  permanecia sem cobertura em texto simples.

- Fórmulas de cortesia cazaques „Хабарласыңыз"/„Байланысыңыз" (contacte-
  nos), bem como formas verbais sérvias „Помоћи", „Чекамо" e „Пишите"
  sem modelo próprio de reconhecimento de idioma, eram reconhecidas por
  engano, em frases de contacto telefónico, como nome de pessoa ou local.

- A palavra de cortesia azerbaijana „Xahiş" (por favor/pedido) sem modelo
  próprio de reconhecimento de idioma era reconhecida por engano, em
  frases de contacto telefónico, como nome de pessoa.

- Palavras indonésias e malaias de cortesia/imperativo sem modelo próprio
  de reconhecimento de idioma, como „Silakan", „Mohon" (indonésio),
  „Sila" e „Tolong" (malaio), eram reconhecidas por engano, em frases de
  contacto telefónico, como nome de pessoa ou local.

- A forma imperativa usbeque „Kutamiz" (esperamos) sem modelo próprio de
  reconhecimento de idioma era reconhecida por engano, em frases de
  contacto telefónico, como local.

- Formas imperativas turcas sem modelo próprio de reconhecimento de
  idioma, como „Arayınız" (ligue) e „Bekliyoruz" (esperamos), eram
  reconhecidas por engano, em frases de contacto telefónico, como nome de
  pessoa.

- Formas imperativas noutros idiomas sem modelo próprio de reconhecimento
  de idioma (checo, eslovaco, grego), como „Zavolejte" (ligue), „Prosíme"
  (pedimos) e „Περιμένουμε" (esperamos), eram reconhecidas por engano, em
  frases de contacto telefónico, como nome de pessoa ou local.

- Formas imperativas húngaras e polacas, como „Hívjon" (ligue), „Kérjük"
  (pedimos), „Várjuk" (aguardamos), „Zadzwoń" (ligue) e „Czekamy"
  (esperamos), eram reconhecidas por engano, em frases de contacto
  telefónico, como nome de pessoa ou local.

- Numa lista numerada de nomes sem forma de tabela (por exemplo, „1. Robert
  Brown", por baixo „2. Mary Johnson"), um nome com determinados apelidos
  ingleses (entre outros, „Brown", „White", „Green", „Black", „Young") era
  completamente ignorado – o modelo de linguagem tinha associado ao nome o
  número da linha seguinte, fazendo com que o resultado nunca coincidisse
  exatamente.

- No modelo de linguagem polaco, a inicial de primeiro nome antes de um
  apelido (por exemplo, „J. Kowalski", „A. Nowak") permanecia por
  reconhecer e por limpar no texto – só o apelido era substituído. Outros
  idiomas verificados (entre outros, alemão, inglês, romeno, croata,
  húngaro, russo) já incluíam a mesma inicial antes.

- Um nome de pessoa atrás de um título em minúsculas como „dr.", „ing." ou
  „dipl. ing." não era de todo reconhecido em húngaro, romeno e croata –
  não só o título, mas o nome inteiro perdia-se (por exemplo, „dr. Kovács
  Béla", „ing. Andrei Popescu", „dipl. ing. Marko Horvat").
- Em atas de reunião eslovenas, uma designação de cargo pura antes dos
  dois pontos (por exemplo, „Tajnik:", „Podpredsednik:", „Poročevalec:",
  „Predsedujoči:") era reconhecida por engano como nome de pessoa, assim
  que noutro local da ata já constasse um nome de orador real.
- Em atas de reunião russas, uma designação de cargo pura antes dos dois
  pontos (por exemplo, „Секретарь:", „Докладчик:", „Докладчица:") era
  reconhecida por engano como nome de pessoa, assim que noutro local da
  ata já constasse um nome de orador real.
- Em atas de reunião romenas, uma designação de cargo pura com artigo
  definido antes dos dois pontos (por exemplo, „Secretarul:",
  „Președintele:", „Vicepreședintele:", „Moderatorul:", „Consilierul:")
  era reconhecida por engano como nome de pessoa – „Președintele" já
  sozinho, os restantes adicionalmente, assim que noutro local da ata já
  constasse um nome de orador real.
- Em atas de reunião croatas, uma designação de cargo pura antes dos dois
  pontos (por exemplo, „Izvjestiteljica:", „Zapisničar:"/„Zapisnicar:",
  „Predsjedavajući:") era reconhecida por engano como nome de pessoa.
- Uma morada de apartado postal polaca „Skrytka pocztowa" atrás de uma
  legenda de remetente ou destinatário (por exemplo, „Odbiorca: Skrytka
  pocztowa 45") era reconhecida por engano como nome de pessoa.
- Uma morada de apartado postal croata „Poštanski pretinac" atrás da
  legenda de morada „Adresa:" (por exemplo, „Adresa: Poštanski pretinac
  45", também com „br." anexado para o número) era reconhecida por engano
  como nome de pessoa.
- Um local sem outra legenda em texto corrido norueguês (por exemplo,
  „Anna Hansen bor i Oslo") não era reconhecido – o modelo de idioma
  próprio designa ali os locais, na maioria das vezes, com uma etiqueta
  própria ainda não atribuída, em vez do habitual „LOC".
- Uma data na ordem ISO ano-mês-dia com hífen ou ponto (por exemplo,
  „2024-12-31") não era de todo reconhecida como data nalguns idiomas –
  mais notoriamente em lituano, onde documentos oficiais indicam datas
  predominantemente nesta ordem.
- Um NIF húngaro (közösségi adószám) na forma de 11 dígitos sem
  separadores, igualmente válida oficialmente (por exemplo, „12345678123"
  em vez de „12345678-1-23"), não era reconhecido.
- Um número fiscal polaco NIP com os separadores no agrupamento 3-2-2-3
  (por exemplo, „856-73-46-215", como é habitual em faturas de empresas e
  empresários em nome individual) não era reconhecido – só o agrupamento
  3-3-2-2 para pessoas singulares era detetado.
- Um nome de empresa sob a legenda de campo eslovaca „Zamestnávateľ:" ou
  „Názov zamestnávateľa:" (empregador/empresa) não era reconhecido.
- Um nome de empresa sob a legenda de campo romena „Angajator:" ou
  „Denumire angajator:" (empregador/empresa) não era reconhecido.
- Um nome de empresa sob a legenda de campo húngara „Cég:" ou
  „Munkáltató:" (empresa/empregador) não era reconhecido.
- Um nome de empresa sob a legenda de campo polaca „Pracodawca:" ou
  „Nazwa firmy:" (empregador/empresa) não era reconhecido.
- Um nome de empresa sob a legenda de campo eslovena „Podjetje:" ou
  „Delodajalec:" (empresa/empregador) não era reconhecido.
- Um nome de empresa sob a legenda de campo croata „Tvrtka:" ou
  „Poslodavac:" (empresa/empregador) não era reconhecido.
- Um montante monetário por extenso com moeda em minúsculas (por exemplo,
  „500 euro") não era reconhecido, só a forma com maiúscula („Euro") era
  detetada.
- O apelido atrás de „Schwager"/„Schwägerin" (cunhado/cunhada) (por
  exemplo, „Der Schwager Bauer erhält die Erbschaft.") não era
  reconhecido.
- Numa morada turca sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „34000 İstanbul
  İstiklal Caddesi No: 45"), o número de porta permanecia por limpar.
- Numa morada eslovaca sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „831 01
  Bratislava Hlavná 15"), o número de porta permanecia por limpar.
- Um país de nascimento sem outra legenda num campo de formulário croata
  (por exemplo, „Zemlja rođenja: Njemačka") não era reconhecido.
- Um país de nascimento sem outra legenda num campo de formulário
  lituano (por exemplo, „Gimimo valstybė: Vokietija") não era
  reconhecido.
- Um país de nascimento ou de residência sem outra legenda num campo de
  formulário polaco (por exemplo, „Kraj: Niemcy") não era reconhecido.
- Uma nacionalidade ou local de residência sem outra legenda num campo de
  formulário esloveno (por exemplo, „Državljanstvo: Nemčija") não era
  reconhecido.
- Um país de residência sem outra legenda num campo de formulário
  norueguês (por exemplo, „Bosted: Tyskland") não era reconhecido.
- Nova página de definições „Notificações" (antes uma secção em
  „Programa"): as três notificações da barra de tarefas (pré-visualização
  pronta, processamento concluído, atualização descarregada) ficam agora
  num local próprio.
- Novo: o resultado pode agora ser colocado adicionalmente como ficheiro
  de texto simples (.txt) ou com a extensão .md ao lado – para
  processamento posterior numa IA ou noutro programa.
- Numa indicação de contacto croata com a legenda „Osoba za kontakt"/
  „Kontakt osoba" (por exemplo, „Osoba za kontakt: Golub Marko"), o nome
  permanecia totalmente por reconhecer quando o apelido era
  simultaneamente um substantivo comum (Golub = „pomba").

- Numa indicação de contacto romena com a legenda „Persoana de contact"/
  „Persoană de contact" (por exemplo, „Persoana de contact: Lup Ion"), o
  nome permanecia totalmente por reconhecer quando o apelido era
  simultaneamente um substantivo comum (Lup = „lobo") e o primeiro nome
  muito curto e genérico.

- Numa indicação de contacto polaca com a legenda „Osoba kontaktowa"/
  „Osoba do kontaktu" (por exemplo, „Osoba kontaktowa: Wilk Adam"), o
  apelido permanecia por reconhecer quando era simultaneamente um
  substantivo comum (Wilk = „lobo", Zielony = „verde").

- Numa morada romena sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „010061
  București Strada Victoriei 30"), o número de porta permanecia por
  limpar.
- Numa morada sérvia sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „11000 Beograd
  Bulevar Kralja Aleksandra 73"), o número de porta permanecia por
  limpar.
- Numa morada grega sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „104 32 Αθήνα
  Ερμού 15"), o número de porta permanecia por limpar.
- Numa morada eslovena sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „1000 Ljubljana
  Slovenska cesta 58"), o código postal permanecia por limpar.
- Numa morada lituana sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „LT-01100
  Vilnius Gedimino pr. 9"), o código postal permanecia totalmente por
  limpar.
- Numa morada húngara sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „1052 Budapest
  Kossuth Lajos utca 12"), o código postal permanecia por limpar.
- Um apelido atrás de „Erben" (herdeiros) (por exemplo, „Die Erben Wagner
  erhielten die Mitteilung fristgerecht.") permanecia, no contexto de
  herança/sucessão, quase sempre por reconhecer.
- Um apelido atrás de „Geschwister" (irmãos) (por exemplo, „Die
  Geschwister Bauer wohnen in Linz.") permanecia, até agora, quase sempre
  por reconhecer – ao contrário de „Familie"/„Ehepaar", isto afetava não
  só nomes homónimos de profissões (Koch, Bauer, Richter), mas qualquer
  apelido neste local.
- Um apelido atrás de „Ehepaar" ou „Eheleute" (casal) (por exemplo, „Das
  Ehepaar Koch zieht um.") permanecia por reconhecer quando era
  simultaneamente um substantivo comum ou designação profissional (Koch,
  Bauer, Richter).
- Um número comum de encomenda, adjudicação ou artigo na grelha de
  agrupamento típica de um número fiscal ou de segurança social (por
  exemplo, „030 4471 2298") era ocultado por engano como tal, sem
  qualquer legenda associada.
- Um número de comprovativo/processo no formato „ano/número sequencial"
  (por exemplo, em „Rechnung Nr. 4/2024/778899") era ocultado por engano
  pela deteção de números de telefone como número de telefone.
- Um nome atrás de „Herr"/„Frau" com uma cadeia de vários títulos
  académicos antes („Herr Dr. med. Weber", „Herr Prof. Dr. Krause")
  permanecia até agora totalmente desprotegido – até agora só era
  reconhecida uma única palavra de título entre a saudação e o nome.
- Uma referência de processo judicial no formato clássico com sigla de
  câmara/secção („4 Ca 1523/24", „Az.: 7 O 234/25") permanecia até agora
  totalmente desprotegida – também a forma curta habitual „Az."/„Gz." não
  era reconhecida ao lado da legenda por extenso.
- Um número de cartão de crédito separado a meio do seu agrupamento de
  quatro por uma quebra de linha – por exemplo, numa coluna de tabela
  estreita – permanecia até agora totalmente desprotegido.
- Um número de identificação fiscal separado a meio do seu agrupamento
  por uma quebra de linha – por exemplo, numa coluna de tabela estreita
  ou num campo de formulário – permanecia até agora totalmente
  desprotegido.
- Um número de segurança social separado a meio do seu agrupamento por
  uma quebra de linha – por exemplo, numa coluna de tabela estreita –
  permanecia até agora totalmente desprotegido, nem sequer parcialmente
  substituído.
- Um número de porta com intervalo como „12a-14b" ou „3-5" só era
  substituído a metade – a segunda parte depois do hífen permanecia em
  aberto no resultado.
- Um número de chassis (FIN/VIN) separado a meio dos seus 17 carateres por
  uma quebra de linha, espaço ou hífen – por exemplo, numa coluna de
  tabela estreita ou num campo de documento do veículo – permanecia até
  agora totalmente desprotegido.
- Uma saudação de carta/e-mail como „Liebe Anna!" ou „Lieber Hans" – sem
  vírgula depois do nome, a forma mais comum em e-mails informais –
  deixava o nome totalmente desprotegido, mesmo no documento completo com
  texto corrido e fórmula de despedida por baixo.
- A mesma lacuna afetava também as saudações informais de chat/e-mail
  „Hallo Anna!", „Hi Anna!", „Hey Anna!" e „Servus Anna!" sem vírgula – o
  nome permanecia igualmente totalmente desprotegido.
- Um bloco de assinatura puro que começa diretamente com „MfG" ou
  „Herzlichst" – por exemplo, copiado da área de transferência, sem
  frase anterior – deixava o nome por baixo totalmente desprotegido.
- Um campo com várias pessoas, por exemplo „Angehörige: Kaczmarek, Piotr
  (Sohn), Kaczmarek, Anna (Ehefrau)", fundia ambos os nomes com a
  indicação entre parênteses num único resultado, demasiado longo – o
  segundo nome permanecia, em parte, desprotegido no resultado.
- Uma rua sem sufixo „-straße"/„-weg" – como é habitual no meio rural, por
  exemplo „Am Marktplatz 5" ou „Im Grund 12" – não era reconhecida quando
  seguida por uma linha de código postal-localidade, por exemplo num
  certificado de residência: „Neue Anschrift: Am Weidengarten 17, 54295
  Trier" perdia a rua por completo, só o código postal era removido.
- Um nome atrás de uma legenda de campo composta com barra (por exemplo,
  „Name/Vorname: Bauer Klaus") não era, em parte, reconhecido – um
  apelido ambíguo como „Bauer" permanecia por detetar sem o comprovativo
  do campo. A mesma lacuna afetava campos combinados como „PLZ/Ort: 04109
  / Leipzig". O mesmo se aplicava a campos combinados com conector por
  extenso em vez de barra, por exemplo „Vor- und Nachname: Bauer Klaus"
  ou „Nachname bzw. Vorname: …".
- Uma data de nascimento na forma „Datum der Geburt: …" e uma data de
  óbito na forma „Todesdatum: …" ou „Datum des Todes: …" não eram
  reconhecidas – só „Geburtsdatum: …" ou „Sterbedatum: …" funcionavam.
- Uma data de casamento na forma „Datum der Heirat: …" ou „Datum der
  Hochzeit: …" não era reconhecida – só „Hochzeitsdatum: …",
  „Heiratsdatum: …" e „Datum der Eheschließung: …" funcionavam, apesar de
  data de divórcio, naturalização e união de facto já conhecerem há
  muito a mesma forma „Datum der X".
- Uma data de divórcio na forma „Datum der Scheidung: …" não era
  reconhecida – só „Scheidungsdatum: …" e a forma verbal posposta
  funcionavam, apesar de data de naturalização e união de facto
  conhecerem desde o início a mesma forma „Datum der X".
- Uma data de união de facto não era, até agora, de todo reconhecida –
  nem com legenda („Verpartnerungsdatum: …", „Datum der
  Lebenspartnerschaft: …") nem em texto corrido („… wurden am …
  verpartnert"). É agora substituída, como data de nascimento, casamento,
  divórcio e naturalização, como tipo de indicação próprio.
- Uma data de naturalização não era, até agora, de todo reconhecida – nem
  com legenda („Einbürgerungsdatum: …") nem em texto corrido („… wurde am
  … eingebürgert"). É agora substituída, como data de nascimento,
  casamento e divórcio, como tipo de indicação próprio.
- Uma data de divórcio não era, até agora, de todo reconhecida – nem com
  legenda („Scheidungsdatum: …") nem em texto corrido („Die Ehe wurde am
  … geschieden"). É agora substituída, como data de nascimento, óbito e
  casamento, como tipo de indicação próprio.
- Uma data de casamento atrás do sinal genealógico de casamento „⚭" sem
  legenda não era reconhecida, apesar de as datas de nascimento e óbito
  na mesma linha, através de estrela e cruz, já serem reconhecidas –
  agora a data de casamento é também reconhecida.
- Uma data de óbito atrás da cruz de necrologia sem legenda
  („*03.06.1940 †21.11.2023") não era reconhecida, apesar de a data de
  nascimento antes, através da estrela genealógica, já ser reconhecida –
  agora a data de óbito é também reconhecida.
- O apelido antes do primeiro nome no fim de uma linha de assunto/tíquete
  com texto objetivo antes e travessão separador („Betreff: Reklamation -
  Bauer, Anna") não era reconhecido com um apelido homónimo de profissão
  – é agora reconhecido.
- Números de candidato e requerente atrás da sua legenda
  („Bewerbernummer: 4471829", „Antragstellernummer: 7654321") escapavam
  totalmente à deteção – são agora reconhecidos.
- Substituir deixa de ocultar quando não há espaço para um marcador
  legível – um marcador demasiado pequeno é agora escrito mais pequeno,
  em vez de se tornar uma barra vazia, enquanto ainda houver algum
  espaço. Novo, além disso: se um local encontrado numa imagem (cabeçalho
  de carta, fundo de digitalização) é legendado ou apenas ocultado pode
  agora ser definido independentemente do restante tipo de resultado. E
  um local encontrado numa imagem que é totalmente removida era
  legendado como se a imagem permanecesse – o marcador ficava claro sobre
  um fundo que nunca era ocultado, desaparecendo assim invisível sobre o
  papel agora branco.
- Um local encontrado numa imagem **mantida** era sempre ocultado a
  preto e branco ao substituir, independentemente da apresentação
  escolhida (cores por categoria, arco-íris…) – visível como uma quebra
  entre etiquetas coloridas em texto corrido e barras pretas no cabeçalho
  de carta. O fundo de imagem segue agora a mesma cor que o marcador ao
  lado.
- A deteção do número de identificação de veículo (FIN/VIN) marcava
  qualquer código alfanumérico de 17 dígitos sem I/O/Q incondicionalmente
  como número de chassis – também números de encomenda, série e chave de
  licença que têm, por acaso, a mesma forma. Agora só conta com uma
  palavra de contexto próxima („FIN", „VIN", „Fahrgestell", „Chassis" e
  semelhantes).
- Em sistemas de tíquetes/calendário, a deteção de nomes arrastava, atrás
  de „Assigned to"/„Closed by" e semelhantes, a palavra de campo seguinte,
  quando esta seguia diretamente na mesma linha sem separador („Assigned
  to Max Mustermann Priority High" tornava-se „Max Mustermann Priority").
  Em cabeçalhos de commit Git, a deteção de nomes arrastava igualmente a
  chave de rodapé **seguinte**, quando duas linhas ficavam unidas por
  apenas um espaço em vez de uma quebra de linha („Author: julia bergmann
  Reviewed-by: …" tornava-se „julia bergmann Reviewed-by"). Ambos os
  travões foram complementados.
- O nome atrás de „p.A.", „zH"/„zHd", „i.A."/„i.V." e „geb." arrastava
  uma palavra de departamento diretamente seguinte para o mesmo
  resultado, quando estava sem separador na mesma linha („p.A. Max
  Mustermann Buchhaltung" tornava-se „Max Mustermann Buchhaltung",
  „i.A.Max Mustermann Vertrieb" tornava-se „Max Mustermann Vertrieb"). O
  mesmo travão de „Assigned to"/rodapés Git foi agora também acrescentado
  aqui.
- Um IBAN legendado diretamente sobre a linha BIC, BLZ ou SWIFT arrastava
  a sua legenda para o seu próprio resultado, porque „BIC" e „BLZ" em si
  pareciam mais um bloco de números – de „IBAN: DE89 … 0130 00" e da
  linha por baixo resultava um único resultado, demasiado abrangente, e a
  legenda da linha seguinte desaparecia junto ao limpar. Era afetada
  quase qualquer conta bancária com IBAN e BIC uma sob a outra.
- O painel de resultados diz agora **onde** está um marcador que não
  consegue encontrar na página. Dois casos comunicavam até agora apenas
  „não encontrado", apesar de a substituição ter ocorrido: se o marcador
  estiver em texto secundário não visível – por exemplo, o endereço de
  destino de uma ligação, uma anotação ou um campo de formulário –, a
  linha traz agora isso como informação própria („no texto secundário"),
  e o clique explica-o. E se o marcador foi escrito de forma abreviada
  por falta de espaço („[N382]" em vez de „[NAM382]"), o clique na linha
  longa salta agora para o local da forma curta e indica a renomeação; a
  atribuição liga expressamente ambas as linhas entre si para esse
  efeito.
- Se o mesmo valor substituto constar várias vezes no documento, cada
  clique adicional na linha do painel salta, em ciclo, para o próximo
  local encontrado – também além dos limites de página; a barra de
  estado conta em conjunto („Resultado 2 de 4"), e o local atualmente
  visado tem uma moldura mais intensa do que os restantes. E se um
  marcador constar apenas na lista de resultados, mas em lado nenhum do
  documento (porque o local se fundiu numa substituição sobreposta), a
  barra de estado diz-o agora, em vez de o clique permanecer
  silenciosamente sem consequência.
- Um primeiro nome abreviado atrás de „an" ou „für" é agora reconhecido
  de forma fiável como nome – „Überweisung an M. Wagner" e „Rechnung für
  M. Wagner" permaneciam até agora muitas vezes por limpar, enquanto o
  mesmo nome com outra legenda antes (por exemplo, „Zahlungsempfänger:")
  já era encontrado. Eram afetadas sobretudo linhas de extrato de conta e
  de lançamento.
- „Angeklagter"/„Angeklagte"/„Beschuldigter"/„Beschuldigte" (arguido/a)
  valem agora como campo de nome: se um nome estivesse em documentos de
  processo penal diretamente atrás de uma destas legendas, não era, até
  agora, de todo reconhecido em cerca de metade dos nomes verificados –
  nem primeiro nome nem apelido.
- O local clicado no painel de resultados fica agora emoldurado a azul em
  vez de marcado a amarelo – sobre as áreas coloridas do semáforo de
  verificação, o amarelo dos resultados de pesquisa não era reconhecível.
  Além disso, o clique encontra agora também valores substitutos de
  várias palavras (nomes inventados, números mascarados): até agora,
  ficava sem efeito nessas linhas, porque o local era procurado apenas
  palavra a palavra.
- Pais adotivos, de acolhimento e padrastos/madrastas („Adoptivvater",
  „Pflegemutter", „Stiefvater" e outros) são agora reconhecidos como
  campo de nome; o nome escapava antes à limpeza
- Tabelas e listas ricas em números deixam de ser descartadas por
  engano: se um número curto (por exemplo, uma parte de número de
  cliente mal lida como número de telefone) fosse substituído, a
  verificação final comunicava a mesma sequência de dígitos como
  indicação remanescente também quando esta constava, por acaso, apenas
  noutro número completamente diferente – e não gerava nenhum resultado.
  Um número só conta agora como resto onde está como número autónomo.
- Certidões de registo civil: „Vater:"/„Mutter:" (pai/mãe) são agora
  reconhecidos como campo de nome; o nome do progenitor escapava antes à
  limpeza
- Outros cargos familiares („padrinho", „avô/avó", „cônjuge",
  „companheiro/a", „tio", „tia") são agora reconhecidos como campo de
  nome; o nome escapava antes à limpeza
- O código bancário alemão (Bankleitzahl) é agora também reconhecido na
  forma oficialmente agrupada ("370 400 44", "370.400.44", "370-400-44",
  "370/400/44"), não apenas como oito dígitos seguidos.
- O número de segurança social de reforma alemão é agora também
  reconhecido com ponto, hífen ou barra entre os cinco blocos
  ("65-170839-J-08-8", "65.170839.J.08.8"), não apenas com espaços.
- A janela principal aparece mais depressa: as bibliotecas de deteção
  (Presidio, incluindo a base de modelos de idioma) eram, até agora,
  carregadas já durante a construção da janela – no Windows, cerca de
  quatro segundos antes de sequer haver algo visível. Carregam agora por
  completo em segundo plano; o botão „Limpar" só fica livre, como até
  agora, quando tudo estiver pronto.
- Documentos do Office com muitas imagens ou vídeos são escritos mais
  depressa: multimédia já comprimida é guardada no pacote de resultado
  em vez de ser comprimida inutilmente uma segunda vez – até agora, isso
  não poupava um único byte e tornava os JPEGs, aliás, maiores.
- Folhas de cálculo e outros documentos com muitas unidades de texto
  pequenas são verificados mais depressa: a deteção de idioma processa
  agora todas as células e parágrafos de um documento numa só passagem
  em vez de individualmente – com resultados comprovadamente idênticos
  (400 células: de cerca de 4,7 para 2,5–3,5 segundos).
- Páginas de PDF do tipo lista (índices, listas de posições) são
  significativamente mais rápidas ao inserir marcadores: a procura de
  espaço por legenda percorria, até agora, todas as palavras da página –
  agora só o contexto de linha, com resultado comprovadamente igual (numa
  página com 300 legendas, cerca de dezasseis vezes mais rápido).
- Documentos ricos em imagens poupam vários passos de trabalho
  desnecessários por imagem: a contagem de rostos e códigos em páginas de
  PDF deixa de descodificar a imagem de página duas vezes, a verificação
  de metadados deixa mesmo de desencriptar uma imagem limpa, imagens
  pixelizadas são escritas com a compressão PNG normal em vez da mais
  lenta (mesmo tamanho, um terço do tempo), e sem marca de água definida
  deixa de haver a reescrita inútil de todo o PDF no final.
- PDFs digitalizados com reconhecimento de texto ativado ficam
  significativamente mais rápidos: cada página era, até agora, renderizada
  duas vezes em resolução completa (uma para ler, uma para rasterizar) –
  a imagem é agora reutilizada. E, no Windows/Linux, o reconhecimento de
  texto lê as faixas de uma digitalização grande numa só passagem, em vez
  de um arranque de programa próprio por faixa.
- Documentos grandes são limpos significativamente mais depressa: a
  comparação de valores já encontrados crescia, até agora, com o número
  de resultados (um bloco de texto de 64 KB custava, no fim de um
  ficheiro grande, cerca de um segundo só nisso, agora um sexagésimo), e
  a pesquisa de formas jurídicas de empresa percorria todas as cerca de
  280 formas do catálogo sobre cada trecho de texto (agora cerca de vinte
  vezes mais rápido, com resultados comprovadamente idênticos).
- Um nome diretamente a seguir a „Beste Grüße"/„Beste Wünsche" sem texto
  ou pontuação anterior não era de todo reconhecido – um bloco de
  assinatura puro, sem texto corrido antes, fazia o nome desaparecer sem
  deixar rasto.
- Um campo de morada no início do documento com um apelido homónimo de
  profissão („Bauer Anna", „Koch Stefan" como primeira linha sobre rua e
  localidade) permanecia, até agora, em parte por reconhecer ou era
  classificado como indicação de local em vez de pessoa – sem frase
  anterior, faltava ao modelo de linguagem a estrutura frásica que, de
  outro modo, permite reconhecer „Bauer" como nome e não como profissão.
- Um nome atrás da marca de assinatura „gez." com um apelido homónimo de
  profissão antes do primeiro nome („gez. Bauer Anna" no final de uma
  decisão ou sentença) permanecia, até agora, incompletamente
  reconhecido – só o primeiro nome era encontrado, o apelido desaparecia
  sem deixar rasto.
- Um nome diretamente atrás de um número de cliente, contrato ou
  identificação semelhante sem linha própria („Vertragsnummer 55219
  Bauer Anna", „Kundennr. 4711 Bauer Anna") permanecia, com um apelido
  homónimo de profissão, até agora incompletamente ou de todo por
  reconhecer.
- O símbolo na barra de menu do macOS é agora um modelo que se adapta,
  como os símbolos vizinhos, ao modo claro e escuro – com as duas barras
  recortadas, continua reconhecível como Maskuro. Se o vigilante da área
  de transferência estiver a funcionar, isso é indicado por um ponto
  destacado na ponta do escudo.
- Um clique no painel de resultados leva agora também, no modo
  anonimizador, ao local encontrado: mudar de página, deslocar até à
  imagem, marcar a amarelo. Até agora, o clique ficava sem efeito ali,
  porque considerava os marcadores ainda sem número – desde que cada
  local encontrado tem o seu próprio número, o local é inequívoco. Só no
  marcador realmente sem número é que a barra de estado continua a
  explicar porque não é possível determinar um destino de salto.
- O primeiro guardar no editor de correção (Ctrl+S ou o botão de
  disquete) pergunta agora pelo local, como „Guardar como…" – pré-
  preenchido com a pasta do original e o nome do resultado. Até agora, o
  ficheiro ia parar silenciosamente ao lado do original. Quem já tiver
  escolhido antes o local de gravação através da barra de estado não é
  perguntado de novo; cada gravação seguinte continua a escrever o mesmo
  ficheiro, como até agora.
- Se a verificação de segurança antes de guardar comunicar um local
  suspeito, „Voltar à verificação" leva agora até lá: o primeiro local
  encontrado desloca-se até à imagem e é emoldurado a vermelho, a barra
  de estado nomeia-o. Até agora, ficava-se sozinho com o número de
  página e coordenadas de ponto. A partir da janela principal, o editor
  abre-se para esse efeito no local. Também no aviso sobre um número de
  página divergente, o botão leva agora até lá – à primeira página que
  só existe num dos dois documentos.
- Quem mudar a pré-visualização para „Lado a lado em duas colunas"
  recebe agora automaticamente uma janela onde ambas as faixas cabem –
  até agora espremiam-se na largura antiga, até se arrastar manualmente.
  É alargada, no máximo, até à margem do ecrã e nunca voltada a estreitar
  automaticamente; uma largura arrastada manualmente mantém-se.
- Apelido e primeiro nome em colunas de tabela separadas (por exemplo,
  „Apelido | Nome" numa confirmação de inscrição ou numa exportação CSV)
  permaneciam em aberto – cada célula por si parecia, para a deteção,
  uma palavra qualquer sem contexto de nome. São agora reconhecidos.
- Nome e primeiro nome no verso de uma carta de condução europeia
  permaneciam em aberto – estão ali atrás dos códigos de campo oficiais
  „1." e „2." em vez de atrás de uma palavra alemã, e é precisamente isso
  que os deixava por reconhecer. São agora reconhecidos quando o número
  da carta de condução (código de campo „5.") está ao lado.
- O primeiro nome do titular do veículo no certificado de matrícula
  permanecia em aberto – está atrás do código de campo oficial „C.1.2"
  em vez de atrás de uma palavra alemã como „Vorname", e é precisamente
  isso que o deixava por reconhecer. Apelido e primeiro nome sob os
  códigos de campo C.1, C.1.1 e C.1.2 são agora reconhecidos.
- A primeira linha da zona legível por máquina (MRZ) num passaporte ou
  bilhete de identidade permanecia em aberto – traz o nome no formato
  „APELIDO<<PRIMEIRO NOME" e escapava por completo mesmo com o novo
  detetor de MRZ para a linha de dígito de controlo. Um resultado só
  conta agora quando, diretamente ao lado, houver uma segunda linha de
  MRZ válida quanto ao dígito de controlo – a própria linha de nome não
  tem dígito de controlo próprio.
- A segunda linha da zona legível por máquina (MRZ) num passaporte ou
  bilhete de identidade permanecia totalmente por reconhecer – contém o
  número do passaporte, a data de nascimento e a data de validade em
  texto simples, mas não coincidia com nenhum detetor existente. Um
  detetor próprio verifica agora os quatro dígitos de controlo ICAO.
- Uma matrícula de veículo sem qualquer espaço em relação à legenda
  permanecia em aberto – „KennzeichenM-AB1234" ou „KFZ-KennzeichenM-
  AB1234" não eram de todo reconhecidos, porque a verificação de
  matrícula subjacente exige um carácter não alfanumérico antes da
  matrícula. Afetava indicações de veículo sem espaço entre a palavra de
  campo e a matrícula.
- Um número de telefone sem qualquer espaço em relação à legenda
  permanecia em aberto – „Handynummer0171/2345678" ou „Tel0171/2345678"
  não eram de todo reconhecidos, porque a verificação de número de
  telefone subjacente exige um espaço ou sinal de pontuação antes do
  número. Afetava indicações de contacto sem espaço entre a palavra de
  campo e o número.
- Um nome de nascença atrás da abreviatura „geb." não era de todo
  reconhecido – „Julia Bergmann (geb. Weber)" encontrava apenas „Julia
  Bergmann", o ponto em „geb." fazia o modelo de linguagem ignorar por
  completo o nome seguinte. Afetava indicações de pessoa com nome de
  nascença entre parênteses ou atrás de vírgula.
- O primeiro nome antes de uma alcunha entre aspas permanecia em aberto
  quando saudação e título estavam juntos antes – „Herr Dr. Klaus "KP"
  Peters" resultava apenas em „Peters", „Klaus" permanecia legível.
  Afetava assinaturas e indicações de contacto com título e alcunha.
- Um nome atrás da forma curta sem ponto „zH"/„zHd" (aos cuidados) não
  era de todo reconhecido – ao contrário de „z.Hd." com ponto, a
  estrutura frásica em falta arrastava o nome consigo. Afetava moradas
  sem ponto na abreviatura.
- Um nome atrás de „p.A." (por endereço) não era de todo reconhecido – o
  ponto na abreviatura fazia o modelo de linguagem saltar por completo a
  deteção de nomes. Afetava faturas e candidaturas com morada coletiva.
- Um nome atrás de „i.A."/„i.V." (em nome de/em representação de) colado
  sem ponto não era de todo reconhecido, por exemplo „i.A.Robert Lang"
  sem espaço – o mesmo erro de estrutura frásica que em „p.A.". Afetava
  linhas de assinatura e assinaturas de e-mail em casos de representação.
- Uma lista de presenças pura com marcador de lista sem qualquer outra
  indicação („- Max Mustermann", também com ponto no fim da linha)
  perdia todos os nomes para o mesmo travão que, na realidade, só devia
  proteger enumerações objetivas como „- Farbe: Blau". Tais listas são
  agora reconhecidas.
- Ficheiros que deixaram de poder ser limpos voltam a poder ser limpos.
  Um valor que já tinha sido substituído pela deteção podia ser
  reencontrado numa marca própria já substituída como „[SVNR1]" – a prova
  final descartava então um ficheiro impecavelmente limpo. Além disso,
  uma referência telefónica numa tabela CSV é agora também removida, e
  quem limitar a pesquisa a tipos individuais recebe-os agora de forma
  igual em todo o documento – também no texto alternativo de uma imagem,
  num cabeçalho Excel, numa lista de seleção ou num atributo HTML.
- Um nome atrás do cabeçalho de e-mail „To:" (ou „To" sem dois pontos)
  não era reconhecido, porque um modelo de idioma alheio lia a linha
  inteira como um único resultado inofensivo e engolia por completo o
  nome nela – ao contrário de „Cc:", „Bcc:" ou „From:" antes do mesmo
  nome. Um nome atrás de „To" é agora encontrado de forma fiável.
- A data de casamento não podia ser tratada, em regras próprias, como
  data („deslocar" era recusado com „só existe para datas"), faltava na
  atribuição de grupo dos tipos de resultado – não podendo assim ser
  desligada através das marcas „O que é procurado" – e recebia, em vez
  de uma sigla curta como na data de óbito, o texto completo como
  marcador. Corrigido nas seis tabelas de sigla/legenda.
- Um valor conscientemente desmarcado na pré-visualização podia, mesmo
  assim, ser ocultado noutro local: se, por exemplo, se desmarcasse um
  endereço de e-mail, o próprio endereço permanecia, mas a sua parte
  local sem domínio era substituída assim que coincidisse com o nome de
  utilizador derivado de uma pessoa ainda selecionada
  („anna.musterfrau@beispiel.de" ao lado de „Anna Musterfrau"). Um texto
  desmarcado fica agora tabu em todo o documento, independentemente do
  tipo de resultado de que provém.
- Uma data de nascimento permanecia por reconhecer quando um registo de
  família ou extrato de registo civil a indicava sob um cabeçalho comum
  com o local de nascimento („Geburtsdatum, Geburtsort: 19.11.1982,
  Steyr") – até agora, a segunda palavra de campo entre „Geburtsdatum" e
  a data fazia a deteção falhar por completo.
- Um número de telefone já reconhecido permanecia legível na sua forma
  abreviada de confirmação, quando era mencionado noutro local do mesmo
  documento apenas com os últimos quatro dígitos („erreichbar unter der
  Nummer ...5678", „Rückruf unter ...5678") – a mesma estrutura que no
  IBAN e no cartão de crédito.
- Um número de cartão de crédito já reconhecido permanecia legível na
  sua forma abreviada de confirmação, quando era mencionado noutro local
  do mesmo documento apenas com os últimos quatro dígitos („Ihre
  Kreditkarte endet auf ...0366") – a mesma estrutura habitual em
  confirmações de pagamento que no IBAN.
- Um IBAN já reconhecido permanecia legível na sua forma abreviada de
  confirmação, quando era mencionado noutro local do mesmo documento
  apenas com os últimos quatro dígitos („Die IBAN endet auf ...3201") –
  uma estrutura habitual em e-mails de confirmação.
- Um orador num chat ou numa ata de reunião permanecia por reconhecer
  quando antes do seu nome estava uma saudação („Herr Bauer: …", „Frau
  Koch: …") – e isso afetava muitas vezes também a linha de orador
  seguinte na mesma ata, porque restavam poucas linhas reconhecidas para
  sequer classificar o documento como ata.
- Uma data de nascimento permanecia por reconhecer quando a palavra de
  campo „geboren" (nascido) estava DEPOIS da data em vez de antes („Das
  Kind wurde am 14.01.2026 geboren") – é assim que, por exemplo, um
  certificado de licença parental ou de proteção da maternidade formula
  a data de nascimento da criança. Os padrões existentes até agora
  pressupunham sempre a palavra de campo antes da data.
- Uma legenda de formulário com um sinal de reação ou marca de visto
  diretamente antes („Ansprechpartner 😊:", „Kontaktperson ✓:") deixava
  de ser reconhecida como legenda, e o nome por baixo ou a seguir ficava
  assim, em parte, apenas incompletamente encontrado (por exemplo, só o
  apelido em „Mayer Roman").
- A mesma lacuna afetava também indicações especialmente protegidas
  segundo o Art. 9.º do RGPD (religião, saúde, sindicato): um sinal de
  reação diretamente antes do separador ou da quebra de linha
  („Konfession 😊: römisch-katholisch") fazia a legenda falhar por
  completo, e a indicação permanecia totalmente por reconhecer.
- Uma morada com nome duplo com hífen na localidade (por exemplo, „79761
  Waldshut-Tiengen", „78050 Villingen-Schwenningen") perdia por completo
  o código postal, apesar de a própria localidade ser reconhecida e
  ocultada – num documento de veículo ou carta, o código postal
  permanecia assim legível.
- Uma coluna de tabela sem espaçamento entre colunas (extrato de texto de
  PDF real) podia, sob uma coluna de nomes, ocultar por engano também
  duas maiúsculas colocadas lado a lado por acaso como pessoa, por
  exemplo dois nomes de local numa linha de dados; isso só acontece
  agora quando nenhum outro resultado no mesmo local já reconhece outra
  coisa.
- A mesma coluna de nomes ocultava, na mesma forma de linha, também duas
  palavras comuns desconhecidas do modelo de linguagem (por exemplo,
  „Frontend Backend", „Turbo Modul") por engano como pessoa, porque ali
  nenhum outro resultado ativava o travão; agora exige adicionalmente que
  pelo menos uma das duas palavras seja, ela própria, lida pelo modelo de
  linguagem como nome próprio.
- O número de segurança social de reforma alemão não era reconhecido no
  seu agrupamento oficial completo (por exemplo, „65 170839 J 08 8" –
  como consta no cartão de segurança social e na folha de vencimento) e
  permanecia no original; só eram reconhecidas a grafia compacta e a
  forma agrupada apenas até à letra.
- O número de identificação fiscal não era de todo reconhecido na sua
  grafia oficial (agrupamento 2-3-3-3, por exemplo, „48 836 075 988" –
  como consta em qualquer notificação fiscal real e comunicação do
  Bundeszentralamt für Steuern) e permanecia no original; só o
  agrupamento mais raro 3-3-3-2 estava coberto.
- O número fiscal da Renânia do Norte-Vestfália (por exemplo,
  „221/5147/0815", com o segundo grupo de quatro em vez de três dígitos)
  não era de todo reconhecido em notificações fiscais e permanecia no
  original – qualquer outro estado federado já estava coberto.
- Em contratos de trabalho, um nome atrás da legenda „Arbeitgeber:"
  (empregador) era totalmente ignorado assim que o apelido fosse
  simultaneamente uma palavra comum (por exemplo, „Bauer Anna") –
  „Arbeitgeber" consta tanto como legenda de nome como de empresa na
  lista, e a atribuição de empresa sobrepunha-se à atribuição de nome.
- Num cabeçalho de contrato de arrendamento com as legendas
  „Vermieter:"/„Mieter:" (senhorio/inquilino), um apelido que fosse
  simultaneamente uma palavra comum (por exemplo, „Bauer") era ignorado –
  só o primeiro nome permanecia reconhecido. Partes arrendatárias
  numeradas („Mieter 1:", „Mieter 2:") eram adicionalmente afetadas,
  mesmo com nomes sem esta ambiguidade.
- Numa ata de tribunal com as legendas „Zeuge:"/„Kläger:"/„Beklagter:"
  (testemunha/autor/réu) (também com numeração, „Zeuge 1:", „Zeuge 2:"),
  um apelido que fosse simultaneamente uma palavra comum (por exemplo,
  „Bauer") era igualmente ignorado – só o primeiro nome permanecia
  reconhecido.
- Em certidão de herança, procuração, processo de injunção e contrato de
  compra e venda, um apelido que fosse simultaneamente uma palavra comum
  (por exemplo, „Bauer") era ignorado atrás de legendas como
  „Erblasser:", „Erbe:", „Vollmachtgeber:", „Bevollmächtigte:r",
  „Antragsgegner:", „Schuldner:", „Gläubiger:", „Käufer:", „Verkäufer:",
  „Vermächtnisnehmer:" ou „Testamentsvollstrecker:" – em parte, só o
  primeiro nome permanecia reconhecido, em parte, o nome inteiro
  desaparecia.
- Numa lista de várias partes antes do separador de rubrum „./." (por
  exemplo, „Sand, Werner und Huber, Anna ./. Wechsler, Martina"), a
  primeira parte permanecia sem máscara – só a parte imediatamente
  adjacente a „./." era reconhecida.
- No separador de rubrum „./." (por exemplo, „Sand./.Wechsler"), o nome
  a seguir ao sinal era totalmente ignorado quando ali não havia espaço –
  só com espaço antes e depois a deteção funcionava.
- O apelido „Wahr" era totalmente ignorado quando estava sozinho (por
  exemplo, „Frau Wahr bearbeitet Ihren Vorgang.") – a palavra consta, por
  acaso, também na lista de palavras alemãs comuns, que de outro modo
  filtra resultados de nome em frases como „Das ist wahr.".
- Apelidos como „Los", „Weit", „Rund" ou „Hoch" eram totalmente ignorados
  quando estavam sozinhos (por exemplo, „Herr Hoch übernahm die
  Leitung.") – todas as quatro palavras constam, por acaso, também na
  lista de palavras alemãs comuns, que de outro modo filtra resultados de
  nome em frases como „Rund einhundert Gäste kamen zur Feier.".
- Apelidos como „Ganz" ou „Recht" eram totalmente ignorados quando
  estavam sozinhos (por exemplo, „Herr Ganz unterschrieb den
  Vertrag.") – ambas as palavras constam, por acaso, também na lista de
  palavras alemãs comuns, que de outro modo filtra resultados de nome em
  frases como „Ganz genau, das stimmt.".
- Um campo de formulário com um asterisco ou um número de nota de
  rodapé sobrescrito atrás da legenda (por exemplo, „Konfession*:
  römisch-katholisch" ou „Religionszugehörigkeit¹: evangelisch") não era
  reconhecido e permanecia em texto simples – só a forma sem este sinal
  funcionava.
- O mesmo campo permanecia em texto simples quando havia mesmo dois
  sinais de nota de rodapé atrás da legenda (por exemplo, „Konfession**:
  römisch-katholisch" ou „Gewerkschaft¹²: ver.di").
- Um número de versão como „Softwareversion 4.2.1.19" ou „Firmware Build
  2.0.4.11" deixa agora de ser ocultado por engano como endereço IP. O
  mesmo se aplica agora a números de comprovativo e processo como
  „Rechnungsnummer 10.20.30.40" ou „Bestellnummer 7.8.9.10".
- Dois IBANs diretamente um sob o outro (por exemplo, o próprio e o de
  um parceiro comercial estrangeiro no cabeçalho de fatura) deixaram de
  ser ambos reconhecidos – o segundo permanecia despercebido.
- Um IBAN legendado arrastava, por vezes, a palavra seguinte na frase
  ("Bankverbindung AT61 … wird belastet" era ocultado até "wird"
  incluído), assim que a palavra seguinte estivesse em minúsculas – o
  resto em texto simples ao lado permanecia intocado.
- As moradas do Liechtenstein são agora reconhecidas („FL-9490 Vaduz"),
  tal como já antes as alemãs, austríacas e suíças.
- O número de passaporte é agora reconhecido e removido atrás da sua
  legenda (por exemplo, „Reisepassnummer: C01X00T471").
- O número de título de residência e de certificado de residência é
  agora reconhecido e removido atrás da sua legenda.
- Um número de identificação atrás da sua legenda é agora também
  reconhecido quando um travessão separa em vez de dois pontos (por
  exemplo, „Kundennummer – K903944").
- Uma conta bancária legendada como „IBAN" ou „Kontonummer" é agora
  também reconhecida quando um travessão separa em vez de dois pontos.
- Um nome atrás de uma legenda como „Kontaktperson (Vertrieb)" ou
  „Sachbearbeiter/in" é agora também reconhecido com acrescento entre
  parênteses ou terminação neutra em género com barra.
- A mesma forma de género com asterisco („Sachbearbeiter*in") é agora
  também reconhecida.
- Um nome atrás de uma legenda é agora também reconhecido quando um
  sinal de igual separa em vez de dois pontos (por exemplo,
  „Ansprechpartner = Mayer Roman" ou „Kontaktperson=Mayer Roman"), como é
  habitual em ficheiros de configuração ou cabeçalhos CSV. Se vários
  destes pares legenda-valor estiverem separados por ponto e vírgula
  numa linha, só o primeiro valor é agora reconhecido, em vez do resto
  da linha inteira.
- Um par de coordenadas GPS atrás da palavra „Koordinaten" é agora
  reconhecido de forma fiável (por exemplo, „Koordinaten: 48.2082,
  16.3738") – a palavra tinha a forma de flexão errada no catálogo
  interno.
- Um número de identificação atrás da sua legenda (número de cliente,
  número de contrato, referência de processo, número de bilhete de
  identidade e cerca de mais cem palavras de campo) deixava de ser
  reconhecido assim que a legenda não estivesse exatamente na grafia
  maiúscula/minúscula registada – „kundennummer:" num e-mail ou
  „KUNDENNUMMER:" num cabeçalho de formulário permaneciam intocados.
</content>

### Novo

- **Valores substitutos realistas são agora um exemplo conscientemente
  aplicado, em vez de um padrão.** A tabela de exceções no separador
  „Marcadores" começa vazia. Um novo botão insere, a pedido, valores
  falsos plausíveis para nome, local, morada, organização, e-mail,
  telefone, extensão e IBAN. Deixa expressamente os montantes monetários
  no marcador numerado; a estratégia „inventar" continua a poder ser
  escolhida manualmente para tipos individuais.
- **O nível de IA pode usar a placa gráfica.** No Windows, pode
  carregar-se para isso um pacote adicional de cerca de 17 MB; depois
  disso, o nível de IA calcula, numa placa gráfica adequada,
  significativamente mais depressa do que no processador. Quem não
  tiver uma, ou não carregar nada, continua a trabalhar sem alterações –
  só que mais devagar. No macOS, a aceleração já está incorporada.
- **Duas novas notificações através do ícone da barra de tarefas**:
  quando a pré-visualização antes de substituir está pronta para revisão
  e quando um processamento está concluído. Ambas vêm ativadas por
  defeito e podem ser desligadas individualmente em *Definições →
  Programa → Notificações*.

### Alterado

- **O número do bilhete de identidade e da carta de condução são agora
  reconhecidos** quando a sua legenda está antes („Personalausweisnummer:
  …", „Führerscheinnummer: …") – até agora, ambos escapavam a qualquer
  deteção.
- **O Maskuro segue agora os designs de contraste do Windows.** Quem
  tiver ativado um em *Definições → Acessibilidade → Designs de
  contraste* recebia-o, até agora, em todo o lado exceto aqui: o Maskuro
  aplicava depois as suas próprias cores. Agora mantém-se o design do
  sistema – janela, listas, zona de depósito, registo e cores de estado.
  O semáforo colorido de verificação na pré-visualização e na janela de
  correção deixa de existir ali propositadamente; o que ele diz consta,
  desde então, de qualquer forma como sinal e como palavra ao lado.
- **A necessidade de verificação deixa de constar apenas na cor.**
  Vermelho, laranja e verde são quase igualmente claros – quem tiver
  deficiência de perceção de vermelho-verde via, na pré-visualização e
  no painel de resultados, uma lista sem diferenças, e isso afeta cerca
  de um em cada doze homens. Cada linha traz agora adicionalmente um
  sinal que se distingue pela forma: ▲ verificar primeiro, ● verificar,
  ○ bem comprovado, ◆ sem avaliação. A dica curta diz-o por palavras, e
  um leitor de ecrã lê-o em voz alta.
- **Alt volta a abrir os menus como habitualmente.** A barra de menu não
  tinha atalhos de teclado: quem não usasse o rato tinha de percorrer
  cada menu com as setas. Agora cada entrada traz uma letra sublinhada –
  Alt+D para „Ficheiro" (Datei), a partir daí B para „Sair" (Beenden) –,
  e isso em todos os idiomas da interface.
- **Os elementos de controlo voltam a dizer a um leitor de ecrã para que
  servem.** Na janela de correção, na janela de regras, no registo, nas
  listas de palavras, na ajuda, na execução de pesquisa e em mais cinco
  janelas, listas, campos de pesquisa, listas expansíveis e cursores
  eram até agora anunciados apenas como „árvore" ou „caixa de
  combinação" – sem indicar de quê. Cerca de quarenta locais têm agora
  um nome. (A janela principal estava correta desde agosto; as janelas
  que vieram depois nunca acompanharam esse passo.)
- **Quem usa o teclado vê, em todo o lado, onde está.** Nos cursores de
  necessidade de verificação, na caixa de verificação e no botão „nunca
  mais" da pré-visualização, nos títulos de tipo dentro dela, no painel
  de páginas da janela de correção e na barra lateral das definições,
  faltava o contorno que o sistema normalmente coloca à volta do
  elemento de controlo selecionado.
- **Uma letra de sistema maior deixa de cortar nada.** Quem definir, em
  *Acessibilidade → Tamanho do texto*, mais de 175%, perdia até agora o
  fim das legendas na monitorização de pastas e nos campos de atalho de
  teclado. A lista de capítulos da ajuda já cortava nomes de capítulo
  longos mesmo com letra normal; agora quebra-os e indica o nome
  completo na dica curta.

- **A deteção tornou-se significativamente mais rápida.** O detetor de
  números de identificação legendados („Kundennummer: K903944")
  verificava, até agora, mais de 1200 padrões individuais em sequência
  por trecho de texto – era o maior item isolado do tempo de deteção, em
  cada parágrafo e cada célula de tabela. Agora é um único padrão com o
  mesmo resultado: no corpus de medição, não muda um único resultado, o
  nível base por trecho de texto fica cerca de três a quatro vezes mais
  rápido.
- **A janela aparece imediatamente ao arrancar.** Até agora, a janela
  principal carregava as ferramentas de idioma completas antes de sequer
  se mostrar – cerca de quatro segundos de tempo cego a cada arranque.
  Os modelos carregam agora, como previsto, em segundo plano, enquanto a
  janela já está pronta; o botão Limpar só fica livre, como até agora,
  quando tudo estiver pronto. Também chamadas puramente informativas da
  linha de comandos (por exemplo, `--version`) respondem agora de
  imediato, em vez de ao fim de vários segundos.
- **As imagens só são lidas uma vez na deteção automática de idioma.**
  Até agora, o reconhecimento de texto corria duas vezes sobre a mesma
  imagem no padrão „Idioma: automático" – uma vez para a suposição de
  idioma, uma vez para a verificação propriamente dita. Ficheiros de
  imagem, imagens da área de transferência e a janela de texto ficam
  assim cerca de duas vezes mais rápidos; com o reconhecimento de texto
  desligado, deixa de haver a leitura que, até agora, corria mesmo
  assim, sem se notar.
- **As páginas web e e-mails guardados são limpos mais depressa.** Os
  valores em atributos HTML, comentários e blocos de dados incorporados
  eram, até agora, reconhecidos individualmente – uma página de câmara
  municipal com centenas de legendas colocava centenas de perguntas
  individuais à deteção. Agora são reunidos e reconhecidos apenas uma
  vez por valor diferente; no corpus de medição não muda nenhum
  resultado, .html e .eml ficam cerca de um terço mais rápidos.
- **Também os depósitos secundários de folhas de cálculo e apresentações
  são reconhecidos de forma agrupada.** Textos alternativos, cadeias de
  fórmula, legendas de diagrama, comentários, memórias intermédias de
  tabela dinâmica e propriedades de documento colocavam uma pergunta de
  deteção própria por valor – uma pasta de trabalho com milhares de
  linhas de tabela dinâmica, correspondentemente milhares. Agora corre
  uma execução agrupada sobre os valores diferentes, e a passagem
  completa de ajuste no final só corre quando, desde o texto corrido,
  surgiram realmente novos valores. No corpus de medição não muda
  nenhum resultado.
- **PDFs ricos em formulários são limpos mais depressa.** Campos, notas,
  marcadores e referências repetem em massa os mesmos valores („Off" em
  cada campo de marcação, o mesmo autor em cada anotação) – cada um
  colocava, até agora, a sua própria pergunta de deteção. Por execução,
  um valor é agora reconhecido apenas uma vez; a substituição e o ajuste
  de consistência continuam a correr por local, sem alteração.
- **Ficheiros de tabela grandes (.csv/.tsv) são limpos
  significativamente mais depressa.** As quatro passagens de ajuste de
  tabela decompunham, até agora, cada uma por si, o mesmo ficheiro
  carácter a carácter em células (com 40 MB, cerca de 30 s de trabalho
  extra); agora a decomposição corre uma vez. A deteção de cabeçalho de
  coluna (colunas de data de nascimento e número de pessoal) coloca,
  em vez de uma pergunta por célula, uma agrupada – com resultados
  idênticos, cerca de vinte vezes mais rápido. E a junção de colunas de
  nome em grandes listas de pessoal deixou de ser quadrática no número
  de linhas.
- **O painel de indicadores deixa de bloquear a janela.** Ao expandir os
  indicadores, o seu texto era, em muitos ficheiros grandes, primeiro
  reunido, deixando a janela parada durante segundos. O cálculo corre
  agora em segundo plano; o painel abre de imediato e traz os números
  depois.
- **O relatório da execução de pesquisa deixa de bloquear a janela.**
  Depois de pesquisar muitos milhares de ficheiros, a pasta comum era
  recalculada para cada ficheiro afetado; em execuções grandes, a janela
  ficava parada durante dezenas de segundos. O relatório aparece agora
  de imediato.
- **PDFs com reconhecimento de texto são verificados mais depressa.**
  Cada página era, ao reler, desnecessariamente convertida duas vezes
  para formato PNG; agora a imagem já existente é reaproveitada. O
  resultado é inalterado, só a verificação corre mais fluida.
- **Anotações com gradiente em imagens grandes deixam de tremer.** Ao
  ajustar pelas alças de uma anotação com gradiente, este era, até
  agora, recalculado ponto a ponto – num grande captura de ecrã, uma
  paragem visível. O resultado é o mesmo, só sem a pausa.

### Corrigido

- **A cruz para remover um ficheiro da lista voltou a ser um X
  simples.** A nova ferramenta do editor „Remover" tinha, por engano,
  usado a mesma identificação de símbolo, mostrando assim também a sua
  cruz vermelha com a linha de texto tracejada em cada linha de
  ficheiro. Ambas as ações têm agora nomes de símbolo separados e
  mantêm a sua apresentação respetivamente adequada.
- **Indicações de várias partes são agora reconhecidas em PDFs também
  além de uma quebra de linha visível.** O Maskuro lê adicionalmente o
  texto de página gerado geometricamente como uma vista de texto corrido
  de deslocamento equivalente. Isto aplica-se a todos os detetores de
  nível base e avançado, bem como a padrões de pesquisa próprios, não
  apenas ao caso „Diabetes mellitus Typ 2" visível em primeiro lugar.
  Linhas vazias e limites reconhecidos de tabela ou secção continuam a
  ser limites rígidos; os resultados continuam a encaixar exatamente nas
  palavras a ocultar.
- **O exemplo em „Pseudonimizar" contradizia-se a si próprio.** A frase
  prometia „mesma pessoa, mesmo número" e mostrava depois dois números
  diferentes – exatamente a imagem correta em „Anonimizar". Ambos os
  exemplos correspondem agora à sua própria frase.
- **Um marcador recém-inserido podia permanecer, ao „Recuperar
  original", como um amontoado de letras sobrepostas, em vez de
  desaparecer.** Um marcador inserido numa só cor escrevia, até agora,
  um comando de saída próprio por carácter, dos quais só o primeiro
  trazia uma matriz de texto própria – na edição seguinte do mesmo local
  (por exemplo, „recuperar" logo depois), os restantes comandos de
  carácter recebiam, sucessivamente, os índices de carácter do primeiro,
  e o marcador dividia-se em duas posições sobrepostas. Um marcador de
  uma só cor recebe agora um único comando de saída para todo o seu
  texto.

- **Se o mesmo valor ocultado ou removido constasse em duas linhas na
  janela de correção e ambas fossem marcadas para recuperação, a
  segunda linha contava por engano como „não inequívoca" – apesar de o
  valor já ter sido recuperado há muito.** Ambas as linhas contam agora
  como concluídas.

- **O nome a seguir a „Reply-To:" é agora encontrado.** Num cabeçalho de
  e-mail como „Reply-To: Huber", o nome permanecia até agora totalmente
  por reconhecer – o modelo de linguagem lia „Reply-To:" como uma pessoa
  própria, errada, e ignorava o nome real a seguir.

- **As palavras de cabeçalho de e-mail „Reply" e „Fwd" deixam de ser
  ocultadas elas próprias como nome.** Numa linha de assunto como „Fwd:
  Angebot von Huber", até agora era reconhecida e ocultada, além do
  nome, também a própria palavra de cabeçalho.

- **„Arbeitgeber: Siemens AG" é agora reconhecido como empresa, não
  mais como pessoa.** Se o valor de empresa atrás da legenda
  „Arbeitgeber" trouxesse uma forma jurídica como GmbH, AG ou KG,
  permanecia, apesar da deteção de organizações ativada, um resultado
  de pessoa – até agora, só o caso mais restrito sem forma jurídica
  („Wollmuth und Partner") era reconhecido como empresa.

- **Uma morada já reconhecida deixa de permanecer noutro local.** Se
  uma morada de rua fosse reconhecida e substituída num local, a mesma
  morada podia permanecer num segundo local – por exemplo, num rodapé
  difícil de ler de um documento digitalizado, onde o reconhecimento de
  texto automático a lia de forma corrompida. As moradas são agora
  removidas, como já há muito nomes e empresas, de forma consistente em
  todo o documento.

- **E-mails com vários destinatários eram danificados em silêncio ao
  limpar.** Uma mensagem `.msg` com dois ou mais destinatários perdia,
  ao guardar, partes da sua estrutura interna, tornando o resultado
  limpo incompleto. A causa era uma confusão entre componentes internos
  com o mesmo nome, que ocorrem em cada destinatário. Tais mensagens são
  agora reconstruídas por completo.

- **Dois dos documentos de teste incluídos não podiam ser abertos no
  Word e no PowerPoint.** Quem descarregasse o corpus de medição
  recebia, em `format_dokument.docx`, „Erro ao abrir o ficheiro no
  Word", e em `format_praesentation.pptx`, „O ficheiro está danificado".
  Ambos os ficheiros já estavam com erro antes de o Maskuro os tocar – a
  versão limpa apenas propagava o erro. O LibreOffice abria ambos sem
  problemas, por isso ninguém tinha notado.

- **Uma IA própria na Internet é agora contactada de forma
  encriptada.** Quem inserir, para a IA própria, um endereço externo
  sem „https://" (como muitas vezes consta na folha do departamento de
  TI), contactava-a até agora através de uma ligação não encriptada – o
  texto não ocultado saía em texto simples. Tais endereços são agora
  contactados via „https://"; um servidor na própria rede continua
  acessível sem alteração. Se o servidor seguir um redirecionamento
  para outro computador, a chave de acesso deixa de o acompanhar.

- **Também uma imagem danificada perde agora os seus metadados
  ocultos.** Se uma imagem incorporada não pudesse mais ser totalmente
  aberta (por exemplo, uma fotografia cortada), mantinha até agora os
  seus dados EXIF e GPS – o local de captura e o nome do fotógrafo
  permaneciam invisíveis no resultado. Tais imagens são agora libertadas
  destes dados mesmo quando já não podem ser exibidas.

- **Um ficheiro incorporado que não pôde ser limpo é agora comunicado,
  em vez de ser transmitido em silêncio.** Se numa apresentação ou pasta
  de trabalho houvesse um objeto incorporado demasiado profundamente
  aninhado ou que não pudesse ser aberto, permanecia até agora
  inalterado no resultado, sem aviso – o ficheiro valia como limpo. Tais
  casos constam agora no aviso „NÃO puderam ser verificados", tal como
  um formato antigo incorporado.

- **As listas escuras voltam a ser uniformemente escuras e legíveis.**
  No macOS, as listas de ficheiros alternavam entre linhas quase pretas
  e cinzento-claras; ao corrigir, o mesmo valor de verificação verde,
  laranja ou vermelho parecia por isso diferente consoante a linha. A
  janela, listas, letra, marcadores e seleção provêm agora de uma
  paleta clara/escura comum. A lista de resultados codificada por cor
  deixa também de colocar riscas em zebra sob as suas cores.

- **Indicações de profissão com „als" (como) eram ocultadas por engano
  como nome.** Uma frase como „Als Koch ist er seit vier Jahren bei uns
  tätig." perdia a profissão, não apenas um nome – „als" introduz uma
  indicação de cargo tal como „der" ou „die". Apelidos reais no mesmo
  local (por exemplo, com uma saudação antes) não são afetados.

- **Um cabeçalho de tabela podia arrastar um número de posição para um
  montante monetário** (só com a opção „Remover também montantes
  monetários" ativada). Se uma linha terminasse numa moeda („… Einzelpreis
  EUR") e a seguinte começasse com um número, resultava, por engano, um
  montante através da quebra de linha. O separador entre moeda e número
  permanece agora na mesma linha.

- **Uma abreviatura curta em maiúsculas podia engolir uma parte inteira
  da frase, ou colar-se antes de um nome corretamente reconhecido.** Se
  numa linha houvesse uma palavra de duas letras em maiúsculas como
  „DI", „AG" ou „KG" – abreviaturas comuns, não nomes –, a linha inteira
  era pesquisada experimentalmente em minúsculas, e a abreviatura
  arrastava, ocasionalmente, palavras vizinhas (também verbos) para um
  único suposto nome. Só a partir de três letras é que uma palavra em
  maiúsculas desencadeia agora esta segunda verificação. Com siglas um
  pouco mais longas como „CEO" ou „USB", permanecia um segundo erro: o
  nome já corretamente encontrado („Schneider") recebia a sigla antes
  dele como prefixo arrastado para o resultado („CEO Schneider"). A
  sigla fica agora de fora.

- **Uma data de nascimento sem espaço a seguir permanecia.** Se atrás de
  „geb." não houvesse espaço antes da data – como é habitual em
  formulários compactos („geb.14.03.1988") –, o Maskuro não reconhecia o
  campo e deixava a data intocada. Formas curtas comuns como
  „Geburtsdat." ou „Geb.-Dat." são agora também reconhecidas.

- **Um IBAN com barras como separador permanecia.** Tal como em números
  de telefone („0664/1234567"), alguns modelos também escrevem o IBAN
  em blocos com barra („AT48/3200/0000/1234/5864") em vez de espaço ou
  hífen. Esta grafia é agora também reconhecida.

- **Um número de segurança social austríaco com hífen, ponto ou barra
  permanecia ou estava mal legendado.** Entre os dois blocos de números
  estava até agora previsto apenas um espaço; grafias como
  „1237-010180", „1237.010180" ou „1237/010180" não eram reconhecidas
  (ou, no caso da barra, sob o tipo errado). O dígito de controlo
  continua a confirmar cada resultado, independentemente do separador.

- **Um nome atrás de „c/o" numa morada nem sequer era removido.** „c/o
  Max Mustermann, Hauptstraße 5, 1010 Wien" ocultava rua e localidade,
  mas deixava o nome a seguir totalmente intacto. O nome é agora
  reconhecido; „c/o" em si mantém-se visível como indicação de morada.

- **Um número de cartão de crédito agrupado com pontos permanecia.**
  Grafias como „4111.1111.1111.1111" não eram reconhecidas; números
  separados por espaço ou hífen não eram afetados por isto. A soma de
  verificação continua a confirmar cada resultado.

- **Um número de identificação fiscal agrupado com hífens permanecia,
  bem como um NIF austríaco com hífen ou ponto.** Espaço, barra e ponto
  já estavam previstos no NIF; faltava o hífen; no NIF („ATU12345678"),
  faltavam o hífen e o ponto depois do prefixo. O dígito de controlo do
  NIF continua a confirmar cada resultado.

- **Um valor de campo entre aspas permanecia, por exemplo numa linha do
  tipo JSON como „vorname": „Max".** A deteção através de uma legenda de
  campo („Vorname: …") pressupunha, até agora, que nem a legenda nem o
  valor estivessem entre aspas. Tais linhas são agora também
  reconhecidas – assim como legendas de campo com um ponto de lista YAML
  antes („- Vorname: Max") ou uma tabulação em vez de um espaço antes
  dos dois pontos.

- **A palavra de cabeçalho de e-mail „Sent" era ela própria ocultada
  como nome.** Num cabeçalho como „Sent: Huber", isso afetava, até
  agora, tanto „Sent" como o próprio nome; palavras de cabeçalho
  relacionadas como „Subject" ou „Betreff" nunca foram afetadas por
  isto. „Sent" permanece agora também.

- Um nome atrás dos cabeçalhos „Errors-To:" ou „Resent-From:"
  permanecia por detetar quando tal linha estava copiada em texto
  simples (por exemplo, uma mensagem reencaminhada ou um relatório de
  incidente) – ao contrário de „Reply-To:" ou „Return-Path:", o nome
  desaparecia aqui por completo, em vez de apenas ser delimitado de
  forma imprecisa. É agora encontrado.
- Um mesmo ficheiro dava, por vezes, resultados diferentes em duas
  limpezas: se duas deteções atingissem exatamente o mesmo local com o
  mesmo comprimento e a mesma confiança (por exemplo,
  „Sozialversicherungsnummer 1237/010180" como AT_SVNR ou como número de
  identificação geral), era ao acaso qual vencia – o valor era removido
  em ambos os casos, só a legenda do marcador mudava. O empate é agora
  sempre resolvido da mesma forma.
- Uma designação de função diretamente antes de um substantivo (por
  exemplo, „Behandelnder Arzt: Dr. …" ou „Zuständiger Sachbearbeiter
  ist …") era, por vezes, ocultada por engano, como se fosse ela própria
  um nome. Apelidos reais ao lado não são afetados por isto.
- Um apelido real que, por acaso, parece um adjetivo (por exemplo,
  „Schöne", „Lange", „Junge") e está diretamente antes de outro
  substantivo (por exemplo, „Kontaktperson: Schöne Assistentin")
  permanecia, desde a última correção, por ocultar no texto – uma fuga
  de dados. Só uma lista estreitamente delimitada de designações de
  função reais (por exemplo, „Behandelnder", „Zuständiger") é agora
  tratada, nesta estrutura, como não-nome.
- Um apelido isolado no final de um resultado de nome de várias linhas
  que, por acaso, parece um adjetivo (por exemplo, „Schwarz", „Kurz",
  „Alt", „Frisch", „Gut", „Reich") permanecia por reconhecer antes de
  dois pontos imediatamente seguintes – a limpeza confundia-o com uma
  legenda de campo como „Telefon:". Uma lista fechada de apelidos
  ambíguos conhecidos protege-o agora.
- Um apelido isolado que, por acaso, é uma palavra alemã comum
  („Gross"/„Grosse", „Gut", „Kurz", „Lang"/„Lange") perdia-se, até agora,
  **por completo** – também em frases simples como „Herr Gross
  unterschrieb den Vertrag." A causa estava na própria lista de
  palavras vazias (stopwords) do spaCy, que contém estas palavras; uma
  lista fechada de apelidos conhecidos protege-os agora de serem
  descartados.
- Em contratos de trabalho, empréstimo, fiança, fidúcia e insolvência,
  bem como em tutela/curatela e encomendas de perícia, um apelido que
  fosse simultaneamente uma palavra comum (por exemplo, „Bauer") era
  ignorado atrás de legendas como „Auftraggeber:", „Auftragnehmer:",
  „Arbeitnehmer:", „Versicherter:", „Darlehensgeber:", „Darlehensnehmer:",
  „Bürge:", „Sicherungsgeber:", „Treuhänder:", „Treugeber:",
  „Insolvenzverwalter:", „Gutachter:", „Sachverständiger:", „Vormund:"
  ou „Pfleger:" – em parte, só o primeiro nome permanecia reconhecido,
  em parte, o nome inteiro desaparecia.
- No aviso legal, um apelido que fosse simultaneamente uma palavra
  comum (por exemplo, „Bauer") era ignorado atrás das legendas
  „Geschäftsführer:", „Geschäftsführerin:", „Vertretungsberechtigt:",
  „Inhaber:" ou „Inhaberin:" – em „Geschäftsführer:"/„Inhaber:", o nome
  inteiro desaparecia; em „Vertretungsberechtigt:", só o primeiro nome
  permanecia reconhecido.
- Um bloco de contacto cuja legenda estava sozinha na sua linha e
  trazia a forma neutra em género com dois pontos („Ansprechpartner:in",
  nome por baixo) era **totalmente** ignorado – os dois pontos eram lidos
  como separador de campo, „in" como valor de campo (descartado), e o
  nome real na linha seguinte deixava assim de ser processado. A forma
  com asterisco („Ansprechpartner*in") não era afetada por isto.
- Se o nome e a legenda com a mesma forma de género com dois pontos
  estivessem **numa** linha („Ansprechpartner:in Anna Berger"), o
  marcador arrastava a palavra „in" para a substituição, em vez de
  remover apenas o nome – o próprio nome continuava a ser capturado por
  completo.
- Um nome numa coluna de tabela sob um cabeçalho de coluna de pessoa
  (por exemplo, „Name Vorname Geburtsdatum" sobre „Bauer Anna
  03.05.1985", como num recibo de vencimento) era totalmente ignorado
  assim que entre as colunas houvesse apenas um único espaço e nenhuma
  linha começasse com um número de estrutura – exatamente a forma em
  que um extrato real de texto de PDF entrega tais linhas.
- Num chat ou numa ata de reunião com nomes de orador antes dos dois
  pontos (por exemplo, „Bauer 🙂: Ich stimme dem Vorschlag zu."), o nome
  permanecia totalmente por reconhecer assim que houvesse um sinal de
  reação entre o nome e os dois pontos e o apelido fosse simultaneamente
  uma palavra comum („Bauer", „Koch", „Schneider" e semelhantes) – uma
  ata inteira podia assim ficar sem um único orador reconhecido.
- A mesma lacuna de linha de orador existia também com outros sinais
  intermédios antes dos dois pontos: um acrescento de estado entre
  parênteses („Bauer (Vorsitz): …", „Bauer (abwesend): …"), uma hora
  entre parênteses retos („Bauer [14:32]: …") e um sinal de nota de
  rodapé imediatamente junto ao nome („Bauer*: …"). Também aqui o
  orador permanecia totalmente por reconhecer assim que o apelido fosse
  simultaneamente uma palavra comum.
- Se uma pessoa já reconhecida constasse num excerto de protocolo ou
  registo anexado à mesma mensagem (por exemplo, um tíquete de suporte)
  adicionalmente como nome de utilizador na forma „primeironome.apelido"
  – em minúsculas, sem espaço, ligado por um ponto –, este nome em
  texto simples permanecia legível, apesar de o mesmo nome na carta já
  estar ocultado.
- A mesma lacuna de nome de utilizador existia também com um sublinhado
  em vez de um ponto („primeironome_apelido") – um formato igualmente
  comum em excertos de protocolo e registo.
- E também na ordem inversa o nome de utilizador permanecia legível
  („apelido.primeironome" ou „apelido_primeironome") – alguns sistemas
  colocam o apelido antes do primeiro nome no nome de utilizador do
  registo.
- Uma data de óbito permanecia por reconhecer quando não havia outra
  indicação ao lado („Herr Bauer ist am 12.03.1985 verstorben") – não
  havia até agora deteção própria para isso, e a data genérica não se
  aplica a este limiar padrão.
- Uma data de óbito permanecia também por reconhecer quando a frase
  usava a forma verbal em vez do particípio („Frau Meier verstarb am
  12.03.1985", „Er starb am 12.03.1985") – só „ist … verstorben"/„ist …
  gestorben" funcionava até agora.
- Uma data de casamento permanecia por reconhecer, seja qual fosse a
  forma em que constasse („Eheschließung am 12.03.2010",
  „Hochzeitsdatum: 12.03.2010", „Herr und Frau Bauer heirateten am
  12.03.2010") – não havia até agora deteção própria para isso, e a
  data genérica não se aplica a este limiar padrão.

- **No editor de correção, uma segunda moldura sobre um marcador acabado
  de inserir podia deixar um resto de carácter vermelho**, por exemplo
  „[G" em vez de „[BEG1]" – sem qualquer aviso, pois o resto já não
  pertencia à indicação confidencial (essa já tinha sido removida no
  primeiro gesto), mas apenas ao próprio marcador. A causa era a
  coloração: um marcador recém-inserido era escrito carácter a carácter
  no ficheiro, mesmo com um padrão de cor única – uma moldura posterior
  sobre o mesmo local deixava assim de encontrar um texto contínuo onde
  se pudesse localizar. Agora, um marcador de cor única fica como uma
  peça única no fluxo, tal como a limpeza automática sempre fez; só um
  gradiente real ou texto arco-íris continua a precisar de carateres
  individuais. A contraverificação incorporada reconhece agora também
  esse resto, mesmo quando a cadeia exata de carateres do marcador já
  não ocorre.
- Uma lista de nomes numerada com número de estrutura escalonado
  („1.1 Max Mustermann", „1.2 Huber Franz" …) perdia todos os nomes para
  o mesmo travão que, na realidade, só devia proteger estruturas e
  listas de posições reais – sem cabeçalho de coluna sobre a lista, não
  havia testemunho que salvasse um nome.
- Um nome numa linha de início de sessão em inglês de um registo de
  sistema („Accepted password for Max Mustermann from 10.0.0.5 port
  51000 ssh2") não era reconhecido – o modelo de linguagem alemão só o
  encontrava quando antes estava „invalid user", caso contrário
  permanecia. Tais excertos de registo são muitas vezes anexados sem
  alteração a um relatório de incidente. Nomes atrás de „for" antes de
  um endereço IP são agora reconhecidos de forma fiável.
- O nome do devedor na referência de mandato SEPA de um extrato de
  conta ou diário de lançamentos (por exemplo, „MREF+Mustermann
  Klaus+SVWZ+ Miete August") permanecia em aberto – sem espaço, sem
  estrutura frásica, apenas campos em maiúsculas separados por „+", e,
  na ordem ali habitual „Apelido Primeiro nome", a deteção também não o
  encontrava por acaso. É agora reconhecido.
- A rua com número de porta na primeira linha de uma tabela de morada
  (por exemplo, „Apelido | Nome | Rua | Código postal | Localidade")
  permanecia em aberto – o modelo de linguagem adivinhava ali um local
  errado, mas mais longo, ao longo de várias colunas, que suprimia o
  resultado de morada correto e mais curto. É agora reconhecido.
- A mesma fuga ocorria com uma tabulação em vez de „|" ou „;" como
  separador de coluna – ali a morada desaparecia mesmo por completo, em
  vez de apenas se perder. É agora reconhecido.
- Uma rua com número de porta permanecia em aberto quando, logo a
  seguir sem espaço, seguia um código postal com vírgula (por exemplo,
  „Bahnhofstrasse 12,80331 München", como numa coluna de tabela
  separada por vírgulas) – a vírgula parecia uma casa decimal de uma
  quantidade, e a rua nem sequer valia, para o padrão, como morada. É
  agora reconhecido.
- Uma rua com número de porta permanecia em aberto quando, logo a
  seguir sem vírgula, seguia o prefixo de local „St." (Sankt) (por
  exemplo, „Hauptstraße 5 St. Pölten", um cabeçalho de carta sem código
  postal antes) – „St." parecia a unidade de quantidade, e a rua nem
  sequer valia, para o padrão, como morada. É agora reconhecido.
- Um acrescento de porta/andar depois de um número de porta (por
  exemplo, „Lerchenfelder Gürtel 43/12") permanecia visível em aberto
  quando, logo a seguir, houvesse uma única letra que, por acaso,
  coincide com uma unidade de medida (por exemplo, „h" para hora) – a
  morada era então limpa só até ao número de porta, sem o seu
  acrescento, em vez de ser capturada por completo ou de todo.
- Uma linha de assunto com um apelido homónimo de profissão antes do
  primeiro nome („Betreff: Bauer Anna", „Betreff: Bauer, Anna")
  permanecia até agora totalmente por reconhecer – também a meio do
  documento com uma frase completa antes. É agora reconhecido.
- Um número fiscal alemão com espaço, ponto ou hífen entre os blocos
  (por exemplo, „Steuernummer: 30 815 08153" ou „30.815.08153")
  permanecia até agora por reconhecer – só a grafia com barra era
  encontrada. É agora reconhecido.
- Um nome atrás de uma legenda de campo médica („Patient:", „Hausarzt:",
  „Behandelnder Arzt:", „Überweisender Arzt:" e as suas formas
  femininas) permanecia até agora por reconhecer quando o apelido era
  simultaneamente uma palavra alemã comum (por exemplo, „Patient: Bauer
  Thomas"). É agora reconhecido.
- Um nome atrás da legenda de campo „Zahnarzt" (dentista) em linha
  própria (por exemplo, „Zahnarzt", por baixo „Huber Franz") permanecia
  até agora por reconhecer – nem primeiro nome nem apelido. „Zahnärztin"
  e a forma simples „Arzt" não eram afetadas por isto. É agora
  reconhecido.
- Um apelido atrás de „Herr"/„Frau", seguido de uma fórmula burocrática
  como „zur Kenntnisnahme", „zur Unterschrift" ou „zur Weiterleitung",
  era, até agora, capturado de forma demasiado ampla, arrastando a
  fórmula para o resultado de nome – de „Frau Petra Klein zur Vertretung
  in allen Angelegenheiten" resultava a substituição de „Petra Klein zur
  Vertretung", e o resto da frase ficava gramaticalmente mutilado.
  Predicados nobiliárquicos reais como „von der Leyen" ou „zu
  Guttenberg" não são afetados por isto.
- A mesma redação excessiva de fórmula burocrática também estava por
  trás do nome num cabeçalho de e-mail „To:", num código de habilitação
  (C.1/C.1.1/C.1.2), num código de carta de condução, num campo de
  formulário entre parênteses („[Vorname]: …") e numa fórmula de
  despedida sem ponto – em todos esses locais, „zur"/„von" e afins
  arrastavam uma fórmula seguinte como „zur Unterschrift" ou „zur
  Vertretung" para o resultado, em parte ficava mesmo a mera palavra de
  partícula como resto de nome no resultado. Também aqui, predicados
  nobiliárquicos reais permanecem totalmente preservados.
- O número de matrícula (estudante) atrás da sua legenda não era, até
  agora, de todo reconhecido – „Matrikelnummer 7654321" escapava
  totalmente à deteção, nem como número de identificação nem através do
  modelo de linguagem, porque o número sozinho não tem forma
  reconhecível.
- O mesmo se aplicava ao número de participante – „Teilnehmernummer
  4471829" escapava totalmente, nem como número de identificação nem
  através do modelo de linguagem.
- No currículo, o nome sob o título de secção „Persönliche Daten" (dados
  pessoais) escapava muitas vezes total ou parcialmente à deteção,
  quando estava, sem saudação, na forma „Apelido Primeiro nome"
  diretamente por baixo.
- O mesmo se aplicava ao título de secção „Kontaktdaten" (dados de
  contacto) – ali o nome escapava mesmo totalmente, não apenas em parte.
- Num certificado de residência ou lista de candidaturas com coluna
  combinada „Name, Vorname" (grafia de registo de residentes, valor por
  exemplo „Mustermann, Max" numa célula), o nome escapava totalmente à
  deteção quando se seguia outra coluna, como a data de nascimento.
- Uma data de nascimento na forma habitual em bilhete de identidade e
  certificado de residência „Geburtsdatum/-ort: 22.07.1978 / Rostock"
  não era reconhecida – só a forma com vírgula „Geburtsdatum,
  Geburtsort: …" funcionava.
- „Bürgerservice" e „Bürgerbüro" (serviço/gabinete de atendimento ao
  cidadão) eram, ocasionalmente, ocultados por engano como local,
  sobretudo depois de um travessão como separador de enumeração (por
  exemplo, „Wenden Sie sich an das Bürgerservice – Bürgerbüro …").
- Um número de telefone legendado, cortado a meio por uma quebra de
  linha (por exemplo, de uma coluna estreita de cabeçalho de carta ou de
  uma extração de texto de PDF na largura da coluna: „Telefon: 0176
  12\n34567"), era, em parte, ocultado apenas a metade – o resto atrás
  da quebra de linha permanecia legível.
- Um número de identificação legendado (cliente, membro, contrato e
  semelhantes), cortado a meio por uma quebra de linha (por exemplo,
  „Kundennummer: K903\n944" numa coluna estreita), era ocultado apenas a
  metade – o resto atrás da quebra de linha permanecia legível.
- Um nome com título académico antes de uma designação profissional
  depois de vírgula (por exemplo, „Dipl.-Ing. Sabine Roth,
  Projektleiterin") permanecia totalmente desprotegido – a linha parecia
  um cabeçalho de coluna tabular e era descartada por engano como
  conteúdo objetivo.
- O título „Dr.-Ing." (um grau de engenharia alemão comum) antes de um
  nome não era incluído no valor de pessoa mascarado e permanecia
  legível – a mesma armadilha do hífen que em „Dipl.-Ing.".
- Os títulos „Dipl.-Kfm.", „Dipl.-Kffr." e „Dipl.-Psych." (licenciado em
  gestão/gestora/psicólogo) antes de um nome não eram incluídos no valor
  de pessoa mascarado e permaneciam legíveis – a mesma armadilha do
  hífen que em „Dipl.-Ing." e „Dr.-Ing.".
- Um endereço MAC na grafia Cisco com pontos em vez de dois pontos (por
  exemplo, „aabb.ccdd.eeff", como aparece em registos de switch e
  tíquetes de suporte) não era de todo reconhecido e permanecia legível.
- Um apelido atrás de „Familie" (família) (por exemplo, „Die Familie
  Gruber unterschreibt den Vertrag") permanecia, consoante a estrutura
  frásica, por reconhecer e assim legível – também com predicado
  nobiliárquico antes („Familie von der Leyen").

- Numa morada croata sem sinal de pontuação separador entre código
  postal+localidade e rua+número de porta (por exemplo, „10000 Zagreb
  Ulica Ivana Lučića 5"), o número de porta permanecia por limpar.

- Numa indicação de contacto lituana com a legenda „Kontaktinis asmuo"
  (por exemplo, „Kontaktinis asmuo: Vilkas Jonas"), o apelido permanecia
  por reconhecer quando era simultaneamente um substantivo comum
  (Vilkas = „lobo", Vanagas = „açor").

- Um país de nascimento ou de residência sem outra legenda num campo de
  formulário dinamarquês (por exemplo, „Fødeland: Tyskland" ou „Bopæl:
  Tyskland") não era reconhecido.

- Um país de nascimento ou de residência sem outra legenda num campo de
  formulário romeno (por exemplo, „Țara: Germania" ou „Țara de
  reședință: Franța") não era reconhecido.

- Um nome de empresa sob a legenda de campo lituana „Darbdavys:" ou
  „Įmonės pavadinimas:" (empregador/empresa) não era reconhecido.

- Um nome de empresa sob a legenda de campo russa „Работодатель:" ou
  „Наименование организации:" (empregador/empresa) não era reconhecido.

- Uma data por extenso com nome de mês em romeno (por exemplo, „31
  decembrie 2024") não era reconhecida.

- Um nome de nascença húngaro atrás da abreviatura „szül." (por
  exemplo, „Nagy Éva (szül. Kovács)") não era reconhecido e permanecia
  visível em texto simples.

- Uma página de perfil HTML guardada (ou um e-mail com uma página web
  anexada) podia deixar o nome civil por limpar quando este constava
  apenas nos campos de perfil Open Graph
  `profile:first_name`/`profile:last_name`/`profile:username" – estes
  trazem o nome decomposto, em vez de descritivo como `og:title", e são
  agora também limpos.

- Uma mensagem de não entrega (bounce/NDR) trazia muitas vezes os
  cabeçalhos do e-mail originalmente não entregue (remetente,
  destinatário, assunto) numa terceira parte de anexo própria – esta
  permanecia, na versão limpa, totalmente intocada. Esta parte é agora
  limpa como o resto do relatório de entrega.

- O editor individualmente nomeado de uma área protegida no Word
  (Restringir edição → Exceções, `w:permStart`) permanecia em texto
  simples, mesmo quando o mesmo nome já estava há muito limpo no texto
  corrido. É agora também removido.
</content>

## 0.10.42-alpha.20260827 – 27 de agosto de 2026

### Novo

- **Perfis de deteção nomeados tornam vários casos de trabalho acessíveis
  num só gesto.** Em *Definições → Deteção → O que é removido*, a seleção
  atual de categorias e tipos pode ser guardada e reaplicada de imediato
  através de um campo de seleção. O perfil fixo *Padrão* corresponde ao
  estado de fábrica anterior e não pode ser eliminado. Um perfil altera
  exclusivamente o que é removido; idioma, tipo de saída, profundidade de
  deteção, bem como termos e padrões de pesquisa próprios, permanecem
  inalterados.

- **O tipo de resultado é agora escolhido diretamente antes de limpar.**
  Um campo de seleção comum na janela principal define, para todo o
  lote, se o Maskuro insere marcadores legíveis, oculta ou remove sem
  substituto. Os dois campos separados para PDF e Office na janela de
  definições deixaram de existir; com isso, a decisão importante fica
  visível e deixa de poder divergir sem intenção em lotes mistos. O tour
  guiado explica a nova seleção antes da primeira limpeza.

- **Temas e marcas de água identificam claramente os PDFs concluídos, a
  pedido.** Doze aparências completas harmonizam textos substitutos e
  áreas de ocultação; novos entre eles: Pride, bem como Primavera, Verão,
  Outono e Inverno. *Dossiê Secreto* traz diretamente um `TOP SECRET`
  diagonal. Independentemente disso, pode escolher-se um texto de marca
  livre ou uma imagem, ícone ou SVG próprios, com cor e opacidade. As
  imagens importadas são incorporadas sem os seus metadados e continuam
  disponíveis mesmo que o ficheiro de origem seja movido. Ao corrigir, o
  Maskuro substitui a sua marca de água anterior, em vez de a sobrepor
  várias vezes. As marcas de água de texto são desenhadas como última
  camada de PDF com contorno claro, para permanecerem visíveis também em
  imagens escuras e texto denso. O editor de correção ignora por
  completo a marca de água do Maskuro e deixa de a oferecer como
  candidata a ocultação.

- **Os temas de saída próprios podem ser guardados e partilhados.** A
  combinação atual de texto substituto, ocultação e marca de água recebe
  um nome, permanece nas definições e pode ser exportada ou importada
  como JSON sem texto simples. A pré-visualização de impressão a preto e
  branco alerta para contrastes fracos; o confetti de sucesso opcional
  mantém-se puramente na interface.

- **Uma última prova de exportação e uma imposição de verificação
  explicativa fecham a fase de apresentação.** Antes de guardar
  definitivamente, o Maskuro compara novamente, camada de texto contra
  pixels renderizados, cada local de PDF conhecido com precisão de
  valor; os avisos indicam exclusivamente a página e as coordenadas. No
  editor, *Porque é que isto está oculto?* mostra categoria, via de
  deteção e margem de segurança, nunca o texto simples removido, e nunca
  no documento final.

- **As barras de ocultação já podem ser bonitas.** Em *Definições →
  Aparência* estão disponíveis padrões de cor, seletores de cor livres,
  gradientes, arco-íris, riscas, pontos, flores, estrelas, corações,
  patas, nuvens, raios, grãos de café, patos, sóis, folhas, flocos de
  neve, padrões de papel, marcador de texto, fita-cola e padrões
  aleatórios reprodutíveis, com pré-visualização imediata. Os textos
  substitutos recebem, à escolha, uma cor, um gradiente, um arco-íris,
  uma pílula ou uma etiqueta. As cores de categoria distinguem nomes,
  moradas, contactos e indicações médicas. O PDF assume a composição
  completa; Word, PowerPoint, OpenDocument e HTML usam a cor de base
  opaca escolhida. A proteção não muda com isto: o Maskuro remove
  primeiro o conteúdo confidencial e só depois desenha a cor ou o padrão
  sobre o local vazio.

- **O Maskuro volta a estar disponível para Linux – como AppImage, DEB,
  RPM e arquivo portátil.** DEB e RPM registam no sistema entrada de
  programa, associações de ficheiro, comando de terminal e ícone; o
  AppImage funciona sem instalação. As atualizações mantêm-se, numa
  instalação DEB ou RPM existente, no mesmo formato de pacote, e
  preferem o AppImage nos restantes casos.

- **A verificação visual deixa de apresentar texto de PDF comum uma
  segunda vez como novo resultado.** O olhar final de OCR e a
  reconstrução segura das páginas visíveis continuam totalmente ativos;
  mas, por defeito, só contam como nova fonte de resultado áreas que o
  texto de página e a verificação de imagem individual ainda não tenham
  lido. Assim, linhas de produto deixam de se tornar novos nomes ou
  empresas apenas por causa de uma segunda leitura de OCR divergente.
  Quem continuar a querer dois julgamentos independentes sobre todo o
  texto visível ativa, nas definições, *Verificar de novo toda a página
  de PDF visível quanto a indicações*.

- **Os PDFs podem agora ser vistos de forma contínua, folha a folha ou
  como página dupla.** Três ícones de vista compactos ficam em baixo,
  diretamente ao lado de „Largura" e „Página". Contínuo rola no rebordo
  da folha para a página seguinte; Página única mantém a roda do rato na
  folha atual; Página dupla mostra um fólio, torna a folha clicada
  editável e move Avançar/Recuar um fólio inteiro. As miniaturas de
  página e a lupa de comparação abrem também numa coluna base esquerda
  visivelmente mais estreita, deixando mais espaço à página de trabalho.

- **Agora vê o que o nível de IA fez.** Depois de cada execução, consta
  em „Detalhes", por ficheiro, uma linha sobre isso – „Nível de IA: 12
  casos limite verificados, 3 descartados" –, e se não encontrou nada
  para alterar, isso também consta. Até agora, o nível mais dispendioso
  ficava totalmente em silêncio: não era possível perceber de fora se
  sequer tinha sido consultado.

  Quem precisar de mais detalhe ativa, em „Definições → IA", *Registar
  cada pergunta à IA no registo*. Depois disso, o ficheiro de registo
  regista, por pergunta, o tamanho, a duração e o número de deteções,
  bem como o tempo de espera devido a um limite de quantidade do
  servidor remoto. O botão „Mostrar ficheiro de registo" ao lado abre a
  pasta – está no diretório de dados da aplicação, que no Windows está
  oculto e que ninguém encontra por si só. No ficheiro constam
  exclusivamente tamanhos, nunca texto dos seus documentos.

- **O Maskuro reconhece quando o seu serviço de IA limita o número de
  pedidos.** Serviços alojados permitem muitas vezes apenas poucos
  pedidos por minuto – quatro não é raro. Os excedentes não são
  recusados, mas têm de esperar, e de dois segundos por resposta passam
  a quarenta. Isto parecia, até agora, que o modelo era lento. Agora o
  Maskuro lê o limite a partir da resposta do serviço, deixa de enviar
  mais perguntas em simultâneo do que as aceites, indica o limite em
  „Verificar ligação" e inclui-o na estimativa de duração.

- **A pré-visualização de página usa o seu Word, Excel e PowerPoint – e
  é, com isso, cerca de seis vezes mais rápida.** Até agora precisava do
  LibreOffice, que está instalado em poucos computadores de escritório;
  quem não o tivesse via um botão que pedia uma instalação externa.
  Agora vale: se o Microsoft Office estiver instalado, é usado
  automaticamente – sem configuração, sem descarregamento, sem marcar
  nada. O LibreOffice mantém-se como segunda via e, em ficheiros
  OpenDocument, é mesmo a primeira; se um falhar, tenta-se o outro.

  A diferença nota-se sobretudo a trabalhar: depois de cada substituição,
  a página é recomposta, o que custa, via Office, cerca de meio segundo
  em vez de três. A primeira vista de um documento continua a demorar
  alguns segundos; depois disso, acompanha os seus gestos sem tempo de
  espera.

  O seu próprio Word aberto não é tocado nesse processo: o Maskuro inicia
  uma sessão própria, invisível, abre o ficheiro apenas para leitura,
  desliga macros e termina tudo de novo assim que a janela de correção
  fecha. Ficheiros protegidos por palavra-passe são recusados, em vez de
  ficarem presos numa caixa de diálogo invisível.

- **A configuração inicial pergunta agora também sobre rostos, códigos e
  assinaturas – e carrega tudo o que falta de uma só vez.** Ao lado da
  deteção avançada, ficam na primeira página os três interruptores de
  imagem: tornar áreas de rosto irreconhecíveis, tornar códigos de
  barras e QR irreconhecíveis, ocultar assinaturas manuscritas em
  páginas de PDF. O limite do PDF está indicado de forma visível junto
  à marcação; os ficheiros do Office não são pesquisados
  automaticamente quanto a assinaturas. Por baixo das marcações consta
  quantos megabytes custa o clique em „Seguinte". Depois disso, o
  carregamento é feito numa **única** janela com uma **única** barra de
  progresso para tudo em conjunto, em vez de em vários diálogos
  sucessivos; uma interrupção termina todo o processo e não deixa nada
  a meio. Quem não quiser nada disso retira as marcações – então também
  nada é carregado.

- **A pré-visualização pode ser reduzida por necessidade de verificação e
  recolhida por tipo.** Por cima da lista está um cursor *Ocultar bem
  comprovados*: quanto mais à direita estiver, mais oculta do verde em
  direção ao vermelho; totalmente à direita só resta o que o programa
  adivinhou sozinho. Um clique no título de um tipo recolhe-o. Ambos são
  um auxílio de leitura, não uma seleção – o que está oculto ou
  recolhido permanece marcado e é substituído; quantas linhas de quantas
  estão visíveis consta por baixo do cursor. Em listas curtas, o cursor
  não aparece. A mudança para duas colunas mantém agora também os
  interruptores *nunca mais*.

- **A lista de imagens pode abrir-se sozinha antes de cada execução.**
  Quem quiser decidir sobre cada imagem individualmente marca, em
  „Imagens", a nova marcação *Definir individualmente antes de cada
  execução*. A lista com pré-visualização aparece então sozinha ao
  limpar, em vez de ter de clicar todas as vezes em „Definir
  individualmente…"; se a interromper, também não se limpa. Se nenhum
  dos ficheiros escolhidos contiver uma imagem, não aparece nada. Por
  defeito, a marcação está desligada.
- **O Maskuro encontra assinaturas manuscritas em páginas de PDF e
  remove-as dos pixels.** Até agora, a assinatura permanecia sob um
  documento limpo – o reconhecimento de texto lê letra impressa, e o
  que não lê não é substituído. A pesquisa é um interruptor próprio e
  precisa de um modelo de deteção, carregado uma única vez.

  Encontra, medido, cerca de 84 em 100 assinaturas e cobre-as em cerca
  de quatro quintos. É uma ajuda, não uma garantia: depois de cada
  execução, o relatório indica quantas foram encontradas – também
  quando não houve nenhuma, pois isso pode significar que não há
  nenhuma ou que uma foi omitida. Em 72 páginas comerciais reais sem
  assinatura, não inventou nenhuma.

  Uma assinatura **desenhada** é encontrada, mas não removida: é feita
  de linhas, não de pixels, e uma barra por cima seria apenas uma
  cobertura sob a qual as linhas continuariam. Esses locais são
  contados e nomeados, para que possam ser ocultados manualmente na
  janela de correção.

  Os ficheiros Word, Excel, PowerPoint e OpenDocument não são
  pesquisados automaticamente quanto a assinaturas. A interface, a
  configuração inicial, o descarregamento de modelo, a linha de
  comandos e o manual indicam agora expressamente este limite.

- **O tour guiado passa agora também pela pré-visualização – a janela em
  que decide.** No documento de exercício, abre-se sozinha, mesmo que
  tenha desligado a pré-visualização de outra forma (a sua definição
  mantém-se como está). É explicado o que significam as cores, porque é
  que cada linha traz apenas uma pergunta – há sequer uma pessoa ali? –
  e para que serve „nunca mais". Nas cores, o foco recai sobre uma linha
  bem comprovada, geralmente o IBAN – o exemplo verde que a frase
  indica; depois sobre a menos comprovada, e aí pode clicar você mesmo a
  meio da explicação: retira a marcação, o valor permanece no documento.
  Numa lista longa, a janela abre-se maior para a visita guiada, para
  que a explicação não fique sobre as linhas. Se a janela abrir uma
  segunda vez, o tour explica também porquê – a página concluída é lida
  de novo como imagem, e nesse processo surgem fragmentos que parecem
  um nome.

- **O editor abre grande na primeira vez.** Original, resultado, barra de
  ferramentas e lista de resultados ficam lado a lado e tinham pouco
  espaço no tamanho base anterior. Quem reduzir a janela recebe o seu
  tamanho de volta da próxima vez – ninguém é sobreposto.

- **Um duplo clique num marcador recupera-o** – em Word, Excel,
  PowerPoint, OpenDocument, Texto, e-mail e HTML. E quem arrastar sobre
  vários marcadores e escolher „Recuperar seleção" recupera todos de uma
  vez. Já não é preciso acertar exatamente no parêntese reto. Marcadores
  que, ao anonimizar, valem para vários valores diferentes ficam
  excluídos disto – são contados e nomeados, não adivinhados.

- **O manual tem um capítulo „Pré-visualização antes de substituir".** A
  janela vem ativada por padrão e é a única em que decide – no manual
  isso constava até agora apenas numa oração secundária. Agora consta
  ali o que significa uma marcação (aplica-se a **cada** local
  encontrado, não apenas ao indicado), porque só há uma pergunta a
  responder por linha, o que „nunca mais" provoca de forma permanente, e
  porque a janela pode abrir uma segunda vez num PDF. Em todos os
  dezoito idiomas, e na lista de definições, o interruptor está agora
  também indicado.

### Alterado

- **O painel „Valores substituídos" tem um cursor sobre as cores, e o
  modo de aprendizagem deixou de estar ali.** Com mais de oito valores,
  fica por cima da lista o mesmo cursor que na janela de
  pré-visualização: *Ocultar bem comprovados* reduz a apresentação ao
  que realmente precisa de ser verificado. No documento nada muda com
  isso, e quantas linhas de quantas estão visíveis consta por baixo – o
  campo de pesquisa e o cursor contam em conjunto. A marcação *Modo de
  aprendizagem* desapareceu do painel; continua disponível no menu
  *Ferramentas* e na barra de ferramentas.

- **O painel „Valores substituídos" mostra agora as mesmas cores que o
  documento.** Cada linha ali tem o mesmo fundo do local no documento e
  do valor na pré-visualização: vermelho significa „adivinhado sozinho,
  aqui vale a pena olhar primeiro", verde „reconhecido por um padrão
  nomeado". Dentro de cada tipo, o mais incerto fica em cima – trabalha
  assim a lista de cima para baixo e vê primeiro o mais importante. Até
  agora, tudo ali aparecia igualmente claro e ordenado alfabeticamente.

- **O modo de aprendizagem vem desligado de fábrica.** Depois de uma
  correção na janela de correção, o programa perguntava até agora, por
  si próprio, se disso deveria resultar uma regra própria. Esta pergunta
  surge a meio do trabalho; quem não a pediu sente-a como interrupção.
  Quem quiser as regras liga o botão *Modo de aprendizagem* na barra de
  ferramentas – a escolha vale então de forma permanente, em ambas as
  direções.

### Corrigido

- **Os ficheiros de regras exportados são agora expressamente assinalados
  como merecedores de proteção.** Termos próprios e exceções podem
  constar neles em texto simples; além disso, o ficheiro pode conter o
  sal de hash com que valores presumidos podem ser confirmados. A
  exportação bem-sucedida mostra por isso um aviso e pede para proteger
  o ficheiro e só o partilhar deliberadamente com destinatários
  autorizados.

- **A última verificação de segurança deixa de reter ficheiros de
  Office limpos por causa dos seus próprios marcadores.** Uma sigla de
  tipo como „SVNR" consta também em `[SVNR1]`; até agora isso valia como
  suposto resto de texto simples e o ficheiro concluído era descartado.
  Ao mesmo tempo, números de telefone e IBANs são agora também
  atualizados onde o Office guarda a mesma indicação sem espaços
  visíveis numa referência ou num ficheiro incorporado.

- **Word, Excel, PowerPoint e OpenDocument deixam de manter uma cópia de
  campo descoberta tardiamente.** Se um valor for reconhecido pela
  primeira vez num depósito secundário ou num ficheiro de Office
  incorporado, uma passagem final estreita limpa também as cópias
  visíveis e ocultas já lidas anteriormente. Marcadores de referência já
  gerados não são substituídos uma segunda vez.

- **Ao recuperar individualmente uma lista de seleção do Word, uma
  seleção vizinha deixa de vir junto sem ser pedida.** O parágrafo
  original completo só é assumido quando também os seus atributos
  deixarem de conter marcadores em aberto.

- **Digitalizações difíceis de ler perdem menos indicações
  relacionadas.** Uma leitura alternativa de OCR com saudação e nome de
  duas partes é mantida; fragmento de rua, número de porta e código
  postal com localidade protegem em conjunto toda a linha de morada,
  mesmo quando se decompõe em blocos de OCR vizinhos. Campos de fatura e
  artigo, bem como linhas de evento ao lado, não são arrastados nesse
  processo. Uma data válida decomposta, a seguir a „nascido", em várias
  palavras de OCR e sinais de pontuação, é também tornada totalmente
  irreconhecível.

- **O confetti de sucesso é agora visível ao abrir automaticamente o
  editor.** Os confetes saem diretamente do botão *Limpar*, em vez de
  cair do rebordo superior da janela. O editor só espera pelo primeiro
  jato, com 850 milissegundos de duração, e abre-se depois
  automaticamente; sem confetti ativado, continua sem atraso.

- **O contador de páginas e a barra de zoom deixam de saltar ao passar
  sobre os ícones de vista.** O Qt redistribuía o espaço livre da barra
  de estado assim que aparecia a dica de um símbolo. Ambos os grupos de
  controlo mantêm agora a sua largura natural e posição fixa ao passar o
  rato.

- **A medição de velocidade de um servidor de IA ligado falhava
  sempre** – em qualquer servidor, desde que existe a IA própria.
  Perguntava com um limite de resposta estreito e depois tentava ler a
  resposta cortada por isso; isso tinha de falhar, e era guardado „não
  medido". As consequências viam-se por todo o lado: a estimativa de
  duração calculava o seu servidor com a velocidade do modelo incluído
  num computador de escritório, e nas definições constava
  permanentemente que a velocidade ainda não tinha sido medida. Agora é
  medida pela quantidade que o servidor gerou, e não pelo conteúdo da
  sua resposta.

- **„Deteção máxima (IA) – lenta" constava mesmo quando não era
  verdade.** A legenda e a indicação descreviam o modelo incluído num
  computador de escritório – „um modelo de linguagem neste computador",
  „até uma hora em documentos grandes". Quem tivesse ligado o seu
  próprio servidor de IA lia ali duas coisas erradas: não se calcula no
  seu computador, e a resposta chega em segundos em vez de horas. Ambas
  vêm agora da medição. Se não houver nenhuma, a aplicação deixa de
  afirmar algo e diz que ainda não foi medido.

- **Recuperar funciona agora também sobre uma seleção arrastada.** Quem
  arrastasse sobre vários marcadores e quisesse premir *Recuperar
  seleção* encontrava o botão cinzento: só ficava ativo quando a
  marcação fosse **exatamente** um marcador – arrastada sobre um
  parágrafo, nunca é. O caminho por trás disso já existia, só que
  ninguém lá chegava. Agora basta marcar a área; todos os marcadores nela
  contidos voltam de uma só vez.

- **Recuperar falhava se a lupa de comparação estivesse aberta.** A lupa
  memoriza o local sob o cursor do rato, para acompanhar no original. Ao
  recarregar depois de uma recuperação, devolvia esse local numa forma
  que a vista de texto não conseguia interpretar – e, como um erro assim
  a meio da interface termina o programa, a recuperação transformava-se
  numa falha. A lupa fica aberta na posição de base, atingindo assim o
  caminho comum.

- **Depois de recuperar, a vista deixa de saltar para o início do
  documento.** Num documento mais longo, depois de cada gesto
  desaparecia o local em que se estava a trabalhar. Agora o parágrafo
  que estava em cima mantém-se em cima.

- **Sem LibreOffice, a pré-visualização de página diz de onde vem, em vez
  de apenas faltar.** Os dois botões *Pré-visualização de página* e
  *Ocultar como PDF* estavam bloqueados e indicavam na dica apenas que
  não foi encontrado LibreOffice; não havia em lado nenhum na aplicação
  um caminho até lá. Um clique abre agora uma indicação com o caminho
  até ao LibreOffice gratuito e de código aberto. O manual e as
  perguntas frequentes estavam errados neste ponto – anunciavam um
  módulo para descarregar que a aplicação não oferece.

- **Antes de entregar, o ficheiro concluído é pesquisado por completo
  uma última vez – agora também em Word, Excel, PowerPoint,
  LibreOffice, e-mail, HTML e texto.** Até agora, só o PDF tinha este
  último olhar. Todas as verificações anteriores olham para um local que
  alguém indicou previamente; um depósito em que ninguém pensou, por
  isso, também ninguém verifica. No final, o Maskuro procura agora,
  sem distinção, tudo o que foi substituído – em cada parte do pacote.
  Se algo permanecer, **não** é gerado nenhum resultado, e a mensagem
  indica o valor. Um ficheiro que se considera limpo é pior do que
  nenhum.

- **Os nomes em `<script>` e `<style>` são agora comunicados.** Ambos
  continuam intocados – ali está código de programa, e uma substituição
  a meio de um identificador transforma uma página web numa página web
  avariada. Mas isso não era dito até agora, e esse era o erro: uma
  regra de estilo `content: "Anna Musterfrau"` fica **visível** no ecrã
  do destinatário, e no resultado continuava lá, enquanto o programa
  comunicava a página como limpa.

- **Nas definições, os modelos adicionais voltam a poder ser carregados
  e removidos.** O botão ao lado de „Deteção avançada" e „Deteção máxima
  (IA)" acabava, ao ser premido, na janela de relatório de erro, em vez
  de obter o modelo. A segunda via – a marcação na deteção, que pergunta
  sozinha pelo modelo – nunca foi afetada por isto.

- **Os nomes contidos em nomes de folha e de intervalo de uma tabela são
  agora comunicados.** O nome de uma folha está no separador em baixo, o
  nome de um intervalo nomeado no campo de nome e em cada fórmula que o
  usa. Ambos continuam a não ser substituídos – as fórmulas referem-se a
  eles, e uma pasta de trabalho com erros de referência não ajuda
  ninguém –, mas agora consta ali. Até agora, a mensagem só aparecia
  para o nome de folha de uma pasta de trabalho Excel: um intervalo
  nomeado „Bezuege_Brunnthaler" saía em silêncio, e numa folha de cálculo
  LibreOffice o programa ficava totalmente calado. Uma folha „Notizen
  Ortner" valia assim como limpa, e o primeiro olhar do destinatário
  recaía sobre o nome.

  Só é comunicado o que realmente leva a uma pessoa: uma palavra que já
  foi substituída na mesma pasta de trabalho, ou um resultado que
  seleciona uma de várias palavras. Uma palavra isolada como
  „Zustaendig" ou „Bezug_Umsatz" deixa de desencadear um aviso – antes
  teria feito isso, e um aviso que aparece em cada segunda pasta de
  trabalho já não é lido por ninguém depois da terceira vez.

- **„Recuperar original" recupera agora realmente tudo.** Em alguns
  documentos faltavam depois carateres isolados – de „Seestraße 14"
  resultava „Seestraße 4", de „An:" um „An", de „nordlicht-planung" um
  „nordlicht planung" –, e linhas inteiras nem sequer voltavam.
  Exatamente aí, deixava de ser possível selecionar algo com o rato ou
  ocultar algo mais: o texto estava no papel, mas o programa já não o
  reconhecia. Eram afetados carateres estreitos – o um, os dois pontos,
  o hífen – em documentos que definem cada carácter individualmente; o
  documento de exercício é um deles.

- **E esses mesmos documentos deixam de ser transformados em imagem ao
  limpar.** Como um destes carateres permanecia, a segunda verificação
  comunicava um resto e a página era rasterizada por precaução. O texto
  ali passava então a ser apenas uma imagem: já não pesquisável, já não
  selecionável, maior no ficheiro. O documento de exercício mantém-se
  agora como texto real em ambas as páginas.

- **As marcas coloridas deixam de permanecer sobre texto recuperado.**
  Quem anulasse uma substituição continuava a ver o retângulo colorido
  sobre a palavra restaurada – afirmava „aqui foi removido algo", apesar
  de estar de novo o original.

- **Uma barra deixa de revelar o comprimento da palavra por baixo.** Ao
  ocultar, a barra cobre agora, em linhas curtas, a **linha inteira** –
  bloco de morada, dados de cabeçalho, célula de tabela estreita. Se a
  linha inteira não couber (a linha de tabela comum com três colunas),
  mantém-se o campo; numa linha de texto corrido, mantém-se exato à
  palavra, pois de outro modo um nome a meio da frase enegrecia a frase
  inteira. E barras que ficam umas sob as outras passam a ter o **mesmo
  comprimento**: no bloco de morada há um valor em cada linha, e três
  barras de comprimentos diferentes continuavam a revelar quão longas
  eram as linhas. Só crescem, no entanto, até onde o papel está livre –
  antes de uma coluna vizinha, a barra para.

- **„Linha inteira" oculta agora realmente a linha inteira.** Até agora,
  a barra terminava no próximo espaço maior – ou seja, no fim do campo.
  Em texto corrido isso não se notava, ali o campo é a linha; em dados
  de cabeçalho e tabelas, sim: de „Nome: Anna Musterfrau   Departamento:
  Vendas" resultava uma barra que terminava exatamente na última letra
  do nome – e assim o seu comprimento continuava no papel. A barra vai
  agora da primeira à última palavra da linha e leva consigo as colunas
  vizinhas. Quem só quiser atingir o valor escolhe „Palavras"; o
  automatismo oculta, sem alterações, campo a campo.

- **Antes de entregar, o ficheiro concluído é pesquisado uma última
  vez.** Todas as verificações anteriores olham para um local que alguém
  indicou previamente – texto de página, retângulo de resultado, área de
  imagem. Mas um PDF tem mais depósitos do que uma enumeração consegue
  abranger: anotações, valores de formulário, marcadores, informações do
  documento, anexos de ficheiro, JavaScript. No final, o Maskuro
  pesquisa por isso o ficheiro escrito, sem distinção, por tudo o que
  substituiu – em todo o lado, exceto no texto de página, onde o mesmo
  texto literal também pode estar presente de forma permitida. Se algo
  permanecer ali, **não** é gerado nenhum resultado, e a mensagem indica
  o valor. Um documento que se considera limpo é pior do que nenhum.

- **O que não pôde ser verificado deixa de valer como verificado.** De
  três formas, até agora, uma falha da segunda verificação parecia um
  resultado limpo. Uma página cuja camada de texto não pôde ser lida
  valia como especialmente limpa – ali não havia mesmo nada a
  encontrar; é agora rasterizada. Se uma página com um local de
  resultado remanescente não pudesse ser rasterizada como alternativa,
  era entregue em silêncio; agora a limpeza prefere interromper-se. E a
  contraverificação na janela de correção comunicava, depois de um erro
  próprio, „nada resta" – impossível de distinguir, na janela, de tudo
  ter sido removido; agora aparece o aviso, com o botão „Rasterizar
  página".

- **„Repor padrão" não repunha a maioria das definições.** Nove em vinte
  e duas marcações permaneciam inalteradas depois do gesto – entre elas
  a pré-visualização, „Abrir ficheiros limpos depois", a janela de
  correção, o arquivamento imediato e ambas as marcações de
  atualização. O ficheiro guardado estava de facto esvaziado, mas a
  janela mantinha os valores antigos e voltava a escrevê-los no clique
  seguinte. Agora cada marcação volta, e a nota „alterado" desaparece
  com ela.
- **„Arquivar automaticamente relatório de verificação por limpeza"
  aparecia marcado, mas estava desligado.** Depois de repor, a marcação
  ficava definida enquanto o valor estava apagado – deixava de ser
  gerado qualquer relatório, sem nada que o indicasse. O mesmo se
  aplicava ao registo de verificação e à captura de ecrã própria; o seu
  atalho de teclado é agora também corretamente registado ou removido
  ao repor.

- **As barras de uma linha têm agora o mesmo aspeto.** Até agora, cada
  local encontrado trazia a sua própria barra, e a sua altura vinha do
  tipo de letra da palavra atingida. Numa linha com legenda e valor em
  tamanhos diferentes, ficavam por isso lado a lado um traço grosso e um
  fino, com rebordos desalinhados, e onde dois locais encontrados só
  estavam separados por um espaço, ficava por cima um vão claro. As
  barras da mesma linha têm agora o mesmo rebordo superior e inferior, e
  o que só está separado por um espaço torna-se uma barra. O que deve
  permanecer entre dois locais encontrados – a vírgula depois do nome,
  uma legenda, um montante – continua a separá-las. Aplica-se tanto a
  páginas compostas como a digitalizações.

- **Os separadores em „Sobre este programa" voltam a começar no topo.**
  Proteção de dados, condições de licença e avisos de licença abriam a
  meio do texto – quem os lesse tinha primeiro de rolar até ao topo
  para ver a primeira linha.

- **A caneta deixa de abrir uma segunda janela de editor, trazendo antes
  para a frente a existente.** Até agora, cada clique criava uma nova. A
  janela não tem entrada própria na barra de tarefas – quem a
  minimizasse já não conseguia acedê-la e clicava outra vez; ao
  restaurar a janela principal, todas as janelas acumuladas vinham
  então de uma vez para a frente. Agora, mais documentos aparecem na
  barra de separadores da janela aberta, e um documento que já lá esteja
  não recebe um segundo separador.

- **„Deteção avançada" deixa de trazer a nota „alterado" enquanto lhe
  falta o modelo.** É entregue ativada, mas sem o modelo carregável não
  pode de todo estar ativa – nas definições, a linha constava por isso,
  em cada computador recém-configurado, como alterada, apesar de
  ninguém lhe ter tocado. Porque a marcação está desligada, diz agora
  apenas a sua legenda: „Modelo ainda não carregado".

- **A faixa de introdução explicava a área de PDF em ficheiros do Office
  e de texto.** Ali constava „clicar numa palavra oculta-a" – mas num
  ficheiro Word, um clique não oculta nada, ali marca-se e depois
  prime-se um botão. Diz agora o que se aplica em cada vista.
- **A barra de ferramentas estava sobrecarregada de legendas na vista de
  texto.** „Substituir seleção", „Ocultar seleção", „Recuperar seleção",
  „Pré-visualização de página" e „Ocultar como PDF" aparecem agora como
  símbolo – tal como os seus equivalentes num PDF. Os seus nomes
  mantêm-se na dica e no menu.
- **Ctrl+roda do rato na lupa de comparação não movia o seu cursor de
  zoom em conjunto.** O tipo de letra ficava maior, o cursor e a
  percentagem ao lado continuavam a afirmar o estado antigo.
- **O programa de instalação de uma atualização não vinha para a
  frente** – era preciso primeiro clicar nele na barra de tarefas
  (apenas Windows).
- **Um ano no início de linha valia como código postal austríaco.** Num
  currículo, de „2020 Estratégias de vendas" resultava um marcador – a
  linha inteira desaparecia. Um número de quatro dígitos entre 1900 e
  2099 precisa agora de um segundo sinal de morada: a rua por cima, uma
  palavra de campo antes, uma indicação de país ou um nome de local
  conhecido. Blocos de morada têm isso; colunas de anos não.
- **Um par mês-ano valia como número de telefone.** De „Desde 08.2010
  123-Verkauft GmbH" resultava um „número de telefone" – mês, ano e os
  primeiros algarismos do nome da empresa a seguir.
- **O relatório dizia „verificado por reconhecimento de texto" e
  omitia o que este não lê.** Se as imagens forem mantidas, consta agora
  que material manuscrito ali não é encontrado – uma assinatura ou um
  nome inserido à mão permanece. Até agora, esta frase só constava em
  páginas digitalizadas; um PDF comum com uma assinatura incorporada não
  recebia nenhuma palavra sobre isso.
- **Um marcador sobre fundo de imagem ocultado ficava na margem esquerda
  da sua barra.** Se um valor for encontrado numa imagem – por exemplo,
  um nome digitado ao lado de uma assinatura digitalizada –, a área de
  imagem tem de ser ocultada em toda a largura. O marcador, mais curto,
  deixava ao lado preto nu, o que parecia dois processos. Fica agora
  centrado sobre a barra.

## 0.10.41-alpha.20260826 – 26 de agosto de 2026

### Novo

- **Depois do período de teste, uma janela lembra a licença uma vez por
  arranque.** Aparece cinco minutos depois do arranque – não de imediato,
  para não atrapalhar ninguém antes do primeiro gesto – e aguarda enquanto
  decorre uma limpeza. A partir dali, um caminho leva à compra e outro à
  introdução de uma chave já comprada; „Mais tarde" fecha-a assim que os
  cinco segundos no botão terminam. Nada é bloqueado: o nível gratuito
  continua a funcionar como até agora.

- **O tempo de espera antes de uma execução no nível gratuito passa agora
  a dez em vez de trinta segundos.** Serve para lembrar a licença, não
  para travar o trabalho.

- **Os três avisos sobre a licença têm agora o mesmo aspeto.** Tempo de
  espera, lembrete nos últimos dias de teste e aviso após o período de
  teste têm a mesma faixa, a mesma estrutura e os mesmos botões; o tempo
  restante consta agora no botão em vez de um número grande ao lado.

- **A lista de resultados na pré-visualização volta a ficar em coluna
  única.** A partir de nove valores ficava em duas colunas; ao percorrer,
  o olhar salta entre duas faixas, e aqui decide-se linha a linha. Quem
  preferir as duas faixas volta a ativá-las em baixo à esquerda na
  janela – a escolha fica guardada, e ao alternar, os valores já
  desmarcados permanecem desmarcados.

- **O nível de IA está aberto a quem ligar o seu próprio servidor de
  IA.** „Definições → IA" reúne tudo: a ligação, o que a IA pode fazer, o
  que lhe é dado a fazer – e, por cima, o interruptor do nível, com
  contraverificação, assim que um servidor estiver registado. Um modelo
  de linguagem que calcule no próprio posto de trabalho permanece
  reservado: precisa de vários minutos para dez páginas e não serve,
  assim, para o dia a dia.

- **É possível ligar uma IA própria.** Em vez do modelo de linguagem
  incluído, um modelo maior pode responder noutro computador – num
  servidor interno ou numa estação de trabalho com placa gráfica
  potente. É exigido um serviço com interface compatível com OpenAI
  (Ollama, LM Studio, llama.cpp-server, vLLM, LocalAI); é configurado em
  „Definições → IA própria", com uma verificação de ligação que
  efetivamente interroga o modelo, mede a velocidade e determina a forma
  de resposta possível. Vários trechos de texto correm em simultâneo em
  vez de sequencialmente.

- **O que a IA pode fazer e o que lhe é dado a fazer é agora
  configurável.** Três interruptores decidem sobre a verificação de casos
  limite, a pesquisa autónoma e a pesquisa em texto corrido; a instrução
  dada ao modelo está indicada literalmente, pode ser complementada com
  termos internos e repor-se ao padrão com um botão.

- **Se, com isso, o texto sair da própria rede, é emitido um aviso antes
  de cada execução.** O Maskuro reconhece pelo endereço se o servidor de
  IA está dentro de casa e identifica pelo nome um fornecedor conhecido. O
  aviso pode ser desligado, mas só mediante confirmação expressa de estar
  autorizado a essa transmissão, e apenas para esse endereço exato. O
  processo em si não muda: a transmissão continua a constar do registo e
  do relatório de verificação de cada ficheiro. Na linha de comandos não
  se pergunta, interrompe-se – ali é necessário `--ki-auswaerts-erlauben`.

- **A pré-visualização antes de substituir está agora ativa por defeito em
  novas instalações e aplica-se também a conteúdos da área de
  transferência expressamente limpos, bem como a texto e imagens colados
  no programa.** Em lotes de documentos continua a aparecer exatamente uma
  pré-visualização por documento, com todas as páginas; a limpeza
  instantânea e silenciosa de cópias curtas não abre propositadamente
  nenhuma janela.

- **Os resultados podem ser ativados e desativados na pré-visualização
  através de toda a linha colorida.** A marcação é agora grande e com bom
  contraste; adicionalmente, um campo de estado mostra „Substituir" ou,
  riscado, „Substituir", para que valores selecionados e desmarcados
  também se distingam de imediato sobre cores de confiança escuras.

- **Também os PDFs com verificação de segurança visível só abrem a
  pré-visualização uma vez por documento.** Os termos desmarcados
  permanecem desmarcados para a testemunha de página posterior; a sua
  verificação continua a decorrer, sem interromper a mesma execução com um
  segundo diálogo.

- **As palavras substitutas têm o mesmo aspeto no editor de correção,
  também em páginas rasterizadas.** Se o marcador vermelho estiver nos
  pixels em vez de na camada de texto do PDF, recebe agora, ainda assim,
  a mesma área de fundo colorida por confiança que um marcador de texto
  de PDF comum.

- **Já a pré-visualização antes de substituir mostra a necessidade de
  verificação dos termos encontrados.** Cada linha tem a mesma cor
  vermelho–laranja–verde que depois o substituto no editor. Dentro de
  uma categoria, ficam em cima a baixa confiança e os candidatos a falso
  alarme a vermelho, em baixo as fortes comprovações verdes; os empates
  mantêm-se por ordem alfabética. Se o mesmo valor vier de vários locais
  encontrados, conta, por precaução, a avaliação mais duvidosa entre
  eles. Casos especiais não avaliados ficam em amarelo neutro, entre o
  vermelho e o laranja.

- **O resultado pode agora ser copiado diretamente do editor de correção
  como ficheiro.** „Copiar resultado" coloca a versão limpa atual na área
  de transferência, sem fechar o editor nem procurar de novo o ficheiro
  na lista principal. Numa edição manual ainda não guardada, corre
  primeiro automaticamente o caminho de gravação segura completo;
  „Copiar imagem" mantém-se como função separada para pixels puros.

- **As palavras substituídas mostram, de relance, no editor, o que deve
  ser verificado primeiro.** Um mero palpite do modelo de linguagem fica
  a vermelho, mesmo que o spaCy indique para isso 85 por cento de forma
  genérica. Outros julgamentos de modelo não apoiados permanecem, no
  máximo, a laranja; comprovações nomeadas fortes podem ficar a verde.
  Trabalho manual e atribuições mais antigas sem avaliação analisável
  permanecem em amarelo neutro. Também as barras de ocultação automáticas
  trazem estas cores na pré-visualização do editor – agora também quando
  a barra faz parte de uma página de PDF rasterizada. Para isso, a
  atribuição tem de corresponder e a caixa de palavra anterior tem de ser
  comprovadamente preta e opaca; negrito comum não é colorido. No PDF
  guardado, todas as barras permanecem inalteradas, pretas e opacas.

- **O que é desmarcado na pré-visualização pode ser memorizado de forma
  permanente.** Ao retirar a marcação, está a dizer: aqui a deteção
  enganou-se. Até agora isso só valia para este documento. Agora aparece
  na linha um interruptor „nunca mais"; premido, o valor entra de forma
  permanente na lista „Nunca remover" e passa a valer como inofensivo em
  qualquer documento futuro. Por baixo da lista consta o que se torna
  permanente, antes de premir „Substituir". O sentido inverso não existe
  propositadamente: o que já foi encontrado uma vez, a deteção volta a
  encontrar.

- **Um botão repõe todas as definições no estado de fábrica.** Está em
  baixo à esquerda na janela de definições e pergunta previamente. Os
  seus ficheiros, a sua licença, as suas próprias regras de deteção e o
  arranque automático permanecem intocados; o que a sua administração
  impõe continua a valer. Cada definição que se desvia do estado de
  fábrica traz ainda a nota „alterado" – assim vê-se de relance o que foi
  alterado.

### Alterado

- **Um resultado deixa de ser gravado automaticamente – só ao guardar.**
  Uma execução a partir da janela escreve a sua versão limpa primeiro
  num local provisório; o ficheiro „…_bereinigt" ao lado do original só
  surge quando se prime „Guardar". Até lá, o resultado pode ser visto,
  corrigido e copiado. Cada linha concluída tem para isso um botão
  Guardar, por baixo da lista está „Guardar tudo", e no editor vale
  Ctrl+S. Quem esvaziar a lista ou fechar o programa é questionado; o
  que ninguém grava, também não fica em lado nenhum. „Mostrar na pasta"
  está bloqueado antes de guardar – o local provisório não é um destino
  para onde se envie alguém. O ficheiro de atribuição acompanha o
  ficheiro ao guardar.

  Nas definições, em „Programa", „Gravar resultados imediatamente ao
  lado do original" repõe o comportamento anterior. A linha de comandos,
  a vigilância de pastas e o vigilante da área de transferência continuam
  a gravar de imediato, sem alterações – ali não há ninguém que possa
  guardar.

- **A barra de ferramentas do editor de correção está mais arrumada.** O
  modo de aprendizagem está agora na extremidade direita, junto da lupa
  de comparação e „Valores substituídos" – os três interruptores que
  ativam e desativam um modo de funcionamento ficam assim juntos.
  „Aplicar a todas as páginas" foi movido para junto das três formas de
  ocultação, porque só ali produz efeito. „Copiar resultado", „Ficheiro –
  Repor" e „Aplicar a todas as páginas" dispensam legenda; o seu nome
  continua na dica e no menu. Entre „Substituir" e „Recuperar original"
  há um traço separador: os dois são sentidos opostos e, lado a lado,
  pareciam duas variantes da mesma ferramenta.

- **O ícone de „Copiar resultado" mostra agora um documento.** Duas
  folhas com o canto dobrado e linhas de texto, em vez de duas folhas
  iguais com uma pequena seta no canto. „Copiar imagem" traz, em
  contrapartida, o símbolo de imagem, para que ambos se distingam sem
  legenda. O botão „Copiar" na lista de resultados mostra o mesmo símbolo
  de documento – grava o mesmo ficheiro.

- **As definições estão ordenadas e com títulos.** „Deteção" tem agora
  quatro secções: *O que é removido*, *Como é substituído*, *Com que
  rigor se procura* e *Antes e depois da execução*. Reconhecimento facial
  e códigos de barras/QR estão junto das imagens, onde se procuram;
  „Programa" está dividido em *Ficheiros de resultado*, *Ao iniciar*,
  *Atualização*, *Visualização* e *Comunicação connosco*, e o sufixo do
  nome do ficheiro de resultado está junto dos ficheiros de resultado, em
  vez de entre idioma e aparência.

- **A deteção avançada vem ativada de fábrica**, mesmo antes de o seu
  modelo de linguagem estar carregado. Antes, o padrão dependia do
  conjunto de modelos, e um computador recém-configurado corria
  permanentemente no nível mais fraco. A janela de configuração oferece o
  modelo para carregar logo na primeira página e indica o custo ao lado.
  Se faltar, a marcação continua a indicá-lo, em vez de simular um nível
  que não está a funcionar.

- **As duas listas de termos chamam-se agora ao que fazem:** „Remover
  sempre" em vez de „Termos próprios" e „Nunca remover" em vez de
  „Exceções".

- **A janela de pré-visualização está mais clara.** A partir de nove
  valores ficam em duas colunas, as linhas são mais baixas, e o número de
  ocorrências fica logo a seguir ao termo, em vez de na margem direita.

- **No editor de correção, Substituir vem antes de Ocultar** – na barra
  de ferramentas, no menu „Ferramentas" e no clique direito na página.
  Substituir é o caso habitual: um marcador pode ser clicado e
  recuperado, uma barra não.

- **Menos botões duplicados no editor.** „Guardar como…" e „Copiar
  imagem" ficam apenas no menu Ficheiro, com os seus atalhos de teclado
  habituais. Na barra fica um de cada: Guardar e „Copiar resultado" –
  onde se guarda consta, de qualquer forma, na barra de estado e pode
  ser alterado aí com um clique.

- **O vigilante da área de transferência deixa de ser oferecido no
  primeiro arranque.** Intervém em cada operação de cópia do sistema;
  quem vê o programa pela primeira vez não consegue avaliar isso. Nas
  definições continua disponível, aí com a cláusula correspondente ao
  lado.

- **A aparência clara ofusca menos.** O fundo da janela vinha até agora
  do estilo do sistema respetivo, sendo assim a única grande área que
  ninguém tinha decidido – quase branco no Windows. Agora é um branco
  suavizado, igual em qualquer sistema.

- **O tour guiado e o manual explicam as cores.** O que significam
  vermelho, laranja, verde e amarelo atrás de uma palavra substituída
  consta agora como estação própria no tour guiado e como parágrafo no
  manual – em todas as traduções.

### Corrigido

- **O manual e as perguntas frequentes mostravam marcadores que já não
  existem.** Desde a mudança para a forma curta, o Maskuro escreve
  `[NAM1]`; na ajuda continuava a constar `[NAME1]`, e a frase „Por
  defeito é `[NAME1]`" estava simplesmente errada. Nas dezassete versões
  traduzidas constava adicionalmente a marca em **alemão** em vez da
  própria – um leitor espanhol via `[NAME1]`, onde o seu programa escreve
  `[NOMB1]`. O mesmo com a extensão do ficheiro de resultado: ali todas as
  versões prometiam `_bereinigt`, enquanto o programa cria `_limpiado`,
  `_nettoyé` ou `_除去済み`. Também eram afetadas a forma sem número (ao
  anonimizar, tudo se chama `[NAM]`, não `[NAME]`) e a identificação
  derivada do valor ao aplicar hash.

- **A janela de pré-visualização só interrompe uma vez por documento – e
  uma segunda vez apenas quando surge realmente algo novo.** Um PDF é
  lido por dois lados: uma vez a partir do fluxo de conteúdo e, por
  último, a partir da página renderizada e visível. Até agora, cada um
  dos dois perguntava por si. Agora vale: o que decidiu na primeira
  janela continua válido, e valores que já lá estavam não voltam a
  aparecer. Se, pelo contrário, a verificação visual das páginas
  concluídas encontrar algo que antes não estava em lado nenhum, é
  apresentado de novo – sozinho, sem os valores já decididos.

- **A janela de pré-visualização diz agora com base em quê se deve
  decidir.** Em vez de „Retirar a marcação = o valor permanece" – o que a
  marcação *faz*, mas não quando a deve retirar –, consta ali: retire a
  marcação em todos os locais onde não haja um valor pessoal; ali a
  deteção enganou-se. Além disso, cada janela indica de que execução de
  verificação provêm os seus valores.

- **Os marcadores têm o mesmo aspeto em todo o documento.** Em páginas
  reconstruídas como páginas de imagem pela via de OCR, os marcadores
  visíveis eram até agora escritos em tipo de letra de máquina de
  escrever – „[PLZ4]" ficava largo e com serifas ao lado de um
  „[NAM1]" estreito na mesma página. Agora têm o mesmo tipo de letra
  sem serifa que em todo o resto, e também não ficam mais largos do que
  o previsto no ajuste. A camada de pesquisa invisível mantém o seu
  próprio tipo de letra – precisa de dimensões fiáveis, não de aparência.

- **Na barra de ferramentas do editor deixam de aparecer traços
  separadores duplicados.** Onde um grupo inteiro de ferramentas não se
  aplica ao tipo de ficheiro aberto – num PDF, por exemplo, a
  pré-visualização de página e a renderização –, ficavam até agora ambos
  os traços à volta da lacuna.

- **Ao recuperar, deixa de ficar ocasionalmente apenas um local
  branco.** Um texto original já restaurado com exatidão deixa de ser
  pintado de branco pela caixa larga e agregada do seu marcador
  removido. Em recuperações mistas de texto e imagem, o texto só é
  inserido de forma invisível quando a imagem da página já traz
  visivelmente esse mesmo estado original. Isto aplica-se a molduras,
  painel de resultados e anexos de PDF.

- **„Recuperar original" deixa de oferecer desnecessariamente rasterizar
  a página.** A verificação rigorosa de resto de texto mantém-se ativa
  ao ocultar e substituir. Ao recuperar, é omitida: ali volta
  propositadamente conteúdo original, e palavras vizinhas inalteradas na
  moldura de recuperação alargada não eram um erro de limpeza, mas um
  falso alarme.

- **O tour guiado pelo editor explica agora „Substituir" e „Recuperar
  original" como passos próprios.** Ambas as ferramentas são destacadas
  diretamente na barra e descrevem que uma moldura arrastada insere um
  marcador ou recupera o conteúdo original desse local a partir do
  ficheiro de origem.

- **Também os marcadores específicos de país permanecem agora com no
  máximo quatro letras.** Estes tipos faltavam até agora no catálogo
  central de siglas e podiam por isso aparecer por extenso, por exemplo
  `[UMSATZSTEUER_ID1]`. Novas execuções escrevem para isso `[UID1]`;
  todos os tipos alemães e ingleses reconhecidos automaticamente mantêm-se
  inequívocos. Siglas calculadas de outros idiomas de interface deixam de
  crescer além de quatro carateres em caso de homonímia. Legendas de
  regras próprias mantêm-se com o nome exatamente como foram
  introduzidas.

- **Substituir aproveita agora todo o espaço de linha realmente livre,
  antes de ocultar.** O limite rígido anterior, do triplo da largura
  original da palavra, gerava barras mesmo em campos de formulário
  largamente vazios. Também os resultados da verificação visual de OCR
  recebem agora, com texto de PDF preenchido, um marcador legível;
  permanecem a preto apenas conteúdos puramente de imagem, anotação e
  vetoriais, o modo de ocultação escolhido, bem como estreitezas reais
  onde nem sequer cabe uma forma curta inequívoca.

- **Um marcador já visível não é mais escrito uma segunda vez a vermelho
  por cima ao rasterizar por segurança.** A rasterização retoma agora o
  substituto existente a partir da imagem da página e cria apenas uma
  cópia de pesquisa invisível. Se uma barra de segurança tiver de pintar
  exatamente esse local, é renovada toda a caixa real do marcador, em vez
  de apenas a sua âncora original mais curta.

- **„Recuperar original" marca agora apenas alvos seguros dentro da
  moldura arrastada.** Todos os termos substituídos ali dentro acendem
  individualmente e com exatidão; texto corrido inalterado permanece
  intocado. Barras de ocultação vetoriais reais também são marcadas
  individualmente, se sob a sua área preta de PDF houver texto original.
  Em páginas rasterizadas, a pré-visualização abstém-se propositadamente
  de uma suposta área de barra: a antiga pesquisa por pixel ligava ali
  letras, sublinhados e linhas de tabela em grandes áreas vermelhas em
  locais errados. A recuperação em si não é afetada por isto.

- **Ao restaurar em páginas rasterizadas, o texto volta a aparecer.**
  Até agora, ficava ali um local vazio com retângulos coloridos por
  cima. O texto recuperado estava no documento, mas era pintado pelo
  fundo branco de um marcador desenhado mais atrás na construção da
  página.

- **As cores de verificação já não se sobrepõem várias vezes.** O mesmo
  local era colorido por cada entrada da atribuição – numa página com
  cinco locais reais encontrados, cada um pintado cinco vezes, até a
  marca pálida se tornar um bloco intenso. E deixam de aparecer sobre
  palavras que nem sequer foram substituídas: se o valor original ainda
  estiver na página, também já não há ali nenhuma marca.

## 0.10.40-beta.1 – 24 de agosto de 2026

### Corrigido

- **As barras de ocultação no editor têm agora uma margem de segurança.**
  Molduras de palavra, linha e livres cobrem também glifos salientes e
  pixels de margem suavizados; uma verificação de renderização assegura
  adicionalmente que não permanecem restos visíveis nem texto original
  legível.

- **Os textos substitutos mantêm-se legíveis e uniformemente curtos.**
  Novos nomes, moradas e termos livres aparecem, por exemplo, como
  `[NAM1]`, `[ADR2]` e `[BEG3]`. O limite mínimo fixo é 4,5 pontos; em
  caso de falta de espaço, é primeiro encurtado e depois é ampliado o
  espaço útil de linha. Atribuições antigas com marcadores longos
  permanecem legíveis e recuperáveis.

- **As substituições de várias palavras a partir do painel de resultados
  estão protegidas contra marcas duplicadas e restos do original.** A
  regressão passa com e sem marcadores numerados; por cada local
  encontrado mantém-se exatamente uma atribuição conjunta.

- **Conteúdos recuperados da área de transferência não são limpos de
  imediato uma segunda vez no macOS.** Mesmo quando a assinatura do
  sistema só muda com atraso depois da escrita, o Maskuro reconhece de
  forma fiável o seu próprio conteúdo.

### Novo

- **O editor pode repor um ficheiro por completo na versão inicial recém
  limpa.** „Ficheiro – Repor" descarta, após confirmação, todas as
  correções do separador atual, incluindo a lista de substituições e os
  contadores. O comando fica bloqueado sem alterações e pode, por sua
  vez, ser anulado com „Desfazer".

- **As datas deslocadas mantêm agora a sua cronologia de forma fiável ao
  longo de vários ficheiros.** O desvio comum fica fixado de forma
  permanente nas regras já ao ativar a estratégia; além disso, o desvio
  já não pode ser zero dias, deixando assim de manter a data real sem que
  ninguém note.

- **O trabalho manual em PDF cobre agora todo o fluxo profissional de
  ocultação.** Termos individuais, listas e padrões regulares podem ser
  procurados e ocultados com segurança no PDF aberto ou em todos os PDFs
  de uma pasta; páginas inteiras e intervalos de páginas são
  diretamente selecionáveis. Cor, área branca neutra, texto de
  sobreposição, tipo de letra, alinhamento e repetição têm
  pré-visualização; códigos reutilizáveis podem ser geridos, importados
  e exportados. A limpeza de PDF remove, à escolha, todo o conteúdo
  oculto através de reconstrução completa ou classes de dados
  selecionadas. A escolha mais segura é claramente recomendada, padrões
  de pesquisa inválidos são explicados e as execuções em pasta escrevem
  exclusivamente cópias de resultado.

- **A estatística de utilização voluntária mostra agora instalações e
  mudanças de versão.** Para isso, o Maskuro gera um identificador de
  instalação aleatório, guardado localmente. Não contém indicações de
  dispositivo, utilizador ou licença; o servidor guarda apenas o seu
  valor SHA-256. A estatística permanece totalmente desativável nas
  definições.

- **O tour guiado é agora um exercício orientado por ambas as janelas.**
  Coloca ele próprio o documento de exercício inventado na lista, explica
  o caminho até à limpeza e continua automaticamente no editor depois da
  execução. Quem interromper o tour termina também esta continuação.

- **São reconhecidas empresas de quinze outros espaços jurídicos
  adicionais.** Quem limpar documentos do Báltico, Bélgica, Escandinávia,
  Chéquia, Polónia, sudeste da Europa, Singapura, Brasil ou México deixa
  de perder nomes de empresa por a sua forma jurídica ser desconhecida –
  novos entre eles: OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s.,
  o.p.s., S.K.A., Pte. Ltd., bem como S.A. de C.V. e S. de R.L.

### Alterado

- **As barras de ferramentas do editor usam agora o espaço de forma mais
  direcionada.** Símbolos padrão inequívocos e formas de ferramenta
  diretamente reconhecíveis ficam na barra sem texto repetido; ações
  ambíguas mantêm o seu nome. Em „Vista" pode desativar-se „Mostrar
  legendas das ferramentas", para reduzir ambas as barras exclusivamente
  a símbolos. As dicas e os menus permanecem totalmente legendados, e a
  escolha é memorizada.

- **O modo de aprendizagem está agora visível de forma permanente na
  barra de ferramentas.** Pode ser ligado e desligado diretamente ali,
  mesmo com o painel de valores substituídos fechado. A barra de
  ferramentas, o menu Ferramentas e a antiga marcação no painel mostram
  sempre o mesmo estado.

- **„Repor" na lupa de comparação repõe agora apenas o seu zoom.** O
  botão restaura o padrão de 125 por cento, sem ancorar a lupa, deslocá-la
  ou alterar o tamanho da sua janela. Para a configuração completa
  continua responsável „Repor vista".

- **Erros e sugestões podem agora também ser comunicados através do botão
  de Ajuda.** „Comunicar erro…" e „Sugerir…" estão agora ali tal como no
  menu clássico de Ajuda; ambos os caminhos abrem o já existente relatório
  de erro seguro e a lista pública de sugestões, respetivamente.

- **O menu da barra de tarefas é mais curto e está mais claramente
  organizado.** Os dois comandos com atalho global de teclado – limpeza
  da área de transferência e captura de ecrã – ficam agora imediatamente
  um sob o outro, com uma coluna comum de atalhos à direita. „Restaurar
  último conteúdo original" deixa de constar ali; o botão de restauro,
  mais compreensível, mantém-se disponível na janela principal.

- **As páginas legais são acessíveis diretamente em „Ajuda → Informação
  legal".** O submenu leva às condições de licença, à declaração de
  proteção de dados, ao aviso legal e aos termos e condições em
  maskuro.com. As indicações sobre o direito de resolução mantêm-se na
  compra, no site.

- **Os PDFs ocultados manualmente são totalmente reconstruídos ao
  guardar.** Permanecem visíveis as páginas e a sua camada de pesquisa
  relida; metadados, anexos de ficheiro, marcadores, comentários, valores
  de formulário, camadas ocultas, índices de pesquisa, scripts, conteúdo
  recortado e conteúdo oculto sob outros objetos não são transpostos para
  o ficheiro de saída. O texto e os gráficos vetoriais passam então a
  consistir em pixels – é o preço do limite comprovável em relação à
  árvore de objetos de PDF alheia.

- **Ctrl+Shift+B captura agora, por defeito, uma captura de ecrã com o
  Maskuro em todos os sistemas.** A tecla Print Screen e combinações com
  ela continuam disponíveis como atribuição própria. No menu do ícone da
  barra de tarefas, os atalhos globais de teclado ficam agora à direita
  dos comandos correspondentes. As atribuições próprias guardadas
  mantêm-se.

- **O editor arranca com páginas e lupa de comparação à esquerda.** O
  painel de páginas fica em cima, a lupa de original aberta logo abaixo;
  os valores substituídos ficam à direita. Uma disposição própria
  guardada deliberadamente continua a ter prioridade.

- **O documento de exercício deixa de estar permanentemente na janela
  principal.** Faz parte do exercício guiado e continua acessível
  adicionalmente em „Ajuda".

- **O primeiro arranque leva diretamente ao exercício prático.** O guia
  rápido ilustrado deixa de ser oferecido como segundo caminho de
  entrada, com conteúdo duplicado; continua acessível a qualquer momento
  em „Ajuda → Guia rápido".

- **O ícone inativo da barra de tarefas mantém-se a cores completas.**
  Mostra agora o mesmo escudo Maskuro vivo que o modo ativo da área de
  transferência; só com a monitorização ativa é que se junta o ponto
  luminoso verde.

- **O documento de exercício permanece no Maskuro.** O botão de entrada
  gera o PDF inventado e insere-o diretamente na lista de ficheiros, mas
  já não inicia um visualizador de PDF adicional.

- **A pesquisa na janela de correção mantém-se fluida ao digitar.** O
  espaço para o contador de resultados é reservado já ao abrir; o seu
  primeiro texto deixa de alterar a área de desenho e não desencadeia uma
  nova execução de rasterização de PDF.

- **Os nomes de fabricante em indicações de marca permanecem visíveis.**
  Uma entrada como „Marca: TRILUX ou equivalente" descreve o produto
  necessário e deixa de ser ocultada como empresa apenas por causa desta
  legenda. Os campos de fornecedor, empresa e fabricante não são afetados
  por isto.

- **As medições de corpus contam agora resultados ocultados em excesso
  como falsos alarmes.** Quando o Maskuro remove o nome esperado mas
  arrasta consigo parte de uma frase, o número de falsos alarmes sobe
  agora. O relatório indica adicionalmente os excessos em separado; os
  números de falsos alarmes anteriores não são, por isso, diretamente
  comparáveis.

### Corrigido

- **Termos técnicos e oficiais de documentos originais alemães são menos
  vezes ocultados como nomes ou locais.** Equipamentos de veículo, linhas
  de posição e de soma, termos de adjudicação e de proteção de dados,
  referências legais, bem como nomes de ficheiro de materiais públicos,
  só são travados com o seu contexto temático comprovado. Um trema
  perdido no reconhecimento de texto em „Marz 2026" mantém-se protegido
  como mês; „Marz" sem referência de data pode continuar a ser um nome ou
  local real.

- **„Recuperar original" assume de imediato toda a largura necessária.**
  Se a moldura atingir apenas uma palavra de um valor atribuído, o
  Maskuro amplia-a automaticamente, com base na atribuição e na linha
  original, para toda a indicação – por exemplo, de „Planungs" para
  „Nordlicht Planungs GmbH". A moldura ativa resultante mostra também a
  largura total efetivamente recuperada.

- **„Recuperar original" mostra agora as barras pretas como alvo
  inequívoco.** Ao passar por cima ou arrastar, toda a barra detetada
  acende a vermelho com um contorno de alto contraste, em vez de apenas
  uma caixa de texto pouco identificável ao lado. Isto aplica-se também a
  páginas rasterizadas, onde a barra já só consiste em pixels.

- **O tour guiado do editor deixa de omitir estações quando os painéis
  estavam fechados.** Para a visita guiada, o Maskuro abre e organiza
  temporariamente, por si só, o painel de páginas, a lupa de comparação e
  os valores substituídos. Depois de „Concluído" ou de uma interrupção,
  volta a disposição pessoal. Se uma ferramenta não estiver de todo
  disponível para um tipo de documento, a sua explicação mantém-se como
  parágrafo de texto, em vez de desaparecer sem ser notada.

- **„Substituir" mantém-se visível mesmo no mecanismo de recurso de
  segurança do PDF.** Quando o Maskuro tinha de reconstruir uma página
  como imagem devido a um carácter remanescente ou a um fluxo de texto
  danificado, as substituições corretas ficavam apenas invisíveis na
  camada de pesquisa, e na página havia barras pretas. Os valores
  substitutos efetivamente definidos são agora mantidos visíveis a
  vermelho e pesquisáveis em todas as reconstruções por rasterização e
  OCR.

- **Os avisos por cima da versão limpa mantêm-se legíveis na aparência
  escura.** O título da versão, a linha de comando e a introdução
  assumem agora a sua cor de tipo de letra diretamente a partir da
  janela Qt efetivamente apresentada.

- **As molduras de ocultação voltam a assentar sobre o texto em páginas
  de PDF rasterizadas.** As caixas de palavra invisíveis eram, consoante
  o tipo de letra original, mais estreitas do que as letras visíveis.
  Isso criava lacunas na barra ou deixava legível a última letra. As
  caixas mantêm agora a largura, altura e direção de escrita da palavra
  visível.

- **„O que há de novo" volta a começar bem no topo.** A caixa de diálogo
  do changelog coloca agora, depois da construção completa da janela, o
  cursor de texto e a barra de deslocamento expressamente no início, em
  vez de arrancar a meio das novidades consoante o estado do Qt.

- **Fechar durante o reconhecimento de palavras da digitalização mantém-se
  silencioso.** Uma execução de OCR em segundo plano que esteja a acabar
  deixa de enviar dados para uma janela de correção já fechada.

- **Indicações de tempo relativas deixam de ser tomadas por nomes.**
  Expressões fixas como „hoje", „ontem", „amanhã" e „próxima semana" são
  agora reconhecidas pelo Maskuro a partir dos dados de calendário
  oficiais do respetivo idioma do documento.

- **Sair durante o primeiro carregamento do modelo limpa tudo
  corretamente.** Quem fechar o Maskuro ou a janela de correção logo
  após a abertura não deixa nenhum fio ainda a trabalhar no
  reconhecimento de idioma nativo ao terminar o processo. Isto evita o
  relatório de falha esporádico ao sair; um carregamento já em curso é
  concluído de forma ordenada.

- **As caixas de diálogo de arranque com atraso deixam de aparecer depois
  de sair.** Quem fechar a janela principal pouco depois do arranque
  deixa de ver, mais tarde, invisível ou com atraso, a pergunta sobre a
  melhor deteção, as novidades ou a introdução.

- **HTML e e-mail mantêm as suas terminações de linha.** No Windows, a
  serialização de HTML misturava, após limpeza e recuperação, LF e CRLF.
  O conteúdo e a formatação estavam corretos, mas o ficheiro deixava de
  ser byte a byte idêntico. Os ficheiros HTML e as mensagens MIME voltam
  agora a assumir a grafia da sua origem.

- **Os nomes de empresa com uma preposição mantêm-se completos.** Depois
  de uma preposição, o Maskuro cortava nomes como „Gesellschaft für
  Systemtechnik mbH" ou „Bank für Arbeit und Wirtschaft AG" na palavra
  „für". O nome completo da empresa é agora reconhecido; introduções de
  frase reais como „Estamos segurados na Alpha GmbH" mantêm-se visíveis.

- **Os nomes de empresa chineses mantêm-se completos antes da sua forma
  jurídica.** Um componente de marca interpretável como verbo podia,
  apesar do acrescento inequívoco „有限公司", descartar o nome inteiro.
  Em escritas sem maiúsculas e minúsculas, a âncora oficial de forma
  jurídica tem agora prioridade sobre este limite incerto de classe de
  palavra.

- **Páginas de PDF tornavam-se imagens desnecessariamente.** Em PDFs de
  várias páginas cujas páginas partilham uma lista de tipos de letra – o
  que geradores comuns criam assim –, todas as páginas seguintes à
  primeira perdiam a referência aos seus tipos de letra. A consequência
  era dupla: os tremas deixavam de ser pesquisáveis no resultado
  („Auftragsbestätigung" não podia ser encontrado), e a segunda
  verificação passava então a considerar omitidas letras que nunca
  estiveram na página – rasterizava páginas de texto intactas
  transformando-as em imagens, deixando de serem pesquisáveis,
  copiáveis e claramente maiores. No conjunto de verificação, isto
  afetou quatro em dezassete páginas.
- **Uma vírgula sozinha já não desencadeia rasterização.** Se uma área
  encontrada terminar na palavra, o sinal de pontuação ao lado ainda
  cabe, por pouco, dentro dela. Mas uma vírgula ou um ponto não é uma
  indicação omitida, e a rasterização custa a página inteira. Letras e
  algarismos continuam, sem alteração, a ser motivo para reforçar a
  deteção.

## 0.10.38-alpha.20260824 – 24 de agosto de 2026

### Novo

- **Nomes de empresa sem forma jurídica são agora reconhecidos quando a
  sua legenda os menciona.** „Lieferant: Kranzbichler Handels GmbH" já
  era sempre removido – a forma jurídica denuncia a empresa. „Lieferant:
  Dehner Märkte" permanecia, e em propostas, concursos e encomendas o
  fornecedor consta muitas vezes exatamente assim. O mesmo se aplica a
  „Firma:", „Hersteller:", „Fabrikat:", „Arbeitgeber:" e aos seus
  equivalentes em mais oito idiomas, também quando a legenda está
  sozinha na sua linha e o nome por baixo.

  O que a seguir à legenda *não* é uma empresa permanece intocado:
  „Lieferant: siehe Anlage" não é ocultado – caso contrário, ficaria
  „Lieferant: [ORGA1]", afirmando um nome que nunca existiu. Legendas
  atrás das quais está igualmente muitas vezes uma pessoa („Kunde:",
  „Auftraggeber:") ficam propositadamente de fora.

- **Uma imagem colada pode agora também ser editada.** Na janela
  „Limpar imagem", ao lado de „Copiar resultado" há um botão *Editar no
  editor*: a imagem é limpa e depois aberta para ocultar
  adicionalmente, legendar e destacar – o mesmo caminho que uma captura
  de ecrã percorre.

- **Números a seguir à sua legenda são agora encontrados também quando
  identificam um parceiro comercial.** Até agora caíam números de
  cliente, contrato e pessoal; agora também número de devedor, de
  credor e de fornecedor, o número austríaco de entidade patronal, o
  registo ANKÖ e o número WEEE, EAR e EPR de um fabricante – em alemão
  como em inglês. Além disso, o Maskuro entende agora a grafia de
  cabeçalhos de proposta com espaço antes dos dois pontos
  („Kunden-Nr : K903944"). Números de artigo, encomenda, adjudicação,
  proposta e fatura continuam intocados: identificam o processo ou o
  produto, não a pessoa. Quem, mesmo assim, os quiser remover,
  guarda-os como padrão de pesquisa próprio.

- **Agora vê quanto tempo um ficheiro demorou.** Na linha concluída,
  consta a duração ao lado do idioma reconhecido („concluído · Alemão ·
  2,4 s"), no resumo a de toda a execução, no painel de indicadores a
  soma – e no relatório de verificação consta como campo próprio. Com
  vários ficheiros, a linha revela qual deles custou o tempo.

- **Escritas não suportadas pelo OCR do sistema podem ser lidas
  alternativamente com o ficheiro de idioma existente.** Até agora,
  valia: se o reconhecimento de texto nativo do sistema não dominar
  uma escrita (no Mac, por exemplo, devanágari), constava no resultado
  „Imagem(ns) NÃO foi(ram) verificada(s)", e as indicações na imagem
  permaneciam. Agora entra o reconhecimento de texto incluído, se
  existir o ficheiro de idioma adequado. Como uma imagem lida assim é
  menos segura do que uma verificada normalmente, consta isso no
  resultado: „lido pelo método alternativo – por favor verificar".
  Medido num estado intermédio histórico do teste em hindi: **dez
  indicações a mais encontradas e quatro falsos alarmes a menos**
  (64% → 73%). O valor final atual consta mais acima e não deve ser
  confundido com este.

- **O reconhecimento de texto pergunta pelo idioma correto.** Para
  todos os idiomas de documento além de alemão e inglês, era usado até
  agora o modelo de deteção inglês, mesmo quando o ficheiro de idioma
  adequado estava disponível. No Windows, isto afetava qualquer
  idioma – grego, japonês ou hindi eram lidos ali com o modelo
  inglês.

- **Um assistente de configuração no primeiríssimo arranque.** (Quem já
  usou o Maskuro não o recebe – „primeiro arranque" significa primeiro
  arranque, não primeiro arranque depois desta atualização.) Três
  perguntas em vez de seis imagens: o idioma dos seus documentos, se o
  texto em imagens é lido em conjunto, e como quer alcançar o Maskuro
  no dia a dia. No final, os três caminhos continuam disponíveis –
  documento de exercício, tour guiado ou o guia rápido ilustrado. Tudo
  pode ser saltado, e „Ajuda → Repetir configuração" traz-o de volta.

- **F1 abre o manual no capítulo correspondente.** Na janela principal,
  nas definições (ali consoante a página), na janela de verificação e
  na gestão de idiomas; na janela de correção via Shift+F1, porque F1
  ali sempre mostrou os atalhos de teclado. Até agora, a ajuda começava
  sempre no topo, com 25 capítulos.

- **Novo primeiro capítulo do manual: „Comece em três minutos".** Quatro
  passos, não é preciso mais para um documento – em todas as 18
  traduções.

- **Um tour guiado pela janela.** „Ajuda → Tour guiado pela janela" foca
  um elemento de controlo após outro e escreve uma frase ao lado – na
  janela principal oito estações, na janela de correção sete. Ao
  contrário do guia rápido ilustrado, explica a janela em que está
  sentado neste momento. Interromper a qualquer momento com Esc.

- **Um documento de exercício para experimentar sem risco.** Sob a área
  de depósito consta agora „Abrir documento de exercício" (também no
  menu Ajuda). Cria uma folha inventada – nome, morada, número de
  telefone, IBAN, número de segurança social – e na folha consta
  também o que pode fazer com ela e o que verá depois. Nenhuma palavra
  ali pertence a uma pessoa real; o primeiro documento que envia
  através do Maskuro não precisa por isso de ser real.

- **„Apenas verificar…" está agora ao lado de „Limpar".** Mostra onde
  estão dados pessoais – ficheiro, tipo e quantidade – sem alterar ou
  escrever nada. Quem tiver colocado um documento verifica assim antes
  de limpar. Até agora, este caminho só estava no menu Ficheiro, sob
  „Verificar pasta…", e percorria uma pasta inteira em vez dos
  ficheiros colocados.

- **Quando nada é encontrado, consta agora o que pode estar na causa.**
  Por exemplo: no ficheiro há imagens, mas „Verificar também texto em
  imagens" está desligado. Ou: o idioma definido não corresponde ao do
  documento. E, se não se verificar nenhum destes casos, o Maskuro
  diz-o também.

- **A janela de correção recebe-o na primeira vez com três frases:**
  clicar oculta uma palavra, arrastar oculta uma área, à direita ficam
  os valores substituídos. „Compreendido" retira o aviso de forma
  permanente; „Ajuda → Mostrar introdução de novo" traz-o de volta.

- **Clicar em palavras agora também em páginas digitalizadas.** Até
  agora, só se podia clicar em palavras onde o PDF trouxesse uma
  camada de texto – numa digitalização não era possível, e no mesmo
  documento podia variar de página para página. Tais páginas são agora
  lidas uma única vez pelo reconhecimento de texto; depois disso,
  clica-se em palavras como em qualquer outro lado. A barra de estado
  diz o que está a acontecer.

- **O painel de páginas volta a ser uma área.** Terminava a meio da
  sua coluna: barra de título cortada, ao lado uma faixa de outra cor,
  e a página atual só se reconhecia por uma caixa colorida atrás do seu
  número. Agora preenche a sua coluna, pode ser alargado, e a página
  atual é destacada como um bloco inteiro – com pré-visualização de
  página sem distorção dentro.

- **Os locais substituídos brilham em amarelo pálido.** Na
  pré-visualização de página, isto permite ver de relance onde algo foi
  substituído – a mesma cor que a lupa de comparação usa sobre o
  original. O contorno vermelho ao apontar com o rato mantém-se
  inalterado.

- **„Repor vista" na janela de correção** (menu „Vista"). Quem tiver
  deslocado, destacado ou fechado o painel de páginas ou a lista de
  resultados repõe assim tudo onde estava no primeiro arranque.

### Alterado

- **Os marcadores são mais curtos.** De `[SOZIALVERSICHERUNGSNR_1]`
  resulta `[SVNR1]`, de `[ORGANISATION_1]` um `[ORGA1]`, de `[EMAIL_1]`
  um `[MAIL1]`. O motivo não é estético: um marcador mais longo do que o
  valor que substitui alarga a linha e deixa de caber numa coluna de
  tabela estreita – ali ficava até agora uma barra preta, que já não diz
  a ninguém que ali esteve algo. Onde há uma abreviatura comum, esta é
  usada (`[BLZ1]`, `[KFZ1]`, `[IBAN1]`). Resultados de execuções
  anteriores continuam utilizáveis: a grafia antiga continua a ser
  reconhecida, e os ficheiros de atribuição de ontem funcionam sem
  alterações.

- **O ícone do programa tem agora o mesmo aspeto em todo o lado.** Na
  barra de menu do Mac aparecia até agora um escudo monocromático, que
  o próprio sistema colorava de preto ou branco; na barra de tarefas do
  Windows, um verde ou cinzento. Agora cada barra traz o mesmo escudo
  Maskuro azul. Como se vê se a área de transferência está a ser
  monitorizada permanece igualmente claro: se a monitorização estiver
  ativa, um ponto verde fica no escudo; se estiver parada, o mesmo
  escudo aparece pálido. Também nos tamanhos mais pequenos, ambas as
  barras de ocultação aparecem agora no escudo – até agora, a barra de
  tarefas mostrava ali apenas uma.

- **Os rostos são reconhecidos com um modelo cujas imagens de
  treino surgiram com consentimento.** É agora distribuído o
  MediaPipe BlazeFace (Apache-2.0); o detetor anterior permanece
  incorporado e comutável, mas deixa de ser incluído, porque a sua
  origem de treino não está esclarecida de forma conclusiva. Para a
  deteção, nada muda: em 324 retratos e 143 imagens sem rosto, a nova
  versão encontra o mesmo, com igualmente poucos erros, e precisa de um
  terço do tempo.

- **O OCR é a âncora de segurança para a garantia máxima de PDF.** A
  execução normal de PDF usa-o e gera a reconstrução mínima completa.
  Quem desligar o OCR expressamente recebe a via de objetos mais
  compatível; a interface, a mensagem final e o manual dizem agora
  expressamente que esta via não oferece a mesma arquitetura contra
  canais de PDF ocultos desconhecidos.

- **O bloqueio de venda passa agora a bloquear também o modelo YuNet
  até agora incluído.** A licença MIT do peso exato mantém-se
  documentada, mas não chega, quanto à cadeia de dados de treino
  publicamente visível via WIDER FACE, como liberação de produto
  conservadora. Antes da venda é necessário um esclarecimento por
  escrito ou a substituição por um modelo com uma cadeia comercial de
  dados e pesos comprovável.

- **Nomes de empresa e organização são agora removidos por defeito.**
  Até agora permaneciam, a menos que fossem expressamente solicitados.
  Isso era, para uma carta comercial, o padrão errado: quem partilha
  uma proposta não quer nela o nome do cliente. „Kranzbichler Handels
  GmbH", „Institut für Bauphysik" e semelhantes são por isso tratados
  como um nome. Quem precisar de outra forma desativa-o na janela; na
  linha de comandos, o interruptor chama-se agora
  `--ohne-organisationen`. O antigo `--mit-organisationen` continua a
  ser aceite e deixa de fazer efeito, para que scripts e atalhos
  existentes não quebrem. Datas e valores monetários continuam
  excluídos, sem alteração.

- **Ocultar tem agora três formas em vez de duas marcações.**
  „Palavras", „Linha inteira" e „Moldura livre" ficam como uma escolha
  lado a lado – vale sempre exatamente uma. Até agora, „Linhas de
  texto" e „Linha inteira" eram dois interruptores independentes que
  podiam estar ambos ativos, e a moldura livre não era sequer um
  botão, mas o estado desligado do primeiro. Os três ficam visíveis
  junto à sua ferramenta e ficam cinzentos enquanto outra ferramenta
  estiver selecionada.

### Melhorado

- **O primeiro documento fica pronto cerca de um segundo mais depressa.**
  Antes de a limpeza começar, o Maskuro determina o idioma do
  documento – e, para isso, carregava até agora as listas de palavras
  dos 48 idiomas por uma via que carregava muito mais do que as
  palavras. Isso era cerca de metade do tempo de espera até ao primeiro
  resultado. A própria deteção mantém-se inalterada: vê as mesmas
  palavras de antes, apenas mais depressa. Cada documento seguinte não
  era, de qualquer forma, afetado por isto.

- **Documentos com parágrafos muito longos são verificados mais
  depressa.** Num parágrafo sem quebra de linha, o Maskuro lia-o por
  inteiro de novo para cada local encontrado; agora basta uma vez.
  Quanto mais longo o parágrafo, maior a diferença – medido, cerca de
  um sétimo menos de tempo de cálculo. No resultado nada muda.

### Corrigido

- **Com uma empresa, desaparecia muitas vezes meio a frase junto.** Se um
  nome de empresa estivesse em texto corrido – „Information über die
  Gottwald GmbH & Co KG", „… (AGB) der Musterbetriebe GmbH" –, não era
  só o nome que era ocultado, mas tudo o que estava antes até ao
  início da frase. O texto tornava-se assim ilegível, e parecia que a
  ocultação tinha sido feita ao acaso. Nomes de empresa que trazem
  eles próprios um „für" ou „und" („Bank für Arbeit und Wirtschaft AG")
  mantêm-se, com isto, completos sem alteração.

- **Os nomes de empresa permaneciam em cabeçalhos de carta, apesar de
  removidos no texto.** Numa proposta, a sede da empresa constava ainda
  legível na imagem do cabeçalho de carta – o mesmo local que o Maskuro
  tinha ocultado no texto corrido; no texto pesquisável do resultado,
  constava mesmo, de forma invisível, ainda lá dentro. O que foi
  removido uma vez é agora removido também onde existe apenas como
  imagem. Isto também funciona com logótipos e marcas nominativas
  desenhadas como gráfico.

- **O macOS perguntava a cada arranque pela captura de ecrã**, mesmo
  quando a autorização já tinha sido concedida há muito. O aviso ao
  arrancar testava uma captura, e é precisamente isso que traz o
  diálogo do sistema ao ecrã. Agora, ao arrancar, só o próprio Maskuro
  pergunta, e apenas uma vez; o sistema só pergunta quando efetivamente
  captura um ecrã.

- **Termos técnicos comuns eram tomados por locais e empresas.**
  „Einspeisepunkt", „Flachdach", „Verteileranlage", „Meldersockel" e
  dezenas de palavras semelhantes desapareciam de propostas e cadernos
  de encargos. O Maskuro reconhece-os agora pela sua palavra-base: o
  que termina em „-anlage", „-punkt" ou „-kanal" é uma coisa. Nomes de
  local como Berlim, Melk ou Wieselburg não têm tal palavra-base e
  permanecem intocados – assim como moradas como „Der Graben" ou „Alter
  Markt".

- **Documentos em japonês, coreano, chinês, tailandês e guzerate podiam
  fazer o programa cair.** Se um documento nestes cinco idiomas
  contivesse um endereço de Internet sem „https://" antes, a limpeza
  interrompia-se com um erro interno – com a janela aberta, isso
  também perdia o resto do trabalho. Todos os quarenta e oito idiomas
  de documento selecionáveis funcionam agora até ao fim; se faltar o
  dicionário de frequência para um idioma, a indicação permanece, em
  caso de dúvida, em vez de desaparecer.

- **As legendas de campo só protegiam em alemão e inglês.**
  „Reference" permanecia, o italiano „Riferimento" e o português
  „Referência" eram removidos como indicação de local – o mesmo nome
  de campo, a mesma linha, resultado diferente. Quem não trabalhasse em
  inglês estava, com isto, em desvantagem. O Maskuro conhece agora, em
  todos os onze idiomas mantidos, os mesmos nomes de campo.

- **„Recuperar original" recuperava demasiado em páginas
  digitalizadas.** Uma moldura sobre uma linha ocultada de um bloco de
  morada expunha de novo o **bloco inteiro** – e a página ficava
  rasgada: restos de barra permaneciam, dos quais sobressaíam finais de
  palavra isolados. A causa era que barras umas sob as outras, numa
  página rasterizada, se tocam e por isso valiam como uma única área.
  Agora é recuperada exatamente a linha para a qual a moldura aponta;
  as linhas vizinhas permanecem ocultadas, e a barra da linha atingida
  desaparece por completo.

- **Indicações de quantidade em listas de posição eram tomadas por
  moradas.** Numa linha como „1.4  Kabelgraben  100,00  m", „Kabelgraben
  100" era substituído como rua com número de porta. Tais linhas
  permanecem agora; moradas reais – também „Hauptplatz 1, 3250
  Wieselburg" – continuam reconhecidas sem alteração.

- **Antes de um nome de empresa, desaparecia meia frase.** De „Vertrag
  zwischen der Firma Gottwald GmbH & Co KG und dem Auftraggeber."
  resultava „[ORGANISATION_1] und dem Auftraggeber." – o início da
  frase desaparecia, e com ele a indicação do assunto. Agora cai apenas
  o próprio nome da empresa. Onde a palavra genérica pertence ao nome
  („Deutsche Bank AG", „Universität Wien"), tudo permanece como até
  agora.

- **Numa ata, permaneciam intervenientes cujo nome é também uma
  profissão.** „Bauer:", „Koch:", „Weber:" antes de uma intervenção
  eram omitidos, „Gruber:" ao lado não – o Maskuro precisava, até
  agora, de pelo menos um nome reconhecido no documento para sequer
  ler as linhas como intervenções. Se o documento tiver um título como
  „Ergebnisprotokoll" ou „Niederschrift", isso basta agora. Linhas de
  aviso („Achtung: …", „Hinweis: …") permanecem intocadas.

- **Uma legenda de campo desaparecia junto com o seu valor.** De
  „Projekt: Sanierung und Erweiterung Gemeindezentrum" resultava um
  único marcador – também a palavra „Projekt:" desaparecia, e com ela a
  indicação do que ali tinha estado. As legendas permanecem agora. Onde
  uma legenda pertence à indicação e carrega o seu significado
  („Durchwahl 214"), nada muda.

- **A deteção máxima não eliminava termos técnicos comuns.**
  „Flachdach", „Einspeisepunkt", „Elektrotechnik" e termos técnicos
  semelhantes eram substituídos como local ou empresa mesmo com o
  nível de IA ativado – a IA nunca recebia precisamente estes
  resultados para avaliação. Agora também os verifica: num corpus de
  textos de concurso e contrato, isto elimina todos os 27 erros, sem
  que nenhuma indicação real permaneça. Nomes, empresas e locais
  continuam reconhecidos sem alteração.

- **Palavras genéricas para tipos de instituição eram tomadas por
  organizações.** Num texto de contrato, desapareciam „Hochschulen und
  Universitäten", „Staatliche und private Schulen", „Akademische
  Lehrkrankenhäuser", „Bildungseinrichtung" e „Zulieferfirmen" –
  palavras que não designam um local específico, mas um tipo de local.
  Permanecem agora. Se estiver um nome próprio antes („EU-Kommission"),
  continua a ser substituído, e nomes de empresa não são de todo
  abrangidos pela regra.

- **Nomes em listas só caíam quando eram comuns.** Numa lista de
  participantes ou de presenças sob um cabeçalho de coluna „Name",
  „Anna Huber" e „Thomas Müller" eram removidos, mas „Wójcik
  Aleksandra" ou „Kücükgöl Sinan" não – a mesma linha, a mesma
  estrutura. Quem tivesse um nome mais raro estava, com isto, pior
  protegido. Agora decide o cabeçalho de coluna: o que consta sob
  „Name" é um nome. Uma lista de posições com cabeçalho de coluna
  técnico permanece intocada.

- **Um número de telefone a seguir a „Durchwahl" era cortado a
  meio.** De „Durchwahl 0732 771190" resultava „[DURCHWAHL_1] 771190" –
  a segunda metade do número permanecia legível. Agora cai o número
  completo por inteiro, e a legenda permanece. Um ramal real
  („Durchwahl 214") continua a ser substituído com a legenda, sem
  alteração.

- **Alguns PDFs deixaram de poder ser limpos de todo.** Se um perfil de
  cor ou os metadados numa imagem não pudessem ser comprovadamente
  removidos, a execução interrompia-se sem resultado – eram afetados
  documentos comerciais comuns, como páginas de condições gerais,
  cadernos de encargos e concursos. Tais ficheiros são agora limpos, e
  um aviso indica os locais que ficaram por resolver: podem conter uma
  identificação de dispositivo, de fabricante ou de captura. O
  original mantém-se, como sempre, inalterado.

- **Cargos contratuais eram tomados por pessoas.** „Bieter",
  „Verbraucher", „Mieter", „Käufer", „Auftraggebers" e cerca de mais
  quarenta palavras de cargo eram substituídos onde estivessem sem
  artigo – em títulos de contrato, colunas de tabela e linhas de
  assinatura. Um texto de contrato sem um único dado pessoal ficava,
  por vezes, ilegível com isto. Estas palavras permanecem agora. Se ao
  lado estiver uma indicação de pessoa – uma saudação, um primeiro
  nome, uma palavra de campo como „Ansprechpartner" –, continua a ser
  substituído: „Herr Bieter" e „Frau Käufer" são nomes. Apelidos
  comuns que são simultaneamente profissões (Bauer, Richter, Koch) não
  são de todo abrangidos pela regra.

- **Uma rua escrita de forma abreviada era ignorada quando o número de
  porta ficava colado ao ponto.** „Schlesischestr.31" não valia como
  morada – e, como o código postal ao lado retira a sua validade do
  resultado de morada, também ele permanecia. No resultado, a morada
  composta por rua e código postal podia ser reconstruída, e isso
  apenas em algumas páginas do mesmo documento. Ambos caem agora em
  conjunto. Designações técnicas com número anexado („Kabelrinne200")
  permanecem intocadas.

- **Uma morada em duas linhas era unida num único marcador.** Se num
  bloco de morada o código postal estivesse acima da rua, o Maskuro
  unia ambas as linhas num único resultado: no resultado, a quebra de
  linha desaparecia, e o código postal permanecia legível antes disso.
  Agora cada linha é encontrada e substituída por si; a formatação de
  texto mantém-se. A mesma causa arrastava, por vezes, também o apelido
  da linha acima para dentro da morada.

- **A via máxima de PDF deixa de assumir objetos do original.** Com o
  reconhecimento de texto ativado, o Maskuro reconstrói cada página por
  completo a partir da imagem PDFium visível. No novo ficheiro mínimo
  entram apenas esta página de imagem e uma camada de pesquisa
  recém-gerada, limitada ao texto OCR – não a árvore de objetos
  alheia, com comentários, anexos, ações, camadas, metadados, perfis
  de cor ou chaves privadas. Isto aplica-se também a conteúdos em
  aparências de anotação, padrões, tipos de letra Type 3, objetos de
  formulário e máscaras suaves. O ficheiro de origem mantém-se
  intocado.

- **Rostos e códigos em gráficos de PDF aninhados eram ignorados.**
  Ambos os detetores veem agora, adicionalmente, a imagem de página
  renderizada completa. Com isso, também retratos e códigos QR/de
  barras em anotações, padrões, glifos Type 3 e máscaras de
  transparência chegam aos detetores; áreas reconhecidas são – se
  ativado – tornadas irreconhecíveis antes da reconstrução mínima. A
  própria deteção continua falível.

- **A falta de um motor de OCR terminava, em PDFs, com um erro
  interno.** A execução máxima interrompe-se agora de forma controlada
  e sem ficheiro de destino, em vez de gerar um ficheiro incompleto ou
  não verificado.

- **Vários valores reais de contacto e comerciais escapavam, enquanto
  texto comum era substituído.** Campos de nome sobre quebras de linha,
  nomes de banco e empresa, formas jurídicas, números de identificação
  legendados, datas de nascimento, bem como limites de telefone, URL e
  IBAN, são agora verificados de forma mais rigorosa. Ao mesmo tempo,
  permanecem mais vezes intocados países em texto comum, palavras de
  cargo e genéricas, códigos de artigo/norma, colunas de números e
  abreviaturas comuns.

- **Linhas de OCR mistas e rodadas eram lidas incorretamente.** Palavras
  verticais incertas são agora relidas localmente na posição correta;
  valores latinos técnicos em texto não latino recebem um testemunho
  independente em inglês. Um único dígito isolado incerto só é
  corrigido quando duas sequências de dígitos próximas coincidirem.
  Formas jurídicas polacas na forma de OCR „sp. z 0.0." são lidas, em
  contexto fechado, como „sp. z o.o.".

- **A medição de imagem podia ignorar restos de valor parcialmente
  visíveis.** Verifica agora recortes locais sobrepostos, distingue
  letra de marcador branca sobre uma barra preta de glifos originais e
  transpõe caixas de imagem bruta também para PDFs mínimos rodados e
  recém-renderizados. O corpus principal sintético fixo atinge, com
  isso, 1.392/1.392 indicações de referência removidas, com 0 falsos
  alarmes e 0 erros de processamento. É uma comprovação de corpus, não
  uma promessa geral de 100%.

- **Deixam de ser oferecidos modelos de linguagem não comerciais.** As
  seis variantes spaCy italiana e grega sob CC BY-NC-SA 3.0 foram
  removidas do catálogo, do descarregamento e da via de carregamento;
  também pastas de modelo já existentes são ignoradas. Ambos os idiomas
  usam agora, em vez disso, o modelo multilíngue licenciado sob MIT.

- **O nome sob „Ansprechpartner" era removido apenas a meio.** Se a
  legenda estiver sozinha numa linha e por baixo „Nachname Vorname", o
  primeiro nome permanecia sempre que fosse simultaneamente uma palavra
  comum – de „Mayer Roman" resultava „[NAME_1] Roman". Tais linhas são
  agora tomadas por inteiro. Um departamento no mesmo local
  („Technischer Innendienst") continua intocado. Corrigido também de
  passagem: „Ansprechpartner" não contava de todo como campo de nome,
  apesar de „Kontaktperson" o fazer desde sempre.

- **O nome de empresa sem forma jurídica permanecia quando havia uma
  palavra de setor pelo meio.** „Kranzbichler Handels GmbH" era
  removido, o „Kranzbichler" isolado três parágrafos depois não – com
  „Kranzbichler GmbH", em contrapartida, sim. Agora ambos funcionam.
  Palavras comuns ficam excluídas disto: „Deutsche Bank AG" não faz de
  „deutsche" no texto uma empresa.

- **O mesmo valor chamava-se, no mesmo documento, uma vez nome e outra
  vez local.** „Anna Musterfrau … Musterfrau" resultava em „[NAME_1]" e
  „[ORT_1]" – no segundo local falta o primeiro nome, e sem ele
  tornava-se um local. Ambos eram removidos, mas lia-se como duas
  coisas diferentes. Um valor mantém agora a designação da sua primeira
  ocorrência.

- **Datas deixaram de ser removidas.** Uma data composta apenas por
  dígitos („01.03.2026") deixou de passar, desde a última versão, uma
  verificação pensada para nomes, permanecendo no documento – também no
  modo „deslocar", e sem linha no relatório de verificação. Era
  afetado apenas quem tivesse ativado expressamente indicações de
  data.

- **Países e continentes deixam de ser ocultados.** „A entrega vai para
  os Estados Unidos", „Fraqueza de mercado na Ásia", „a norma vale na
  Roménia" – tais indicações nada dizem sobre uma pessoa e permanecem
  agora. Se, pelo contrário, o nome do país pertencer a uma morada ou
  estiver a seguir a uma legenda como „Residência" ou „Local de
  nascimento", continua a ser removido. **As cidades não são
  afetadas** – „Estou agora em Bilbao" continua a ser uma indicação
  sobre uma pessoa e continua a ser ocultada.

- **Palavras abreviadas tornavam-se endereços web.** Se no texto
  constar „bzw. deutsche" ou „incl. der", alguns PDFs fornecem o ponto
  sem espaço – daí resultava „bzw.de" ou „incl.de", um endereço válido
  com terminação de país, e era removido. Tais pares de palavras
  permanecem agora. Endereços reais não são afetados, também sem
  „www." antes.

- **Colunas de números de balanços eram ocultadas como números de
  telefone.** Em relatórios anuais e tabelas de preços, o ano anterior
  e o ano corrente ficam lado a lado – „64.518  65.133". Isso valia
  como um número de telefone e era removido, assim como intervalos
  numéricos como „12200-23200" e uma data seguida de um número. Tais
  números permanecem agora. Inversamente, um número de telefone real é
  reconhecido de forma mais segura: as legendas „Telefon", „Fax",
  „Mobil", „Durchwahl" e os seus equivalentes nos outros idiomas de
  interface contam agora também – até agora, o programa só reconhecia
  ali as palavras inglesas.

- **Nomes numa tabela numerada permaneciam.** Uma lista de participantes
  ou tabela de pessoal na forma habitual – cabeçalho de coluna, por
  baixo „1.1 Auersperg Bernhard Montage 03.03.2026" – não era limpa de
  todo: tais linhas pareciam a lista de posições de uma proposta, onde
  os termos técnicos devem permanecer. Se o cabeçalho de coluna trouxer
  uma legenda de pessoa („Name", „Nachname", „Surname" …), as linhas
  por baixo valem agora como nomes. Listas de posições continuam
  poupadas sem alteração – também quando no cabeçalho de carta consta
  „Sachbearbeiter:".

- **De um nome resultavam, por vezes, dois marcadores lado a lado.**
  Quando um apelido também constava sozinho no documento, o
  processamento posterior substituía, num local como „Anna Musterfrau
  GmbH", primeiro o apelido e depois o primeiro nome – no resultado,
  isso parecia duas pessoas diferentes. Agora prevalece o nome conhecido
  mais longo.

- **Valores inventados não constavam em nenhuma atribuição.** Quem
  tivesse escolhido „Inventar valores" recebia um resultado em que
  „Anna Musterfrau" se tinha tornado „Greta Mayrhofer" – na atribuição
  não constava nada disto, assim que no mesmo documento ocorresse
  também uma única substituição anónima. Com isso, nenhum valor
  inventado podia ser recuperado, e o ficheiro de atribuição omitia a
  substituição. O mais delicado era o terceiro ponto: quem lê o
  resultado vê um nome credível e não tem indício de que é inventado.
  Agora, cada substituição consta na atribuição.

- **A atribuição chamava „substituído" ao ocultado.** Um e-mail partilha
  uma atribuição com os seus anexos, e o anexo pode ser ocultado
  enquanto o texto do e-mail traz um marcador. Na atribuição constava
  então o mesmo para os três locais – „substituído" –, e a recuperação
  procurava no anexo um marcador que ali não existia: a barra
  permanecia. Agora consta, por local encontrado, o que ali realmente
  aconteceu, e ambos os anexos voltam.

- **Valores que só constavam numa imagem não podiam ser recuperados.**
  No painel de resultados, constavam duplicados – uma vez como
  marcador que não existia em lado nenhum do documento („O marcador não
  foi encontrado no documento"), uma vez como local ocultado. A
  primeira linha era pura contabilidade e desapareceu.

- **Valores ocultados só podiam ser recuperados uma vez.** Se o mesmo
  valor estiver em vários locais, um clique recupera todos – mas as
  restantes linhas permaneciam no painel de resultados, e o clique
  seguinte comunicava „Não inequívoco". Desaparecem agora também.

- **As recuperações faltavam no registo de verificação quando o modo de
  aprendizagem estava desligado.** Quem restaurasse, na janela de
  correção, um valor recuperado, não voltava a encontrar o processo no
  registo de verificação assim que as perguntas de aprendizagem
  estivessem desativadas – o comprovativo dependia de um interruptor
  que só se refere às sugestões de regra. Com o registo de verificação
  ativado, pergunta-se agora pelo motivo independentemente disso, e a
  linha é escrita.

- **Ficheiros arrastados para dentro permaneciam por limpar – e nem
  sequer eram comunicados.** Quem arrasta um ficheiro para dentro de um
  documento, em vez de o enviar como anexo, faz com que o Word ou o
  PowerPoint o guarde por inteiro dentro do documento. Ficava depois
  inalterado no resultado, incluindo o seu nome de ficheiro original e
  o caminho de armazenamento – e estes, na prática, trazem muitas vezes
  eles próprios um nome. Tais ficheiros são agora limpos como o
  resto do documento.

- **E onde isso não é possível, o Maskuro diz-o.** Se num objeto
  incorporado houver um formato antigo (Word 97, Excel 97) para o qual
  não existe limpeza, aparece agora uma mensagem ATENÇÃO com o nome do
  ficheiro. Até agora era entregue em silêncio, sem alteração.

- **Palavras rasgadas e siglas eram tomadas por nomes.** Se uma palavra
  num PDF estiver dividida no final da linha, resulta, ao ler alguns
  ficheiros, um fragmento – „Jahresent… gelts", „Gewerbli…". Tais
  fragmentos, palavras coladas („TürverschlussmitV") e siglas nuas
  („JY", „FFB") eram ocultados como se fossem nomes. Permanecem agora.
  Um nome com o mesmo dano de divisão continua a ser ocultado enquanto
  houver uma saudação junto – e nomes que já por si trazem uma
  maiúscula dentro da palavra (McKenzie, MacDonald, LeBlanc) não são,
  de qualquer forma, afetados por isto.

- **Indicações de medida e meses valiam como morada.** Em documentação
  técnica, „2000 Lux", „1200 Mbit", „1500 Watt", „5308 Platz" e „2022
  Mrz" eram ocultados – quatro dígitos e uma palavra em maiúsculas
  pareciam um código postal com localidade. Um código postal só conta
  agora quando também houver um sinal de morada: uma indicação de
  país, uma legenda de campo, o início de linha, uma rua na linha
  acima ou um local que também a deteção de idioma vê ali. Em cinco
  cadernos de encargos, isto elimina 14 ocultações erradas, sem que
  nenhuma morada real permaneça.

- **A deteção mais rigorosa substituía demasiado.** O nível ativável
  „deteção mais rigorosa" tomou, em documentos comerciais alemães,
  termos técnicos por nomes e locais – „Photovoltaikanlage",
  „Einspeisepunkt", „Flachdach", „Personaleingang" – e ocultou
  designações de empresa em listas de posição corridas. A causa era
  uma proteção: os seus resultados eram excluídos das verificações que
  reconhecem uma linha de posição ou de diretório. Esta proteção só se
  aplica agora a nomes de várias partes, para os quais o nível existe –
  „Anna Huber" numa linha de diretório continua assim reconhecido, uma
  única palavra comum numa linha de posição deixa de ser afetada. Numa
  proposta técnica, isto reduz para metade as ocultações erradas do
  nível, sem que se perca nenhum nome.

- **Os diagramas traziam os seus dados de origem completos –
  não verificados.** Quem insere um gráfico no Word ou no PowerPoint faz
  com que o programa coloque a tabela a partir da qual foi calculado
  como ficheiro próprio dentro do documento. Visíveis são apenas os
  poucos números no gráfico; na tabela está a lista inteira, incluindo
  as linhas que nem sequer aparecem no gráfico. Até agora, esta tabela
  era entregue sem alteração. Agora é limpa em conjunto, com os mesmos
  marcadores que o resto do documento.

- **O mesmo para objetos incorporados em ficheiros OpenDocument** (ODT,
  ODS, ODP): um gráfico ou uma tabela inseridos permaneciam intocados.

- **Documentos Word: notas de rodapé e notas finais não eram
  limpas.** O seu texto permanecia completo no resultado – também
  nomes, moradas e números de conta. Era afetado qualquer documento
  Word com uma nota de rodapé ou final. Da mesma forma, permanecia
  intocado um bloco de texto automático que viaja invisivelmente com o
  documento.

- **Word: indicações em listas de seleção, comentários e descrições de
  imagem.** As entradas de um campo de seleção (visível só ao expandir),
  o autor de um comentário, a descrição de um desenho e o endereço
  atrás de um comando de referência permaneciam no resultado.

- **Excel: a tabela dinâmica trazia os dados de origem uma segunda
  vez.** Uma pasta de trabalho com uma tabela dinâmica guarda nela uma
  cópia completa das linhas avaliadas – invisível, mas no ficheiro.
  Esta cópia permanecia até agora inalterada, mesmo quando na própria
  folha tudo já estava substituído. Era afetada qualquer avaliação
  distribuída com uma tabela dinâmica.

- **Excel: comentários de conversa e os seus autores.** O texto de um
  comentário do tipo mais recente e o diretório dos comentadores – nome
  de apresentação e identificação de início de sessão, em empresas
  geralmente o endereço de e-mail – permaneciam no resultado. O mesmo
  diretório em documentos Word também.

- **Propriedades de documento definidas pelo utilizador no Word e no
  Excel.** Campos como „Mandant" ou „Aktenzeichen", que um escritório de
  advogados junta aos seus modelos, não eram até agora limpos. Não são
  visíveis em nenhuma vista e viajam, mesmo assim, com cada cópia.

- **Folhas de cálculo (ODS): a lista de seleção de uma célula.** Como
  no Excel desde a versão anterior, é agora também limpo, em tabelas
  OpenDocument, o que aparece ao expandir uma célula. Referências a
  outras células permanecem intocadas, para que a lista continue a
  funcionar.

Todos estes locais podem ser recuperados como habitualmente através da
atribuição.

- **Mensagens do Outlook: um ficheiro danificado terminava a limpeza
  abruptamente.** Certos ficheiros `.msg` danificados levavam a uma
  interrupção em vez de a uma mensagem; agora são lidos na medida do
  possível.

- **O ficheiro de atribuição só é agora legível para si.** Contém os
  dados originais em texto simples e ficava, até agora, com as
  permissões habituais ao lado do resultado – num depósito partilhado,
  qualquer um o podia abrir. No resultado limpo propriamente dito nada
  muda; este destina-se, de facto, a ser partilhado.

- **Os modelos de idioma carregados posteriormente são agora
  verificados com mais rigor antes de serem descompactados.** Um
  pacote manipulado – por exemplo, de uma partilha empresarial que
  serve vários postos de trabalho – podia, ao descompactar, colocar
  ficheiros fora da pasta prevista. No carregamento habitual, nada
  muda.

- **Capturar uma imagem de ecrã – e é logo limpa.** Com
  `Ctrl+Shift+B`, através de „Ficheiro → Capturar imagem de ecrã…" ou
  através do ícone na barra de tarefas, arrasta uma moldura sobre o
  ecrã. O que está dentro segue depois o mesmo caminho que qualquer
  outro ficheiro: o reconhecimento de texto lê o texto do ecrã, nomes,
  moradas, números de telefone e endereços de e-mail são ocultados, e
  depois a imagem fica aberta no editor, onde pode ocultar
  adicionalmente com uma moldura o que foi omitido. A imagem limpa
  vai para o ambiente de trabalho (ou para a pasta de saída definida);
  a captura **bruta** não é guardada em lado nenhum e é apagada ao
  sair. O reconhecimento de texto é ativado para esta execução, mesmo
  que esteja normalmente desligado – numa imagem, sem ele não haveria
  nada a encontrar. No Mac, o sistema pergunta na primeira vez pela
  autorização „Gravação de ecrã".

- **Agora é possível desenhar sobre imagens: retângulo, elipse, seta,
  texto e marcas de passo numeradas.** Em seis cores e três espessuras
  de traço, selecionáveis com as teclas 1 a 5. Destina-se a capturas de
  ecrã e instruções: mostrar o que importa, sem abrir para isso um
  segundo programa. Desfazer e ajustar pelas alças aplicam-se como a
  qualquer barra – uma anotação pode assim ser deslocada e ampliada
  depois de definida.
  **Desenhar não é expressamente ocultar.** Um retângulo desenhado é
  uma moldura, não uma barra: o que está por baixo permanece legível e
  segue com o ficheiro. Para remover indicações continuam a existir
  „Ocultar" e „Pixelizar"; as ferramentas de desenho ficam por isso
  numa linha própria da barra de ferramentas, e a linha de indicação
  diz-o enquanto uma delas estiver selecionada.

- **A imagem editada vai para a área de transferência com um clique.**
  „Copiar imagem" no editor (ou `Ctrl+C`) coloca-a como está – colar
  basta para a levar para uma mensagem ou e-mail. Com isso, o caminho
  desde o toque na tecla até ao chat tem quatro passos e não precisa de
  nenhuma pasta.

- **A isto junta-se um marcador de texto, sombra e gradientes.**
  „Destacar" colore uma área sem a cobrir – o conteúdo por baixo
  permanece legível, e é exatamente isso que o distingue da barra.
  „Sombra" destaca uma anotação de um fundo agitado, „Gradiente" deixa
  a cor esbater-se na direção do arrasto; ambos aplicam-se às seis
  ferramentas de desenho.

- **Corrigido antes de afetar alguém:** a nova linha de ferramentas
  teria aparecido quase vazia para quem já tivesse usado o Maskuro – a
  divisão de janela memorizada era de antes e não lhe teria deixado
  espaço. Uma divisão desatualizada é agora descartada; a janela do
  editor fica então, uma única vez, na sua divisão base.

- **A própria captura de ecrã pode ser desligada.** Quem estiver
  habituado ao Greenshot, ShareX ou à Ferramenta de Recorte desliga, em
  „Definições → Programa", „Capturar imagem de ecrã com o Maskuro". O
  Maskuro nem sequer regista então o atalho de teclado – fica para a
  sua ferramenta –, e a alteração aplica-se de imediato, sem
  reiniciar. Uma imagem assim capturada continua a poder ser limpa:
  Ctrl+V traz-a da área de transferência para a janela.

## 0.10.37-alpha.20260821 – 21 de agosto de 2026

### Novo

- **Ao anonimizar, cada local encontrado passa a ter o seu próprio
  número.** Até agora, todas as pessoas chamavam-se `[NAME]`, todos os
  locais `[ORT]` – com isso, deixava de ser possível dizer a que local
  pertencia que valor, e não havia nada a recuperar. Agora os números
  continuam a contar por ocorrência: o mesmo nome consta em três locais
  como `[NAME_1]`, `[NAME_3]` e `[NAME_7]`. No documento, continua a não
  ser possível reconhecer quais os locais que pertencem uns aos outros –
  mas, com o ficheiro de atribuição, cada um pode ser recuperado
  individualmente. O ficheiro de atribuição volta por isso a ser
  selecionável também ao anonimizar; guarde-o separado do resultado.
- **Meses, dias da semana, moedas, unidades e formas jurídicas de
  empresa em todos os 48 idiomas de documento deixam de valer como nomes
  ou locais.** Os nomes de calendário e de unidade vêm do Unicode CLDR
  (gerados, não escritos), as formas jurídicas do direito societário dos
  países – também com várias palavras („sp. z o.o.", „Pty Ltd") e antes
  do nome („株式会社"). Onde um nome de mês é simultaneamente um primeiro
  nome (Julho, Augusto, Maio), decide a estrutura: com dia ou ano ao
  lado, é uma data; caso contrário, um nome. A isto juntam-se saudações e
  títulos, fórmulas de saudação completas, tipos de documento e
  palavras-base de rua para 28 idiomas com modelo de linguagem próprio,
  siglas legais (RGPD, código fiscal, § 6 n.º 1) bem como nomes de
  idioma como valor de campo („Idioma: Alemão"). As listas estão em
  „Ajuda → Listas de palavras…".
- **Índia: morada e código PIN são reconhecidos** – „15 गांधी मार्ग",
  „नई दिल्ली 110001", bem como „15 Gandhi Marg, Nova Deli 110001". O
  pacote de país Índia só conhecia até agora números de identificação;
  em documentos em hindi, as moradas permaneciam por isso.
- **Cada ficheiro do Office limpo é reaberto como pacote antes da
  entrega.** Um extrato de texto não deteta quando o Word, o Excel ou o
  LibreOffice recusariam o ficheiro (entrada duplicada, XML rasgado,
  uma parte em falta). E conta-se contra o original o que uma limpeza
  nunca pode alterar: páginas de um PDF, folhas, linhas e células de uma
  tabela, diapositivos de uma apresentação. Se a prova falhar, aparece
  um aviso ATENÇÃO no resultado e no relatório de verificação – o
  original permanece inalterado.
- **Também o automatismo oculta o campo inteiro.** No modo de ocultação,
  a barra cobre, em linhas curtas – bloco de morada, célula de tabela,
  dados de cabeçalho –, a linha inteira em vez de apenas o valor
  encontrado: uma barra do comprimento da palavra revela quão longa era
  a palavra. Legendas e montantes ao lado permanecem, e linhas de texto
  corrido (mais longas do que metade da largura de texto) continuam a
  ser ocultadas exatamente à palavra, para que um nome a meio da frase
  não enegreça a frase inteira.
- **O recuperado volta a parecer-se com o original.** „Recuperar
  original" e „Anular substituição" no editor de PDF escrevem agora a
  área exatamente a partir do ficheiro de origem – o mesmo tipo de
  letra, o mesmo tamanho, a mesma cor e posição, numa digitalização os
  mesmos pixels. Até agora, o texto era reinserido num tipo de letra
  substituto e tinha um aspeto reconhecidamente reconstruído. A barra de
  uma ocultação anterior desaparece agora por completo, em vez de ser
  pintada de branco – um fundo de célula colorido numa tabela
  mantém-se. Isto aplica-se também em páginas rodadas, a texto de
  objetos de formulário incorporados e a **campos de formulário
  preenchidos**: na cópia de trabalho rasterizada para o efeito, volta o
  recorte da página original recém-renderizada – mesmo onde nenhuma
  camada de texto conhece o valor do campo. Também **imagens
  substituídas** no PDF voltam assim – pixelizadas, desfocadas ou
  totalmente removidas, por inteiro ou apenas o recorte arrastado. Só
  onde o ficheiro de origem já não está ao lado do resultado é que se
  mantém o caminho anterior.
- **Valores ocultados e removidos sem substituto também podem ser
  recuperados em Word, Excel, PowerPoint e OpenDocument.** Até agora, a
  recuperação precisava ali de um marcador no texto – uma barra ou um
  vazio não tinham caminho de volta. Agora o painel de resultados
  oferece as linhas „ocultado" e „removido" assim que o ficheiro de
  origem intocado está ao lado do resultado: o Maskuro compara o
  resultado com o original e reinsere o valor no local da barra ou do
  vazio – incluindo formatação; um percurso dividido volta a ficar
  inteiro. Aplica-se igualmente a texto, HTML, e-mail e aos anexos de
  Office de um e-mail; se o texto do e-mail tiver um marcador e o anexo
  uma barra, ambos são recuperados de uma só vez.
- **Também os anexos de PDF de um e-mail ou de uma mensagem do Outlook
  podem ser recuperados** – marcadores (numerados e anónimos), barras e
  conteúdo removido sem substituto. Sem camada de texto, o local vem do
  anexo original; o valor volta letra a letra, na ordem de leitura do
  original.
- **Valores mascarados podem ser recuperados** – no PDF e na vista de
  texto. Uma máscara („**** **** **** **** 3201") nunca é inequívoca,
  dois números têm a mesma; por isso, a recuperação nunca segue o
  caminho literal, perguntando antes ao original que valor estava
  naquele local. Até agora, estas linhas não eram sequer operáveis no
  painel de resultados.
- **Imagens incorporadas em Word, Excel, PowerPoint e OpenDocument podem
  ser recuperadas.** Um valor ocultado numa imagem volta através da sua
  linha de painel – o Maskuro lê a imagem original e recupera
  exatamente esse local; uma imagem desfocada, removida ou tratada com
  rostos e códigos é recuperada por inteiro pela nova entrada
  „Recuperar imagens incorporadas" no menu Editar, a partir do
  ficheiro de origem – também através dos anexos de Office de um e-mail
  ou de uma mensagem do Outlook. Uma imagem que esteja ela própria como
  anexo e tenha sido ocultada por reconhecimento de texto também volta
  através da sua linha de painel.
- **Valores inventados podem ser recuperados na vista de texto.** Até
  agora, o painel indicava ali „Não inequívoco". Agora a recuperação
  procura o valor no original e exige, no mesmo local do resultado,
  exatamente o substituto inventado – um nome inventado nunca é
  substituído literalmente em todo o lado, pois poderia estar
  verdadeiramente em algum sítio.
- **A recuperação em Word, Excel, PowerPoint e OpenDocument mantém a
  formatação do original.** Se um valor se estendesse por várias
  passagens – „Anna" normal, „Musterfrau" a negrito e vermelho –, voltava
  até agora inteiro na primeira passagem, perdendo o negrito e a cor.
  Agora os carateres voltam a distribuir-se como no original; um
  parágrafo do Word fica depois byte a byte idêntico ao original. O
  mesmo se aplica a páginas HTML, à parte HTML de um e-mail e ao corpo
  HTML de uma mensagem do Outlook (.msg) – no e-mail mantém-se também o
  doctype, que a limpeza removia até agora em silêncio.
- **Os ficheiros de texto mantêm a sua codificação.** A limpeza e a
  recuperação escrevem agora `.txt`, `.md` e `.csv` na codificação em
  que foram fornecidos – UTF-8 com e sem BOM, UTF-16, Windows-1252. Até
  agora, um ficheiro Windows-1252 tornava-se sempre UTF-8, e um ficheiro
  UTF-16 voltava danificado, mesmo quando não havia nada a substituir.
- **As imagens recuperadas mantêm o seu modo de cor.** Uma digitalização
  em escala de cinzentos volta como escala de cinzentos, em vez de um
  ficheiro RGB três vezes maior; uma paleta como paleta, preto e branco
  como preto e branco – na imagem inteira, com os mesmos valores do
  original. Aplica-se a ficheiros de imagem e a imagens em PDFs. CMYK e
  16 bits mantêm-se RGB, porque o resultado PNG não consegue suportar
  nenhum dos dois.
- **Uma moldura na imagem recupera toda a edição que toca.** Rostos
  pixelizados têm uma margem à volta da caixa detetada; quem arrastasse
  a moldura só sobre o rosto ficava com um anel pixelizado. Agora a
  moldura cresce até à alteração contígua em relação ao original – basta
  uma moldura sobre a zona dos olhos. Barras separadas ao lado
  permanecem; numa fotografia totalmente removida ou totalmente
  desfocada, continua a valer a moldura arrastada. Aplica-se a
  ficheiros de imagem e imagens em PDFs.
- **Barras de ocultação em toda a linha.** No modo de linha do editor, a
  barra corre agora da primeira à última palavra da linha, deixando de
  cobrir apenas a palavra atingida – uma barra do comprimento da palavra
  revela quão longa era a palavra, e de seis carateres antes de um
  código postal pode adivinhar-se um nome de local. Legendas, montantes
  e colunas de tabela ao lado do valor permanecem – a barra cobre o
  campo, não a linha da fatura. O novo interruptor „Linha inteira" ao
  lado de „Linhas de texto" volta a colocar exato à palavra, quando as
  palavras vizinhas devem permanecer; a escolha é memorizada.

### Corrigido

- **As imagens em páginas HTML e e-mails ficavam por verificar – o nome
  no logótipo continuava legível depois da limpeza.** Uma imagem
  incorporada na página (endereço `data:`) não era tocada de todo, só o
  seu texto alternativo; o logótipo no ramo HTML de um e-mail (imagem
  inline sem nome de ficheiro) escapava ao filtro de anexos; e no
  anexo de imagem com nome, a regra de imagem „desfocar"/„remover"
  ficava sem efeito. Agora, os três seguem o mesmo caminho que um
  ficheiro de imagem: reconhecimento de texto na imagem mantida,
  rostos, códigos, metadados e a regra de imagem. O relatório indica as
  imagens – também o aviso, quando ficam por verificar sem
  reconhecimento de texto –, e „Recuperar imagens incorporadas", bem
  como a recuperação a partir do painel de resultados, conhecem também
  estas imagens.
- **Um ficheiro do Office com imagem não podia sequer ser limpo, quando o
  reconhecimento de texto não dominava o idioma.** No Mac, o
  reconhecimento de texto nativo do sistema lê; para hindi, grego,
  croata ou lituano não consegue, e diz-o há pouco tempo – mas em Word,
  Excel, PowerPoint e OpenDocument, isso interrompia a limpeza
  **inteira**, e não era gerado nenhum ficheiro. No entanto, o texto
  podia ser limpo sem problemas; só a imagem não era legível. Agora o
  ficheiro é escrito como no PDF e em imagens individuais, e no
  resultado consta que as imagens NÃO foram verificadas – com o motivo
  e a indicação para „Gerir idiomas".

- **Em pastas de trabalho Excel, ficavam nomes em listas de seleção.** A
  lista de um campo suspenso (validação de dados) é agora limpa como
  qualquer outro conteúdo de célula; referências a intervalos de células
  permanecem intocadas, para que a pasta de trabalho se mantenha
  íntegra.
- **Onde o marcador não cabia, ficava uma barra preta – agora fica ali
  uma forma mais curta.** `[GEBU_1]` em vez de `[GEBURTSDATUM_1]`, e só
  quando nem sequer a forma mais curta couber é que se oculta. Uma
  barra já não diz a ninguém que ali esteve algo; um marcador curto,
  sim. O editor de correção já conseguia isto, a limpeza automática
  ainda não. O ficheiro de atribuição associa ambas as grafias ao mesmo
  valor, para que também a forma abreviada possa ser recuperada.
- **O primeiro clique em „Substituir" deixava a janela de correção parada
  por instantes.** A deteção que dá ao marcador o seu tipo (`[NAME_3]`
  em vez de `[BEGRIFF_3]`) só era carregada nesse momento – cerca de
  dois a três segundos. Agora é preparada em segundo plano ao abrir a
  janela; medidos, os 2289 milissegundos passaram a 193.
- **Duas limpezas simultâneas podiam carregar o mesmo modelo de idioma
  em duplicado** – por exemplo, a monitorização de pasta e a janela
  principal. Como cada modelo ocupa várias centenas de megabytes, a
  necessidade de memória ficava, por instantes, no dobro. Agora a
  segunda execução espera pelo modelo da primeira.
- **O local na linha de data é agora removido também quando o modelo de
  linguagem sozinho não o reconhece:** o que é encontrado com segurança
  como código postal com localidade („3335 Amstetten") arrasta consigo o
  seu nome de local em todo o documento – como um apelido a partir de um
  nome completo. E uma sigla com dígito antes de um nome („T3 Hofbauer
  Christian") mantém-se legível, em vez de desaparecer com o marcador.
- **Três fugas de uma segunda leitura de uma encomenda real foram
  fechadas:** o responsável „T3 Hofbauer Christian" valia, por causa da
  sigla „T3", como cabeçalho de coluna e permanecia legível; um local
  que o modelo de linguagem lia através da quebra de linha para dentro
  do cabeçalho de coluna engolia „Pos." e deixava o primeiro nome do
  cliente; e um nome com saudação („Herr Robert Köttel") arrastava
  apenas o apelido, não o primeiro nome – e, em vez disso, todos os
  „Herr". As siglas são agora apenas letras, nomes de duas palavras
  deixam de ser cabeçalho, os resultados são cortados antes de um
  cabeçalho de coluna, e a saudação não conta para o nome.
- **O local na linha de data („Melk, 05.08.2026") diretamente sob o
  bloco de morada permanecia legível.** O modelo de linguagem colava-o
  ao local da linha do código postal, formando um único resultado, que
  caía por inteiro contra o padrão de código postal. Agora, o resto
  sobressalente permanece um resultado próprio. Encontrado pela nova
  segunda leitura do resultado (`werkzeuge/zweitlesung.py`).
- **Mac: uma digitalização num idioma que o reconhecimento de texto
  nativo do sistema não domina (por exemplo, hindi, grego, croata,
  lituano) valia como verificada.** Era lida com o recurso em inglês, a
  escrita estrangeira permanecia na imagem, e o relatório dizia „nada
  encontrado". Agora diz „Imagem(ns) NÃO foi(ram) verificada(s)" com o
  motivo, e a gestão de idiomas deixa de prometer reconhecimento de
  texto para tais idiomas apenas por existir um ficheiro de idioma
  Tesseract.
- **No PDF, o sinal de pontuação a seguir a um valor substituído
  permanece.** De „Admissão em 01.03.2026, alta em 04.03.2026." resultava
  até agora „Admissão em [DATUM_1] alta em [DATUM_2]" – faltavam a
  vírgula e o ponto final, tanto em marcadores como em datas deslocadas.
  Agora só é removido o valor reconhecido, não a palavra inteira até ao
  próximo espaço; vírgula, ponto e vírgula, ponto ou parêntese a seguir
  permanecem no seu lugar, e o marcador não passa por cima deles.
- **Russo e ucraniano corriam, sem se notar, com o modelo multilíngue
  mais fraco**, quando faltava um pacote auxiliar para a análise de
  formas de palavra (`pymorphy3`) – os modelos próprios não podiam
  então ser carregados, e „Львів" tornava-se uma pessoa. Para o
  reconhecimento de nomes, a análise de formas de palavra não é
  necessária; o modelo é agora carregado sem ela, e os locais voltam a
  ser locais.
- **Os avisos de licença em 16 idiomas estavam desatualizados.** Ali
  constava ainda que o código-fonte MPL era disponibilizado „a pedido",
  o QPDF valia como MPL-2.0, sete componentes faltavam na tabela
  (wordfreq, Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet),
  o parágrafo sobre o spaCy estava em inglês, e no final havia uma
  secção de substituição em inglês. Agora todas as 18 versões estão ao
  nível da alemã: arquivos de código-fonte permanentes em
  maskuro.com/quellcode/oss/, QPDF Apache-2.0, via Qt-LGPL, origem dos
  modelos. Também a tabela em inglês tem as linhas em falta.

- **Palavras de contrato no genitivo alemão („des Angebotsinhaltes", „des
  Anbotes", „des Terminplanes") deixam de valer como local.** Uma única
  palavra a seguir a um artigo genitivo ou dativo com terminação
  flexionada é uma palavra comum – nomes de local não flexionam („nach
  Graz"). Se o local constar noutro lugar do documento sem artigo
  („Burgenland"), também „des Burgenlandes" continua a ser reconhecido.
- **Valores deslocados, mascarados e inventados rasterizavam a página de
  PDF.** A segunda verificação depois de remover só permitia, no
  retângulo do resultado, um marcador entre parênteses retos; uma data
  deslocada („01.07.2026") ou um valor mascarado („****1234") valia como
  resto omitido, e a página era convertida em imagem por precaução –
  com „Substituir" não. Agora, tais páginas mantêm-se como texto, e a
  recuperação a partir do painel ou da moldura volta a fornecer o
  original.
- **Valores substitutos de várias palavras não podiam ser anulados no
  PDF através do painel de resultados.** Um nome inventado („Greta
  Mayrhofer") ou um IBAN mascarado („**** **** **** **** 3201")
  consiste em várias palavras; a pesquisa de localização comparava
  palavra a palavra e comunicava „O marcador não foi encontrado no
  documento". Agora, palavras consecutivas da mesma linha são lidas em
  conjunto.
- **Depois de recuperar um valor removido sem substituto, a sua linha de
  painel permanecia.** Valores que a estratégia „ocultar" remove sem
  substituto no modo de marcador não têm marcador com o qual o painel
  pudesse medir um desaparecimento. Agora, a linha é riscada assim que
  o valor volta a estar no documento.

- **Compostos abreviados como „E-Helfer" ou „U-Bahn" deixam de valer
  como nome.**
- **Restos de hifenização („Leis-") e compostos excessivamente longos
  („Bauarbeitenkoordinationsgesetzes", „Baustellenkoordinator") deixam
  de valer como nome ou local.** Num texto de concurso digitalizado,
  isto significou menos 28 palavras ocultadas.
- **Listas de posições de propostas digitalizadas deixam de valer como
  diretório de nomes.** A passagem adicional para diretórios (linhas
  curtas) transformava „Kälterohr" e „Außengeräte" em pessoas; agora
  suspende-se assim que números de posição como „1.1.5" constem no
  início da linha. Linhas de data em cadeias de e-mail não contam, nesse
  processo, como números de posição.
- **Cabeçalhos de coluna e números de posição de propostas digitalizadas
  („Pos.", „Pos. 1.1.3", as siglas „E/L/S") valiam como nome ou
  local.** Uma abreviatura sozinha na sua linha, uma legenda com número
  e letras isoladas linha a linha não são.
- **A página „respirava" na janela de correção depois de abrir a lupa de
  comparação** – com „Largura de página" e „Ajustar", a escala depende
  da janela de visualização, e isso muda a cada barra de deslocamento
  que aparece ou desaparece; cada ação seguinte deslocava a página um
  pouco mais. A área de desenho ajusta-se agora sozinha até estabilizar.
  E botões de zoom, cursores e atalhos de teclado mantêm o centro da
  imagem mesmo quando surge uma barra de deslocamento ao ampliar.
- **Digitalizações guardadas na transversal são agora lidas na vertical,
  e a letra pequena em digitalizações grandes deixa de se perder.** Uma
  proposta digitalizada de 24 páginas mantinha, em cada rodapé, seis
  IBANs bancários, número de registo comercial e NIF legíveis: a
  digitalização estava rodada 90° no PDF, e o reconhecimento de texto
  omitia linhas inteiras em imagens muito grandes, consoante o tamanho
  da imagem. Agora a rotação visível é considerada, e imagens grandes
  são lidas em faixas sobrepostas – os rodapés ficam pretos.
- **Ruas a seguir a pessoas com hífen antes da palavra-base („Josef
  Admanseder-Straße 7", „Abt-Karl-Straße 8", „Dr.-Karl-Renner-Straße
  12") são reconhecidas como morada.** No cabeçalho de carta de uma
  proposta digitalizada, uma morada assim permanecia legível, porque o
  padrão exigia um espaço antes de „Straße".
- **IBANs do reconhecimento de texto que trazem um O em vez de 0 ou um l
  em vez de 1 são agora reconhecidos.** Na letra pequena de uma
  digitalização, o reconhecimento de texto lê de bom grado dígitos como
  letras; o número tinha então a forma de um IBAN, mas a soma de
  verificação não batia certo, e permanecia. Se a soma de verificação
  falhar, é agora tentada a leitura com dígitos – se estiver certa, é o
  IBAN. Dígitos de controlo realmente errados continuam errados.
- **Fragmentos de frase como „folgenden Codes auf der" valiam como
  local.** Um nome ou local que começa por uma palavra em minúscula não
  o é – exceto em partículas nobiliárquicas („van Gogh", „de Vries").
- **No editor, ficava a última letra ao lado da barra de ocultação**
  („…6", „…t", „…g"), e a barra tinha a altura da moldura arrastada em
  vez da linha. Causa: se o editor não conseguisse medir a página,
  considerava toda a moldura como „nenhuma palavra atingida" e
  aplicava-a exatamente – sem a regra de que meia palavra nunca fica.
  O mesmo acontecia com comandos de texto individuais que o editor não
  conseguia localizar. Agora conta sempre a caixa de palavra ao lado: o
  que a moldura sobrepõe substancialmente cai por inteiro.
- **A última letra de uma palavra ultrapassava a barra de ocultação.** A
  barra era dimensionada segundo a largura de avanço das métricas do
  tipo de letra; se o tipo de letra desenhasse um glifo mais largo, o
  seu resto ficava ao lado da barra. A caixa de um carácter passa agora
  a incluir também o glifo desenhado.
- **A mensagem sobre converter uma página em imagem prometia demais.**
  „A apresentação mantém-se igual" não é verdade depois de rasterizar:
  o texto e os gráficos passam a ser pixels, o ficheiro fica maior. A
  mensagem diz agora isso – e indica também o segundo motivo pelo qual
  se rasteriza (a reconstrução teria danificado a página).
- **O texto a seguir a um valor removido deslocava-se até um ponto para
  a esquerda.** Ao recompor uma linha, o início era medido pela margem
  do glifo, a continuação pela origem da pena – a largura de avanço da
  primeira letra ficava como erro („C" 0,5 pt, „I" 1,0 pt). Agora a
  composição calcula sempre com a origem da pena; a continuação fica no
  décimo de ponto no seu lugar.
- **O NIF austríaco com espaços („ATU 187 35901") e um número de registo
  comercial sem „FN" sob a sua legenda („Firmenbuchnummer: 30799v") são
  reconhecidos.** Ambos estavam manuscritos num formulário de concurso
  digitalizado e permaneciam legíveis, apesar de o reconhecimento de
  texto os ter lido corretamente.
- **Páginas de PDF na transversal eram convertidas em imagem sem
  motivo, depois de ocultar.** A verificação de integridade comparava
  original e resultado na apresentação rodada, mas calculava as suas
  zonas de ocultação sem rotação – numa página com marca de rotação, a
  própria ocultação ficava assim ao lado da sua zona e era considerada
  dano. Tais páginas mantêm agora a sua camada de texto e gráficos
  vetoriais.
- **Também páginas direitas eram ocasionalmente convertidas em imagem
  sem necessidade**, quando o texto a seguir a um marcador se deslocava
  um ponto – permitido, mas a comparação de imagem era mais fina do que
  a sua própria tolerância. Agora compara em meios pontos, atingindo
  assim exatamente a sua tolerância: até dois pontos de desvio, nada
  dispara; acima disso, tudo.
- **Indicações em objetos de formulário incorporados permaneciam.**
  Alguns modelos colocam o cabeçalho ou o rodapé de carta como
  formulário próprio, que a página apenas incorpora. Um resultado ali
  era planeado e contado como removido, mas nunca escrito – o texto
  continuava lá, e só a rasterização da página inteira o apanhava.
  Agora o próprio formulário é reescrito; um formulário que está em
  várias páginas, uma única vez.
- **Páginas de PDF eram rasterizadas em imagem, apesar de nada ter
  permanecido legível.** Uma proposta de sete páginas foi assim afetada
  em seis páginas; cresceu de 73 kB para 3,3 MB e perdeu o seu texto
  para uma imagem. A causa eram espaços que estão várias vezes seguidos
  no documento, mas que o leitor só comunica uma vez: o texto a seguir a
  uma indicação removida deslocava-se para a direita na largura desta,
  a segunda verificação encontrava a palavra vizinha no retângulo do
  resultado e recorria à rasterização. Restos de linha mantidos ficam
  agora de novo exatamente no seu lugar; a mesma proposta é limpa sem
  uma única página rasterizada (76 kB).
- **Nomes de chave e cabeçalhos de fatura valiam como pessoas.** Num
  ficheiro de acesso, o nome da variável de ambiente
  („AWS_ACCESS_KEY_ID") era substituído, não só o seu valor; numa
  fatura em inglês, o título „Bill to" caía como primeiro nome. Um
  identificador em maiúsculas com sublinhados nunca é um nome, e uma
  palavra numa linha que, por inteiro, é uma legenda de campo, também
  não – o destinatário abaixo continua a ser encontrado.
- **A pesquisa na janela de correção bloqueava em páginas de PDF
  grandes.** Cada letra no campo de pesquisa fazia rasterizar de novo a
  página, apesar de só o realce mudar. A imagem de página renderizada
  mantém-se agora, enquanto a página, o zoom e a vista forem os mesmos –
  também o original na lupa de comparação; folhear, ampliar e um novo
  estado de ficheiro continuam a desenhar de novo como até agora.
- **Números de posição em propostas valiam como endereço IP ou número de
  telefone.** Uma linha de artigo como „1.3.3.4 … 5-Port Gigabit Switch"
  deixava o número de estrutura tornar-se um endereço de rede, porque
  „Port" contava como contexto técnico – agora só conta como indicação
  autónoma („Port 80"), não como parte de palavra. E „1.3.3.6 216879"
  (número de posição mais número de artigo) deixa de ser ocultado como
  número de telefone. Endereços IP e números de telefone reais em tais
  listas continuam reconhecidos.
- **Linhas de artigo em propostas valiam como código postal com
  localidade.** „35252 DIETZEL SALR" (número de artigo com fabricante) e
  „1000 AWG" (quantidade com secção de condutor) eram ocultados como
  morada em linhas de posição numeradas, porque uma palavra em
  maiúsculas a seguir a um número valia como nome de local em
  maiúsculas. Em listas de posições, isso deixa de se aplicar; „1080
  WIEN" no bloco de morada e locais em minúsculas continuam
  reconhecidos em todo o lado.
- **A deteção adicional de nomes ocultava, em propostas, linhas de
  função e cabeçalhos de coluna.** „Partiestundensatz Monteur +
  E-Helfer" valia 49 vezes como pessoa, o cabeçalho de coluna „Pos.
  Bezeichnung Menge EH" 19 vezes como local – uma encomenda de 19
  páginas ficava assim ilegível. Tais resultados em linhas de posição
  caem agora quando trazem eles próprios carateres que nenhum nome tem
  (mais, barra, dígito, sigla) – também quando a linha termina com um
  montante („Alternativ Markt … - PV/LS AC-Versorgung 1 290,00"). Nomes
  em diretórios e listas – para o qual este nível serve – não são
  afetados.
- **„Der Kunde" transformava, em condições comerciais, cada „Kunde" num
  nome.** Se a deteção adicional de nomes incluísse o artigo no
  resultado, este valia como nome de duas partes e protegia todos os
  outros 35 locais da mesma palavra. Agora o artigo é retirado, e „der
  Kunde" cai tal como já „des Kunden" caía.
- **Legendas valiam como valor.** „E-Mail" era ocultado sete vezes como
  endereço de e-mail, „Telefonnummer" e „Faxnummer" como número de
  telefone. Um endereço sem @ e um número de telefone sem dígitos
  deixam de contar.
- **Siglas de coluna de uma letra („L: 154,50", „S: 0,00") valiam como
  nome** – 25 vezes numa proposta fotovoltaica. Uma única letra não é
  nem nome nem local.
- **Páginas de PDF eram convertidas em imagem com demasiada
  frequência.** Duas causas, ambas encontradas em propostas reais: se um
  PDF definir cada glifo como comando próprio e por baixo houver um
  glifo de espaço sem carácter de texto, a atribuição deslocava-se a
  partir daí em um – do valor removido ficava a última letra
  („ŠkodaTopCar**d**"), e a segunda verificação rasterizava a página com
  razão. E uma palavra dividida no fim de linha („Datenschutz-") valia
  como deslocada por causa da marca de hífen da biblioteca de leitura.
  Ambos corrigidos: uma proposta de veículo passou de 4 páginas
  rasterizadas para 0, uma encomenda de 19 páginas de 7 para 0 – o texto
  mantém-se texto, o ficheiro mantém-se pequeno.
- **Mais dois motivos de rasterização corrigidos:** se um documento
  trouxer ele próprio um tipo de letra chamado „F1", os marcadores sobre
  imagens eram definidos nesse tipo de letra e ficavam ilegíveis –
  agora o tipo de letra próprio de legenda recebe um nome livre. E se
  faltar à biblioteca de leitura um espaço a meio de um comando de texto
  longo, o local é agora comprovado também em tipos de letra
  multibyte (mesmo código, mesmo carácter), em vez de ser adivinhado
  para o fim – antes disso, ficava uma letra do valor removido e o
  resto do texto deslocava-se visivelmente para o lado. A isto juntam-se
  dois últimos casos: um comando com dezenas de glifos de espaço fazia
  a atribuição descontrolar-se (o nome a seguir permanecia), e um
  título grande com largura prévia não encontrava o seu primeiro
  carácter (o nome da empresa permanecia). **De nove propostas reais,
  já não é rasterizada nenhuma página** – antes eram 30 de 90.
- **Ao rasterizar, imagens desapareciam sob um bloco preto.** Se uma
  página tiver de ser convertida em imagem, é renderizada a partir do
  original – e isso não conhece limpeza de imagem. Até agora, por isso,
  *toda* a área de imagem da página caía sob uma barra, mesmo a
  intocada. Numa proposta, a morada e dois logótipos de certificado
  estavam na mesma imagem de cabeçalho de carta; a barra levava
  consigo os logótipos. Agora é inserida a imagem já limpa: a morada
  nela está ocultada, tudo o resto continua visível. Uma imagem removida
  deixa papel branco em vez de uma caixa preta.

- **Digitalizações limpas tornavam-se muitas vezes maiores do que o
  original.** Cada imagem em que algo foi ocultado voltava ao ficheiro
  como imagem bruta não comprimida – numa digitalização de 24 páginas,
  isso fazia crescer de 11,8 para 52,9 MB. As imagens mantêm agora o
  tipo em que se apresentavam: uma fotografia mantém-se fotografia, uma
  digitalização de fax mantém-se preto e branco, uma imagem sem cor não
  é guardada como imagem a cores. O mesmo ficheiro tem agora 15,6 MB,
  sem diferença visível.

- **Ficheiros PDF digitalizados de equipamentos de escritório voltavam
  como padrão às riscas.** Tais digitalizações colocam o texto como
  camada nítida a preto e branco sobre uma imagem grosseira a cores –
  Canon, Xerox e Kofax constroem assim os seus ficheiros. Ao ocultar na
  imagem, esta camada era reescrita de forma incorreta; o resultado
  ficava ilegível. Numa proposta de seis páginas, isto afetou nove em
  dezasseis imagens. Agora é tratada corretamente, na sua própria cor, e
  os locais ocultados desaparecem de facto.

- **„Remover todas as imagens" tirava a uma página digitalizada o seu
  texto.** A camada de texto de tal digitalização é tecnicamente uma
  imagem – era removida ou desfocada juntamente, e restava uma folha
  vazia. Agora mantém-se; logótipos, carimbos e assinaturas continuam a
  ceder.

- **A verificação de páginas de PDF danificadas deixa de rasterizar por
  causa de um desvio minúsculo.** Um trecho de texto reancorado ao
  limpar pode deslocar-se até dois pontos; a comparação de imagem
  contava isso, mesmo assim, como dano e reconstruía a página como
  imagem – com isso, perdiam-se gráficos vetoriais como linhas de
  tabela, e sobre os resultados ficava uma barra em vez de um
  marcador. A comparação permite agora o mesmo pequeno desvio que a
  verificação de palavras; danos reais continuam a ser detetados.

- **A recuperação de muitos valores em sequência deixou de falhar no
  Windows com „Acesso negado".** Quem, num ficheiro de Office,
  recuperasse muitas linhas do painel em rápida sucessão podia falhar
  por um bloqueio de ficheiro efémero do antivírus; a troca aguarda
  agora brevemente por tais bloqueios.

- **A via de transmissão de comandos do Windows terminava o verificador
  em vez de verificar.** A verificação de atividade da instância à
  escuta enviava, por engano, um verdadeiro Ctrl+C ao seu próprio grupo
  de consola no Windows; agora consulta o sistema sem sinal.

- **Legendas de campo com várias palavras não faziam efeito, mas os
  seus fragmentos faziam.** „Date of birth", „Bank account", „Cuenta
  bancaria" e „Numero de cliente" constavam na lista de legendas, mas
  eram ali decompostas em palavras isoladas e por isso nunca coincidiam;
  restavam fragmentos como „de" e „of", que desde então valiam como
  legenda – mas „de" é parte de nome („Anna de Vries"). Ambos
  corrigidos: as expressões fazem agora efeito como um todo, os
  fragmentos desapareceram.

- **Fórmulas de saudação alemãs com „ß" eram tratadas como nome de
  pessoa, apesar de constarem na lista.** Sob „Herzliche Grüße" ou „Mit
  freundlichen Grüßen" ficava no resultado um marcador, apesar de ambas
  as expressões constarem desde sempre na lista de exceção. A causa era
  uma grafia que nunca chegava à comparação; foram afetadas oito
  entradas em cinco listas. Todas fazem agora efeito.

- **„John Staff" permanecia por substituir.** Um apelido que é também um
  cabeçalho de coluna em inglês era descartado juntamente pelo filtro de
  legendas. O cabeçalho continua intocado, o nome por baixo volta a ser
  substituído.

- **Valores de campos de formulário legendados permanecem protegidos no
  nível de IA.** O árbitro local do nível de IA recebia até agora
  também, para avaliação, resultados cujo significado já a legenda do
  campo comprovava („Data de nascimento:" sobre o valor) – e podia
  descartá-los. Tais valores estruturalmente comprovados deixam agora
  de lhe ser apresentados. O ficheiro de atribuição indica agora,
  adicionalmente, para cada substituição, a via de deteção
  („comprovativo").

- **Uma página de PDF cujo texto mantido sofreu dano ao limpar é agora
  detetada e reconstruída como imagem do original.** Em alguns tipos de
  letra de geradores, trechos de texto mantidos podiam aparecer como
  blocos pretos depois da limpeza, ou palavras juntavam-se, apesar de
  todas as indicações a remover terem sido corretamente removidas. O
  Maskuro compara agora o resultado palavra a palavra e pixel a pixel
  com o original; uma página danificada é substituída pela sua imagem
  limpa – com barras de ocultação sobre os resultados, áreas de imagem
  ocultadas e texto pesquisável. A página mantém-se legível, a remoção
  fiável.

### Alterado

- **Nas interfaces traduzidas, cada termo técnico chama-se agora sempre
  o mesmo em todo o lado.** Para uma e a mesma palavra alemã, existiam,
  consoante a janela, duas ou três traduções lado a lado: o registo de
  verificação chamava-se em norueguês, em parte, „Revisjonslogg", em
  parte „Kontrollogg"; o nível gratuito, em parte „Gratisnivå", em parte
  „Gratisversjon" – e de forma semelhante numa dúzia de outros idiomas.
  Quem procurasse uma definição encontrava-a na janela seguinte com
  outro nome. Foi uniformizado para a palavra que a interface já usa
  com mais frequência.

  Com isto vieram à luz locais onde uma palavra estava a ser usada para
  duas coisas **diferentes**: francês, grego e coreano usavam para
  „ocultar" e „mascarar" a mesma expressão – precisamente onde o
  programa explica a diferença („Ocultar remove sem substituto,
  Mascarar mantém a forma"). Ambos estão agora separados. Para o sueco,
  esta decisão ainda está pendente: ali, ocultar chama-se „maskera" – a
  mesma palavra que mascarar.

- **A pergunta sobre o tipo de utilização no primeiro arranque
  desapareceu.** Pouco depois do arranque surgia uma janela („Privado ou
  na empresa?"), e nas definições havia uma linha sobre isso. Ambos
  deixaram de existir – sem substituto. Uma indicação sem consequência
  leva a indicar erradamente quem quer a licença errada, e quem for
  honesto não precisa dela; custava a cada um um clique num momento em
  que ninguém pensa em tipos de licença. Qual a licença certa consta
  onde é decidida: na página de preços, na compra e na ajuda. As
  organizações que implementam o Maskuro de forma centralizada continuam
  a impor o tipo de utilização através do ficheiro de diretrizes.

- **Os avisos sobre o tipo de licença indicam o caso em questão.** A
  licença privada vale exclusivamente para utilização privada; qualquer
  trabalho profissional ou comercial precisa da licença empresarial –
  também como empresário em nome individual sem colaboradores. Isso
  constava assim nas condições de licença, mas nem no programa nem na
  ajuda: ali falava-se sempre apenas do domínio empresarial, que não
  abrange precisamente este caso: o computador de um trabalhador
  independente não pertence a nenhum domínio. O aviso ao ler uma
  licença privada diz-o agora, tal como o capítulo de licença do manual
  e as perguntas frequentes, que receberam para isso uma entrada
  própria. Continua a não ser bloqueado nada.

- **Os caminhos ainda não distribuídos estão agora reunidos.** As
  definições ganharam uma página „Programador"; ali constam a deteção
  máxima (IA) com a sua contraverificação, o catálogo de listas de
  palavras e a monitorização de pastas. Os três estão construídos, mas
  não testados em escala – por isso só são visíveis com uma licença de
  programador, e isso em todo o lado ao mesmo tempo: a página, as
  entradas de menu e o efeito na execução dependem da mesma decisão.
  Sem esta licença, um nível de IA anteriormente ativado fica sem
  efeito; a sua definição não é apagada e volta a valer assim que o
  caminho for distribuído.

### Melhorado

- **„O que é procurado" mostra mais três listas da deteção de nomes.** As
  saudações a seguir às quais a palavra seguinte é lida como nome; os
  títulos e cargos que, a seguir a elas, ainda **não** são o nome
  („Herr Bürgermeister Huber"); e as oitenta legendas multilingues com
  as quais se reconhecem referências de processo, números de assunto e
  de caso. As três sempre fizeram efeito, mas não eram visíveis na
  visão geral.

- **„O que é procurado" mostra duas listas de palavras até agora em
  falta.** As saudações e títulos que transformam uma palavra anterior
  em nome („Herr", „Frau", „Dr."), e as siglas das organizações de
  normalização, com as quais o Maskuro distingue uma referência
  normativa como „ÖNORM B 2110" de uma pessoa. Ambas influenciam a
  deteção desde sempre, mas não constavam na visão geral.

- **Listas de posições, índices, enumerações de equipamento e
  referências normativas permanecem legíveis.** A deteção reconhece
  agora a estrutura da linha: um nome adivinhado numa linha de estrutura
  („1.3.1 Energieerdkabel 1kV"), numa linha de índice com pontos de
  guia, numa enumeração („- carregamento sem fios com anel magnético"),
  por cima de uma linha de quantidade/preço, num cabeçalho de coluna ou
  a seguir a „mediante" é um termo técnico e deixa de ser substituído.
  Nomes reais permanecem protegidos – por saudação, legenda de campo e
  comprovativo noutro local do documento; no corpus de medição, nenhuma
  indicação perdeu a sua proteção. No corpus empresarial, os falsos
  alarmes descem assim de 25 para 6.

- **Títulos, legendas de formulário e fórmulas de saudação são menos
  vezes tomados por nomes – em alemão e inglês.** As listas de palavras
  com que o Maskuro distingue termos comuns de nomes de pessoa cresceram
  significativamente: legendas de faturas, formulários e correspondência
  oficial („Aktenzeichen", „Verwendungszweck", „Kostenstelle", „Sort
  code", „Subtotal"), títulos de secção de candidaturas e relatórios
  („WERDEGANG", „QUALIFIKATIONEN", „SUMMARY", „REFERENCES"), tipos de
  documento em alemão e inglês („Auftragsbestätigung", „Niederschrift",
  „Timesheet", „Agreement"), bem como formas de comando de instruções
  („Sende…", „Select…"). O lado inglês estava, até agora,
  notoriamente pouco preenchido.

- **Os campos legendados revelam agora o que contêm também quando a
  legenda é composta.** „Lieferanschrift", „Rechnungsadresse",
  „Sachbearbeiterin", „Kontoinhaber", „Contact person" e „Billing
  address" atribuem agora o valor ao lado ou por baixo ao mesmo tipo que
  o simples „Anschrift" ou „Name" – num formulário preenchido com
  caixas, isso é a diferença entre encontrado e omitido.

- **Na janela de correção, a roda do rato continua a folhear na margem
  da página.** Quem rolar mais no fim de uma página chega ao topo da
  seguinte; quem rolar para trás no início chega ao fundo da anterior –
  um documento pode assim ser percorrido do início ao fim sem tocar nos
  botões de página. O teclado (Page Up/Page Down) já conseguia isto;
  uma pequena pausa entre duas mudanças de página evita que a inércia
  de um trackpad atravesse metade do documento.

- **As miniaturas de página na janela de correção ficam centradas no
  painel.** Até agora ficavam coladas à margem esquerda, e ao alargar,
  só a margem vazia à direita crescia.

- **A barra de símbolos da janela de correção mostra os seus grupos.**
  Os traços separadores têm agora espaço e cor, „Pesquisar" e „Aplicar a
  todas as páginas" aparecem como grupos próprios junto das
  ferramentas, e „Aplicar" só aparece em tipos de documento onde pode
  produzir efeito. Cada entrada na barra e nos menus traz agora uma
  imagem: „Linhas de texto" e a lupa de comparação receberam símbolos
  próprios (a lupa partilhava até agora o seu com „Antes/Depois"), a
  isto juntam-se zoom, página inteira, largura de página, rodar,
  folhear e os atalhos de teclado. „Abrir com programa do sistema"
  aparece agora também na barra ao lado de Imprimir – o caminho do
  resultado concluído até ao programa habitual é um clique, não uma
  passagem por menu.

- **Na limpeza da área de transferência, volta a constar que é preciso
  verificar.** Nas definições, o aviso consta permanentemente ao lado do
  interruptor: o Maskuro pode não ver dados pessoais ou tratar
  indicações de forma incorreta, o texto colado deve ser verificado
  antes de ser partilhado. Ao ativar, a mensagem indica-o também
  adicionalmente, e fica registado na área de saída – mesmo quando não
  está a correr nenhum ícone na área de notificação. Em cada operação de
  cópia individual, não aparece propositadamente: um aviso que
  aparecesse cinquenta vezes por dia deixaria de ser lido a partir da
  terceira vez.

## 0.10.36-beta.1 – 20 de agosto de 2026

### Melhorado

- **Documentos técnicos comerciais deixam de ser ocultados em excesso.**
  Quatro travões de deteção, obtidos a partir de onze propostas e
  encomendas reais: números de estrutura („1.3.1.1") deixam de valer como
  endereços IP, referências normativas („ÖNORM EN 62446") e códigos de
  identificação deixam de valer como código postal ou número de telefone,
  e palavras de função a seguir a artigos („o cliente", „do contratante")
  deixam de valer como nomes – nas condições comerciais de uma proposta
  real, isto devolve legibilidade a todas as 46 palavras de função, em vez
  de ficarem ocultadas. Moradas com indicação de país („A 3390 Melk",
  „D-94032 Passau") são agora removidas por completo, em vez de deixar o
  código postal como órfão.

- **As listas de palavras estão agora totalmente visíveis.** Em „Ajuda →
  Listas de palavras..." podem ser consultadas as listas de deteção e de
  contraverificação usadas localmente, com idioma, finalidade, origem e
  conteúdo. Incluem-se também listas Wordfreq, médicas, pessoais e
  geridas centralmente, bem como as reservas de valores substitutos
  inventados. O manual descreve o catálogo numa secção própria.

- **As linhas de ficheiro concluídas mostram o idioma de deteção usado.**
  Depois de „concluído" aparece agora, por exemplo, „Alemão" ou „Inglês",
  para que uma seleção automática de idioma inadequada seja notada de
  imediato. Se foi necessário recorrer a outro idioma instalado, uma seta
  mostra ambos os idiomas.

- **A nova lupa de comparação mostra de imediato, durante a leitura, o
  local correspondente no original.** O seu recorte ampliado do original
  segue o cursor do rato sobre o resultado, que continua editável; no
  texto, segue o parágrafo. A lupa pode ser usada encostada ao rebordo da
  janela ou destacada como janela própria e maximizável. O seu zoom é
  ajustável diretamente entre 50 e 300 por cento e fica memorizado, tal
  como a ativação. „Repor" traz também uma lupa maximizada ou ancorada de
  forma desfavorável de volta a um tamanho utilizável à esquerda. Os
  valores originais substituídos aparecem realçados a amarelo na lupa,
  para que as palavras afetadas se destaquem de imediato durante a
  leitura. Uma vez ativada, volta a abrir-se em futuros documentos
  adequados – mesmo depois de reiniciar o programa. O anterior alternador
  antes/depois mantém-se no menu de vista. O manual descreve-a numa secção
  própria.

- **As comprovações de código aberto e de modelos são agora exatas por
  lançamento.** A construção do pacote gera uma lista de componentes
  legível por máquina, com hashes dos textos de licença incluídos. Fontes
  MPL, origem dos modelos, revisões fixas, alterações e SHA-256 são
  comprovadas separadamente; modelos descarregados posteriormente recebem
  o seu comprovativo de origem diretamente na pasta do modelo. Listas de
  referência móveis do Tesseract e do spaCy foram fixadas de forma
  permanente. As construções de venda permanecem bloqueadas enquanto os
  arquivos de código-fonte exatos da versão distribuída não estiverem
  publicados e verificados na própria página de código-fonte.

- **O conjunto de dados wordfreq local está totalmente documentado em
  termos de licença.** A construção do pacote verifica a versão 3.1.1, 39
  listas pequenas inalteradas incluindo CJK e a tabela de carateres
  chinesa quanto a quantidade, tamanho e soma de verificação do manifesto.
  A nota de código Apache-2.0, a licença CC-BY-SA-4.0 completa, a
  atribuição, as fontes de dados e as listas grandes, Jieba e não
  suportadas que foram omitidas estão documentadas no pacote.

- **Palavras frequentes de frase são ocultadas por engano com menos
  frequência.** Um dicionário de frequência local serve como
  contraverificação adicional quando a deteção de nomes toma um verbo,
  pronome, artigo ou preposição por uma pessoa. O dicionário nunca decide
  sozinho: substantivos, nomes compostos por várias partes, bem como
  nomes em campos, listas e depois de saudações, permanecem protegidos.
  Chinês, japonês e coreano usam exclusivamente os limites exatos de
  token dos seus modelos de linguagem já existentes; para idiomas
  inexistentes não é usado nenhum idioma de dicionário supostamente
  semelhante. Para isso, nenhum texto do documento é transmitido pela
  Internet.

- **Termos técnicos de produto e equipamento deixam de ser confundidos tão
  facilmente com nomes ou localidades.** A contraverificação local combina
  agora frequência, classe de palavra, formação técnica de palavras e
  campos temáticos. Assim, por exemplo, „Travel-Assistent", „Family-Bonus",
  „WLTP-Wert", „Easy-Start" e termos compostos de número, titular ou
  travão permanecem no documento. Componentes em inglês são também
  consultados localmente em texto técnico alemão; nomes próprios reais,
  saudações e campos de pessoa e localidade mantêm prioridade. Além disso,
  uma „garantia do fabricante de 2 anos" deixa de valer como idade.

- **Os direitos de licença do Qt/PySide são agora totalmente
  rastreáveis.** O pacote do programa contém adicionalmente o texto
  integral da GPL-3.0, versões exatas do Qt, uma oferta de código-fonte e
  um guia em alemão/inglês para a substituição das bibliotecas dinâmicas,
  incluindo a nova assinatura local no macOS. Uma construção de venda é
  bloqueada enquanto os arquivos de código-fonte exatos da versão
  distribuída não estiverem disponíveis na própria página de código-fonte.

- **A licença e o estado de atualização indicam agora, para cada nível, de
  forma inequívoca o que se aplica.** Na janela de licença e nas
  definições de atualização consta se estão incluídas atualizações, até
  que data chegam e se a versão em curso permanece utilizável de forma
  permanente. As licenças privadas deixam de instalar, após a data limite,
  qualquer versão publicada posteriormente; mesmo um instalador
  recém-descarregado reconhece, pela sua data de lançamento incorporada de
  forma fixa, se a chave introduzida o abrange. A última versão privada
  coberta permanece utilizável de forma permanente. Se, pelo contrário,
  terminar uma subscrição empresarial, terminam a utilização e as
  atualizações; o período de teste e o nível gratuito não se abrem como
  desvio.

- **As licenças privadas permanentes encontram agora também, depois de uma
  nova instalação, o estado de programa correto.** Um catálogo de versões
  assinado regista todas as versões estáveis e os seus pacotes. Se o
  último instalador abrangido pela compra já não estiver disponível, pode
  usar-se automaticamente, em vez disso, exatamente a próxima versão
  estável superior disponível – nunca uma beta ou nightly. Numa instalação
  demasiado recente, o cliente pode instalar o estado permitido ou mudar
  para a página de compra para um novo período de atualização; um
  retrocesso não acontece silenciosamente. Isto aplica-se também a
  instalações MSI geridas.

- **A ocultação automática de rostos está agora descrita de forma
  inequívoca.** A ajuda do programa e o texto de proteção de dados
  designam a função „Detetar e tornar irreconhecíveis áreas de rosto" e
  distinguem-na de identificação, reconhecimento, comparação facial,
  modelos biométricos e bases de dados de pessoas ou de rostos. Também
  alertam claramente que a deteção totalmente local pode não ver ou
  marcar por engano áreas, devendo por isso o resultado ser verificado
  visualmente. Também num ficheiro de imagem limpo individualmente, o
  relatório de resultado indica agora as áreas de rosto detetadas e
  pixelizadas; a falta de reconhecimento de texto deixa, com isto, de ser
  descrita erradamente como ficheiro totalmente inalterado.

## 0.10.36-alpha.20260820 – 20 de agosto de 2026

### Corrigido

- **As indicações anonimizadas podem agora ser totalmente recuperadas
  independentemente da ordem.** A recuperação anterior procurava o valor
  através de âncoras de texto visíveis. Em tabelas densas, marcadores
  diretamente vizinhos e depósitos internos invisíveis do Office/e-mail,
  faltavam estas âncoras; por vezes, um termo só ficava recuperável depois
  de outro texto simples criar por acaso uma nova âncora. Agora o resultado
  e o original são comparados por cada suporte de formato real com a
  atribuição completa, e apenas são escritos os locais comprovados do valor
  escolhido.

- **Nomes, endereços de e-mail, números e termos de verificação próprios
  continuam a ser operáveis de forma inequívoca mesmo com deteção
  sobreposta.** Se o mesmo valor em texto simples estiver atribuído a dois
  tipos, decide o marcador que efetivamente está no local encontrado, em
  conjunto com a linha da barra lateral selecionada. Um par valor/marcador
  não comprovado continua bloqueado de forma segura.

- **Os casos especiais de e-mail já não deixam marcadores ocultos.** Isto
  aplica-se a assuntos codificados em MIME, anexos de texto e nomes
  separados por marcação HTML em EML e MSG. O HTML em UTF-8 sem indicação
  própria de conjunto de carateres também deixa de ser recodificado para
  mojibake a cada passo de edição em ficheiros do Outlook; resultados mais
  antigos já escritos assim continuam recuperáveis.

### Melhorado

- **Uma nova matriz de liberação testa cada linha anónima da barra lateral
  individualmente e propositadamente ao contrário.** Verifica todos os 14
  formatos de texto, Office, web e e-mail, bem como PDF, e depois também
  fórmulas, atributos, relações, comentários, cabeçalhos de e-mail, anexos e
  depósitos internos secundários. A execução completa no macOS abrange
  agora 149/149 scripts de verificação bem-sucedidos.

## 0.10.35-alpha.20260820 – 20 de agosto de 2026

### Melhorado

- **As medições de idioma comparam agora efetivamente o igual com o igual.**
  O corpus de medição regular contém os mesmos 14 casos de documentos com as
  mesmas sete tarefas de texto e quatro tarefas de imagem em alemão e inglês.
  Uma execução completa repete exatamente esta matriz para todos os doze
  idiomas de corpus existentes. Formulários, tabelas, conversas e outras
  amostras estruturais ainda não totalmente traduzidas mantêm-se, mas são
  indicadas separadamente e já não são misturadas nas quotas de idioma.

- **A execução completa escreve um relatório de medição próprio para cada
  idioma.** Sem indicador de idioma são verificados propositadamente alemão
  e inglês; `--alle-sprachen` exige o corpus completo de doze idiomas e
  interrompe antes do primeiro documento se faltar um idioma ou um caso.
  Resultados com o mesmo nome ficam em pastas de idioma separadas. O
  relatório geral indica, além da taxa de deteção ponderada, também a média
  não ponderada das taxas de idioma.

- **A comparação aberta de idiomas mostra agora também o seu limite real.**
  Na execução regular com reconhecimento de texto, o alemão e o inglês
  removem 218/218 indicações conhecidas sem falso alarme. O teste completo
  com reconhecimento de texto e nível avançado remove 1.255/1.308 indicações
  com 17 falsos alarmes; onze idiomas atingem 100 por cento, o hindi 51 por
  cento. As taxas completas anteriores baseavam-se em conjuntos de documentos
  e valores de referência desiguais e não são comparáveis com a nova matriz.

## 0.10.34-alpha.20260819 – 19 de agosto de 2026

### Corrigido

- **Nomes que ocorrem várias vezes permanecem acessíveis na barra lateral
  após uma única recuperação.** Até agora, toda a linha do nome desaparecia
  já depois do primeiro ponto `[NOME]` recuperado. Outros pontos do mesmo
  nome ficavam assim como marcadores por resolver e chegavam mesmo a ficar
  bloqueados temporariamente, até que outros nomes fossem recuperados. Agora
  a linha só desaparece depois do último ponto; texto simples já recuperado
  não volta, mesmo assim, a ser anonimizado automaticamente. Isto aplica-se
  também a uma recuperação coletiva parcialmente bem-sucedida e à ferramenta
  de moldura em PDFs.

- **„Anular substituição" funciona também a partir da pré-visualização do
  Office.** A página visível ali é apenas uma pré-visualização volátil em
  PDF; agora é corretamente alterado o documento Word, de folha de cálculo
  ou de apresentação subjacente, e em seguida a pré-visualização é
  atualizada.

- **A recuperação traz agora também de volta, na íntegra, as contrapartes
  ocultas de um valor.** Em ficheiros Word, OpenDocument, Excel e
  PowerPoint, os mesmos dados podem estar adicionalmente em fórmulas,
  comentários, gráficos, valores de campo, textos alternativos e destinos
  de referência; HTML, EML e MSG levam-nos ainda em atributos, JSON,
  cabeçalhos de mensagem e anexos. Até agora, consoante o formato, uma
  parte ficava como marcador. Agora, qualquer indicação oferecida na área
  de resultados pode ser recuperada de forma independente e em qualquer
  ordem. Metadados intencionalmente removidos, históricos de alterações e
  cabeçalhos de transporte continuam removidos por motivos de segurança.

- **Ao recuperar a partir de imagens, já não fica uma linha preta na
  margem.** Os limites direito e inferior de uma moldura eram, ao copiar a
  partir do original, definidos um pixel demasiado curtos. As coordenadas
  agora coincidem com a ocultação.

### Melhorado

- **A verificação de liberação envia agora cada uma das 22 extensões de
  ficheiro suportadas por um percurso completo.** Os ficheiros com
  conteúdo são limpos, todos os valores oferecidos são restaurados e, em
  seguida, verificados em profundidade. A isto juntam-se uma operação real
  da barra lateral, comparações de imagem ao nível do pixel e uma
  renderização visível em LibreOffice dos sete formatos de escritório. Os
  pequenos testes de regressão mantêm-se onde cobrem um caso próprio de
  erro ou segurança; foram eliminados um teste HTML comprovadamente
  duplicado e o teste do modo a preto e branco removido.

- **O corpus de medição completo desta versão está disponível para
  reprodução.** O pacote contém 294 documentos sintéticos em doze formatos
  e doze idiomas, 2.564 indicações conhecidas, quatro listas de referência
  legíveis por máquina e um guia. O descarregamento na página de qualidade
  usa um nome de ficheiro dependente do conteúdo, para que os navegadores
  não sirvam por engano uma versão mais antiga da cache.

## 0.10.33-alpha.20260819 – 19 de agosto de 2026

### Novo

- **Também nos ficheiros de imagem é agora possível recuperar pontos
  individuais a partir do original.** A ferramenta de moldura „Recuperar
  original" copia os pixels de volta na mesma posição a partir do ficheiro
  de origem intocado. O caminho permanece bloqueado se a origem faltar ou
  tiver dimensões de imagem diferentes; assim não é possível inserir
  conteúdo de um local deslocado.

### Melhorado

- **As barras de ocultação manuais encaixam agora por norma nas linhas de
  texto.** Um traço sobre várias linhas gera por linha uma barra de altura
  uniforme e deixa livre o espaço em branco entre elas. Para assinaturas,
  gráficos e outros casos especiais, „Moldura livre" volta à altura
  escolhida manualmente.

- **O editor explica o próximo passo diretamente por cima do documento.** A
  indicação muda consoante o tipo de documento e a ferramenta, e diz se se
  espera um clique numa palavra, uma seleção de texto ou uma moldura. Além
  disso, a ferramenta, o cursor do rato e a pré-visualização em tempo real
  já mostram, antes de soltar o botão, o que vai acontecer.

### Removido

- **A saída a preto e branco, propensa a erros, foi removida.** Em alguns
  PDFs, campos de texto invisíveis ficavam deslocados em relação à página
  rasterizada; a aparente redução do tamanho do ficheiro não valia este
  risco de segurança e de apresentação. A limpeza normal de PDF e a
  rasterização direcionada de páginas problemáticas mantêm-se.

## 0.10.32-alpha.20260819 – 19 de agosto de 2026

### Novo

- **A monitorização de pastas funciona agora realmente em segundo plano.**
  Entrada, saída e regras estão numa página própria em „Definições". É
  iniciada e interrompida através do ícone do Maskuro na barra de tarefas
  ou de menu; a entrada só aparece com a licença desbloqueada para isso. A
  janela de definições pode depois ser fechada e a janela principal
  minimizada para o ícone, sem terminar a monitorização.

- **O editor de correção tem agora um interruptor permanente de modo de
  aprendizagem.** Está na área de resultados e no menu „Ferramentas". Se
  for desligado, não aparecem perguntas sobre a criação de regras
  próprias, nem ao recuperar nem depois de correções manuais. O Maskuro
  memoriza a escolha para todos os documentos abertos no futuro; a
  recuperação em si funciona sem alterações.

### Corrigido

- **O grande modelo adicional volta a poder ser carregado.** O
  armazenamento público recusava com 403 a identificação padrão genérica
  do Python. Os pedidos de modelo usam agora a mesma via de rede própria
  identificada do Maskuro que os restantes serviços próprios; o ficheiro
  de quase 596 MB e a sua soma de verificação mantêm-se inalterados.

- **Uma lupa de comparação maximizada já não fica pendurada como uma
  barra estreita no rebordo superior ao ser ancorada.** Antes de ancorar,
  o seu estado de janela livre é normalizado. Um estado maximizado
  guardado é também reconduzido a um tamanho ajustável na próxima
  abertura.

- **Uma recuperação coletiva traz agora efetivamente de volta todos os
  valores selecionados em tabelas e outros formatos de texto.** Em
  marcadores anonimizados como `[EMAIL]`, o Maskuro escrevia até agora os
  valores em sequência. Assim que o primeiro era substituído, os números
  de todos os locais restantes avançavam, mas o plano já calculado ainda
  apontava para os números antigos. Com isso, só voltava parte da
  seleção. Agora todos os valores escolhidos do mesmo marcador são
  escritos em conjunto e com números de local estáveis. Se um local só se
  tornar inequívoco através de outro valor já recuperado, o Maskuro
  verifica-o novamente no mesmo passo – a ordem da seleção deixa assim de
  ter importância.

- **„Anular substituição" já não omite valores selecionados em PDFs.** Se
  um marcador estivesse muito próximo de outra palavra, ou se no original
  houvesse uma vírgula colada diretamente ao valor, a verificação de
  posição podia atribuir por engano a palavra vizinha ou o sinal de
  pontuação ao valor. Na recuperação conjunta, ficavam então marcadores e
  linhas de resultado por resolver. A verificação orienta-se agora pelo
  início real da palavra e considera também uma rotação de página
  diferente entre o original e o resultado.

- **O texto de PDF recuperado mantém agora o seu tamanho original.** Até
  agora, o marcador já definido mais pequeno servia de referência; além
  disso, o limite máximo de 11 pontos pensado para marcadores também se
  aplicava ao texto original. Agora, a caixa original e o tamanho de letra
  original são retomados do ficheiro de origem – tanto na ferramenta de
  moldura como ao recuperar a partir do painel de resultados.

### Melhorado

- **O aviso de verificação indica agora com mais clareza o risco
  residual.** Diz expressamente que o Maskuro pode não ver dados ou tratar
  indicações de forma incorreta, e exige uma verificação completa e, se
  necessário, uma correção manual antes de qualquer publicação ou
  partilha. Isto aplica-se também ao texto da área de transferência e foi
  atualizado por completo nas 17 traduções.

- **O registo de verificação arranca agora também sem nomes de utilizador
  dentro das suas linhas.** O próprio registo continua desativado até uma
  empresa o ativar deliberadamente. Depois disso, sem uma diretriz
  empresarial adicional, não consta nenhum nome de utilizador nem numa
  linha nem no nome de um ficheiro mensal central; aí serve para a
  separação segura um pseudónimo impossível de adivinhar, derivado apenas
  do segredo de perfil local aleatório. A caixa de diálogo de licença
  deixa de recomendar a ativação, pressupõe „Sem registo" e alerta
  previamente para o conselho de trabalhadores, a representação de
  pessoal e a proteção de dados.

- **Substituir indica agora o que substitui.** Um nome marcado torna-se
  `[NAME_3]`, um local torna-se `[ORT_1]`, um número de telefone torna-se
  `[TELEFON_2]` – em vez de tudo se tornar `[BEGRIFF_n]` como até agora. O
  tipo é reconhecido ao clicar; se não for inequívoco – uma palavra comum,
  ou um nome *e* um local numa seleção –, mantém-se o termo genérico. Um
  marcador que afirmasse um tipo incorreto seria pior do que um que não
  indicasse nenhum.

- **As ferramentas na janela de correção têm agora uma tecla.** **S**
  oculta, **E** substitui, **Z** recupera o original, **V** pixeliza. Na
  vista de texto atuam de imediato sobre a marcação, na pré-visualização
  de página selecionam a ferramenta. **As letras seguem o idioma** em que
  utiliza o programa – em inglês B/R/O/P, em italiano O/S/R/P –, pois uma
  regra mnemónica só ajuda no próprio idioma. A tecla está indicada no
  botão. Quem estiver a escrever na barra de pesquisa continua a escrever
  letras normalmente – ali não têm efeito.

- **O programa comunica uma vez por dia em que estado está a funcionar –
  sem qualquer identificação.** Com isso contamos quantas instalações são
  usadas e como isso se distribui por período de teste, nível gratuito e
  licença. É enviado o estado, o sistema operativo, a versão, o canal, o
  país, o idioma, o ambiente e o nível de deteção – **nada sobre os seus
  documentos e nada pelo qual o seu computador pudesse ser reconhecido**.
  Duas comunicações suas parecem-nos comunicações de duas pessoas
  diferentes; não é possível seguir a partir daí um único percurso. O que
  exatamente é enviado e como se pode desativar está descrito no texto de
  proteção de dados, no ponto 5.

- **As páginas digitalizadas na transversal ficam agora automaticamente na
  orientação correta.** Uma folha digitalizada torta, sem isso ficar
  assinalado, é reconhecida pela correção através do fluxo de texto, que
  endireita a vista. Onde isso não é possível – numa digitalização pura
  sem texto legível –, duas novas entradas no menu „Vista" rodam
  manualmente (Ctrl+Shift+L e Ctrl+Shift+R). Só a visualização é rodada:
  o ficheiro não sofre qualquer alteração, e a ocultação continua a
  atingir exatamente o local em que se clica.

- **A distribuição local documenta agora as suas licenças de forma
  completa e visível.** A construção apura os pacotes Python
  efetivamente incluídos, coloca os respetivos textos de licença com uma
  visão geral de versões em `lizenzen` e interrompe-se perante uma lacuna.
  Também o Qt, o Tesseract e o modelo de rostos têm os seus textos
  necessários; as condições do próprio Maskuro acompanham o pacote como
  contrato de licença.

- **Agora é visível em que marcador se encontra o cursor de escrita.**
  Quem clica num marcador vê-o acender por completo – com parênteses e
  número incluídos. O botão „Recuperar seleção" já reagia antes a um
  simples clique; só não era visível qual marca ele atingia. O brilho
  mantém-se mesmo quando o rato se desloca para o botão.

- **O cursor do rato indica agora qual a ferramenta selecionada.** Quatro
  ferramentas partilham a mesma área e o mesmo gesto; até agora todas
  pareciam iguais. Mira significa ocultar, mão fechada substituir, mão
  aberta recuperar.

- **Um documento do Office preparado é agora recusado pelo próprio
  programa.** Um ficheiro Word, Excel ou OpenDocument pode trazer
  instruções que, ao abrir, buscam um ficheiro alheio do seu computador
  para dentro do seu texto ou esgotam a memória. Ambos já eram recusados
  até agora – mas pela biblioteca XML incorporada, não pelo Maskuro. Agora
  é o próprio programa que decide, independentemente da versão dessa
  biblioteca que estiver no pacote. Para documentos comuns nada muda.

### Corrigido

- **O painel de resultados remove agora marcadores ocultados.** Se, por
  exemplo, `[NAME_1]` fosse ocultado na janela de correção, a sua linha de
  valor ficava até agora à direita, mesmo já não havendo tal local no
  documento. A linha desaparece agora com o último local encontrado; se
  o mesmo marcador ainda ocorrer noutro local, mantém-se.

- **Ao recuperar numa página rodada, a palavra vizinha permanece agora
  intacta.** A barra de ocultação ultrapassa propositadamente um pouco o
  texto; já esta margem estreita podia até agora levar consigo uma
  palavra adjacente como „no". Agora só conta uma sobreposição clara, não
  o toque na margem.

- **Uma segunda substituição na mesma linha levava consigo o resto da
  frase.** Quem substituísse „Sachbearbeitung Quaxi Blubbo übernimmt"
  duas vezes seguidas obtinha „Sachbearbeitung [ORT_1] [ORT_2]" – a
  palavra a seguir desaparecia sem substituto, sem qualquer aviso. A causa
  era o marcador ao lado: o resto da linha começa, após a primeira
  substituição, com um espaço, e a procura da sua posição de texto
  apanhava o parêntese de fecho do vizinho. Depois disso, tudo ficava
  deslocado um caráter. Era afetada toda a linha em que se substituía ou
  ocultava duas vezes – também ao recuperar ao lado.

- **Substituir deixa de ocultar quando o marcador é demasiado longo.** Se
  não houvesse espaço ao lado da palavra para `[BEGRIFF_2]`, a área era
  até agora pintada de preto – e assim já não se via sequer que ali tinha
  estado algo, muito menos era possível recuperá-lo. Agora é escrita uma
  forma mais curta: `[BEGR_2]`, `[BE_2]`, em último caso `[B_2]`. O número
  sequencial mantém-se em cada nível – é por ele que a recuperação
  reencontra o local. Só onde nem a forma mais curta cabe é que se mantém
  a barra.

- **Substituir deixava o texto por remover quando já se tinha ocultado na
  mesma linha.** Quem, na janela de correção, recuperasse um nome do
  original, substituísse depois o primeiro nome (não havia espaço ali –
  ficou uma barra) e a seguir substituísse o apelido, obtinha o marcador
  inserido, mas o nome **não removido**. Só foi detetado pelo aviso da
  segunda leitura. A causa estava na própria linha: depois da primeira
  ocultação, o resto dela começa com um espaço, e a procura da posição de
  texto não encontrava aí nenhum ponto de apoio. Isto afetava toda
  segunda ocultação na mesma linha.

- **Uma deteção avançada ativada sem o seu modelo é agora detetada.** A
  marcação podia estar ativa enquanto faltava o modelo – as definições
  aplicam-se a cada instalação, mas o modelo fica junto ao programa. A
  limpeza corria então sem esse nível, sem qualquer aviso. Agora a
  marcação indica que o modelo falta, e o resultado traz um aviso. A sua
  escolha, feita uma vez, permanece guardada: assim que o modelo estiver
  carregado, volta a fazer efeito.

- **Ao anonimizar, é agora recuperado o termo correto.** Quem substituísse
  vários termos manualmente e depois recuperasse um deles obtinha sempre
  o **primeiro** – de „Schmidt" resultava „Müller". A atribuição só
  memorizava uma substituição por marcador, e ao anonimizar todos usam o
  mesmo marcador; o segundo termo e todos os seguintes perdiam-se. Agora
  cada valor recebe a sua própria linha – também na lista de
  substituições, que antes era demasiado curta.

- **Em tabelas, agora também é possível recuperar.** Num CSV ou numa lista
  de pessoal, os marcadores estão diretamente lado a lado, separados
  apenas por ponto e vírgula. Até agora, o programa não conseguia
  determinar ali qual o valor que estivera em que local, e recusava – com
  `[NAME]` funcionava, com `[GEBURTSDATUM]` e `[TELEFON]` não. Agora
  decompõe a linha em todos os marcadores. Se um local permanecer
  realmente ambíguo, continua a recusar: um valor reposto incorretamente
  seria pior do que uma informação em falta.

- **E a recusa é agora visível.** Estava em cinzento discreto no rebordo
  inferior da janela, e a frase era tão longa que ficava cortada – parecia
  que nada acontecia. As frases foram encurtadas, e a linha brilha durante
  alguns segundos na cor de aviso.

- **Uma recuperação mantém-se agora também depois da próxima
  intervenção.** Quem, ao anonimizar, recuperasse vários locais e depois
  substituísse outra coisa, encontrava todos os locais recuperados de
  novo substituídos e tinha de recomeçar do início. A causa estava na
  atribuição: mantinha o valor, e o alinhamento automático para marcadores
  uniformes trazia-o de volta na escrita seguinte. Agora vale: o que
  recupera, fica recuperado – outros locais do mesmo valor não são
  afetados por isso.

- **Em ficheiros de texto, Word, Excel e e-mail, basta agora realmente um
  clique no marcador.** O aviso sobre isto já constava da versão
  anterior, mas o botão „Recuperar seleção" permanecia bloqueado enquanto
  nada estivesse exatamente marcado – não se chegava sequer ao caminho que
  teria definido a própria seleção.

### Corrigido

- **O registo de verificação já não revela o nome do ficheiro.** Regista
  os ficheiros propositadamente como valor de dispersão em vez de texto
  simples, porque um nome de ficheiro revela o cliente e o objeto do
  litígio. Mas este valor de dispersão podia ser confirmado por
  tentativa – um caminho não é um número aleatório. Agora entra no
  cálculo um valor aleatório desta instalação: contar e distinguir no
  registo continua a funcionar, recalcular a partir de fora já não.

## 0.10.31-alpha.20260819 – 19 de agosto de 2026

### Melhorado

- **Também em ficheiros de texto e de folha de cálculo o marcador acende a
  vermelho ao apontar.** Até agora, a pré-visualização a vermelho só
  existia numa página de PDF. Agora ambas as vistas mostram o mesmo: o que
  está a vermelho é atingido pelo próximo gesto – e basta um clique para
  recuperar.

- **Um clique numa palavra basta – o editor define o retângulo sozinho.**
  Na janela de correção era preciso, até agora, arrastar um retângulo
  sobre cada local. Agora basta um clique: a moldura ajusta-se à palavra e
  permanece ativa, podendo assim ser ainda ampliada ou deslocada. Ao
  apontar com o rato, a palavra já acende a vermelho, para que se veja
  antecipadamente o que o clique atingiria. Onde não há palavra, arrasta-se
  uma moldura como até agora.

- **Já não é preciso apontar com precisão com o retângulo.** Quem arrasta
  um retângulo sobre um marcador ou uma ocultação refere-se sempre ao
  local inteiro – nunca a metade dele. Por isso, a moldura cresce
  automaticamente até ao todo que toca: até ao marcador inteiro, à barra
  inteira ou, numa folha digitalizada, à área ocultada inteira. Nunca fica
  mais pequena do que a moldura arrastada.

- **Agora a ocultação é feita palavra a palavra.** Uma moldura sobre
  metade de uma palavra ocultava até agora também só metade – e um nome
  meio ocultado continua a ser um nome. As palavras tocadas caem agora por
  inteiro; a vizinha permanece intocada.

- **Em texto e folhas de cálculo, basta um clique no marcador.** „Recuperar
  seleção" exigia até agora que se marcasse com exatidão o marcador
  incluindo os parênteses retos. Agora basta colocar o cursor lá dentro; a
  seleção salta visivelmente para o marcador inteiro.

- **A Bélgica foi adicionada como país.** Selecionável nas definições;
  passam a ser reconhecidos números de telefone belgas, o número de
  registo nacional (Rijksregisternummer, com dígito de controlo), o número
  de IVA/empresa (BTW, com dígito de controlo), moradas em ambas as
  línguas oficiais e o código postal com localidade. Até agora, os números
  de telefone belgas permaneciam por não haver sequer o país no catálogo.

- **O canal de atualização diz agora quão cedo recebe novidades – não até
  onde.** Quem estivesse em „Versão de teste" não via sequer oferecida
  uma nova pré-visualização ou uma nova versão estável, e tinha de mudar
  de canal manualmente para sequer saber disso. Agora é oferecido também
  tudo o que é mais fiável: Versão de teste recebe versões de teste,
  pré-visualizações e versões estáveis; Pré-visualização recebe
  pré-visualizações e estáveis. Nunca ao contrário – em Pré-visualização
  não é oferecida nenhuma versão de teste, mesmo que seja mais recente.

- **Na janela de definições, as linhas voltam a estar mais afastadas.** As
  quatro páginas usavam espaçamentos próprios em vez da grelha que vale no
  resto do programa; especialmente na página „Deteção" as caixas de
  verificação ficavam por isso visivelmente demasiado apertadas.

### Corrigido

- **Os formulários PDF preenchidos já não aparecem vazios na edição
  manual.** Para isso, o Maskuro converte exclusivamente a cópia de
  trabalho volátil em páginas estáticas: os valores inseridos tornam-se
  visíveis e podem ser efetivamente ocultados; campos de formulário
  legíveis não ficam ocultos no ficheiro. O original permanece interativo
  e inalterado. Isto aplica-se agora também a formulários XFA dinâmicos:
  um PDFium com suporte a XFA constrói primeiro os valores e as quebras de
  página, e só depois é gerado um novo PDF exclusivamente a partir de
  páginas de imagem estáticas. Se a construção XFA falhar, o ficheiro é
  recusado com segurança em vez de ser aberto aparentemente vazio.

- **„Cancelar" atua agora também durante a deteção mais rigorosa.** Até
  agora, o botão bloqueava-se ao clique, mas a execução continuava a
  calcular até ao último bloco – num ficheiro longo são minutos sem saída,
  e o botão parecia ter surtido efeito. Agora a execução termina no bloco
  seguinte.

- **Em ficheiros CSV, os nomes são agora encontrados mesmo quando não há
  espaço antes deles.** Em `P-1000;Brunnthaler, Elisabeth`, o número de
  pessoal cola-se ao nome através do ponto e vírgula, e para a deteção
  isso era uma única palavra sem nome dentro – em listas de pessoal, o
  nome inteiro permanecia, consoante a linha. Números de telefone,
  fórmulas e o número de colunas do ficheiro não são afetados por isto.

- **Um nome cujo primeiro nome e apelido têm ambos hífen é agora
  reconhecido.** „Marie-Luise Habsburg-Ott" permanecia no meio da frase,
  enquanto „Dragan Mitrović" na mesma frase era encontrado – precisamente
  a combinação de duas metades ligadas escapava ao modelo de linguagem.
  Substantivos comuns ligados como „Nord-Süd-Verbindung" ou
  „Software-Entwickler" não são afetados por isto.

## 0.10.30-beta.1 – 18 de agosto de 2026

### Melhorado

- **O tamanho de letra da vista de texto pode agora ser ajustado
  visivelmente.** O cursor em baixo à direita, que até agora só ampliava
  na pré-visualização de página, ajusta agora, na janela de correção, o
  tamanho de letra (50–300%) em ficheiros de texto e do Office – tal como
  „Ampliar"/„Reduzir" no menu Vista. Ctrl+roda do rato já sempre
  conseguia isso, mas só quem tinha experimentado é que sabia; agora
  cursor, indicação e roda funcionam em conjunto.

- **Na aparência escura, está agora uma folha branca sobre uma área de
  trabalho escura.** Até agora era ao contrário: à volta da folha
  mantinha-se uma área clara, e o próprio texto estava claro sobre
  escuro. Agora a folha mantém-se, em ambas as aparências, branca como
  papel com letra preta – tal como uma página de PDF, que também não
  fica escura no modo escuro – e a área à volta é escura.

### Corrigido

- **Depois de uma ocultação a meio de uma frase, o resto da frase deixa
  de se perder.** Quem, na janela de correção, atuasse três vezes sobre o
  mesmo local – substituir, ocultar, depois „Recuperar original" – via o
  início da frase apagado: de „Para questões, contacte a
  Contabilidade." resultava „contacte a Contabilidade.", sem aviso. Era
  afetado qualquer local onde já se tivesse removido algo a meio de uma
  linha.

- **Um erro de arranque deixa de arrastar consigo o encerramento.** Quando
  a construção da janela principal falhava, o encerramento a partir do
  ícone da barra de tarefas também falhava depois – e este segundo erro
  ocultava, no relatório de erro, a causa real. Agora o programa
  encerra-se corretamente mesmo a partir de uma janela meio construída, e
  as definições guardadas permanecem intocadas.

- **„Antes/Depois" deixa de saltar para o início do documento.** Quem, na
  janela de correção, tivesse rolado para baixo e mudasse para o
  original para comparar, acabava de novo lá em cima – e tinha de
  reencontrar o local manualmente. A vista mantém-se agora na mesma
  linha, em ambas as direções.

- **Ao ocultar, ficava a última letra em linhas de texto justificado.**
  Quando um comando de texto desenha mais glifos do que a biblioteca de
  leitura reporta carateres – engole de bom grado um espaço em texto
  justificado –, a atribuição deslocava-se em um, e de „Dr. Michael
  Handler aus Willendorf" resultava „[NAME] r aus f": duas letras
  remanescentes a meio da frase limpa (encontrado numa ata real de
  câmara). A atribuição é agora reverificada com base no texto literal do
  próprio comando, onde este é legível – deixa de ser adivinhada.

- **„Lerchenfelder Gürtel 43/12" só era removido a meio.** Os padrões de
  morada não conheciam Gürtel, Kai, Lände, Zeile, Markt nem Graben como
  palavra-base de rua, e o número de porta não podia ter partes com
  barra (43/12, casa/porta) – o número ficava ao lado do marcador.
  Ambos foram acrescentados; moradas de Viena e Salzburgo caem agora por
  inteiro.

- **As páginas web guardadas continuam funcionais depois da limpeza.** Os
  endereços que o carregamento lento (lazy-loading) guarda em atributos
  data (`data-lazy-src`, `data-lazy-srcset`) eram substituídos como
  referências – numa página real de câmara municipal, dezasseis – e as
  imagens da página deixavam então de carregar. Os endereços web ficam
  agora ali, tal como em `src` e `href`; nomes, endereços de e-mail e
  números de telefone em atributos data continuam a ser substituídos.

- **Documentos em japonês e coreano corriam como chinês.** A deteção de
  idioma juntava as três escritas, não encontrava palavras funcionais em
  texto japonês (sem espaços) nem coreano (com partículas coladas) – e
  usava então simplesmente o primeiro idioma CJK do catálogo. Uma ata de
  câmara japonesa e uma ata de reunião coreana eram assim lidas com o
  modelo chinês. Agora decide o próprio aspeto da escrita: kana significa
  japonês, hangul significa coreano.

- **Mais deslizes do teste de campo em dez outros idiomas:** cargos como
  „Primar", „Gradonačelnik", „Ordfører", „Başkanı" ou „Δήμαρχος" deixam
  de valer como nomes de pessoa; legendas de campo turcas („Adı",
  „Soyadı") e palavras de conversa gregas („Ωραία", „Βεβαίως") deixam de
  cair; números de decisão e de parágrafo com data („323/25-6-2008",
  „27 30.09.2024") deixam de ser números de telefone; e fragmentos de
  frase com ponto („10.An", „T.U.EE", „…pa") deixam de ser substituídos
  como endereços web.

### Novo

- **Relatórios de verificação automáticos a pedido.** Uma marcação nas
  definições (página „Programa") cria, por si só, depois de cada
  limpeza, um PDF de relatório de verificação – com data e hora no nome,
  numa pasta própria, nunca ao lado do resultado. Não é possível gerar
  uma folha a posteriori; quem precisa dela para o processo, tem-na
  sempre assim. Por defeito, o arquivamento está desligado.

- **O registo de verificação pode agora ser ativado no programa.** Ao ler
  uma licença empresarial, o Maskuro pergunta uma vez se o registo deve
  ser mantido – um comprovativo só vale se correr desde o início. Para
  isso há um interruptor nas definições (página „Programa", visível com
  licença empresarial ou no período de teste); o ficheiro de diretrizes
  da administração continua a valer e pode forçar o valor como até
  agora. Uma linha de registo própria „ativado" regista desde quando é
  mantido – assim fica também comprovado e assinado o início do
  registo. Por defeito, o registo permanece desligado.

- **O painel de indicadores mostra o que o nível de IA fez.** Uma nova
  linha indica quantos resultados incertos o modelo avaliou, manteve e
  descartou, e quantos encontrou adicionalmente – até agora, o seu
  trabalho era invisível a menos que se clicasse em cada valor no editor
  de correção. Apenas números, nunca valores ou justificações; sem
  trabalho de IA, a linha não aparece.

- **Recuperar funciona agora também em e-mails e páginas HTML.** Em
  `.eml`, `.msg` e páginas web guardadas não era até agora possível
  anular um marcador – a aplicação dizia-o honestamente, mas é
  precisamente o e-mail o formato com mais dados pessoais. Agora a
  recuperação funciona da mesma forma ali: a partir do painel de
  resultados, com seleção marcada e também com marcadores anonimizados.
  O ramo HTML invisível de um e-mail (o que o Outlook realmente mostra) é
  atualizado em conjunto, para que a vista e a mensagem digam o mesmo.

- **O painel de resultados recupera também valores anonimizados – por
  valor.** „Anular substituição" estava até agora bloqueado em ficheiros
  anonimizados, porque „[NAME]" vale para todos os nomes ao mesmo tempo.
  Agora a recuperação consulta o original para saber a que valor
  pertence cada local – no PDF pelas coordenadas do local encontrado, na
  vista de texto por comparação com o original – e recupera exatamente
  os locais do valor escolhido. As linhas dos restantes valores mantêm-se.

- **Também os marcadores anonimizados podem ser recuperados
  individualmente.** Ao anonimizar, todas as indicações de um tipo têm o
  mesmo nome – „[NAME]" vale para cada pessoa, e até agora isso queria
  dizer: não é possível recuperar individualmente. Agora consulta-se o
  original, que de qualquer forma está ao lado do resultado: na vista de
  texto, marcar o marcador e escolher „Recuperar seleção" – volta
  exatamente esse local com exatamente o seu valor. Se o valor não puder
  ser lido do original sem ambiguidade, a aplicação diz-o, em vez de
  adivinhar. Um ficheiro de atribuição continua a não ser criado nesse
  caso.

- **A janela de correção abre-se sozinha depois da limpeza.** Nenhuma
  ferramenta encontra tudo – por isso o olhar de verificação sobre o
  resultado passa a ser o caso normal, não um clique extra. Quem não
  quiser isto desativa-o nas definições, em „Deteção" („Mostrar resultado
  depois na janela de correção").

### Melhorado

- **A seleção de país passa agora a „automática".** Até agora valia, de
  fábrica, o espaço linguístico da interface – num computador alemão,
  também documentos neerlandeses ou franceses eram limpos apenas com os
  detetores DACH, e uma morada como „Universiteitslaan 1" permanecia
  (encontrado em atas de câmara reais e públicas). Agora a seleção de
  país orienta-se pelo idioma do documento; quem tiver feito uma escolha
  fixa nas definições mantém-na.

- **Menos ocultações erradas.** Uma série de deslizes, medidos no corpus
  de verificação e em atas de reunião reais em seis idiomas, deixa de
  ocorrer: nomes de empresa com forma jurídica („Musterfirma GmbH")
  deixam de valer como pessoa ou local, passando a valer como
  organização; fórmulas de saudação e saudações nuas („Saygılarımızla",
  „Buenas tardes", um „Frau" isolado) deixam de ser nomes; cargos
  („Bürgermeister", „Sindaco", „Alcalde") permanecem; números de lei e de
  decisão („39/2015") e montantes com ponto de milhar („330.000") deixam
  de ser números de telefone; inícios de frase como „Envíame" ou
  „Estarei" deixam de cair como nome; um resultado que atravesse uma
  linha vazia deixa de contar como nome. O número da fatura de uma
  fatura mantém-se como referência de documento – número de cliente e
  referência de processo continuam a cair.

- **Antes de carregar o modelo de IA, consta agora para que serve.** A
  caixa de diálogo de carregamento indica as tarefas do modelo –
  avaliar resultados limítrofes, encontrar nomes adicionais, sugerir
  regras e perfis – e diz abertamente que não é um assistente de
  conversa. As perguntas frequentes respondem à mesma questão de forma
  detalhada („O que pode e o que não pode o nível de IA?"), em todas as
  traduções.

### Corrigido

- **Os PDFs de relatório de verificação a partir da linha de comandos já
  podem ser pesquisados.** No Windows, o caminho de PDF sem interface
  arrancava sem uma única letra tipo – cada carácter era desenhado como
  caixa substituta, e a folha não trazia texto legível: quem quisesse
  pesquisar ou copiar algo dali não encontrava nada. Agora, nesse caso, o
  relatório carrega os tipos de letra do sistema; o texto fica incorporado
  e legível. Os relatórios gerados a partir da janela nunca foram
  afetados.

- **„Recuperar original" sobre várias linhas de uma digitalização deixava
  faixas pretas entre as linhas.** Numa página convertida em imagem, a
  moldura limpava apenas as próprias faixas de linha; os restos da
  ocultação anterior mantinham-se nos espaços entre elas. Agora a moldura
  arrastada divide-se por completo pelas linhas.

- **Uma segunda moldura sobre um marcador deixava um resto vermelho.** O
  marcador é quase sempre mais largo do que a palavra que representa;
  quem depois ocultasse sobre o mesmo local atingia só o seu início –
  ficava um fragmento como „RIFF_1]" a meio da frase, e a recuperação
  colocava depois o texto original nesse local em vez de no da palavra.
  Um marcador cortado cai agora sempre por inteiro.

- **Numa página rodada, ocultar sobre um marcador apagava uma frase sem
  relação.** O marcador desenhado posteriormente era confundido, ao
  remover, com o texto anterior: ele próprio permanecia, aparecia o aviso
  „ainda está no documento" – e, noutro local da página, desaparecia sem
  substituto uma frase que nada tinha a ver com a moldura. Um marcador é
  agora reencontrado pelo seu texto literal; a cadeia „substituir,
  ocultar, recuperar" funciona assim também em páginas digitalizadas na
  transversal.

- **O manual ainda recomendava `python3-tk` em dez idiomas.** Na resolução
  de problemas constava que, no Linux, podia faltar o tkinter – um
  conselho de antes da interface Qt, que já não ajuda ninguém. Agora
  consta, em todas as versões, o mesmo parágrafo que em alemão: faltam
  as bibliotecas de sistema de que o Qt precisa para a apresentação.

- **O capítulo de licença do manual estava desatualizado nas dezasseis
  traduções.** Em dez idiomas lia-se ainda que o Windows Server precisava
  de uma licença empresarial com acesso de servidor e que ali não havia
  período de teste nem nível gratuito – desde que um lugar conta uma
  pessoa e não uma máquina, ambas as afirmações são falsas. Faltavam
  também, em todo o lado, as informações sobre quando um lugar ocupado
  volta a ficar livre, que a licença se confirma regularmente e o que é
  transmitido nesse processo, e a ativação sem Internet constava apenas
  como versão resumida, sem os três passos e sem o aviso de que o
  computador funciona depois um ano sem ligação.

- **Faltavam sete parágrafos sobre a correção em dez idiomas.** Quem lesse
  a ajuda em dinamarquês, finlandês, francês, italiano, neerlandês,
  norueguês, polaco, português, sueco ou espanhol não encontrava nem a
  pré-visualização de página para ficheiros do Office, nem „Ocultar
  manualmente", nem toda a secção sobre como o programa aprende com uma
  correção – incluindo a tabela com as três larguras. Em „O que é
  detetado" faltava, nas mesmas dez versões, o caminho através da legenda
  no documento.

- **Com uma licença lida, o programa deixava de arrancar.** Em vez da
  janela, aparecia „Não foi possível iniciar o programa" – e isso com
  qualquer licença, seja qual fosse. A causa era a linha na exibição da
  licença que avisa pouco antes do fim do prazo de teste; acedia a algo
  que ali não estava disponível. Sem licença – no período de teste e no
  nível gratuito – o erro não ocorria, por isso só agora foi detetado.

- **No formulário, os nomes de campo mantêm-se.** „Data de nascimento" e
  „Morada" desapareciam com o seu valor: o marcador ficava pequeno e
  vermelho no lugar do *nome do campo*, e o campo por baixo ficava vazio.
  O nome do campo não faz parte dos dados – mantém-se agora, e o
  marcador fica onde estava o valor.

- **Títulos de documento em idioma estrangeiro deixam de ser tomados por
  nomes.** Por cima de um formulário italiano constava „FATTURA", por
  cima de um espanhol „PERMISO PARENTAL" – ambos eram substituídos. A
  lista de palavras de documento só conhecia os equivalentes em alemão.

- **De uma fatura já não desaparece nenhuma posição.** „Materialaufschlag
  1  84,00" era tomado por uma morada e substituído por um marcador de
  local – ao documento faltava depois uma linha. Uma linha que termina
  com um montante é uma posição e não uma morada; moradas reais
  („Hauptstraße 1  120,00") não são afetadas.

### Alterado

- **„Monitorizar pasta…" e a linha de comandos deixam, por agora, de
  estar disponíveis.** Ambos os caminhos estão construídos e funcionam,
  mas nenhum dos dois foi testado em escala: a monitorização de pastas
  nunca teve um teste no Windows, e a linha de comandos dá a um script
  duas dezenas de opções que nunca correram em nenhum utilizador. O que
  altera documentos sem supervisão não deve fazê-lo sem verificação – por
  isso foram retirados até o teste ser feito. A entrada de menu falta, e
  `--wache` já não consta em `maskuro --help`.

- **Mantém-se o que apenas lê e o que de qualquer forma é necessário.** A
  execução de pesquisa (`--suchlauf`) e a verificação (`--nachpruefen`)
  continuam a funcionar na linha de comandos – não alteram nenhum
  ficheiro. Da mesma forma o arranque através do Explorador, do menu de
  contexto, da área de transferência e da janela; nada disso muda.

- **„Obter do scanner" tem agora um capítulo próprio no manual.** Estava
  até agora no final de „Monitorizar pasta". No Mac, o conselho ali dizia
  para monitorizar uma pasta; agora diz para arrastar as páginas
  digitalizadas para a janela.

### Corrigido

- **„Recuperar original" sobre várias linhas destruía a estrutura.** Uma
  moldura sobre um marcador, um cargo inalterado e uma segunda
  substituição inseria toda a área de novo como **uma** linha – de três
  linhas resultava uma, e o que já não cabia tornava-se uma barra. Agora
  cada linha é recuperada por si só.

- **E o texto inalterado permanece intocado nesse processo.** Quem
  arrastar sobre uma substituição *e* texto comum recupera apenas a
  substituição; o resto não é tocado. Também o último resto do marcador
  antigo desaparece nesse processo – antes, o seu parêntese de fecho
  ficava a meio da frase.

- **Ao substituir, deixam de ficar restos do texto antigo.** Num
  título a negrito ficava depois „1. R[BEGRIFF_2]ige [BEGRIFF_1] …
  che" – o marcador estava lá, mas com sílabas do original ao lado.
  Agora é limpa a área que se contorna, não apenas as caixas das
  palavras dentro dela.

- **Um marcador anónimo deixa de ser recuperado incorretamente.** Ao
  anonimizar, cada nome recebe o mesmo `[NAME]`. A recuperação usava a
  primeira entrada disponível e escrevia-a em cada local encontrado – de
  „Georg Aigner" resultava „Anna Musterfrau", ou seja, um nome errado no
  documento. Agora consta ali que já não é possível dizer qual a
  indicação pretendida; o documento permanece intocado.

### Novo

- **„Recuperar original" funciona agora também numa página
  rasterizada.** Se uma página tivesse sido convertida em imagem,
  aparecia até agora uma recusa: o texto recuperado ficaria por baixo da
  imagem da página. Agora o local é limpo na imagem e o texto é escrito
  por cima – como um marcador numa digitalização. O conteúdo vem, nesse
  caso, do ficheiro original, que não está rasterizado.

- **„Recuperar seleção" passa agora a ser um botão próprio.** Já
  funcionava antes, mas só se, por acaso, se marcasse um marcador e se
  premisse „Substituir seleção" – uma função que só se encontra por
  acaso não existe, para o utilizador.

### Alterado

- **Em texto simples, CSV e mensagens do Outlook, deixa de haver
  „Ocultar seleção".** Estes formatos não podem conter uma barra; o
  botão colocava ali um marcador e dizia-o também – mas um botão que faz
  algo diferente do que o seu nome indica não tem lugar ali.

- **Uma ferramenta diz agora quando não tem nada a fazer nesse local.**
  Um marcador não pode ser substituído outra vez, sobre uma ocultação não
  é colocado nenhum marcador, e onde já está o original não há nada a
  recuperar. Até agora, estes gestos faziam algo que parecia ter efeito,
  mas não tinha nenhum.

## 0.10.29-alpha.20260817 – 17 de agosto de 2026

### Corrigido

- **Na janela de correção, agora atua toda moldura que se arrasta.** Quem
  trabalhava duas vezes no mesmo local – primeiro substituir, depois
  ocultar, depois recuperar o original – via o segundo e o terceiro gesto
  desvanecerem-se silenciosamente: a moldura ainda ativa do gesto anterior
  interceptava-o. O mesmo acontecia ao mudar de ferramenta, em que a
  ferramenta antiga continuava a atuar sem aviso.
- **Uma moldura demasiado estreita diz que é demasiado estreita.** Até
  agora, a pré-visualização acendia uma palavra a vermelho, e ao soltar
  não acontecia nada, sem aviso.

- **As mensagens do Outlook já podem finalmente ser corrigidas.** Um
  `.msg` mostrava na janela de correção „Este formato não pode ser exibido
  aqui" – era o único formato suportado sem qualquer forma de correção
  manual. Agora o remetente, o destinatário, o assunto e o corpo da
  mensagem aparecem identificados na vista e podem ser marcados e
  substituídos como em qualquer outro formato de texto.

- **„Substituir seleção" mantém-se na seleção num e-mail.** Quem
  marcasse um nome no texto corrido perdia com isso também o remetente e o
  destinatário dos cabeçalhos, e a mensagem indicava um marcador diferente
  daquele que estava no texto. Agora o valor marcado é substituído em
  todo o lado – também no remetente, se for aí que está – e mais nada é
  alterado.

- **Uma moldura sobre várias linhas já não destrói o texto.** Até agora
  surgia um único marcador num só local: da palavra cortada ficava um
  resto colado a ele, e da segunda linha o texto desaparecia sem
  substituto – nem marcador, nem barra, apenas um vazio. Agora cada linha
  recebe o seu próprio marcador com o valor que realmente lá estava.

- **„Recuperar original" funciona agora também depois de uma ocultação.**
  A janela indicava sucesso, e o texto nunca mais voltava: a barra preta
  contava como obstáculo, pelo que já não havia espaço para o texto
  recuperado. A barra recua agora, e o texto recuperado aparece a preto
  como texto normal – não a vermelho como um marcador.

- **„Recuperar original" num local intocado já não faz nada.** Quem
  arrastasse a moldura sobre texto onde nada tinha sido alterado via o
  texto removido e reinserido mais pequeno e deslocado – sendo indicado
  sucesso. Agora aparece a indicação de que não há nada a recuperar.

### Novo

- **Também é possível ocultar em Word, Excel, PowerPoint, OpenDocument e
  texto.** Até agora só havia ali „Substituir seleção"; uma barra estava
  reservada à vista de PDF, sem que houvesse razão para isso. Onde uma
  barra não é representável – em texto simples e numa mensagem do
  Outlook –, o valor continua a ser substituído por um marcador como
  antes, e é isso que consta também na mensagem.

- **Marcar um marcador recupera-o.** Na vista de texto (Word, Excel,
  PowerPoint, OpenDocument, Texto), basta agora marcar o marcador e
  premir „Substituir seleção": o valor original volta. Até agora a janela
  remetia para isso o painel de resultados.

- **Os intervenientes numa ata de reunião são reconhecidos mesmo quando o
  seu nome é também uma palavra comum.** „Gruber: A receção ocorre na
  próxima semana." era substituído, „Bauer: Concordo." permanecia – o
  apelido parece, para a deteção, um substantivo comum. Linhas de aviso
  da mesma estrutura permanecem intocadas: de „Atenção: A instalação deve
  ser desligada." não resulta um nome.

- **„Está a usar a versão mais recente" era dito mesmo quando não era
  possível verificar.** Se o servidor de atualização recusar o pedido –
  porque chegaram demasiados pedidos do mesmo endereço de Internet ou
  porque ele próprio está com problemas –, o programa ficava parado na
  sua versão antiga e afirmava ser a mais recente. Foi exatamente isso
  que aconteceu a 17 de agosto num Mac: a 0.10.25 ficou parada, enquanto
  a 0.10.28 estava disponível há horas.

  Agora a janela diz o que se passa, indica a hora da próxima verificação
  – e assinala expressamente que **não** está estabelecido se a própria
  versão é a mais recente.

  Na maioria dos casos, a causa não está no próprio computador: em muitas
  ligações, vários clientes partilham o mesmo endereço de Internet, e o
  servidor conta-os em conjunto. Por isso, o Maskuro procura a lista de
  versões neste caso por uma **segunda via** e, ainda assim, encontra
  normalmente versões novas. Se a recusa persistir, o servidor é deixado
  em paz até à hora indicada – mesmo que se prima o botão outra vez;
  insistir só prolonga o bloqueio.

- **Indicações de quantidade já não são tomadas por nomes de
  localidade.** Num contrato de prestação de serviços, „Vier-Tage-Woche"
  (semana de quatro dias) desaparecia atrás de um marcador de local – em
  pleno objeto do contrato. Tais combinações de palavras com número e
  hífen („Drei-Punkte-Plan", „24-Stunden-Dienst") permanecem agora. As
  moradas ficam excluídas disto: um „Zwei-Brüder-Weg" continua a ser
  substituído.

## 0.10.28-alpha.20260817 – 17 de agosto de 2026

### Alterado

- **Os lugares de licença são agora efetivamente contados.** Até agora,
  nenhum posto de trabalho se registava alguma vez no serviço de
  licenças – uma licença de dez lugares corria em quantos computadores se
  quisesse, sem que ninguém soubesse. Novo: o computador que inicia o
  programa ocupa um lugar; um lugar fica livre automaticamente ao fim de
  **sete dias sem arranque**, para que um dispositivo avariado ou um
  colaborador que saiu não bloqueie nada de forma permanente.

  Um pequeno excesso é aqui **apenas indicado e não bloqueado**: até dez
  por cento acima do número comprado, todos continuam a trabalhar – o
  portátil novo ao lado do antigo ainda registado não deve ser motivo
  para contactar o apoio ao cliente. Quem exceder esse limite passa para o
  nível gratuito e é avisado disso; os computadores que já lá estavam não
  notam nada.

- **Uma licença comprada confirma-se regularmente.** Se isso não for
  possível durante **30 dias**, vale o nível gratuito até voltar a ser
  possível. Nada é desligado, e a partir de uma semana antes aparece o
  aviso na janela. Assim que o computador volta a ter Internet, isto
  resolve-se por si só. O período de teste e o nível gratuito continuam a
  não comunicar nada – quem nunca compra, nunca telefona.

- **„Ativar sem Internet" funciona finalmente.** A ativação era, até
  agora, verificada e guardada, mas depois não era lida por ninguém – não
  alterava nada nos direitos. Agora é a saída para computadores sem
  acesso à rede: é válida durante **um ano**, depois disso obtém-se uma
  nova com um código de pedido novo. É necessário um dispositivo com
  Internet uma vez por ano para isso – o próprio computador permanece
  offline de forma permanente.

- **A ativação também pode agora ser feita a partir da conta de
  cliente** – em „As minhas licenças" no site. Aí consta também quais os
  computadores associados à sua licença e quando os respetivos lugares
  voltam a ficar livres; isso não era visível em lado nenhum até agora. A
  página sem sessão iniciada mantém-se para quem não tem acesso à loja –
  em troca, exige adicionalmente o endereço de e-mail da encomenda, para
  que a chave de licença sozinha não seja suficiente.

- **E na janela consta agora para onde enviar o código de pedido.** O
  processo em papel dizia „introduzir num dispositivo com ligação à
  Internet" e não indicava nenhum endereço; a página de ativação já
  existia há muito, mas não estava ligada a partir de lado nenhum. Agora
  consta **maskuro.com/lizenz-freischalten** na caixa de diálogo, no
  manual e nas perguntas frequentes – e no site, por baixo da chave de
  licença.

- **O botão „Ativar sem Internet…" permanece visível**, mesmo quando a
  licença não é válida no momento. Antes desaparecia junto com ela – ou
  seja, exatamente quando é necessário.

- **„Todos os lugares ocupados" diz agora a verdade.** O aviso terminava
  com „O programa continua a funcionar sem alterações"; isso deixa de ser
  verdade quando não foi atribuído nenhum lugar. Ali consta agora que,
  até nova ordem, vale o nível gratuito.

### Novo

- **Ao ativar a limpeza da área de transferência, consta agora que é
  preciso verificar.** A mensagem passa a indicar a mesma frase que
  também consta no resultado de um ficheiro: o Maskuro não deteta, em
  todos os casos, todos os dados pessoais.

  Aqui pesa mais do que noutros locais. Num ficheiro vê-se o resultado
  antes de o entregar. Na área de transferência não – copia-se, cola-se,
  e o texto limpo já está na janela de e-mail. A mensagem diz por isso
  expressamente para rever o texto **colado**.

  Aparece ao ativar, não a cada cópia: o que aparecesse cinquenta vezes
  por dia, já ninguém leria a partir da terceira vez.

- **„Copiar tudo" por baixo da lista – e „Remover tudo" afasta-se.** O
  novo botão coloca de uma vez todos os resultados concluídos na área de
  transferência, para anexar a um e-mail ou colar noutro programa. Até
  agora isso só era possível pelo menu, e mesmo aí apenas para as linhas
  **selecionadas** – quem quisesse todas tinha primeiro de premir Ctrl+A.

  Com isto, a linha de botões foi reordenada: à esquerda está o que
  acrescenta algo, à direita, depois de um espaço, o que remove algo.
  „Remover tudo" estava até agora imediatamente ao lado de
  „Adicionar…", e um deslize custava a lista inteira. A mesma regra já se
  aplica, desde 13 de agosto, a cada linha concluída.

- **Postos de trabalho sem Internet recebem agora os seus modelos de
  idioma de dentro de casa.** Limpar sempre funcionou ali sem ligação – o
  carregamento posterior de um modelo de idioma não, e um modelo pesa
  várias centenas de megabytes.

  A administração reúne os ficheiros uma vez num computador com ligação e
  coloca-os numa partilha, no processo de implementação ou numa pen. O
  local é registado centralmente (campo `modellquelle` em `vorgaben.json`
  ou a variável de ambiente `MASKURO_MODELLQUELLE`). A partir daí, cada
  carregamento posterior serve-se primeiro dali – modelos de idioma, o
  dicionário japonês e o nível avançado – e só vai à rede se faltar um
  ficheiro.

  As somas de verificação continuam a aplicar-se sem alteração. Uma
  partilha de ficheiros interna é muitas vezes mais fácil de descrever
  do que um lançamento na rede; não deve tornar-se o caminho mais cómodo
  para um modelo introduzido sub-repticiamente.

  Como se constitui um tal acervo e como funcionam a licença e a ativação
  sem Internet consta em `OFFLINE.md`.

- **„Recuperar original" – uma moldura recupera o que foi removido a
  mais.** Na janela de correção há uma nova ferramenta: arrastar a
  moldura sobre o local, e o texto volta a estar lá como estava no
  original.

  Isto fecha a lacuna que o painel de resultados deixava em aberto. Ali só
  era possível anular uma substituição se o seu marcador fosse
  inequívoco – portanto não ao anonimizar, onde „[NAME]" aparece em
  qualquer indicação deste tipo, e de todo não em locais ocultados, onde
  não sobra nenhum marcador. É precisamente aí que se acumulam os
  deslizes: „Utilizador", „Número de inventário", „Assinatura" são
  facilmente tomados por nomes.

  A moldura não precisa do marcador: o **local** vem do retângulo, o
  **conteúdo** do ficheiro original – o mesmo que o alternador
  antes/depois mostra. Anonimizado ou pseudonimizado deixa assim de
  importar.

  O texto recuperado aparece a preto, não a vermelho: volta a ser texto
  simples e não um marcador. Uma entrada só desaparece da lista de
  resultados quando o seu marcador **não** aparece mais em lado
  nenhum do documento – se o mesmo valor tiver sido substituído em
  vários locais, permanece para os restantes.

  Numa página que foi convertida em imagem, a ferramenta recusa e explica
  porquê: o texto recuperado ficaria por baixo da imagem da página e não
  seria visível.

### Corrigido

- **Ao recolher „Detalhes" e „Indicadores", ficavam restos de imagem no
  ecrã.** Recolhida, parte do conteúdo deslizava para debaixo do rebordo
  inferior da janela e permanecia ali sobre o fundo, até algo mais ser
  desenhado por cima.

  Ambas as áreas têm uma altura mínima, para que, abertas, tenham um
  tamanho utilizável. O movimento ao recolher reduzia, porém, apenas a
  altura máxima – e abaixo da sua altura mínima uma área não encolhe. O
  conteúdo permanecia assim com 200 pontos de altura, enquanto a janela já
  se reduzia para 24; a diferença ficava abaixo do rebordo. Agora a
  altura mínima cede durante o movimento e volta depois.

- **A janela ficava cada vez mais pequena ao recolher e abrir
  repetidamente.** Ao abrir, cresce no máximo até 92% da altura do ecrã;
  se o espaço for escasso, cresce assim menos do que seria necessário. Ao
  recolher, retirava-se, mesmo assim, o valor total. Agora é devolvido
  exatamente o que a abertura custou.

- **Um resto de uma indicação ocultada podia ficar visível.** Num
  currículo, de „*30.12.1991" permaneciam legíveis no resultado os
  carateres „*30.1" – ou seja, o dia e o início do mês da data de
  nascimento. O programa tinha até detetado o resto e, por isso,
  convertido a página numa imagem; foi precisamente isso que piorou a
  situação, pois com isso o resto deixava de ser pesquisável, mas
  continuava legível – e já não era possível corrigi-lo.

  A causa estava entre duas verificações. A mais rigorosa das duas
  verifica se, na área de uma indicação removida, ainda está algo que ali
  não devia estar; comunica a sua deteção como um conjunto de carateres,
  porque a ordem de leitura se desloca ao substituir. O mecanismo de
  recurso, que pinta esses locais antes de converter, procurava esse
  conjunto de carateres como texto na página – e nunca o encontrava. Por
  isso não era pintado nada. O local era conhecido o tempo todo e é agora
  transmitido diretamente, em vez de ser procurado de novo.

  Era afetada qualquer página cujo resto fosse encontrado apenas por
  esta verificação – independentemente do tipo de ficheiro e do idioma.

- **Numa digitalização inserida na transversal, o reconhecimento de texto
  não encontrava nada.** Quem coloca uma folha de lado no alimentador
  obtém um ficheiro em que a escrita está rodada 90 graus. Até agora, o
  Maskuro não lia ali **nenhuma** indicação – e o ficheiro parecia depois
  inofensivo: nada foi encontrado, logo nada foi comunicado, e a morada
  continuava legível na imagem. Agora o reconhecimento de texto endireita
  a página por si só; na imagem de verificação, voltam a cair todas as
  indicações.

  Dois limites indicados abertamente: uma folha **de cabeça para
  baixo** (180 graus) continua a não ser lida, e numa digitalização muito
  má, endireitar não ajuda – aí há muito pouco legível para sequer
  determinar a orientação. Cada imagem demora, por isso, cerca de um
  quinto mais.

### Alterado

- **„Instalar automaticamente" chama-se agora ao que faz.** A marcação
  nas definições prometia mais do que cumpria: carrega a nova versão por
  si só e inicia a instalação – mas esta decorre de forma **visível** e
  quer ser confirmada, no Windows incluindo a pergunta do Controlo de
  Conta de Utilizador. Quem lesse „automaticamente" contava com um
  computador que se atualiza sozinho durante a noite, e via-se de manhã
  perante o assistente de instalação. A marcação chama-se agora
  „Carregar atualizações automaticamente e iniciar a instalação", com
  uma frase por baixo a explicar o que isso significa. No comportamento
  nada muda – que o Maskuro não se substitua sem ser notado é intencional
  e mantém-se assim.

## 0.10.27-alpha.20260817 – 17 de agosto de 2026

### Novo

- **Novo: `--ersetzen` para a ligação a um software de escritório de
  advogados.** O resultado ocupa o lugar do ficheiro de origem, em vez
  de surgir ao lado. Com isto, o processo de saída e entrada de um
  software de escritório de advogados („Abrir e editar" no processo
  eletrónico) funciona sem qualquer interface: o software entrega o
  ficheiro e recebe-o de volta, limpo, no mesmo local.

  **Este interruptor contorna o primeiro princípio**, e por isso só
  existe na linha de comandos – não na janela – e apenas quando a sua
  administração o autoriza (entrada `ersetzen` no ficheiro de
  diretrizes). Sem autorização, a chamada interrompe-se e diz porquê;
  criar em silêncio um segundo ficheiro seria o erro mais grave, pois
  então a versão não limpa seria reintroduzida no sistema.

  É escrito primeiro um ficheiro vizinho; só quando este está pronto é
  que ocupa o lugar da origem. Uma interrupção ou erro deixa assim a
  origem **byte a byte inalterada** e não deixa nenhum fragmento. No
  registo de verificação, a substituição consta como campo próprio –
  um verificador precisa de saber que a versão não limpa já não está
  aqui.

- **O manual explica agora o aviso do Windows no primeiro arranque.**
  Nova primeira secção „O Windows avisa no primeiro arranque – o que
  fazer", com duas imagens e três passos: „Mais informações" é uma
  pequena ligação, não um botão – é precisamente aí que a maioria
  fica presa –, depois „Executar mesmo assim".

  Que ali conste „Editor desconhecido" é toda a mensagem do aviso: os
  pacotes são, neste momento, distribuídos sem certificado.
  Consideramos mais correto explicar isso do que ocultá-lo.

- **O caminho de volta deteta agora quando o texto e a atribuição não
  combinam.** Quem cola a resposta noutro processo recebia até agora
  nomes alheios no texto certo – sem erro, sem mensagem, apenas
  errado. O Maskuro memoriza agora quais os marcadores que a última
  execução efetivamente gerou, e comunica qualquer um que não
  pertença a ela. Se nenhum deles provier da última execução, nada é
  inserido, e a janela diz porquê – em vez de, como até agora,
  presumir um prazo expirado.

  **Um limite permanece, e consta também no manual:** os marcadores são
  numerados por execução, o primeiro nome chama-se assim sempre
  `[NAME_1]` em cada documento. Se o texto alheio trouxer apenas tais
  marcadores, a confusão não é detetável.

- **O PDF pode agora ser gerado a preto e branco.** Uma marcação no
  modo de funcionamento converte cada página numa imagem a preto e
  branco – com uma camada de texto invisível por baixo, portanto
  continua legível e pesquisável. Para o envio via beA e vias
  semelhantes com limites rígidos de tamanho: em média, sobre o nosso
  corpus de medição, **68% mais pequeno** (linha de comandos:
  `--monochrom`).

  **O quanto vale depende do documento** – e isso consta também junto
  à marcação: digitalizações e conteúdo com imagens encolhem muito, um
  documento de texto esbelto sem tipos de letra incorporados pode até
  ficar maior. Experimente num ficheiro antes de o ativar para um
  lote.

  O preço: cada página é recalculada – com mil páginas, isso demora
  minutos. E as ilustrações perdem tudo entre preto e branco; para
  texto isso é indiferente, para uma fotografia não.

- **A lista de resultados na janela de correção conta agora consigo.**
  Por cima da lista consta „5 resultados", e assim que filtra, „1 de 5
  resultados". Essa é a diferença entre „filtrei" e „são cinco, e
  vi-os todos" – o gesto com que se verifica se um nome foi realmente
  substituído em todo o lado.

- **O registo de verificação pode agora ser pesquisado e filtrado.** A
  vista em „Ficheiro → Registo de verificação" tinha até agora uma
  tabela e mais nada – num mês com três mil execuções via-se que
  tinha acontecido muito, mas não o quê.

  Novos são um **campo de pesquisa**, **três filtros** (processo,
  resultado, tipo) e o **paginar**, a isto juntam-se três colunas que
  antes não existiam: **Processo** (ocultado ou substituído),
  **Confiança** e **Duração**. Por cima da lista consta quanto está
  agora visível e quanto o filtro oculta.

  „Guardar como CSV…" gera agora **o que está visível** – quem
  filtrou recebe o filtrado, e a mensagem indica o número.

  Um traço em Confiança ou Duração significa que nada foi medido para
  essa linha – por exemplo, por ser mais antiga do que esta função.
  Estes valores **não** são calculados posteriormente. Um filtro por
  utilizador continua a não existir; uma linha isolada é, mesmo
  assim, encontrada pela pesquisa.

### Removido

- **O aviso de transparência na janela „Sobre este programa" desapareceu
  de novo.** Estava ali desde a 0.10.22-beta.1 e dizia que a aplicação
  foi desenvolvida com apoio de inteligência artificial. Não é exigido
  em lado nenhum, e, precisamente numa aplicação de proteção de dados,
  alguns liam-no como uma afirmação sobre o funcionamento – como se os
  documentos fossem para um serviço na rede. A limpeza continua a ser
  feita exclusivamente no próprio computador; isso consta onde deve
  estar, no separador „Proteção de dados".

### Corrigido

- **O programa trocava o seu próprio ícone por um pior.** Quem
  registasse o menu de contexto a partir do programa ficava depois com
  um escudo diferente na barra de tarefas do que depois da instalação –
  semelhante, mas com barras alinhadas à esquerda em vez de centradas e
  visivelmente mais grosseiro. Por trás disso estava um recurso de
  emergência: se o programa não encontrar o modelo de ícone, desenha um
  ele próprio. Era pensado para o caso de **não haver** ícones de todo;
  na realidade, desenhava também quando os incluídos já lá estavam –
  e substituía-os. Numa versão instalada a partir do setup não há
  modelo, por isso afetava ali toda a gente. Os ícones existentes
  permanecem agora intocados.

  **As instalações já afetadas não recuperam o ícone correto
  sozinhas** – para isso, reinstale uma vez.

- **„Objektkennung: OB-4711-22" valia como nome de utilizador.** O
  detetor de nomes de utilizador verificava as suas legendas sem
  limite de palavra antes delas – ou seja, apanhava **qualquer**
  palavra que terminasse numa delas: Objektkennung, Fahrzeugkennung,
  Gerätekennung. O valor a seguir era removido, apesar de nada ter a
  ver com um nome de utilizador.

  Composições que são realmente pretendidas – „Benutzerkennung",
  „Anmeldekennung" – constam individualmente na lista e continuam a
  ser encontradas.


- **Em inglês, grego, japonês e coreano, dezasseis marcadores
  apareciam em alemão no resultado.** Quem tivesse definido a
  interface num destes quatro idiomas recebia, para os tipos de dados
  mais recentes, as legendas alemãs escritas no documento – de uma
  palavra-passe resultava `[ZUGANGSDATEN_1]` em vez de
  `[CREDENTIALS_1]`, de um código de diagnóstico
  `[DIAGNOSESCHLUESSEL_1]` em vez de `[DIAGNOSIS_CODE_1]`. Eram
  afetados saúde, diagnóstico, medicação, código de diagnóstico e de
  medicamento, religião, sindicato, opinião política, direito penal,
  credenciais, nome de utilizador, dados de cartão, coordenadas,
  profissão, montante e característica.

  Os restantes 44 idiomas nunca tiveram este erro: obtêm as suas
  legendas dos ficheiros de idioma, onde estes tipos já constavam
  desde o início. Precisamente estes quatro idiomas usam, por outro
  motivo, tabelas próprias – a sua escrita não sobrevive ao conjunto
  de carateres do PDF, razão pela qual ali constam legendas latinas –,
  e nestas tabelas os novos tipos simplesmente faltavam.

  Foi detetado ao traduzir a página do catálogo: o site prometia a
  leitores ingleses legendas que o programa não escrevia. Um teste
  compara agora as quatro tabelas com a lista de todas as legendas
  que podem sequer surgir.

- **A janela de regras deixa de abrir demasiado pequena para o seu
  conteúdo.** No separador „Padrões de pesquisa próprios", a linha de
  explicação do assistente („Procura-se: …") ficava meio escondida
  atrás do campo „Texto de teste" – precisamente a frase com que se
  verifica, sem conhecimentos de expressões regulares, se a regra
  própria procura o correto. A janela tinha uma dimensão mínima fixa
  de uma altura com menos separadores e podia por isso ser reduzida
  para menos do que cabia. Agora orienta-se pelo seu conteúdo e só
  abre tão pequena quanto tudo permaneça legível.

- **Os nomes em fórmulas de tabela deixam de permanecer.** Uma célula
  tem mais do que um local para texto, e até agora só um era limpo. Se
  um nome estivesse numa fórmula – `="Frau "&"Sieglinde Ortner"` – ou
  fosse o último resultado calculado de uma fórmula, permanecia
  inalterado na pasta de trabalho, apesar de a mesma pessoa estar
  substituída na célula ao lado. Quem clicasse na célula lia-o na
  barra de edição.

  Ambos são agora substituídos. Só é tocado o que está entre aspas:
  referências de célula, nomes de função e nomes de folha permanecem
  intocados, `=SUMME(K2:K6)` continua a calcular. Como o mesmo nome
  recebe em todo o lado o mesmo marcador, também
  `=SUMMEWENN(A:A;"Huber";B:B)` continua a encontrar as suas linhas.

- **Os diagramas deixam de mostrar nomes.** Um diagrama guarda uma
  cópia própria das suas legendas de eixo – continua a desenhar mesmo
  quando as células de origem já estão vazias há muito. Sob as
  barras, permaneciam por isso cinco nomes de pessoa, enquanto a
  tabela por cima estava limpa. Aplica-se a folhas de cálculo **e**
  apresentações.

- **Intervalos nomeados com texto fixo são limpos.** Um intervalo
  nomeado pode conter, em vez de uma referência de célula, um texto
  fixo; se ali estivesse um nome, permanecia. O **nome** do intervalo
  continua a permanecer – fórmulas referem-se a ele, e uma
  renomeação resultaria num erro de referência. Como no nome de
  folha, é comunicado, não substituído.

- **Uma data de nascimento reconhecida uma vez desaparece em todo o
  documento.** Uma data por si só nada diz – só uma palavra de campo a
  torna uma data de nascimento, e é precisamente por isso que uma
  data de fatura fica em paz. Mas se a mesma indicação estivesse uma
  segunda vez no mesmo documento sem essa palavra – no título de uma
  imagem, num campo de formulário preenchido –, permanecia ali, apesar
  de algumas linhas acima „nascido em …" ter sido reconhecido sem
  ambiguidade. Só é transposto o que já foi reconhecido **neste**
  documento como data de nascimento; continua a não se adivinhar
  nada.

- **Dados estruturados em páginas web revelam a sua data de
  nascimento.** No bloco JSON-LD para motores de busca, a data consta
  sob a chave `birthDate` – a chave diz o que é, tal como normalmente o
  título da coluna. É agora lida em conjunto; „Birthday" e „Birthdate"
  valem assim também em formulários como designação de campo.

- **Data de nascimento e número de pessoal são agora também
  encontrados em tabelas.** Numa célula consta apenas o valor nu –
  `14.03.1988`. O que significa é dito apenas pelo título da coluna, e
  este fica muitas linhas acima. No Excel já era lido em conjunto; em
  tabelas LibreOffice e em ficheiros CSV não, e por isso a data de
  nascimento ali permanecia.

  Ambos leem agora o título em conjunto – **mas só se este for, ele
  próprio, uma designação de campo**. Sob „Data de nascimento", a
  data cai; sob „Data da fatura" ou „Data de entrega" não. É
  deliberadamente a interpretação cautelosa: um título como „Nome"
  sobre uma observação qualquer já teria colocado um marcador sobre
  uma frase em que nem sequer surge nenhuma pessoa.

### Corrigido

- **Um CSV limpo continua a ser uma tabela.** A deteção lê uma linha
  CSV como uma frase e, por isso, já colocava os seus resultados por
  cima de um ponto e vírgula. O marcador engolia o separador, a linha
  ficava depois com uma coluna a menos, e o ficheiro deixava de poder
  ser aberto como tabela. Os resultados terminam agora no limite da
  célula, e as aspas da máscara permanecem. As células afetadas são,
  em seguida, relidas por si só – caso contrário, a célula vizinha
  ficaria por limpar, encoberta pelo resultado demasiado longo.

- **Comentários em apresentações.** A observação marginal num
  diapositivo – muitas vezes precisamente onde consta „Por favor
  ligar à Sra. … antes da reunião" – permanecia intocada, incluindo o
  nome de quem a escreveu. No Excel, ambos já tinham sido limpos há
  muito; o PowerPoint guarda o texto de comentário e o autor de forma
  diferente, e isso tinha sido esquecido. Afeta ambas as formas: a
  mais antiga e a que o PowerPoint escreve desde 2019 – ali também o
  endereço de e-mail profissional associado ao autor. As iniciais que
  o PowerPoint mostra no balão de fala são removidas em conjunto.

- **Ficheiros LibreOffice: fórmula, campo de utilizador, autor de
  nota.** O que já tinha sido limpo no Excel permanecia na tabela ODS
  – ali a fórmula não consta como elemento próprio, mas como
  propriedade da célula, e o nome dentro dela sobrevivia. Na abertura
  seguinte, o LibreOffice recalculava-o de novo.

  A isto juntam-se três locais adicionais: o valor de um **campo de
  utilizador** consta, em OpenDocument, uma vez em cima na
  declaração, sendo apenas invocado no texto – até agora só a
  invocação era substituída, pelo que, ao abrir, o valor antigo
  voltava. O **autor de uma nota** e de uma alteração controlada
  permanecia. E numa **folha de cálculo**, o controlo de alterações
  não era de todo limpo – ao contrário do documento de texto –,
  fazendo com que conteúdos de célula apagados, com o nome de quem
  editou, se mantivessem. Referências de célula e fórmulas de soma
  não são afetadas por isto.

- **As páginas web guardadas revelam os seus atributos.** Uma página
  está longe de mostrar tudo o que contém. Um campo de formulário
  preenchido traz a entrada em `value`, uma interface JavaScript
  guarda o seu conjunto de dados em `data-…`, e o bloco para motores
  de busca (JSON-LD) repete-o de forma completa e bem formada: nome,
  data de nascimento, morada, telefone. O texto visível estava limpo,
  tudo isso continuava lá.

  Agora estes locais também são limpos, a isto juntam-se `aria-…` (o
  que é lido em voz alta pelo leitor de ecrã), `placeholder`,
  `summary` e o nome de ficheiro sugerido de uma referência. O bloco
  JSON-LD é, nesse processo, lido como dados e permanece válido – as
  suas chaves e o seu vocabulário mantêm-se, só os valores
  desaparecem. O JavaScript comum continua a não ser tocado.

- **As imagens perdem os seus dados secundários também sem EXIF.** Uma
  fotografia traz anexados o nome do fotógrafo, o momento da captura e
  as coordenadas GPS do local da captura – num anúncio de habitação,
  isso revela a morada, mesmo que no texto não conste nenhuma. Isso
  era removido enquanto a imagem tivesse EXIF. Mas se as indicações
  estivessem depositadas **apenas** como XMP (assim guardam o
  Lightroom e o Photoshop) ou como bloco de texto num PNG (`Author`,
  `Comment`), a imagem ficava totalmente intocada. Ambos são agora
  reconhecidos e removidos – também em imagens que estejam dentro de
  um documento e nele se mantenham. A orientação continua a
  sobreviver, e uma imagem sem dados secundários não é guardada de
  novo desnecessariamente.

- **Destinos de referência em folhas de cálculo, apresentações e
  documentos Word.** Para onde uma referência leva não consta no
  texto, mas num depósito próprio do ficheiro. Um endereço de e-mail
  atrás de „Escrever e-mail" sobrevivia por isso intacto à limpeza,
  enquanto o mesmo endereço no texto estava substituído. `mailto:` e
  `tel:` são agora limpos ali tal como em páginas web guardadas.

### Novo

- **As cartas médicas deixam de voltar danificadas.** Até agora, a
  deteção de nomes tomava substâncias medicamentosas por nomes de
  pessoa: de „Metoprololsuccinat" resultava `[NAME]`, de „Ramipril"
  resultava `[ORT]`. O plano de medicação ficava depois inutilizável –
  enquanto os diagnósticos permaneciam intocados, ou seja,
  precisamente ao contrário. Medido, isto afetava **63% das
  substâncias ativas** e **53% dos termos técnicos clínicos**, e não
  só em alemão: em sete idiomas, 74%, em italiano, todos os
  verificados.

  O Maskuro conhece agora o vocabulário médico e deixa-o em paz.
  Restam 6% em vez de 43% (alemão) e 1% em vez de 74% (nos
  idiomas). Onde houver uma saudação antes – „Estimada Senhora …" –,
  o nome continua a ser um nome, mesmo que se chame por acaso como
  uma substância medicamentosa.

- **Doenças e medicamentos podem ser removidos – se quiser.** Nova
  marcação nas definições: „Remover também doenças e medicamentos"
  (linha de comandos: `--mit-diagnosen`). Para processos de pessoal,
  despedimentos e pareceres, onde o diagnóstico não diz respeito a
  ninguém.

  **Desligado por defeito**, e isso de propósito: uma carta médica
  *consiste* em diagnósticos e substâncias ativas. Quem a anonimiza –
  para investigação, para uma formação, para uma ferramenta de IA –
  quer, na maioria das vezes, manter precisamente este conteúdo e
  livrar-se apenas de quem é a pessoa. O diagnóstico é, ali, o
  conteúdo útil, não a identificação.

  A deteção encontra as designações comuns e não substitui a
  revisão: uma lista de doenças nunca está completa, porque o médico
  escreve „C2-Abusus" onde a classificação usa „Perturbações devidas
  ao álcool".

- **Os códigos de diagnóstico e de medicamento são encontrados.**
  ICD-10 (`I48.2`), ATC (`A10BA02`) e o número central farmacêutico são
  dados de saúde como qualquer diagnóstico por extenso – em cartas de
  alta e documentos de faturação, mesmo a forma mais frequente. Estão
  ativados por defeito, como as restantes categorias especiais do
  Art. 9.º do RGPD.

  Um código de diagnóstico só é reconhecido com comprovativo: com
  „ICD" antes ou entre parênteses a seguir à linha de diagnóstico. Sem
  esta condição, o programa tomaria a tecla de função **F10** por um
  diagnóstico de dependência – na classificação, F10 é exatamente
  isso.

- **O ficheiro concluído pode agora ser copiado.** Em cada linha
  concluída, ao lado de „Ver", „Corrigir" e „Mostrar na pasta", há um
  quarto botão: **Copiar**. Coloca o ficheiro limpo na área de
  transferência – dali segue com Ctrl+V (Mac: ⌘V) para um e-mail, uma
  janela de chat ou uma ferramenta de IA, sem o desvio pela pasta.

  É copiado o **ficheiro**, não o seu texto: a composição de página,
  as imagens e as barras de ocultação mantêm-se assim. Através do menu
  de contexto da lista, também vários resultados selecionados vão de
  uma vez para a área de transferência, e no menu „Ficheiro" consta o
  mesmo caminho como **„Copiar resultado"**, para quem preferir usar o
  teclado.

- **A seleção de país pode agora seguir o documento.** Números de
  identificação, sociais e fiscais variam de país para país, e quais
  os países verificados estava, até agora, fixo para toda a sessão –
  derivado do idioma da interface. Quem trabalha em alemão e limpa
  uma carta francesa procurava nela por isso NIFs alemães e não pelo
  número de segurança social francês.

  Na janela de regras consta agora para isso **„Automaticamente
  segundo o idioma do documento"**. A seleção fixa mantém-se ao lado,
  e isso de propósito: a deteção de idioma não é infalível – se
  detetar mal, aplica-se a seleção de país errada. Quem só trabalha
  documentos de um país está mais seguro com a lista fixa.

  Não são afetados por isto os padrões **alemães** (NIF, matrícula,
  extensão): dependem do idioma, não da seleção de país, e continuam a
  aplicar-se mesmo quando um texto alemão curto é classificado como
  inglês.

- **Palavras-passe, chaves e nomes de utilizador são agora
  encontrados.** Quem cola uma mensagem de erro, um registo ou um
  excerto de um ficheiro de configuração numa janela de IA tem
  quase sempre uma chave de acesso lá dentro – e esta permanecia até
  agora inalterada.

  São reconhecidas ambas: as formas de chave comuns, que falam por si
  (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token, o
  cabeçalho de uma chave privada), e a forma legendada –
  „Password:", „API-Key =", „Token:", „Utilizador:". Só é
  substituído o valor, nunca a legenda: „Password: [ZUGANGSDATEN_1]"
  mantém-se legível, e quem verificar o resultado vê que ali estava
  uma palavra-passe.

  Nome de utilizador e palavra-passe são dois tipos separados. Quem
  quiser remover apenas palavras-passe desliga um e mantém o outro.

- **Códigos de barras e QR em imagens são tornados
  irreconhecíveis.** Numa decisão digitalizada quase sempre há um
  código colado, e nele consta a referência de processo – o mesmo
  número que é removido no texto ao lado. Até agora, a versão legível
  por máquina permanecia: a barra sobre o número não serve de nada, se
  dois centímetros mais adiante um aparelho a lê num segundo.

  São reconhecidos QR Code, Data Matrix, Aztec, Code 128, EAN e as
  restantes formas comuns. Irreconhecível significa pixelizar, e de
  forma mais grosseira do que em rostos: a correção de erro de um
  código recupera surpreendentemente muito a partir de poucos campos
  mantidos, um véu pela metade não seria uma remoção.

  A opção está ao lado de „Tornar rostos irreconhecíveis" e é
  igualmente **ativada por defeito**. Mesmo com a opção desligada, o
  relatório diz quantas imagens trazem um código – um rosto vê-se ao
  folhear, um código toma-se por acessório.

- **Número de verificação do cartão, PIN e data de validade são
  encontrados.** O número do cartão de crédito o programa já
  encontrava; só com as três indicações ao lado é que é utilizável, e
  em qualquer comprovativo de faturação estão juntas. Todas as três
  apenas atrás da sua legenda – „123" sozinho é um número de porta, um
  número de página ou uma quantidade.

- **As coordenadas no texto são encontradas.** De imagens, o Maskuro
  já removia o local de captura; se a mesma indicação estivesse como
  texto num parecer ou num relatório de intervenção, permanecia.
  São reconhecidos graus decimais e a grafia em graus-minutos-segundos.
  Em graus decimais, é preciso que uma palavra como „Local", „Local de
  achado" ou „Coordenadas" esteja próxima – caso contrário, qualquer
  série de medições com dois algarismos decimais seria uma indicação
  de local.

- **Os montantes monetários podem agora ser removidos em conjunto.**
  Nova marcação „Remover também montantes monetários", **desligada**
  por defeito, como as indicações de data acima: num contrato, o
  montante é o conteúdo, e quem oculta tudo não protege ninguém. Numa
  folha de vencimento, numa proposta de acordo ou num extrato de
  conta, é, pelo contrário, precisamente a indicação que diz mais
  sobre a pessoa do que o nome ao lado – isso só sabe quem tem o
  documento à frente.

  Um montante só é reconhecido **com indicação de moeda**: „4.250,00"
  sozinho é uma quantidade, só „4.250,00 EUR" é dinheiro. Símbolo de
  moeda, sigla e nome por extenso contam, antes ou depois, incluindo a
  grafia „990,– CHF".

- **As categorias especiais do Art. 9.º do RGPD são reconhecidas.**
  Confissão religiosa, filiação sindical, convicção política,
  indicações de saúde – e a isto juntam-se as indicações de direito
  penal segundo o Art. 10.º. São os dados cujo tratamento o
  regulamento, em princípio, **proíbe**; por isso são o único grupo
  novo ativado **por defeito**. Quem os quiser manter, decide isso.

  É reconhecida a forma em que constam na prática: o campo de
  formulário na ficha de pessoal – „Confissão religiosa:
  rom.-cat.", „Sindicato: ÖGB", „Grau de incapacidade: 50",
  „Antecedentes: nenhum" –, tanto com dois pontos ao lado como com a
  legenda por cima, como uma folha preenchida os fornece.

  **O texto corrido pertence ao nível de IA.** „Está envolvido há
  anos no sindicato" é a mesma indicação, e nenhum padrão de pesquisa
  a encontra de forma fiável. O nível de IA procura, desde esta
  versão, expressamente também estas categorias; quem precisar do
  texto corrido ativa-o.

- **Características pessoais e profissão – as indicações que mostram
  quem é, mesmo sem nome.** Sexo, estado civil, altura, cor dos olhos
  e do cabelo passam a ser removidos a partir desta versão; profissão,
  função e departamento a pedido, através de uma marcação própria
  („Remover também profissão e departamento") ou `--mit-berufen`.

  **Porque um está ligado e o outro desligado:** „A responsável do
  departamento de Compras" identifica, numa empresa, precisamente uma
  pessoa, mesmo que o nome ao lado esteja ocultado – num parecer ou
  num despedimento, isso deve ser removido. Um organograma de
  colaboradores *consiste*, pelo contrário, em designações
  profissionais; quem as removesse por defeito devolveria uma folha
  vazia. Qual dos casos se aplica só sabe quem tem o documento à
  frente. As características acima constam quase só em campos de
  formulário, são raras e nunca carregam o conteúdo – não custam
  assim nada.

- **Verificar um ficheiro alheio.** „Ficheiro → Verificar ficheiro…"
  relê um documento já ocultado e comunica o que ainda consta nele – e
  **em que local**: página e linha, tipo e comprimento. Para o caso
  de alguém verificar o trabalho de outrem: um processo do escritório
  de advogados, uma informação da autoridade, o próprio correio de
  saída antes do envio.

  **O próprio valor não consta no relatório.** Quem abrir o local
  vê-o de qualquer forma – e o relatório pode por isso ser guardado e
  partilhado, sem ser ele próprio uma coleção de dados pessoais.

  **E o relatório diz, em qualquer caso, o que não pôde ver.** Imagens
  não são lidas; numa digitalização sem camada de texto, „nenhum
  resultado" significa *não verificado*, não *limpo*. Na linha de
  comandos, isso é distinguido pelo valor de retorno:
  `--nachpruefen` devolve 0 para verificado e limpo, 4 para
  resultados e 5 para não verificável. Com isto, o correio de saída
  pode ser retido automaticamente, em vez de ser deixado passar.

- **Relatório de verificação: uma folha por limpeza.** „Ficheiro →
  Guardar relatório de verificação…" – ou `--pruefbericht <pasta>` na
  linha de comandos – escreve um PDF de uma página (opcionalmente CSV
  ou texto) com os dados da execução, os tipos encontrados com
  quantidade, dois indicadores e uma nota de verificação. Para a pasta
  do processo e para a supervisão: o registo de verificação é o
  comprovativo robusto, mas ninguém apresenta um ficheiro JSON
  Lines.

  **Novos são dois números** que até agora não se viam em lado
  nenhum: a *confiança média* – com que certeza a deteção agiu sobre
  o que encontrou – e a *taxa de mascaramento*, a proporção de
  carateres substituídos no texto. Ambos vêm com o seu limite: a
  confiança **nada** diz sobre o que foi omitido, e ao lado consta
  sempre sobre quantos resultados incide; a taxa não conta imagens e
  sai demasiado alta num documento com imagens.

  **Os valores encontrados não constam na folha** – o mesmo limite do
  registo e da execução de pesquisa. Em baixo constam duas linhas que
  não dizem o mesmo: a soma de verificação mostra que a folha está
  inalterada; a linha de registo – só com registo ativo – remete
  para a linha **assinada** que comprova a execução. Só esta
  comprova a origem.

- **„Quão seguro foi isto?" – os indicadores no resultado.** Um botão
  „Indicadores" sob o resultado abre o que até agora não se via em
  lado nenhum: resultados, palavras e carateres, a distribuição por
  tipo como linha de barras, a isto juntam-se a confiança média e a
  taxa de mascaramento. Os mesmos números do relatório de
  verificação, apenas imediatos e sem impressão.

  **Com a sua ressalva na mesma área:** ao lado da confiança consta
  sobre quantos resultados incide, e por baixo a frase de que **nada**
  diz sobre o que foi omitido. Uma percentagem sem essa frase lê-se
  como uma taxa de deteção – e quem a interpretar assim fica pior do
  que sem o número.

  Só é calculado ao expandir: o denominador da taxa de mascaramento
  custa uma leitura por ficheiro, e isso não deve ser pago por quem
  nem sequer olha para os números.

- **Construir padrões de pesquisa próprios, sem escrever nenhum.** O
  separador „Padrões de pesquisa próprios" conduz agora, em três
  passos, através do assunto: *O que procura? → Como é essa indicação
  no seu caso? → Nomear e guardar.* Digita um exemplo – por exemplo
  `KD-004711` –, o programa deriva a regra a partir dele e escreve por
  palavras o que procura. Uma pré-visualização com contador de
  resultados verifica a cada tecla premida.

  **Uma expressão regular não aparece nisto.** A capacidade nunca foi
  o problema: padrões de pesquisa próprios existem há muito, só que
  exigiam uma expressão como `\bKD-\d{6}\b`, e isso ninguém escreve
  num escritório de advogados ou num departamento de pessoal. Quem
  *quiser* escrever uma abre o modo de perito.

  **O catálogo de modelos está reordenado:** treze cartões com nome,
  explicação e valor de exemplo, filtrados por marcas de categoria –
  Finanças, Autoridades, Contacto, Pessoal, Medicina.

  E se o padrão derivado for demasiado amplo, o programa diz-o por
  iniciativa própria: um exemplo composto só de dígitos atinge
  qualquer ano e qualquer montante, e quem não conseguir ler a
  expressão poderia, de outra forma, não o notar.

- **Sete marcas em vez de cinquenta e seis marcações.** Um novo
  separador „O que é procurado" reúne todos os tipos reconhecíveis em
  sete grupos – Pessoa, Contacto e Local, Identificações, Finanças,
  Técnica, Categorias Especiais, Empresas e Próprio. Uma marca ativa o
  seu grupo, „Tudo ligado" e „Tudo desligado" toda a lista; por baixo,
  cada tipo continua marcável individualmente.

  **Por defeito, está tudo ligado, e mantém-se assim.** O que aqui é
  desligado nem sequer é procurado – a intervenção mais grosseira que
  a janela de regras permite, e atua sobre qualquer documento. Por
  isso, sob a lista consta sempre quantos tipos estão desligados, e só
  é guardado o desativado: um novo tipo fica assim ativo mesmo num
  ficheiro de regras de anteontem, em vez de cair silenciosamente de
  fora.

- **Transferir uma moldura para todas as páginas.** Na janela de
  correção, o botão **Aplicar a todas as páginas** pega na moldura
  arrastada por último e oculta o mesmo local em cada página seguinte
  – para cabeçalho de carta, rodapé e campo de referência de processo.
  Num processo digitalizado de oitenta páginas, isso transforma vinte
  minutos em dois.

  **„O mesmo local" significa o mesmo local *relativo* na folha.**
  Num lote do alimentador, regularmente uma página está na
  transversal, outra é A3, uma terceira está rodada; um retângulo
  transferido de forma absoluta cairia ao lado do cabeçalho de carta –
  e ver-se-ia uma barra e pensar-se-ia que o assunto estava
  resolvido.

  **É ocultado, não substituído**, mesmo que a moldura de origem
  fosse um marcador: sob o mesmo retângulo, na página quarenta consta
  algo diferente do que na página um, e um marcador com o mesmo
  número afirmaria uma igualdade que não existe.

- **Uma nota na barra de ocultação.** No direito de consulta de
  processo, consta ao lado de cada ocultação o motivo pelo qual foi
  ocultado. O novo campo **Nota na barra** nas definições – ou
  `--balkenvermerk` – escreve um texto curto em cada barra: „§ 203
  CP", „RGPD", „confidencial". Para um documento emitido por uma
  autoridade, essa é a diferença: o destinatário vê o motivo, sem ter
  um registo que, de qualquer forma, nunca receberia.

  **Vazio por defeito**, pois a nota é visível no documento entregue
  e é, ela própria, uma indicação – diz ao destinatário sob que
  título algo é retido. Só atua ao **ocultar**; onde há um marcador,
  não há barra. Numa barra demasiado pequena para texto legível, é
  omitida – uma nota ilegível parece um erro.

- **Ativar sem ligação à Internet – agora completo.** Na janela de
  licença, já havia há mais tempo „Ativar sem Internet": em cima um
  código de pedido para levar, em baixo o campo para a ativação, que
  regressa. Só que, até agora, **ninguém a conseguia emitir** – faltava
  a ferramenta para isso, e o código não dava em nada. Está corrigido.

  Para autoridades e escritórios de advogados com computadores isolados,
  isto não é um caso especial, mas o caso normal – e é precisamente o
  grupo-alvo em que a promessa „os seus documentos nunca saem do
  computador" mais pesa. O código nada revela sobre documentos:
  contém a identificação de licença e um valor de dispersão do
  computador, mais nada.

- **Obter do scanner.** „Ficheiro → Obter do scanner…" lê diretamente
  um lote e coloca as páginas na lista – para um serviço de
  correspondência, a diferença entre dois passos de trabalho e um. Um
  alimentador de folhas é esvaziado até à última página; aparelho,
  resolução e cor são escolhidos pela caixa de diálogo do sistema do
  scanner, que já conhece.

  **Não é limpo automaticamente.** Primeiro vê o que entrou, e depois
  prime „Limpar" como em qualquer outro ficheiro – uma digitalização
  que passasse de imediato tiraria a possibilidade de ver um lote
  inserido torto.

  **Isto só existe no Windows**, e o item de menu diz isso também no
  Mac: ali, o software do seu scanner escreve numa pasta, e
  „Monitorizar pasta…" limpa tudo o que ali cai.

### Diversos

- **A lista de todas as indicações encontradas está agora incluída** e
  é gerada a partir do código-fonte (`hilfe/GEFUNDENE-ANGABEN.md`): 177
  tipos em 35 países, 23 deles com cálculo de dígito de controlo.
  Indica também como foi contado – nós contamos `[NAME]` uma vez, onde
  outros contam primeiro nome, segundo nome e apelido como três
  entradas.

- **Ocultar existe agora também em Word, PowerPoint, OpenDocument e
  HTML.** A escolha entre marcador e ocultação estava até agora
  disponível apenas para ficheiros PDF. Agora os outros também podem:
  o resultado é removido, e no seu lugar fica uma barra preta – no
  próprio documento, não como imagem por cima. Quem partilhar o
  ficheiro, partilha um processo ocultado e não um em que o ocultado
  ainda está como texto por baixo.

  **É decidido separadamente**, em dois campos de escolha: „Em PDF" e
  „Em Word, PowerPoint, OpenDocument e HTML". Quer-se de forma
  diferente – o PDF ocultado vai para a autoridade, o mesmo assunto
  como ficheiro Word continua a circular na empresa e deve permanecer
  legível. Na linha de comandos, respetivamente `--pdf-modus` e
  `--office-modus`; um „Ocultar" guardado de versões anteriores
  continua a aplicar-se ao PDF.

  Em tabelas, texto simples, CSV e e-mail, a barra não funciona – ali
  falta a área sobre a qual se poderia colocar. Continua a ser
  inserido um marcador, e o resultado **diz-o agora**, em vez de o
  fazer em silêncio.

- **Novo: „Remover" – o local encontrado fica simplesmente vazio.** O
  terceiro modo de funcionamento, ao lado de marcador e ocultar, e o
  único que serve para **qualquer** formato: omitir algo não precisa
  de nenhuma área. No PDF, nada é desenhado; no Word e HTML, o local
  fica vazio; numa tabela, da mesma forma.

  É o mais silencioso dos três: quem lê o resultado não vê que ali
  esteve alguma vez algo – também o comprimento do valor deixa de se
  revelar. Para um documento que alguém deva verificar, o marcador
  continua a ser, na maioria das vezes, a melhor escolha.

  Em imagens, nenhuma das três escolhas vale: os pixels não podem ser
  substituídos por um marcador nem omitidos. O que o reconhecimento
  de texto ali encontra é, como até agora, sempre pintado por cima.

- **A janela de correção deixa de afirmar substituições que não
  existem.** À direita constava, para cada valor, um marcador – também
  numa ficheiro ocultado, em que não ocorre nenhum. Um clique numa
  linha assim não marcava nada, e „Anular" caía no vazio. Agora consta
  ali „ocultado" ou „removido", e as linhas nem sequer podem ser
  anuladas: o texto desapareceu, não há nada a recuperar. Isto
  aplicava-se a ficheiros PDF ocultados, a Word e OpenDocument e a
  tudo o que foi encontrado em imagens.

- **A vista de texto mostra agora as barras como barras.** Um ficheiro
  Word ocultado parecia **vazio** ao corrigir: nos locais ocultados
  havia espaços vazios, como se o programa tivesse engolido o texto. A
  causa era a apresentação, não o resultado – no próprio documento, a
  barra esteve sempre correta. Agora aparece também na vista, preta
  como no resultado, em Word, PowerPoint, OpenDocument e HTML.

- **As mensagens do Outlook (`.msg`) são agora limpas.** O `.eml` já
  existia há muito – mas, em empresas alemãs, o Outlook é o e-mail, e
  ali uma mensagem guardada chama-se `.msg`. Com isto, o formato mais
  denso em dados pessoais fica coberto também na sua forma de
  armazenamento mais comum: assunto, remetente, linhas de
  destinatário, texto da mensagem, versão HTML, lista de
  destinatários e anexos – estes últimos através dos caminhos já
  existentes e com os mesmos marcadores que o texto do e-mail.

  **Um `.msg` traz o mesmo texto várias vezes**, e essa é a armadilha:
  como texto simples, como HTML **e** como RTF. Quem limpar apenas o
  texto simples não fez nada – o Outlook mostra preferencialmente o
  RTF. A versão RTF é por isso removida por completo, assim como os
  cabeçalhos de Internet com a sua cadeia Received e as chaves de
  pesquisa binárias, que sobrevivem a qualquer limpeza de texto. O
  resultado continua a abrir-se no Outlook e mostra o texto sem
  formatação de tipo de letra; o relatório diz-o expressamente.

- **Descrever regras por palavras próprias, em vez de escrever
  regex.** A janela de regras consegue muito e exigia para isso um
  padrão de expressão regular – o local onde a maioria para. Agora
  basta uma frase: „As nossas referências de processo da forma 12 C
  345/26 devem permanecer." O nível de IA sugere a partir disso termos
  e padrões de pesquisa.

  **Só é assumido o que marcar – e por defeito nada está marcado.**
  Junto a cada sugestão consta uma frase sobre o que significa, e o
  número dos seus resultados num texto de exemplo que pode fornecer. O
  que **retira** proteção está identificado como tal: „remover sempre
  este termo" e „nunca remover este termo" pareceriam, de outra
  forma, iguais numa lista. Sugestões que se aplicariam a tudo nem
  sequer são mostradas.

- **O registo de verificação conta agora, em conjunto, todos os postos
  de trabalho.** Se uma organização colocar os registos via
  `protokoll_pfad` numa partilha, cada posto de trabalho escreve ali o
  seu próprio ficheiro mensal – até agora, um encarregado de proteção
  de dados com trinta postos tinha de ver trinta ficheiros
  individualmente. Por cima da lista consta agora uma linha com as
  somas do mês, e **comunica cadeias quebradas com nomes**: uma
  alteração posterior só se nota se alguém verificar, e em trinta
  ficheiros ninguém verifica manualmente.

  **Nenhuma listagem por pessoa** – também não nesta vista. Uma
  classificação „quem limpou quanto" prestar-se-ia a controlo de
  comportamento e desempenho, e é isso que conta em termos de
  representação de trabalhadores, não a intenção. São contadas
  execuções, ficheiros e resultados à escala da organização.

- **„Sugerir perfil a partir de um documento": perguntar às regras
  uma vez em vez de percorrer quarenta e quatro tipos.** Na janela de
  regras há um novo botão: mostra ao nível de IA um documento,
  determina do que se trata – carta médica, candidatura, contrato,
  fatura, decisão – e sugere as estratégias adequadas. Numa carta
  médica, por exemplo, as datas são deslocadas em vez de substituídas,
  porque, num processo clínico, a cronologia é o conteúdo.

  **Os perfis estão no programa, o modelo só escolhe** – as regras de
  ocultação não dependem do que um modelo de linguagem considera boa
  ideia. Cada ponto é sugerido individualmente e com justificação; nada
  é assumido sem confirmação, e o que já definiu por si mesmo permanece
  intocado. Sem o nível de IA, mantém-se o padrão seguro: marcador para
  tudo.

- **Nova estratégia „inventar": um valor falso plausível em vez de um
  marcador.** „A Sra. Berger escreveu ao Sr. Doppler em Fulda" em vez
  de „[NAME_1] escreveu a [NAME_2] em [ORT_1]" – para material de
  formação, processos de demonstração, conjuntos de dados de teste e
  tudo o que depois é apresentado a uma IA. Saudação, construção
  frásica e legibilidade mantêm-se.

  O mesmo valor recebe o mesmo valor falso, em todos os ficheiros de
  um processo e em qualquer computador com o mesmo ficheiro de
  regras – **sem que seja guardada em lado nenhum uma atribuição**
  (o mesmo mecanismo do hash). Endereços de e-mail ficam em domínios
  de exemplo reservados, números de telefone na gama reservada para
  isso, IBANs inventados trazem um dígito de controlo corretamente
  calculado. Possível para nomes, locais, moradas, empresas, e-mail,
  telefone e IBAN; para outros tipos, a regra é recusada, em vez de
  ficar sem efeito.

  **O relatório diz expressamente que foi inventado.** Um documento
  assim limpo lê-se como real e não o é – não serve como comprovativo
  e não pode ser partilhado como original.

- **A contraverificação: „Quem permanece reconhecível?"** Uma nova
  marcação sob o nível de IA apresenta o **resultado concluído** de
  novo ao modelo de linguagem e pergunta quem, apesar da limpeza, ainda
  é reconhecível. Trata-se do caso que nenhuma deteção do mundo
  encontra, porque ali nem sequer consta nenhum nome: „a única
  parteira do distrito", „o colega que se despediu em março depois do
  incêndio". Nenhum padrão se aplica, e no local todos sabem, mesmo
  assim, de quem se trata.

  **Nada é removido nesse processo.** Os locais constam com uma frase
  de justificação no relatório, e a decisão é manual – um programa que
  retire, por iniciativa própria, frases de um documento por lhe
  parecerem reveladoras transforma uma limpeza numa reescrita, e
  ninguém veria o que falta. No máximo cinco locais por ficheiro; o
  que o modelo não conseguir comprovar literalmente é descartado. Na
  linha de comandos: `--restrisiko` junto com `--ki`.

- **O caminho de volta a partir da IA: „Retraduzir resposta".** Até
  agora só estava construída metade do ciclo – copiar texto, colar
  limpo, apresentar à IA. A resposta voltava com `[NAME_1]`, e quem
  precisasse dela reinseria manualmente o que tinha retirado
  manualmente. Agora o caminho de volta está no menu „Programa":
  copiar resposta, clicar na entrada, os nomes reais voltam a
  constar.

  A atribuição para isso fica **apenas na memória**, vale sempre só
  para o último local limpo e expira ao fim de uma hora; quem desligar
  o vigilante da área de transferência livra-se dela de imediato. Só
  pode ser recuperado o que foi substituído – ocultado, mascarado e
  com hash não é reversível, e o programa diz quantos locais teve de
  manter por causa disso. Instalações geridas desligam por completo o
  caminho de volta através da diretriz `rueckweg`.

- **Monitorizar pasta: o que é colocado fica pouco depois limpo à
  saída.** Para um serviço de correspondência, uma equipa de caixa de
  correio ou uma pasta de digitalização – configura-se uma vez, depois
  ninguém mais clica. Encontra-se em „Ficheiro → Monitorizar pasta…",
  na linha de comandos via `--wache <pasta>`.

  O original permanece onde estava; a pedido, é movido inalterado para
  a subpasta „Concluído", nunca sendo nada substituído. Um ficheiro só
  é tocado quando está totalmente escrito – um ficheiro ainda a ser
  copiado pela rede seria, de outra forma, lido a meio e comunicado
  como limpo. O que correr mal fica retido e é comunicado, em vez de
  ser repetido infinitamente. E a vigilância memoriza o concluído sem
  nome de ficheiro: o que está numa pasta de entrada muitas vezes já
  revela, pelo nome, do que se trata.

  **A monitorização de uma pasta fora do próprio perfil de
  utilizador – por exemplo, numa unidade de rede – pressupõe uma
  licença de automatização.** Uma pasta acessível a várias pessoas é
  um serviço e não um posto de trabalho; no próprio perfil e durante o
  período de teste, a restrição não se aplica.

### Corrigido

- **As definições ficavam cortadas à direita.** A janela abria com um
  tamanho fixo, suficiente apenas para o tamanho de letra com que foi
  desenvolvida: no Mac, „Verificar agora", „Alterar…" e as indicações
  ao lado ficavam parcialmente fora. Agora abre tão larga quanto as
  suas páginas precisam – em qualquer idioma e com qualquer tamanho de
  letra, limitada apenas pelo ecrã.

- **„Verificar agora" responde agora de forma visível.** O resultado
  ficava na barra de estado da janela principal – atrás, portanto, da
  janela de definições a partir da qual se perguntou. Quem verificasse
  não via nada. Agora a resposta chega como mensagem sobre as
  definições, e, existindo uma nova versão, leva de imediato à
  instalação. No arranque do programa, mantém-se a barra de estado
  como até agora, sem que nenhuma janela abra sem ser pedida.

- **Os ficheiros copiados não chegavam à área de transferência no
  Mac.** A colocação de ficheiros limpos comunicava sucesso e, mesmo
  assim, não colocava nada utilizável – colar não resultava em nada.
  Era afetado tudo o que escreve ficheiros na área de transferência.

- **E, da área de transferência, só o primeiro ficheiro era lido no
  Mac.** Quem copiasse três ficheiros no Finder e escolhesse „Limpar
  área de transferência agora" recebia dois deles de volta por
  limpar – sem que nada o dissesse. Agora chegam todos.

- **„Verificar ficheiro" aceita agora também ficheiros
  arrastados** – como a janela principal. O que é colocado junta-se,
  em vez de descartar a seleção anterior; colocar a mesma coisa duas
  vezes não altera nada, e o que o programa não consegue ler é
  comunicado em vez de ser engolido.

- **E a janela diz que está à espera de si.** Abria com uma caixa
  vazia e um botão cinzento „Verificar" – isso parece que não há
  nada, não que falta a seleção. Agora consta ali „Ainda nenhum
  ficheiro escolhido – arraste para aqui ou escolha em baixo através
  de 'Selecionar ficheiros…'".

- **Uma execução longa diz agora que está a correr.** „A carregar
  modelo adicional para a deteção mais rigorosa – um momento…"
  permanecia enquanto a deteção calculava: num ficheiro com 47 500
  palavras, portanto dezoito minutos, apesar de o carregamento ter
  terminado ao fim de nove segundos. Quem vê isso pensa que o
  programa ficou preso. Agora segue-se „A deteção mais rigorosa está
  a correr – isto demora alguns minutos em textos longos", e a barra
  de estado conta em conjunto: „Deteção mais rigorosa (7/312)". É
  comunicado a partir do ciclo do modelo – a cada 250 palavras, ou
  seja, a cada seis segundos aproximadamente –, não por bloco de
  texto: um bloco de texto carrega doze mil palavras e demora
  minutos.

- **Uma execução interrompida diz agora que foi interrompida.** Quem
  premisse „Cancelar" lia depois „0 de 1 ficheiro(s) limpo(s)." –
  contado corretamente, mas ainda assim a informação errada. A
  mensagem sobre qual o ficheiro afetado foi sobreposta, no mesmo
  instante, pela mensagem de contagem. E na lista de ficheiros
  continuava „a decorrer…", apesar de nada mais estar a correr; consta
  agora „interrompido".

- **A frase sobre proteção de dados estava cortada.** „… nenhuma
  nuvem, nenhum carregamento. Mais no protec" – com a largura de
  janela com que o programa arranca, terminava a meio da palavra.
  Ocupa agora a largura total.

- **O serviço de licenciamento podia comunicar algo, e ninguém
  ouvia.** Quando todos os lugares de licença estão ocupados, a
  licença expirou, a chave é desconhecida ou a gestão de licenças no
  fornecedor está desligada, o serviço envia exatamente para isso um
  motivo – estava previsto, desde o início, que fosse explicado
  **uma vez**. Nunca era mostrado. Agora aparece um aviso que diz
  primeiro que o programa continua a funcionar sem alterações, e
  depois do que se trata. Uma vez por motivo: quem o fechou não o
  volta a ver na verificação diária – mas sim quando o motivo muda.

- **Uma licença multiplaço comprada na loja mostrava „1 lugar".** A
  loja distribui chaves preparadas e mantém consigo o número de
  lugares comprado; era mostrado, no entanto, o número da própria
  chave, e este é, em qualquer chave de reserva, um lugar. Quem
  comprara oito lugares lia „1 lugar" – e, a partir do segundo
  computador registado, a indicação ficava a vermelho, com „Contacte
  a sua administração". Agora aplica-se o número que o serviço
  comunicou por último; sem resposta, mantém-se o da chave, e nunca
  fica abaixo do volume comprado. O mesmo se aplica a compras
  adicionais e renovações: estas alteram, no fornecedor, o número de
  lugares, não a sua chave.

- **Depois da compra, constava „Licenciado para Licença Privada
  Maskuro".** Isso não é um nome, mas o marcador sob o qual as chaves
  são preparadas – o seu nome não pode constar ali, porque a chave já
  é assinada antes da compra. Em vez de lhe mostrar um nome alheio
  como se fosse o seu, consta agora simplesmente „Licença privada" e o
  número de lugares. Numa licença emitida em seu nome, o seu nome
  consta ali sem alteração.

- **No menu Ajuda constava „Ajuda _FAQ".** O „E" comercial tinha-se
  tornado um sublinhado, porque o Qt o lia como marca de uma letra de
  teclado. Agora consta ali „Ajuda & FAQ".

- **A janela de definições permanecia aberta quando o programa
  desaparecia para o ícone** – e mesmo quando a janela principal era
  fechada. Agora acompanha. (Afeta apenas esta versão; a janela
  própria é nova.)

- **Um pedido de licença recusado diz agora qual a causa.** Se o
  serviço de licenciamento recusasse um pedido sem enviar um motivo,
  constava na janela de licença, a vermelho, „Resposta desconhecida."
  – uma frase com a qual nem o utilizador nem o apoio conseguem fazer
  nada, e que leva a procurar o erro na própria chave. Agora consta
  ali o que realmente aconteceu: que o serviço recusou sem o
  justificar, e a quem se dirigir. Se a gestão de licenças no
  fornecedor estiver temporariamente desligada, isso também é
  indicado – com o aviso de que a sua chave não é afetada por isso.

- **No Mac, idiomas configurados passavam repentinamente a ser
  considerados em falta.** Ao arrancar, o programa comunicava „Não
  está instalado nenhum modelo de idioma" e oferecia a configuração
  inicial, apesar de os idiomas já terem sido carregados há muito –
  quem verificasse em „Idiomas dos documentos" encontrava-os todos
  ali. O programa procurava-os, consoante o caminho de arranque, em
  dois locais diferentes: se fosse iniciado a partir da pasta de
  programas, encontrava-os; se a mesma construção fosse iniciada como
  pasta simples, procurava-os ao lado de si, onde nenhum se encontra.
  A partir de agora, aplica-se, no Mac, sem exceção, o mesmo local no
  perfil de utilizador, seja qual for a forma como o programa está
  empacotado. Nada precisa de ser recarregado.

- **„O que há de novo" mostrava metade da lista.** A janela após uma
  atualização interrompia-se a meio de uma frase, e os pontos
  restantes ficavam como marcadores de lista vazios. A causa era um
  marcador entre parênteses angulares – por exemplo `<ficheiro>.docx`
  –, que a apresentação tomava por formatação e a partir do qual
  descartava tudo o resto. Precisamente as novidades de segurança
  eram afetadas por isto. A ajuda sempre mostrou corretamente tais
  marcadores; esta janela também o faz agora.

- **Beliscar com dois dedos amplia agora na janela de correção.** No
  trackpad, esse é *o* gesto de zoom – no editor, até agora não fazia
  nada, e quem quisesse ver um local mais de perto tinha de recorrer
  ao cursor ou a Ctrl+roda do rato. A página segue o gesto de
  imediato e é redesenhada com nitidez ao soltar.

- **O zoom incide sobre o local que se está a ver.** Beliscar amplia
  em torno do ponto entre os dedos, Ctrl+roda do rato em torno do
  ponto sob o cursor. Botões, atalhos de teclado e o cursor de zoom
  mantêm o centro fixo – a eles não pertence nenhum local para o qual
  se aponte. Antes, em todos eles, mantinha-se apenas o valor de
  deslocamento: a partir de uma página ajustada, isso mantinha o
  rebordo superior, e tudo o que estava por baixo saía da imagem ao
  ampliar.

- **„Antes/Depois" era um botão morto na pré-visualização de
  página.** Enquanto a pré-visualização de página estivesse ativa,
  podia ser premido – e comunicava, todas as vezes, que o original não
  podia ser aberto. Ali também não há nada a comparar: a
  pré-visualização de página é uma imagem da versão limpa, não existe
  uma contraparte do original. O botão está agora bloqueado e indica,
  ao passar o rato, o motivo com a saída (a vista de texto). A sua
  descrição prometia ainda, expressamente, que a comparação
  funcionava „independentemente de estar ativa a vista de texto ou de
  página" – isso nunca foi verdade.

- **A pré-visualização de página fazia o LibreOffice falhar.** Se
  fossem geradas duas pré-visualizações de página em simultâneo – por
  exemplo, „Ocultar como PDF" enquanto a pré-visualização ainda
  calculava –, o sistema comunicava uma falha do LibreOffice, apesar
  de as páginas acabarem por aparecer: ambas as execuções acediam ao
  mesmo depósito de trabalho do LibreOffice, o que este não suporta.
  Agora só uma execução o recebe de cada vez; as restantes recorrem a
  um próprio. Isso demora alguns segundos a mais, mas em troca já não
  aparece nenhuma mensagem de erro, e nenhuma das execuções fica sem
  resultado. Um segundo pedido de renderização ao lado de um em curso
  também deixa de ser sequer aceite.

- **„Mostrar original" podia fazer o programa fechar-se.** Se o
  original não pudesse ser aberto – por ter sido movido, renomeado,
  protegido com palavra-passe ou estar numa unidade desligada –, a
  janela de correção interrompia-se sem aviso, e as cópias de trabalho
  abertas perdiam-se. Agora aparece um aviso, o interruptor volta à
  posição anterior, e a versão limpa mantém-se. Onde o original, em
  princípio, não se aplica – por exemplo, numa pré-visualização de
  página de PDF gerada a partir de um ficheiro Word –, o interruptor
  está bloqueado desde o início e indica, ao passar o rato, o motivo,
  em vez de mostrar o mesmo aviso a cada clique.

- **Os relatórios de erro nunca chegavam.** Quem quisesse comunicar um
  erro recebia „A contraparte recusou o relatório" – e ninguém o
  tinha visto alguma vez. Duas causas, ambas no caminho: o programa
  não se identificava perante o servidor e era por isso recusado pela
  proteção contra acessos em massa, e o endereço remetia para um
  segundo nome que o programa não seguia. Ambos corrigidos; um
  relatório volta a sair. **O mesmo afetava a ativação de licença**:
  registar, cancelar e consultar também não chegavam ao serviço – ali
  apenas de forma discreta, porque um pedido sem resposta,
  propositadamente, nada altera na sua licença. E se uma recusa
  permanecer, mesmo assim, inexplicável, consta agora o seu número
  técnico, em vez de qualquer causa parecer igual.

- **Um clique em „Mostrar original" podia fazer o programa
  fechar-se.** Se o original não pudesse ser aberto – movido,
  renomeado, numa unidade de rede desligada, protegido com
  palavra-passe ou danificado –, a janela de correção desaparecia
  juntamente com todas as cópias de trabalho abertas. Agora o
  alternador mantém-se na versão limpa, e uma caixa diz o que se
  passa; o motivo técnico consta nos detalhes, caso queira comunicá-lo.
  O mesmo se aplica a um resultado que não pode ser exibido: a janela
  abre e diz-o, em vez de desaparecer.

- **A pergunta sobre uma falha aparecia demasiadas vezes – e apagava a
  pista que perguntava.** Aparecia também quando nada tinha falhado: a
  nota surge assim que ocorre, em qualquer lugar, uma perturbação
  inesperada, mesmo que o programa a suporte e depois termine
  normalmente; nunca era removida. E quem respondesse „Não" destruía
  os únicos detalhes do incidente – a nota desaparecia já ao
  *mostrar* a pergunta. Ambos corrigidos: um encerramento ordenado
  remove a nota, só se pergunta perante uma falha real, e só é
  assinalada depois da sua resposta. Os detalhes constam, de qualquer
  forma, no registo de erros do próprio computador – quem não quiser
  enviar nada não perde, mesmo assim, coisa alguma. Continua a ser
  enviado apenas o que viu por completo e autorizou você mesmo.

- **„Limpar" podia ficar bloqueado em silêncio.** Se os modelos de
  idioma ficassem presos ao carregar, o botão permanecia
  desativado – sem explicação. Um clique nele não fazia nada, e a
  barra de estado continuava a dizer „A carregar modelos de
  idioma…", mesmo depois de dez minutos. A causa: perturbações em
  processos de fundo iam para um local que ninguém vê ao arrancar a
  partir do gestor de ficheiros; ficava uma janela que parecia pronta
  a trabalhar e não reagia a nenhum clique. Agora, tais perturbações
  vão para o registo de erros, o carregamento dos modelos de idioma
  comunica a sua falha em qualquer caso, em vez de desistir em
  silêncio, e, se mesmo assim continuar em silêncio, a aplicação diz,
  ao fim de três quartos de minuto, que algo não está bem, com um
  conselho nos detalhes. O botão bloqueado indica, ao passar o rato, o
  seu motivo. Um primeiro carregamento longo não conta, com isto, como
  silêncio: enquanto for comunicado progresso, mantém-se calmo. Nada
  disto conta como falha: a aplicação continua a funcionar, e por
  isso, no arranque seguinte, também não se pergunta a esse respeito.

- **No Mac, o programa deixou de encontrar atualizações – e dizia que
  estava atualizado.** A versão Mac não trazia consigo um diretório de
  certificados de raiz; procurava-o num local que só existe no
  computador onde é construída. Com isso, não conseguia verificar,
  perante nenhum servidor, com quem estava a falar, e interrompia
  qualquer ligação: sem atualizações, sem ativação de licença, sem
  carregamento posterior de modelos de idioma, sem relatório de
  erros. Versões mais antigas transformavam isso, em silêncio, na
  informação „Está a usar a versão mais recente". Os certificados
  estão agora no próprio programa; se não encontrar nenhum ali, usa os
  do sistema e, no Mac, em último recurso, os do porta-chaves – e, se
  não houver nenhum de todo, diz-o, em vez de afirmar uma versão mais
  recente. A própria verificação nunca é desligada com isto.

  Esta única atualização, os utilizadores de Mac ainda têm de
  instalar manualmente: uma versão que não alcança o servidor também
  não se consegue atualizar a si própria.

### Alterado

- **A janela principal foi arrumada.** Em baixo estavam seis botões do
  mesmo tamanho lado a lado – „Sobre…", „Manual" e „Ajuda & FAQ" por
  baixo, apesar de os mesmos três caminhos já constarem no menu Ajuda
  acima. Estão agora reunidos num botão „Ajuda", que os expande;
  nenhum se perde. Ficam em baixo os dois caminhos com que
  realmente se começa: „Limpar" e „Ocultar manualmente…".

- **O que o programa está a fazer consta agora num local fixo.** A
  mensagem („A carregar modelos de idioma…", „(3/7) carta.pdf", „5 de
  7 ficheiro(s) limpo(s).") ficava, até agora, como texto cinzento
  entre duas filas de botões. Recebeu uma área própria, com um ponto
  colorido à frente: cinzento enquanto nada corre, azul durante o
  trabalho, verde após uma execução sem problemas e amarelo quando
  surgiram avisos. O ponto não diz nada que não conste ao lado – só o
  diz mais depressa.

- **As definições passaram a ser uma janela própria.** Estavam, até
  agora, na janela principal – uma caixa com quatro separadores que se
  expandia em „Mais definições" e que era depois pequena demais para o
  seu conteúdo: havia sempre uma barra de deslocamento lá dentro, e a
  escolha entre anonimizar e pseudonimizar ficava meio fora da
  imagem. O botão chama-se agora „Definições…" e abre uma janela com
  uma barra lateral; cada uma das quatro páginas cabe inteira. A
  janela principal deixa de saltar ao abrir, e a lista de ficheiros
  pode ser vista ao lado. Só mudou onde as definições estão – quais
  existem e o que fazem mantém-se inalterado.

- **„Detalhes" expande-se, em vez de saltar.** A janela crescia até
  agora numa imagem, e era preciso procurar o que tinha mudado. Agora
  move-se até lá.

- **Tamanhos de letra e espaçamentos seguem, em toda a janela, a mesma
  medida.** Os títulos tinham, em dois locais, tamanhos diferentes, e
  linhas do mesmo nível estavam espaçadas de forma diferente. Isto é
  visível como calma, não como uma alteração isolada.

- **Anonimizar é agora o padrão.** Até agora, a pseudonimização vinha
  ativada por defeito: as mesmas pessoas recebiam o mesmo número
  (`[NAME_1]`, `[NAME_2]`), as referências mantinham-se legíveis –
  juridicamente, no entanto, continuavam a ser **dados pessoais**.
  Quem nada definir recebe agora o processo que retira os dados do
  âmbito do RGPD: todos os resultados de um tipo têm o mesmo nome
  (`[NAME]`). A numeração continua a ser uma escolha, mantém-se sem
  alteração na mesma janela; as definições existentes permanecem como
  estão. Na linha de comandos, `--pseudonymisieren` (também
  `--mit-nummerierung`) repõe.

- **Os marcadores anonimizados deixam de poder ser anulados
  individualmente.** Quem anonimiza recebe, para cada pessoa, o mesmo
  marcador – e com isso deixa de haver um único local que pertença a
  um determinado nome. A janela de correção oferecia, mesmo assim,
  „Anular substituição": um clique teria inserido *um* dos valores em
  *todos* os locais. As linhas estão agora esbatidas como em
  indicações ocultadas, o clique diz o motivo, e um resultado
  corrigido manualmente deixa de receber um número que não consta em
  lado nenhum do resto do documento.

  Pelo mesmo motivo, deixa de haver „Retraduzir resposta" depois de
  uma execução anonimizada – antes teria colocado um nome alheio no
  lugar de cada pessoa. Quem precisar desse ciclo escolhe
  „Pseudonimizar"; a aplicação diz-o agora também assim, em vez de
  remeter para uma atribuição expirada.

  Na linha de comandos, `--zuordnung` interrompe-se agora ao
  anonimizar, em vez de escrever um ficheiro que não é uma
  retradução – na janela, a marcação já estava bloqueada há muito. Ou
  `--pseudonymisieren` junto, ou omitir `--zuordnung`; a mensagem
  diz-o. O resultado nem sequer é gerado nesse caso, para que um
  script não fique com trabalho pela metade.

- **O canal de atualização passa a estar em „Estável".** Sem escolha
  própria, o canal orientava-se, até agora, pelo tipo de construção da
  versão em curso – quem tivesse experimentado uma versão de teste
  passava a receber, a partir daí, versões de teste de forma
  permanente. Uma mudança de canal é uma decisão e deve permanecer
  assim; o padrão é por isso „Estável". Canais definidos permanecem
  intocados.

### Melhorado

- **„Beschwerdevorgang" (processo de reclamação) deixa de valer como
  nome de local.** No título „Nota de processo – Beschwerdevorgang 12
  C 345/26", o programa ocultava também o processo: o modelo de
  linguagem tomava-o por um local, e isso independentemente do
  contexto. Não é a palavra isolada que é abrangida, mas a
  **palavra-base** da composição – „vorgang" e „notiz" cobrem assim
  também processo comercial, contabilístico e de pagamento, ou a nota
  telefónica. De trinta termos administrativos verificados, três
  desencadeavam antes um falso alarme, agora nenhum; continua a ser
  encontrado tudo o que estiver ao lado („Beschwerdevorgang: Bernd
  Meisinger" perde o nome, não o título).

- **Anonimizar volta a registar – para o ajuste posterior e o
  registo.** No modo de funcionamento anonimizador, o programa não
  memorizava os valores encontrados. Com isso, duas coisas ficavam
  silenciadas: o ajuste de consistência à escala do documento (um
  apelido que surge mais tarde sozinho permanecia) e a lista de
  substituições no registo de verificação. Enquanto anonimizar era a
  escolha mais rara, isso quase não se notava – como padrão, teria-se
  tornado o caso normal. No documento nada muda: o marcador continua
  sem número.

- **„Nenhuma data pessoal" chama-se agora „nenhuma indicação
  pessoal".** No diálogo de recuperação e no aviso de rostos constava
  o termo jurídico *Datum* – o singular de „Daten". Era lido como um
  dia de calendário, tanto mais que a aplicação oferece, noutro
  local, „Remover também datas". Chama-se agora, em todo o lado,
  „Indicação", tal como nos quatro motivos acima na mesma janela.

- **A linha de origem só consta agora na janela „Sobre".** „Made with
  ♥ in Austria" ficava em baixo na janela principal, a meio da fila
  de botões, e lia-se ali como mais um botão. Continua na janela
  „Sobre" – onde se procura.

- **A área de depósito tem agora um limite visível.** O seu rebordo
  tracejado era tão pálido que quase não se destacava da janela – isso
  era indiferente enquanto a área era apenas uma área. Desde que é um
  botão que se pode alcançar com a tecla Tab, este traço é a única
  coisa que a mostra como elemento de controlo; por isso foi reforçado
  para o valor que a norma exige para isso.

## 0.10.22-beta.1 – 15 de agosto de 2026

### Novo

- **Se a monitorização da área de transferência for desligada, fica
  realmente desligada.** O vigilante mantém os últimos conteúdos na
  memória, para que o original possa ser reposto – até agora, mesmo
  quando tinha desligado a monitorização. Agora, o histórico é
  esquecido ao desligar. Isso custa a restauração depois de desligar, e
  é exatamente essa a intenção: desligado significa desligado.
- **O registo de erros deixa de conter caminhos de ficheiro.** Ficava
  apenas no seu computador e nunca era enviado por si só – mas trazia
  caminhos em texto simples, e um nome de ficheiro revela muitas vezes
  mais do que o conteúdo. De „…/Scheidung_Mueller_Vergleich.docx"
  resulta agora, ao escrever, `<ficheiro>.docx`; a extensão mantém-se,
  porque conta para a resolução de problemas. O mesmo se aplica à nota
  depois de uma falha.
- **A lista de substituições avisa agora dentro de si própria.** É o
  único ficheiro em que os seus dados originais estão em texto
  simples, e fica ao lado do resultado – quem partilhar uma pasta,
  partilha-a também. Agora o aviso consta como primeira linha **dentro**
  do ficheiro, a área de saída indica o caminho completo em vez de
  apenas o nome do ficheiro, e na linha de comandos o ficheiro é sequer
  mencionado pela primeira vez: até agora, não se sabia ali de todo que
  tinha sido criado.
- **Anonimizar ou pseudonimizar é agora uma escolha nomeada.** Nesse
  local constava até agora uma marcação „Dar o mesmo nome aos nomes
  iguais – a IA consegue então ainda saber quem é quem". Isso descrevia
  a vantagem e omitia a consequência: marcadores numerados
  sequencialmente (`[NAME_1]`, `[NAME_2]`) são **pseudonimização**, e
  dados pseudonimizados continuam a ser dados pessoais – quem
  acreditasse ter anonimizado com isso, enganava-se. Agora ambos os
  processos ficam lado a lado, cada um com o seu preço. O padrão
  continua a ser pseudonimizar, porque um documento que depois ainda
  seja lido ou processado por uma IA precisa das suas referências. Ao
  anonimizar, a lista de substituições fica bloqueada: tornaria o
  resultado de novo rastreável. O manual e as perguntas frequentes
  explicam a diferença nos 18 idiomas; na linha de comandos, o
  interruptor chama-se agora também `--anonymisieren`.
- **A linha por cima da área de depósito diz agora o que realmente é
  verdade.** Prometia „100% de processamento local – sem nuvem nem
  conta, em conformidade com o RGPD". Para os seus documentos isso é
  verdade, para o programa não com essa generalidade: procura
  atualizações, comunica erros a pedido, carrega modelos
  posteriormente e regista postos de trabalho comprados. Agora consta
  ali a afirmação mais estrita e sustentável: os seus documentos não
  saem do computador.
- **No resultado consta agora sempre que é necessário verificar.** Até
  agora, o Maskuro comunicava, depois de uma execução sem problemas,
  „12 indicação(ões) removida(s)" a verde e mais nada – isso lê-se como
  uma garantia de ter encontrado tudo. Os avisos só apareciam quando
  concretamente algo não podia ser verificado (imagens, anexos
  desconhecidos). Agora consta, de forma bem visível, sob cada
  resultado, que nem sempre são reconhecidos todos os dados pessoais,
  que a verificação cabe ao utilizador e que o que falta deve ser
  completado manualmente – na janela, na área de saída e na linha de
  comandos. Não é uma janela de aviso para fechar: a frase fica lá de
  forma permanente. O guia rápido diz-o agora com as mesmas palavras.
- **Depois de uma atualização, consta no arranque o que mudou.** Até
  agora, uma atualização decorria em silêncio e não se distinguia de um
  reinício. Agora aparece uma vez „O que há de novo" – e quem tiver
  saltado uma versão vê também as intermédias. Não no primeiríssimo
  arranque: ali continua a introduzir o guia rápido.
- **Chinês e japonês encontram agora nomes.** Até agora não encontravam
  **nenhum** – não poucos, nenhum. Faltava a ambos os modelos de
  linguagem a segmentação de palavras, sem a qual uma frase sem
  espaços vale como uma única palavra; o programa recorria, em
  silêncio, ao modelo substituto multilíngue. Ambos os idiomas
  reconhecem agora pessoas e locais como os restantes. O dicionário
  japonês é carregado juntamente com o idioma e não está incluído no
  programa – sozinho, teria cerca de 200 MB, que caso contrário toda a
  gente teria de carregar.
- **A Roménia é selecionável como país.** Até agora faltava por
  completo. Com isso são reconhecidas moradas romenas („Strada
  Victoriei 30"), códigos postais com localidade („010061 București") e
  o Cod Numeric Personal – este último apenas com dígito de controlo
  correto, para que nem todo número de treze dígitos numa fatura seja
  assinalado. Até então, em documentos romenos, o código postal
  permanecia legível ao lado do nome de local ocultado.
- **„Rasterizar página" no editor.** Se o texto de um PDF não puder ser
  removido – acontece em ficheiros de geradores alheios –, a página é
  agora, a pedido, substituída pela sua imagem: o texto fica assim
  irrevogavelmente removido, a página mantém-se legível e pesquisável.
  O aviso que comunica o caso oferece logo o passo como botão; via
  „Ferramentas → Rasterizar página" também funciona por iniciativa
  própria. Desfazer traz a página de volta.
- **A interface está agora disponível também em croata, grego,
  lituano, esloveno, japonês e coreano.** São assim dezoito idiomas. O
  manual, as perguntas frequentes e os textos legais estão completos
  nos seis. As legendas no documento limpo seguem a interface – de
  `[NAME_1]` resulta `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` ou
  `[氏名_1]`. **Em grego, japonês e coreano, as legendas ficam em
  letras latinas** – `[ONOMA_1]`, `[SHIMEI_1]`, `[IREUM_1]`. A
  interface mantém-se na sua própria escrita; só o que é escrito no
  documento fica em latino. O motivo é o conjunto de carateres do PDF:
  ali, legendas gregas e japonesas chegavam antes como `[??_1]`, e com
  isso já não era possível distinguir nome de local.
- **Juntam-se nove países, e sete existentes ficam completos.** São
  reconhecidos de novo números de identificação, fiscais e de
  segurança social, bem como moradas para **Croácia, Eslovénia,
  Grécia, Lituânia, Macedónia do Norte, Rússia, Ucrânia, China e
  Japão**. Nos países existentes, foram fechadas lacunas mais
  relevantes: para os **Países Baixos** e **Portugal** não havia até
  agora nenhum número de pessoa – o BSN neerlandês e o NIF português
  não eram reconhecidos, apesar de constarem em praticamente qualquer
  documento destes países. A Polónia recebe o número fiscal NIP, a
  Dinamarca, a Noruega e a Finlândia as suas moradas, o Canadá o seu
  código postal. São assim **35 países**.

### Removido

- **Para Linux deixa de haver, por agora, um pacote.** O código-fonte
  corre ali, mas faltam, no Linux, três coisas que este manual
  promete: arranque automático, atalhos de teclado globais e –
  consoante o ambiente de trabalho – o ícone na barra. Distribuir um
  pacote que faz menos do que o descrito seria o caminho errado.
  Windows e macOS não são afetados.

### Melhorado

- **As referências de processo são agora encontradas em todos os
  idiomas.** „Aktenzeichen 12/2026-AB" era removido, „File reference
  12/2026-AB" ou „Sygnatura 12/2026-AB" permaneciam: as palavras de
  campo com as quais o Maskuro reconhece um número assim só existiam
  em alemão. Agora conhece os equivalentes em doze idiomas – e, como
  até agora, só é substituído o número, a legenda antes permanece, para
  que no resultado se reconheça o que ali foi removido.
- **O Maskuro ocupa, em repouso, cerca de meio gigabyte a menos.** Ao
  arrancar, era até agora também carregado o modelo adicional da
  deteção mais rigorosa, para que a primeira limpeza não tivesse de
  esperar por ele. Medido, isso custava 648 MB de memória e poupava
  1,9 segundos – e custava-os mesmo quando apenas se abria e fechava a
  janela. O modelo é agora carregado na primeira vez que é necessário;
  a barra de estado avisa. O modelo de linguagem continua a ser
  carregado ao arrancar – a monitorização da área de transferência
  precisa dele de imediato.
- **A área de depósito é agora também operável sem rato.** „Arrastar
  ficheiros para aqui" era uma área que reagia a cliques – com o
  teclado não se chegava lá, e um leitor de ecrã lia-a como uma
  moldura com texto dentro, não como o que ela é. Agora é um botão: a
  tecla Tab salta para ela, Espaço e Enter abrem a seleção de
  ficheiros, e quem lá chegou vê-o pela margem. Através do menu
  „Ficheiro → Selecionar ficheiros" já funcionava antes, mas era
  preciso saber isso.
- **O nome do ficheiro limpo é agora também lido em voz alta.** Na
  lista de ficheiros, consta como segunda linha, mais pequena, sob o
  original – mas estava ali só desenhado, e um leitor de ecrã só dizia
  o original. Precisamente esta linha foi feita contra o engano de que
  uma execução não teve efeito, por na pasta estar o original
  intocado. A linha diz agora, lida em voz alta, „rechnung.pdf,
  Resultado: rechnung_bereinigt.pdf".
- **Elementos de controlo sem legenda dizem agora para que servem.** Os
  botões de símbolo na lista de ficheiros, os botões de desenho na
  janela de correção e todos os campos de seleção e de entrada eram
  sem nome para leitores de ecrã – eram anunciados como „botão" e
  „caixa de combinação", sem indicar de quê. Os botões numa linha
  incluem agora o nome do ficheiro: numa lista com vinte entradas,
  ouvia-se de outro modo vinte vezes a mesma frase.
- **Quem usa o teclado volta a ver onde está.** O botão „Limpar" e os
  botões de símbolo na lista de ficheiros estavam definidos a cores, e
  com isso deixava de aparecer o contorno que o sistema normalmente
  coloca à volta do elemento selecionado – ao percorrer com Tab, o
  olhar caía no vazio. Ambos têm agora um contorno próprio assim que
  chega a sua vez. Os botões não alteram o seu tamanho com isso.
- **Sete cores de texto estavam demasiado pálidas, em ambas as
  aparências.** Medidas segundo a norma habitual (WCAG 2.1), as linhas
  de aviso pálidas, os textos secundários na zona de depósito, os
  pontos do guia e, na aparência escura, adicionalmente o azul e o
  vermelho ficavam abaixo do limite de 4,5:1 – legíveis com boa luz e
  boa vista, caso contrário não. Todas foram reforçadas; a gradação
  mantém-se, os textos continuam a ler-se como texto secundário. Mais
  três – as cores em que avisos e sucesso são comunicados –
  mantinham-se apenas por pouco dentro do limite e foram atualizadas
  também: quem não as lê, não lê a informação sobre se algo correu
  mal. Visivelmente, só mudou o botão „Limpar" na aparência escura: traz
  agora letra escura em vez de branca, tal como os botões de destaque
  do Windows 11 também.
- **Cada linha da lista de ficheiros tem agora a sua própria cruz.** Até
  agora era preciso primeiro selecionar a linha e depois clicar em
  „Remover" – dois passos para uma coisa pequena. A cruz fica à direita
  na linha e precisa de apenas um. O botão „Remover" por baixo deixou
  assim de existir; quem quiser livrar-se de várias linhas de uma vez
  seleciona-as e usa a entrada no menu de contexto, que também indica
  quantas são. „Remover tudo" mantém-se. Da lista é sempre removida
  apenas a linha – nunca um ficheiro no disco.
- **Antes da verificação por IA, consta agora se este computador serve
  para isso.** Até agora, a janela só indicava o tamanho do modelo.
  Quem o ativasse num computador fraco só notava, no primeiro
  documento, que demorava muito tempo – depois de 5,4 GB de
  descarregamento. Agora a janela indica, **antes**, memória e espaço
  livre e diz o que isso significa; **depois**, a velocidade é medida e
  indicada no tamanho relevante: „Um documento de dez páginas demora,
  neste computador, cerca de 12 minutos." Se for demasiado lento, o
  programa desaconselha e oferece desligar de novo o nível – não
  proíbe nada.
- **A medição de velocidade corre agora em qualquer computador.** Até
  agora, só aparecia quando a aceleração gráfica estava também
  configurada – o que só existe no Windows. Em todos os outros
  computadores, o programa estimava por isso a duração com base num
  computador alheio, e precisamente onde é lento, a estimativa estava
  errada.
- **As moradas turcas são agora encontradas também em digitalizações.**
  Num cabeçalho de carta digitalizado, „34710 İstanbul" permanecia
  legível, enquanto a mesma indicação no texto ao lado desaparecia: o
  reconhecimento de texto lê o İ turco sem o seu ponto, e o padrão
  esperava uma letra maiúscula. O mesmo se aplicava a „Bağdat Caddesi".
- **As moradas espanholas sem nome de rua próprio são encontradas.**
  „Gran Vía 5" permanecia, porque o padrão esperava, depois do tipo de
  rua, ainda uma palavra de nome – em „Calle Mayor" existe uma, em
  „Gran Vía" o próprio tipo já é o nome. O mesmo se aplica agora a „La
  Rambla" e „Castellana".
- **Na janela „Sobre este programa" consta agora um aviso de
  transparência** sobre a aplicação ter sido desenvolvida com apoio de
  inteligência artificial. Diz respeito à origem do programa, não ao
  seu funcionamento: a limpeza continua a ser feita exclusivamente no
  próprio computador.
- **„Gerir idiomas" mostra agora primeiro os idiomas utilizáveis.**
  Para metade dos 48 idiomas não existe modelo de idioma próprio; ali,
  um modelo substituto multilíngue reconhece nomes apenas fracamente,
  nalgumas escritas nem sequer. Lado a lado numa lista, todos pareciam
  equivalentes. O padrão mostra por isso apenas idiomas com modelo
  próprio – através de „Mostrados", os restantes podem ser exibidos a
  qualquer momento, com uma frase sobre o que conseguem e o que não.
  Nada desaparece, e quem tiver configurado um idioma limitado
  mantém-no.
- **A pergunta sobre um idioma em falta indica agora a saída.** Se for
  reconhecido um idioma para o qual ainda nada está configurado, o
  programa oferecia até agora apenas „Carregar" ou „Continuar sem". Mas
  a deteção pode estar errada – em formulários curtos e listas com
  pouco texto corrido, decidem poucas palavras. Na janela consta agora
  por isso que se pode interromper e escolher manualmente o idioma
  correto, em vez de usar „Detetar automaticamente". Isso poupa, em
  caso de dúvida, um descarregamento de várias centenas de megabytes
  para um idioma que nem sequer é necessário.
- **As legendas dos marcadores falam agora o idioma da interface.**
  „[NAME_1]", „[ADRESSE_2]" e afins estavam sempre em alemão, seja qual
  fosse o idioma definido ou o idioma em que o documento estava
  redigido. Agora seguem o idioma da interface – em inglês, portanto,
  „[NAME_1]", „[ADDRESS_2]". Não o idioma do documento: este é
  adivinhado em „detetar automaticamente" e por vezes está errado; o
  idioma da interface nunca está.
- **Menos perguntas ao corrigir.** Onde o resultado é guardado consta
  agora de forma permanente em baixo na barra
  („→ vertrag_bereinigt.pdf", a pasta na dica); um clique nisso escolhe
  outro local, sem guardar de imediato. A pergunta ao guardar pela
  primeira vez deixa assim de existir. A pergunta „já editado – começar
  de novo?" pode ser memorizada para a sessão, e duas janelas de
  aviso que só davam uma informação ficam agora na barra de estado.
  Mantêm-se as perguntas que evitam um dano irreversível: o trabalho
  não guardado ao fechar e o aviso sobre texto não removido.
- **O resultado diz agora onde a própria digitalização não era
  legível.** Num documento digitalizado, o reconhecimento de texto do
  aparelho não lê tudo corretamente – de „Solarstraße 9" resulta então,
  por exemplo, „Solaret^aß« B". O que assim foi mal lido, nenhuma
  verificação consegue encontrar: parece, para qualquer padrão de
  pesquisa, um amontoado de letras. O programa não pode alterar isso,
  mas nomeia agora tais locais com o número de página – geralmente ali
  há carimbos, cabeçalhos de carta ou aditamentos manuscritos. Um
  aviso, não um alerta: num documento composto, não aparece.
- **A lista de ficheiros mostra agora como se chama o resultado.** Sob
  o nome do ficheiro consta, depois da execução, o nome do ficheiro
  limpo („→ vertrag_bereinigt.pdf"). Até agora só constava no registo,
  atrás de „Detalhes", e quem verificasse a pasta encontrava o
  original intocado. O nome da origem mantém-se – caso contrário, já
  não seria possível ver de que ficheiro provém um resultado.
- **Os botões numa linha concluída são maiores e mais claros.** Ver,
  Corrigir e „Mostrar na pasta" eram símbolos planos sem área e
  perdiam-se na lista – sendo, depois da execução, o único que ainda se
  clica.

### Corrigido

- **Na interface em idioma estrangeiro, as regras próprias para ocultar,
  mascarar e aplicar hash eram ignoradas em silêncio.** Quem tivesse
  definido que os nomes fossem ocultados em vez de substituídos
  continuava, mesmo assim, a recebê-los substituídos – assim que o
  programa não fosse usado em alemão ou inglês. A definição estava lá,
  simplesmente não fazia efeito, e no resultado não se via a
  diferença. Eram afetados nove dos doze idiomas de interface.
- **A definição „Idioma das legendas" não tinha efeito fora do alemão e
  do inglês.** „Alemão" e „Inglês" podiam ser escolhidos, mas no
  documento continuava o idioma da interface. Agora as três
  possibilidades funcionam; o padrão „como a interface" fornece, sem
  alteração, o mesmo de sempre.
- **Em pequenos excertos de texto, permaneciam nomes – por exemplo, numa
  citação de e-mail copiada.** Quem limpasse um excerto através da área
  de transferência recebia muitas vezes apenas o endereço de e-mail
  ocultado, mas não o nome por baixo. Decisivo era o mero número de
  linhas: a partir de seis linhas, o programa reconhecia o excerto como
  uma enumeração e encontrava os nomes; abaixo disso, não – uma
  citação de e-mail copiada tem cinco. Uma linha adicional qualquer,
  por exemplo um assunto, mudava o resultado. Agora bastam quatro
  linhas, e na medição desaparecem todos os nomes verificados em vez de
  um terço. Isto não afeta documentos mais longos nem texto corrido.
- **A aceleração gráfica da verificação por IA era desligada de novo
  logo depois de configurada.** Depois de configurar, o programa mede
  se a placa gráfica é realmente mais rápida do que o processador
  neste computador – mas essa medição falhava sempre, sem o dizer, e o
  resultado „ambos igualmente rápidos" decidia a favor do processador.
  Quem tivesse carregado os 65 MB ficava, depois disso, com menos do
  que antes. A medição corre agora; se falhar, deixa de alterar seja o
  que for.
- **A estimativa de tempo calculava, em cada computador, com a
  velocidade de outro.** Baseia-se na mesma medição; enquanto esta não
  corresse, valia o valor do computador de desenvolvimento. „Cerca de
  dois minutos" podia assim significar meia hora num computador lento.
- **O nível de IA trabalha com um novo modelo de linguagem
  significativamente melhor** (Qwen3.5-9B em vez de Qwen3-4B) e deixa
  de estar limitado a alemão e inglês, trabalhando em doze idiomas.
  Medido no corpus de verificação: o mesmo número de indicações
  encontradas do que sem o nível, mas menos de metade das ocultações
  supérfluas (75 → 31). O modelo é maior (5,4 em vez de 2,4 GB) e
  precisa de cerca do dobro do tempo de cálculo; ao ativar, é carregado
  uma vez, sendo o antigo removido nesse processo.
- **As moradas em francês, italiano, espanhol, português, polaco,
  turco e sueco são agora removidas por completo.** Até agora,
  desaparecia ali apenas o nome da rua e do local – o número de porta
  e o código postal permaneciam legíveis („[ORT_1] 28, 28013
  [ORT_2]"). Para estes idiomas não havia padrões de morada próprios;
  estão agora completados.
- **Grego e coreano não encontravam nomes de todo.** No grego, a causa
  era o modelo substituto – com o modelo próprio, que agora pode ser
  carregado, nomes e locais são reconhecidos corretamente. No coreano,
  a causa estava no programa: pressupunha que um nome começa por
  maiúscula, e o hangul não conhece maiúsculas. Eram afetadas sobretudo
  unidades curtas – células de tabela, campos de formulário, entradas
  de lista.
- **Um modelo de idioma que não podia ser carregado interrompia a
  limpeza.** Em vez de uma mensagem de erro, entra agora o modelo
  multilíngue, e o resultado indica que se trabalhou com a deteção mais
  fraca. Atualmente afeta chinês e japonês, cujos modelos precisam de
  uma separação de palavras que ainda não acompanha o programa.
- **Um idioma com modelo próprio valia como instalado assim que
  qualquer outro estivesse carregado.** Quem, por exemplo,
  configurasse turco, ficava com o modelo substituto multilíngue – e
  chinês, japonês, coreano ou grego apareciam depois na lista com
  marcação e „0 MB", apesar de faltar o seu modelo próprio. Assim,
  nunca podiam ser carregados posteriormente e trabalhavam de forma
  permanente com o substituto mais fraco. A lista mostra agora o
  estado real, com o tamanho de carregamento.
- **Um nível de deteção falhado ficava em silêncio.** Se „Deteção
  avançada" ou „Deteção máxima (IA)" estivesse ativada, mas o modelo
  não pudesse ser executado, o programa continuava a trabalhar sem
  esse nível – sem uma palavra sobre isso. O resultado parecia como
  qualquer outro, e o interruptor continuava em „ligado": pensava-se,
  assim, que o resultado do nível base era o melhor que se conseguia
  obter. O resultado diz-o agora e indica ambos – o que não foi
  verificado e como o modelo pode ser recarregado. O caso não é raro:
  em alguns computadores, o nível de IA falha ao carregar quando falta
  a aceleração gráfica.
- **Um erro ao carregar o modelo adicional interrompia toda a
  limpeza.** Em „Deteção avançada", só a avaliação do modelo estava
  protegida, não a sua leitura – e é exatamente aí que algo corre mal
  quando o ficheiro está danificado ou não é adequado ao computador. Em
  vez de uma mensagem de erro, existe agora um resultado do nível base
  com aviso.
- **Um idioma deixou de poder ser removido – e por isso também não
  recarregado.** Quem, em „Gerir idiomas", retirasse a marcação e
  aplicasse a alteração lia „Alemão removido", mas via a marcação de
  novo definida de imediato. A causa era a assunção a partir da pasta
  do programa: numa instalação para todos os utilizadores, os modelos
  de idioma ficam protegidos contra escrita na pasta do programa, e o
  programa vai lá buscar os que faltam, em vez de recarregar centenas
  de megabytes. Esta assunção corria a cada acesso – e copiava de
  volta, no mesmo instante, o idioma acabado de apagar. Agora acontece
  uma única vez; os modelos de idioma carregados posteriormente
  mantêm-se. Além disso, o programa verifica depois de apagar: o que
  não pôde ser removido é agora comunicado como falha, em vez de
  „removido".
- **Numa instalação para todos os utilizadores, o carregado
  posteriormente não podia ser guardado.** Quem instala o programa
  para todos os utilizadores tem-no em „Programas", e ali não pode
  ser escrito nada sem direitos de administrador. Para os modelos de
  idioma já havia, há muito, um local alternativo previsto; para outros
  não:
  - O **componente de pré-visualização de página** era descompactado,
    depois de 290 MB de descarregamento, na pasta do programa, e
    falhava ali – sem indicar um motivo. Fica agora junto aos modelos
    de idioma, onde, segundo a intenção, sempre devia estar.
  - A **aceleração gráfica** não pode ser desviada: troca bibliotecas
    no próprio programa. Em vez de primeiro carregar e depois falhar
    em silêncio, o programa diz agora previamente que aqui não é
    possível e o que isso significa – a deteção máxima continua a
    trabalhar, apenas através do processador.
  - Um **idioma incluído do reconhecimento de texto** não podia ser
    removido: era imediatamente restaurado a partir da pasta do
    programa. A mesma causa dos modelos de idioma, a mesma correção.
  - Ao remover um idioma, podiam ser apagados **dados de idioma de uma
    instalação Tesseract alheia**. Agora só é tocada a própria pasta.
  - O local alternativo só se aplicava até agora no Windows. Um
    arquivo Linux para `/opt` tinha a mesma necessidade sem a mesma
    saída.
- **Ao corrigir, desaparecia uma linha inteira, apesar de apenas uma
  palavra estar emoldurada.** Quem, num ficheiro já limpo, ocultasse um
  marcador perdia a linha em que estava: de „Sehr geehrte Frau Doktor
  [NAME_1]" não sobrava nada – e a mensagem dizia „uma palavra removida
  do documento". Era afetado qualquer ficheiro que já tivesse passado
  pelo programa, precisamente o caso para o qual existe a correção. O
  resto do texto permanece agora, no seu lugar inalterado.
- **„EMPLOYEES" por cima de uma lista de nomes era ele próprio
  ocultado.** O mesmo caso de „MITARBEITER" na 0.10.19, só que em
  inglês – ali tinha ficado por resolver. Em maiúsculas, falta ao
  modelo de linguagem a característica distintiva, e o título está
  por cima de uma série de nomes reais. Os nomes por baixo continuam a
  ser encontrados. Não foi incluído „staff": é um apelido existente, e
  a entrada levaria consigo todo „John Staff" – a mesma ponderação de
  então com „Arbeiter".
- **A forma jurídica era substituída uma segunda vez.** Num cabeçalho de
  carta digitalizado, o modelo de linguagem lia „GmbH", a morada e o
  código postal como **um único** local. A morada e o código postal
  recortavam depois as suas partes, e sobrava a forma jurídica como
  resultado próprio: no resultado constava „[ORT_1] [ORT_2]", onde se
  pretendia „[ORT_1] GmbH". O nome da empresa continua a ser
  substituído – só o acrescento isolado permanece agora, e o resultado
  lê-se como um cabeçalho de carta em vez de um exercício de espaços em
  branco.
- **Um resultado recortado não era reverificado.** A causa do caso
  acima, e vai mais além: os filtros contra resultados adivinhados
  corriam sobre o que os detetores **comunicam** – não sobre o que
  resta depois da resolução de sobreposição. Se um resultado longo for
  cortado por um detetor mais forte, o fragmento é um texto diferente
  do avaliado, e ninguém voltava a olhar para ele. Agora sim.
- **„Está a usar a versão mais recente" – apesar de não ter sido
  possível verificar de todo.** Quem tivesse definido como canal de
  atualização „Pré-visualização (Beta)" ou „Estável – recomendado"
  recebia esta informação, apesar de, até agora, nada ter sido
  lançado nesses canais. Agora o programa diz exatamente isso – e
  sugere escolher outro canal nas definições.
- **Fechar a janela durante o carregamento fazia um fio de execução
  falhar.** Quem iniciasse o Maskuro e fechasse logo a janela, enquanto
  os modelos de idioma ainda estavam a ser carregados, recebia no
  registo um relatório de erro: o processo de carregamento
  comunicava-se com uma janela que já não existia. Não tinha
  consequências visíveis, mas no registo constava uma falha onde
  apenas alguém foi mais rápido do que o programa.
- **O resultado é agora observado, não apenas relido.** Até agora, uma
  página valia como limpa quando o valor já não constava no texto.
  Numa digitalização, isso não é prova – ali o texto visível é uma
  imagem. No final, verifica-se por isso se a área no resultado está
  realmente ocultada; se ali ainda houver papel claro, o relatório diz-o
  expressamente, em vez de comunicar „substituído".
- **Uma indicação substituída permanecia na imagem.** Se o valor
  estivesse numa imagem – um cabeçalho de carta digitalizado, um
  carimbo, uma página inteira digitalizada –, era removido do texto do
  documento, mas continuava **visível**: o que a pessoa lê ali são
  pixels. O relatório comunicava, mesmo assim, „substituído". Agora a
  área na imagem é ocultada, seja qual for a estratégia definida, e o
  marcador fica claro sobre este fundo – feio, mas honesto, e a
  atribuição mantém-se. Se um formato de imagem não puder ser
  editado, o resultado diz-o agora expressamente, em vez de parecer
  limpo.
- **Numa digitalização, faltava por completo o marcador.** A camada de
  texto de uma página digitalizada é desenhada de forma invisível, e um
  marcador inserido nela herdava isso: definido, mas não visível. No
  local encontrado, não constava nada depois.
- **Um reconhecimento de texto que não podia sequer correr valia como
  bem-sucedido.** Se faltasse o ficheiro de idioma ou o motor de
  reconhecimento falhasse, o relatório comunicava „Imagem(ns) …
  foi(ram) verificada(s) por reconhecimento de texto (0
  resultado(s))" – ou seja, uma verificação que nunca aconteceu. Numa
  digitalização, essa é a única verificação de todo: um contrato com
  morada legível na imagem de página valia assim como concluído. Agora
  o relatório diz que nada foi verificado, e porquê.
- **O ficheiro de idioma era procurado na pasta errada.** Se no
  diretório de idioma próprio estivessem outros idiomas que não o do
  documento, o motor de reconhecimento recebia precisamente esse
  diretório e falhava – apesar de o idioma adequado estar ao lado.
  Agora é procurado o **idioma**, não a pasta.
- **O aviso sobre texto não removido aconselhava algo que não
  existe.** Remetia para „Ocultar como PDF" – mas isso gera uma vista
  em PDF de ficheiros do *Office* e nem sequer está disponível num
  PDF. Quem quisesse seguir o aviso procurava em vão. Agora consta ali
  o botão que resolve o assunto.
- **No editor, barras e marcadores caíam ao lado do local marcado.** Era
  afetado qualquer PDF em que uma linha termine num hífen e a palavra
  continue na seguinte – em digitalizações isso é particularmente
  notório, porque textos de contrato são compostos com hifenização
  contínua. As duas metades da linha valiam como *uma* palavra que se
  estende ao longo do espelho de texto, e qualquer moldura na sua
  proximidade assumia essa extensão. A própria deteção não muda com
  isto: o corpus de medição fornece o mesmo resultado de antes.
- **O editor avisava que o texto „ainda está no documento", apesar de
  ter sido removido.** Se a mesma palavra ocorresse várias vezes numa
  página – em contratos, a regra –, a autoverificação comunicava, após
  cada intervenção, uma falha. Agora conta as ocorrências, em vez de
  apenas verificar se a palavra ainda está algures. Numa falha real,
  continua a avisar sem alteração.
- **O ficheiro de resultado chamava-se, em cada idioma, „_bereinigt".**
  Pretendia-se sempre que o sufixo do nome seguisse o idioma da
  interface – em inglês, fazia-o de facto („_cleaned"), nos restantes
  dezasseis idiomas não. Quem usasse o programa em finlandês recebia
  „asiakirja_bereinigt.pdf". Agora o ficheiro chama-se
  „asiakirja_puhdistettu.pdf", em japonês „書類_除去済み.pdf" e assim
  por diante – cada um com a palavra que essa mesma interface usa na
  sua mensagem de conclusão. Quem tiver definido um sufixo próprio,
  mantém-no.
- **"Gerir idiomas" ficava sempre legendado em alemao.** Na lista dos
  48 idiomas de documento constavam os nomes em alemao, seja qual
  fosse a interface definida: um utilizador finlandes lia
  "Chinesisch". Agora consta ali o nome no seu idioma e, a seguir, o
  nome proprio - "Kiina (中文)". O nome proprio e intencional: quem
  reconhece o idioma pelo seu proprio nome encontra-o tambem quando a
  palavra finlandesa nada lhe diz.

## 0.10.19 – 12 de agosto de 2026

### Melhorado

- **A entrada no menu de contexto fala agora a sua língua.** Até agora
  aparecia lá o texto em alemão em qualquer sistema – mesmo num Windows em
  inglês. Agora segue o idioma de interface definido, e quem mudar o
  idioma vê a entrada renomeada imediatamente, sem reinstalar. (Windows;
  no macOS e no Linux, o nome do menu é ao mesmo tempo um nome de
  ficheiro – isso fica para mais tarde.)
- **O editor lembra-se em que vista trabalhou pela última vez.** Quem usa
  a pré-visualização de páginas recebe-a automaticamente no documento
  seguinte – sem a ativar de cada vez. Quem nunca a usou não nota nada:
  só é restaurada se o módulo necessário já estiver carregado, nunca é
  carregado nada de propósito para isso.

### Corrigido

- **„MITARBEITER" (COLABORADOR) por cima de uma lista de nomes era
  ocultado.** Em diretórios de colaboradores e organigramas, o cabeçalho
  desaparecia como suposto nome – está lá por cima de uma série de nomes
  reais, e em maiúsculas falta ao modelo de linguagem a característica
  distintiva. Os nomes por baixo continuam a ser encontrados.
- **Indicações de quantidade eram tomadas por moradas.** Em faturas, guias
  de remessa e listas de armazém, indicações como „3390 Protocolo",
  „1030 Montante" ou „3390 Armazém" desapareciam como suposto código
  postal com localidade – qualquer número de quatro dígitos parece um
  código postal austríaco. Se a seguir ao número houver uma palavra que a
  aplicação reconhece como substantivo comum, departamento, atividade ou
  rótulo de campo, esta permanece agora. Indicações de localidade reais
  não são afetadas, mesmo as que são simultaneamente uma dessas palavras
  („4692 Local"). Não fica resolvido o caso de a seguir ao número estar
  uma palavra totalmente comum („3390 Prateleira") – para isso é
  necessário um diretório de códigos postais.
- **A ajuda mencionava uma opção de menu que não existe.** O manual, a
  imagem e a mensagem no final da instalação falavam de „Limpar documento
  para IA"; mas a entrada no menu de contexto chama-se „Remover dados
  pessoais". Quem seguisse a ajuda procurava em vão. Os três locais
  mencionam agora a opção de menu como ela realmente se chama.
- **„Iniciar com o sistema" não podia ser desligado.** Quem tivesse
  assinalado „Iniciar com o Windows" durante a instalação via, mesmo
  assim, uma marcação vazia nas definições – e, mais grave: ligar e
  desligar na aplicação não tinha efeito, o programa continuava a
  iniciar-se com o Windows. A causa eram dois locais onde o Windows
  procura programas de arranque; a aplicação só conhecia um deles. Agora
  ambos contam, o interruptor mostra o estado real e atua em ambas as
  direções. Também considerado: quem desativar a entrada no Gestor de
  Tarefas vê isso agora na aplicação – e quem a voltar a ativar lá anula
  assim a desativação.
- **Cabeçalhos por cima de listas de nomes eram ocultados.** „LISTA DE
  PARTICIPANTES CONVERSA DE OFICINA" ou „VISÃO GERAL DE COLABORADORES
  SERVIÇOS INTERNOS" por cima de uma lista de pessoas desapareciam como
  suposto nome. Em maiúsculas, falta ao modelo de linguagem o seu melhor
  sinal de reconhecimento, e em alemão todos os substantivos são
  escritos com maiúscula inicial – „Teilnehmerliste Werkstattgespräch"
  parece então „Anna Huber". Composições em `-liste`, `-dienst`,
  `-gespräch`, `-sitzung` e `-besprechung` permanecem agora. As palavras
  de base sozinhas continuam a valer como nome: *Liste* e *Dienst* são
  apelidos existentes, *Teilnehmerliste* não é.
- **Indicações colocadas na vertical recebiam um marcador ilegível.**
  Referências de processo na margem da página, iniciais do responsável
  junto à lombada, cabeçalhos de tabela na vertical: essas indicações
  eram encontradas e removidas, mas o marcador saía atravessado sobre o
  texto, comprimido a um ou dois pontos e por vezes para além da borda do
  papel. Agora segue o texto – na vertical, em tamanho legível e na
  mesma direção em que a indicação estava. O mesmo se aplicava a páginas
  rodadas posteriormente (texto escrito na horizontal com rotação de
  página registada, como algumas aplicações de saída produzem); também aí
  o marcador fica agora como se vê a página. „Sehr geehrte Frau Doktor
  Anneliese Berger" dava apenas „Anneliese" como nome – „Berger" ficava
  no documento. O mesmo acontecia com qualquer nome com segundo nome
  („Frau Anna Maria Berger"). A causa era a regra para o nome a seguir a
  uma saudação: tinha duas posições de palavra, e um título ou um segundo
  nome consumia a primeira. Com „Dr." nunca se notava – o ponto quebra a
  regra, e o modelo de linguagem apanhava o nome inteiro. Agora os
  títulos são ignorados sem consumir uma posição, e o nome pode ser
  composto por três partes. Um cargo **depois** do nome continua a não
  funcionar: „Frau Anna Huber Geschäftsführerin" substitui o nome, não o
  cargo.
