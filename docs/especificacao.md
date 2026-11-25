# desembaralhe. — Especificação geral (v0.3)

Oct 23, 2026 · @Karine Araújo

## Visão do produto

O desembaralhe. interpreta tiragens de Tarô e Baralho Cigano realizadas com o baralho físico do usuário. A leitura é personalizada por IA, utilizando uma base de significados revisados e referências verificáveis.

O produto relaciona pergunta, cartas e posições para oferecer uma interpretação compreensível, contextualizada e transparente quanto às suas fontes.

### \
**Decisões já tomadas**\


- **Sorteio físico:** o usuário embaralha e retira as cartas do próprio baralho. O aplicativo interpreta as cartas informadas.
- **Leitura personalizada:** a IA redige a interpretação a partir da pergunta e da tiragem, sem apenas concatenar textos prontos.
- **Base editorial:** os significados utilizados devem vir de conteúdo revisado, vinculado a fontes identificáveis.
- **Oráculos previstos para o MVP:** Tarô Rider-Waite, Tarô de Marselha e Baralho Cigano — Lenormand.
- **Entrada manual:** o usuário informa as cartas e suas posições. Reconhecimento por foto fica para uma versão posterior.
- **IA em toda leitura:** cada interpretação é gerada pela IA para garantir personalização, com custo controlado pelas medidas da seção de custo.
- **Pares do Lenormand:** a base terá todos os 1.260 pares ordenados. A primeira carta é o assunto e a segunda a qualifica.
- **Diário no aparelho durante o piloto:** a entrega usa um buffer temporário no servidor. A sincronização será decidida depois do piloto.
- **Curadoria com IA cruzada:** rascunhos e pré-revisão por dois modelos de fornecedores diferentes, com aprovação humana obrigatória.
- **Melhoria contínua:** revisores autorizados marcam problemas e propõem melhorias de significados, sempre com fonte e aprovação editorial.

### Compromisso do produto

As referências permitem verificar a origem dos significados utilizados. Elas não comprovam previsões ou fatos sobre pessoas.

A leitura deve apresentar possibilidades interpretativas e pontos de reflexão, sem prometer resultados ou apresentar suposições como acontecimentos confirmados.

## Públicos

São dois públicos, e o tarólogo profissional é o que tem mais disposição a pagar, porque usa o app para ganhar dinheiro.

| Público | O que busca | Recursos-chave |
| --- | --- | --- |
| Tarólogo profissional | Agilidade e embasamento nas consultas que vende | Registro de consultas, histórico por consulente, relatório com a própria marca para enviar ao cliente |
| Usuário final | Autoconhecimento e orientação pessoal | Leitura personalizada, diário de tiragens, aprendizado das cartas |

**Hipótese comercial:** profissionais podem ter maior disposição a pagar porque utilizam o produto em sua atividade remunerada. Essa hipótese deve ser validada com uso real e uma oferta concreta.

A validação deve observar:

- Tempo gasto por consulta antes e depois do uso.
- Quantidade e natureza das correções feitas na interpretação.
- Utilidade das fontes durante a consulta.
- Interesse em reutilizar o produto.
- Disposição a pagar por um plano com preço e limites definidos.

## Escopo e estratégia de lançamento

Os três oráculos permanecem previstos para o MVP. Cada tradição e método só deve ser disponibilizado quando houver conteúdo suficiente e aprovado para sustentá-lo.

**Proposta de implementação:** começar com um piloto de uma tradição e métodos curtos. O objetivo é medir qualidade, esforço editorial e custo antes de ampliar a cobertura.

| Fase | Escopo |
| --- | --- |
| Piloto | Uma tradição, poucos métodos, entrada manual, interpretação e fontes |
| MVP | Três tradições com cobertura aprovada, diário e limites de uso |
| Validação profissional | Histórico por consulente, revisão e relatório com marca |
| Expansão | Novos métodos e funcionalidades posteriores ao MVP |

Se o público profissional for priorizado, revisão e relatório devem entrar no piloto desse público.

## Fluxo do usuário

O fluxo possui cinco etapas:

