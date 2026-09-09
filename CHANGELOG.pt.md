O que muda de versão para versão – descrito do ponto de vista da aplicação,
não das suas entranhas. Quem quiser saber *do que* ela é feita encontra isso em
[LIZENZEN.md](LIZENZEN.md); aqui está o que muda para o trabalho com ela.

A numeração segue a contagem habitual: o **primeiro** número muda quando algo
deixa de funcionar como antes, o **segundo** com novas funcionalidades, o
**terceiro** com correções de erros.

## 0.10.52-alpha.20260903 – 3 de setembro de 2026

- Um lote com mais de quatro ficheiros deixa de ficar parado após várias
  respostas nas janelas de pré-visualização. Outros documentos continuam a
  ser preparados em segundo plano; após uma resposta, o ficheiro correspondente
  passa agora a ser concluído de forma fiável e é libertado o lugar seguinte
  no lote.
- A correspondência de marcas de empresa curtas em PDFs limita-se agora ao
  texto reconhecido em imagens. Por isso, no texto normal da página, uma
  deteção longa do modelo que abrange várias linhas já não faz com que uma
  palavra isolada igual noutro ponto seja também ocultada.

## 0.10.51-alpha.20260903 – 3 de setembro de 2026

- A lista de alterações aparece agora na respetiva língua – em
  maskuro.com/neuigkeiten e, no programa, em «Alterações», bem como em
  «Novidades» após uma atualização. Até agora, nas dezoito versões linguísticas
  aparecia texto em alemão sob um título traduzido. Quando ainda falta uma
  tradução, a versão em causa permanece em alemão em vez de desaparecer; a
  lista de versões é igual em todo o lado.

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