### 1. Oráculo

O usuário escolhe Rider-Waite, Marselha ou Lenormand, conforme disponibilidade.

A escolha define o catálogo de cartas, as orientações permitidas, a base de significados e os métodos compatíveis.

### 2. Método de tiragem

O usuário escolhe entre os métodos habilitados para aquele oráculo.

Cada método precisa informar:

- Quantidade de cartas.
- Ordem e disposição das posições.
- Nome e significado de cada posição.
- Tradições compatíveis.
- Versão do método adotado pelo aplicativo.

Métodos candidatos incluem conselho do dia, duas cartas, três cartas, método americano, Cruz Celta e Templo de Afrodite. A lista final e suas definições permanecem em aberto.

Nos métodos de Lenormand, cada método define quais posições são vizinhas e em que direção o par é lido. Na linha de cartas, a leitura vai da esquerda para a direita. No Grand Tableau, também devem ser fixados os sentidos das verticais e diagonais. O backend usa essa definição para montar os pares ordenados enviados à IA.

### 3. Pergunta e tema

O usuário escreve a pergunta e escolhe um tema.

Temas iniciais propostos:

- Amor e relacionamentos.
- Trabalho e carreira.
- Dinheiro.
- Espiritualidade.
- Decisões.
- Geral.

O tema ajuda a selecionar complementos editoriais disponíveis. Quando não houver conteúdo específico para o tema, o sistema pode utilizar o significado geral aprovado, sem inventar uma especialização.

### 4. Cartas

O usuário informa uma carta por posição.

No Tarô, indica a orientação normal ou invertida, conforme as regras habilitadas para a tradição. No Lenormand, o MVP proposto não utiliza cartas invertidas.

Antes de interpretar, o aplicativo apresenta uma revisão com pergunta, método, cartas, posições e orientações.

### 5. Interpretação

O resultado apresenta:

- Síntese relacionada à pergunta.
- Interpretação de cada carta em sua posição.
- Relações entre cartas, quando sustentadas pelo conteúdo disponível.
- Perguntas ou sugestões para reflexão.
- Fontes utilizadas.
- Opção de salvar a leitura.

### Regras do fluxo

- Todas as posições precisam estar preenchidas.
- Uma carta não pode se repetir na mesma tiragem, considerando o uso de um único baralho.
- Alterações de oráculo ou método exigem revisão das cartas preenchidas.
- Reabrir uma leitura salva não gera nova interpretação nem consome crédito.
- Alterar os dados de uma leitura concluída cria uma nova versão.
- O eventual consumo de crédito deve ser informado antes da geração.

## Base de conhecimento

A base será estruturada para permitir recuperação precisa por carta, tradição, orientação e contexto.

Ela substitui a busca ampla em PDFs durante a interpretação. Sua organização facilita a rastreabilidade, mas não elimina a necessidade de revisar o conteúdo e avaliar as respostas da IA.

### Organização em camadas

| Camada | Conteúdo |
| --- | --- |
| Tradições | Convenções e regras de cada oráculo |
| Cartas | Identificadores, nomes e características |
| Significados | Conteúdo geral por carta e orientação |
| Temas | Complementos específicos, quando disponíveis |
| Métodos e posições | Estrutura da tiragem e função de cada posição |
| Combinações | Interações documentadas entre cartas |
| Fontes | Obra, autor, edição, idioma e situação de uso |
| Evidências | Trechos e páginas ou outros localizadores verificáveis |
| Revisões | Responsável, data, versão e aprovação |

Não é obrigatório produzir um texto separado para todas as combinações de carta, posição e tema.

O sistema pode combinar o significado aprovado da carta com a função aprovada da posição. Conteúdos específicos são adicionados quando houver fundamento editorial para isso.

### Dimensionamento inicial

| Conteúdo | Volume de referência |
| --- | --: |
| Tarô completo, normal e invertido, por tradição | 156 entradas |
| Rider-Waite e Marselha, tratados separadamente | 312 entradas |
| Cartas de Lenormand | 36 entradas |
| Pares ordenados de Lenormand, sem repetição da mesma carta | 1.260 pares possíveis |
| Métodos | Uma definição versionada por método e suas posições |

Os 1.260 pares ordenados são obrigatórios: o Lenormand só é habilitado quando todos estiverem aprovados, cada um com evidência. A chave do par é (carta A, carta B), com A diferente de B, e o par invertido nunca substitui o original. Um teste automático confere a cobertura completa antes da liberação.

Como poucas fontes descrevem todos os pares, a maioria será síntese editorial derivada dos significados individuais das duas cartas, identificada como tal e citando as fontes das cartas.

Se forem criadas entradas específicas para todas as cartas nas dez posições da Cruz Celta, serão 1.560 combinações por tradição, antes de considerar temas e fontes. Essa expansão dependerá de necessidade comprovada.

### Curadoria e publicação

O conteúdo segue os estados:

**Rascunho → Em revisão → Aprovado → Publicado**

Entradas podem ser retiradas de publicação sem apagar sua identificação e seu histórico.

- A IA pode auxiliar na elaboração de rascunhos.
- A fonte precisa ser consultada e conferida.
- Cada entrada publicada exige revisão editorial.
- Uma síntese criada pela curadoria deve ser identificada como síntese editorial.
- A participação de profissionais como curadores depende de critérios de seleção, responsabilidades e condições de uso do conteúdo.

### Pipeline de produção com IA cruzada

A IA rascunha e faz a pré-revisão; a pessoa confere e aprova. Toda entrada publicada continua exigindo revisão humana.

1. **Trechos das fontes:** extrair os trechos de cada carta das fontes aprovadas, com obra, edição e página, conferidos por uma pessoa.
2. **Rascunho (modelo A):** gera o texto em formato estruturado, com cada afirmação ligada ao identificador do trecho que a sustenta.
3. **Checagens automáticas:** formato, tamanho, evidências existentes, par sem repetição e textos de A→B e B→A distintos.
4. **Revisão cruzada (modelo B, de outro fornecedor):** classifica cada afirmação como sustentada, parcialmente sustentada ou sem suporte, e aponta mistura de tradições e textos genéricos.
5. **Checagem do conjunto:** detecta textos quase idênticos e verifica a coerência de cada carta nos pares em que aparece.
6. **Roteamento humano:** fila rápida quando os modelos concordam e tudo está sustentado; fila completa, com edição, quando há divergência ou afirmação sem suporte.
7. **Medição:** tempo por entrada, concordância entre modelos e taxa de rejeição humana do que a IA aprovou. Uma taxa alta endurece as regras da etapa 4.

O tempo real por entrada será medido num lote piloto de 50 pares antes de fechar o cronograma. Amostras de entradas já aprovadas devem ser reauditadas periodicamente, porque modelos diferentes podem errar juntos.

### Ciclo de revisão em uso

A base melhora com o uso real por meio de revisores autorizados.

- **Papel de revisor:** permissão concedida a usuários selecionados, como tarólogos curadores. Só esse papel propõe mudanças na base. O usuário comum dá apenas um retorno simples (útil ou não útil, clara ou confusa).
- **Marcações:** o revisor marca o problema numa carta em posição ou num par: significado incorreto para a tradição, fonte que não sustenta, leitura genérica, posição mal contextualizada ou problema de linguagem. Cada marcação guarda a geração de origem e as versões usadas, para separar erro da base de erro da IA.
- **Propostas de melhoria:** sempre com fonte, seguem Proposta → Em análise → Aceita ou Rejeitada. A proposta aceita vira nova versão da entrada e passa pelo fluxo editorial normal. Nada é publicado automaticamente.
- **Fila priorizada:** entradas com mais marcações, de mais revisores diferentes, sobem na fila de curadoria.
- **Salvaguardas:** marcações de um único revisor têm peso menor; a marcação guarda identificadores das entradas, não o texto da pergunta, salvo autorização.
- **Acurácia preditiva fora das métricas:** o registro de que uma leitura "se confirmou" fica no diário do usuário como reflexão pessoal e não altera significados nem métricas de qualidade.

### Conteúdo ausente ou divergente

- Sem significado essencial aprovado, a interpretação não é gerada.
- Sem complemento temático, pode ser utilizado o significado geral.
- Sem combinação cadastrada, a IA não deve apresentar um significado específico daquele par como conteúdo documentado.
- Fontes de tradições diferentes não devem ser misturadas silenciosamente.
- Divergências precisam ser resolvidas editorialmente ou apresentadas com clareza.

### Direitos de uso

Cada fonte deve ter sua situação de uso verificada antes da publicação.

A análise deve considerar obra, edição, tradução, imagens e forma de utilização. Referência bibliográfica, citação e incorporação de conteúdo à base são usos diferentes.

Não presumir autorização apenas pela antiguidade do autor ou pela disponibilidade de um PDF na internet.

## Papel da IA

A IA transforma o conteúdo recuperado em uma leitura personalizada.

Ela pode relacionar os significados à pergunta e às posições, mas deve distinguir a aplicação interpretativa do conteúdo atribuído às fontes.

### Entrada

- Pergunta e tema.
- Oráculo e método.
- Cartas, posições e orientações.
- Significados e regras aprovados.
- Evidências autorizadas para aquela leitura.

### Saída

- Síntese da tiragem.
- Interpretação por posição.
- Reflexões relacionadas à pergunta.
- Identificadores das evidências utilizadas.

O backend utiliza esses identificadores para apresentar autor, obra, edição e página. Esses dados não devem ser inventados ou preenchidos livremente pela IA.

### Regras de interpretação

- Não acrescentar significados sem suporte no conteúdo recebido.
- Não inventar fontes.
- Não prometer resultados.
- Não apresentar acusações ou intenções de terceiros como fatos.
- Não oferecer diagnósticos ou confirmar gravidez, morte ou resultados financeiros.
- Manter linguagem acolhedora e compreensível.
- Tratar a leitura como orientação interpretativa para reflexão.

Perguntas sensíveis devem seguir uma política específica de resposta. O aviso geral do aplicativo não substitui essa política.

## Modelo de redução de custos da IA

A proposta é uma única chamada curta por leitura, num modelo pequeno, com contexto enxuto. Com modelos pequenos, isso custa frações de centavo de dólar por leitura (estimativa aproximada, a validar com medição real).

| Alavanca | Como funciona | Efeito no custo |
| --- | --- | --- |
| Contexto enxuto | Enviar só os trechos da base das cartas sorteadas, nunca livros inteiros ou buscas amplas | Corta o maior volume de tokens de entrada |
| Modelo pequeno por padrão | Modelos pequenos e rápidos redigem bem quando o conteúdo já vem pronto | Custo por token muito menor |
| Roteamento por método | Tiragens simples no modelo pequeno; Cruz Celta e leituras premium num modelo maior | Paga mais só onde há valor percebido |
| Cache de prompt | Instruções fixas e estilo ficam no início do prompt, sempre iguais, para aproveitar o desconto de cache dos provedores | Barateia a parte repetida de toda chamada |
| Saída limitada por método | Tamanho máximo da resposta definido para cada método | Controla os tokens de saída, os mais caros |
| Uma chamada por leitura | Síntese e parágrafos por posição na mesma resposta | Evita várias chamadas por tiragem |
| Limites por plano | Número de leituras por dia ou por crédito, e bloqueio de uso abusivo | Impede que poucos usuários gerem a maior parte do custo |

- **Medição desde o primeiro dia:** registrar tokens de entrada, de saída e custo por leitura e por método. Os preços reais por modelo devem ser confirmados nas páginas dos provedores antes de fechar a precificação.

## 7. Validação e tratamento de falhas

Antes da geração, o backend verifica:

- Compatibilidade entre oráculo, método e cartas.
- Preenchimento e orientação.
- Cobertura editorial necessária.
- Permissão e limite de uso.
- Existência de uma operação idêntica já em andamento ou concluída.

Depois da geração, verifica:

- Estrutura da resposta.
- Presença de todas as posições.
- Referências pertencentes ao contexto enviado.
- Limites de tamanho.
- Ausência de truncamento.

Essas verificações não comprovam fidelidade semântica. A aderência aos significados será avaliada também por revisão humana de amostras.

### Cobrança e recuperação

- Solicitações duplicadas devem retornar a mesma operação.
- Falhas definitivas não devem consumir crédito.
- Se a leitura foi concluída e a conexão caiu, ela deve poder ser recuperada.
- Novas tentativas precisam ter limite e custo registrado.
- Custo do provedor e consumo de crédito do usuário devem ser registrados separadamente.

## 8. Arquitetura do MVP

### Aplicativo

Coleta os dados da tiragem, apresenta o resultado e permite consultar o diário.

### Backend

- Mantém a chave de API fora do aplicativo.
- Autentica usuários.
- Valida entradas.
- Recupera conteúdo aprovado.
- Aplica limites e controla créditos.
- Monta o contexto e chama o provedor.
- Valida e entrega a resposta.
- Registra métricas e versões.

### Base editorial

Armazena significados, métodos, evidências e histórico de revisão.

### Provedor de IA

Recebe apenas o contexto necessário e devolve a interpretação.

**Armazenamento do diário:** no piloto, o diário fica no aparelho. A sincronização será decidida depois das primeiras medições; o buffer de entrega abaixo pode virar a porta de entrada desse armazenamento sem refazer o fluxo.

### Entrega e recuperação da leitura

O resultado fica no servidor só até o app confirmar o recebimento, com prazo máximo curto.

1. O app gera uma chave de idempotência por pedido de leitura.
2. O backend conclui a geração mesmo se a conexão cair e guarda o resultado cifrado num buffer temporário, associado à chave.
3. Ao reconectar, o app pede a leitura pela mesma chave e recebe o resultado existente, sem nova chamada à IA nem nova cobrança.
4. Quando o app salva a leitura no diário, envia a confirmação e o backend apaga o conteúdo.
5. Sem confirmação, o conteúdo é apagado ao fim do prazo (proposta: 24 horas).

- **Mantido no servidor:** apenas metadados da operação (chave, status, modelo, tokens, custo e crédito). Pergunta, cartas e texto não permanecem.
- **Crédito:** consumido somente na entrega. Leitura expirada sem confirmação devolve o crédito; o custo do provedor fica registrado à parte.
- **Reforços opcionais:** cifrar o buffer com uma chave pública efêmera enviada pelo app e escolher provedor de IA com retenção zero ou curta.
- **Privacidade:** a política informa que o conteúdo da leitura fica no servidor por até 24 horas apenas para garantir a entrega.

## 9. Custo e limites de uso

A proposta inicial é utilizar uma chamada principal por leitura, com contexto restrito ao conteúdo necessário.

O modelo será escolhido por avaliação de qualidade, latência e custo. Métodos diferentes só utilizarão modelos diferentes se os testes justificarem essa complexidade.

| Medida | Objetivo |
| --- | --- |
| Contexto selecionado | Reduzir tokens sem remover conteúdo necessário |
| Saída limitada por método | Controlar tamanho e custo |
| Modelo validado para a tarefa | Equilibrar qualidade e preço |
| Novas tentativas limitadas | Evitar custo imprevisível |
| Limites por plano | Controlar consumo e abuso |
| Cache, quando aplicável | Reduzir parte do custo repetido |

Não será assumido um custo fixo por leitura antes das medições.

O cálculo deve considerar tokens, novas tentativas, infraestrutura, pagamento, suporte e curadoria.

## 10. Medição e auditoria

Desde o piloto, serão acompanhados:

| Área | Indicadores |
| --- | --- |
| Fluxo | Início, conclusão e abandono por etapa |
| Qualidade | Fidelidade à base, relevância e erros por tipo |
| Fontes | Referências válidas e conteúdo efetivamente sustentado |
| Operação | Sucesso, falhas, latência e novas tentativas |
| Custos | Tokens e custo por tentativa, leitura e método |
| Curadoria | Tempo de pesquisa, revisão e retrabalho |
| Valor profissional | Tempo economizado, correções e reutilização |

Cada resultado deve informar período e tamanho da amostra.

As metas quantitativas serão definidas antes do piloto e ajustadas com base nas primeiras medições.

### Rastreabilidade

Cada geração registra versões do método, prompt e conteúdo, além de modelo, evidências utilizadas, custo e resultado das validações.

Perguntas e interpretações completas não devem ser enviadas indiscriminadamente para logs e ferramentas de analytics.

### Critérios mínimos de liberação

- Sem erros críticos conhecidos.
- Testes de isolamento entre contas aprovados.
- Testes de duplicidade e cobrança aprovados.
- Referências inválidas rejeitadas nos testes.
- Cobertura editorial suficiente para todos os métodos habilitados.
- Avaliação humana concluída sobre casos representativos.
- Procedimentos de recuperação e exclusão verificados.

Mudanças no modelo, prompt, métodos ou base exigem nova avaliação dos casos afetados.

## 11. Privacidade

O produto pode processar perguntas íntimas e dados sensíveis, inclusive de terceiros.

Antes do lançamento, devem ser definidos:

- Finalidades e bases legais aplicáveis.
- Dados estritamente necessários.
- Retenção e exclusão.
- Condições do provedor sobre armazenamento e uso dos dados.
- Mecanismo aplicável à transferência internacional.
- Controle de acesso ao histórico e aos relatórios.
- Informações e escolhas apresentadas ao usuário.

Não enviar dados cadastrais ao modelo sem necessidade. Retirar nome e e-mail não garante anonimização de uma pergunta.

No uso profissional, dados do consulente devem ficar separados do contexto enviado à IA sempre que possível.

## 12. Fora do MVP

- Reconhecimento de cartas por foto.
- Bot no WhatsApp.
- Chave própria do usuário.
- Versão open source.
- Modelo de IA no aparelho.
- Modo estudo com flashcards e quizzes.
- Lembretes para revisitar leituras após um período.

O retorno ao diário deve incentivar reflexão sobre a experiência, sem tratar coincidências como comprovação de capacidade preditiva.

## 13. Principais riscos

| Risco | Resposta prevista |
| --- | --- |
| Leitura genérica | Avaliação de relevância e testes por método |
| Significado inventado | Contexto controlado, validação e revisão humana |
| Referência válida usada indevidamente | Auditoria da relação entre afirmação e evidência |
| Mistura de tradições | Separação de conteúdo e compatibilidade explícita |
| Curadoria maior que o previsto | Medição por lote e expansão gradual |
| Custo elevado | Orçamento por método e controle de tentativas |
| Cobrança duplicada | Idempotência e testes de concorrência |
| Exposição de dados | Acesso restrito, minimização e retenção definida |
| Uso inadequado de fontes | Verificação dos direitos de cada material |
| Rejeição em lojas | Revisão das regras vigentes e demonstração do diferencial funcional |

## 14. Decisões em aberto

- Qual público orientará a primeira validação?
- Qual tradição e quais métodos entram no piloto?
- Como será comprovada a disposição a pagar?
- Quais recursos profissionais entram no MVP?
- Quais fontes e edições serão utilizadas?
- Quem revisará a base e com quais critérios?
- Quais convenções de orientação serão adotadas em cada tradição, incluindo o sentido das verticais e diagonais no Grand Tableau?
- Quais metas de qualidade, custo e latência liberarão o lançamento?
- O diário passará a ser sincronizado depois do piloto?
- A primeira plataforma será web, Android, iOS ou uma combinação?
- Haverá assinatura, créditos ou ambos?
- Existirá plano gratuito e com quais limites?

## 15. Primeira entrega verificável

A primeira entrega deve permitir executar e auditar o percurso completo:

**Informar pergunta e cartas → recuperar conteúdo aprovado → gerar interpretação → validar referências → salvar → recuperar a leitura sem novo consumo.**

Essa entrega será usada para medir qualidade, custo e esforço de curadoria antes da ampliação do escopo.
