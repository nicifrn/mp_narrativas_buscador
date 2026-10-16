# Plano de trabalho - Busca textual no acervo do projeto Narrativas

**Aluno:** Ítalo (@italogomees) - Técnico Integrado em Informática

**Orientadores:** Prof. Bruno Gomes (@brunogomesifrn) e Entony (@franciscoentony) - NIC/IFRN

**Repositório:** https://github.com/nicifrn/mp_narrativas_buscador

**Período:** 16/10/2026 a 10/12/2026: 8 sprints de 1 semana (de sexta a quinta-feira)

**Projeto pai:** Narrativas, plataforma digital para registro, organização e difusão das narrativas populares do Rio Grande do Norte (resumo em [`docs/projeto_narrativas.md`](projeto_narrativas.md)).

**Trabalho escrito:** TCC no modelo do IFRN, seguindo as normas de [`docs/orientacoes_escrita_tcc.md`](orientacoes_escrita_tcc.md).

> **Leia este documento inteiro antes de começar a Sprint 1.** Ele é a referência completa do seu trabalho: tudo o que você vai programar, pesquisar e escrever está aqui, sprint por sprint. As *issues* do GitHub são o resumo de cada semana e sempre apontam para a seção correspondente deste documento. Se uma *issue* e este documento parecerem dizer coisas diferentes, **vale este documento**.

---

## Sumário

- [1. Como usar este documento e o quadro de tarefas](#como-usar)
- [2. A ideia do trabalho](#ideia)
- [3. Decisões já tomadas](#decisoes)
- [4. Cronograma](#cronograma)
- [5. Como trabalhar no repositório (fluxo do NIC)](#fluxo-git)
- [6. A estrutura de pastas que você vai construir](#estrutura)
- [7. Combinados que valem para todas as sprints](#combinados)
- [8. Como escrever o TCC](#escrita-geral)
- [Sprint 1 - Ambiente, repositório e corpus](#sprint-1-dev)
- [Sprint 2 - As três bases de teste](#sprint-2-dev)
- [Sprint 3 - Estratégias E1 e E2 e o programa de medição](#sprint-3-dev)
- [Sprint 4 - Estratégia E3 (FTS5) e os planos de execução](#sprint-4-dev)
- [Sprint 5 - Medição oficial, consolidação e matriz de acentos](#sprint-5-dev)
- [Sprint 6 - Qualidade dos resultados](#sprint-6-dev)
- [Sprint 7 - Caracterização, gráficos e protótipo](#sprint-7-dev)
- [Sprint 8 - Recomendação e fechamento](#sprint-8-dev)
- [9. Quadro-resumo](#quadro-resumo)
- [10. Riscos e planos B](#riscos)
- [11. Se sobrar tempo](#extras)
- [12. Referências mínimas do TCC](#referencias-minimas)

---

<a id="como-usar"></a>
## 1. Como usar este documento e o quadro de tarefas

### As *issues* e o quadro (kanban)

Eu cadastrei as suas tarefas como *issues* no repositório. Toda semana tem:

- **uma *issue* com a etiqueta `Desenvolvimento`**: o que você vai programar;
- **uma *issue* com a etiqueta `Escrita`**: o que você vai pesquisar e escrever no TCC. Em seis semanas ela é a entrega de uma parte do texto. Em duas semanas (Sprints 1 e 6) não há entrega de capítulo, e a *issue* é uma tarefa menor: na Sprint 1, preparar o documento e ler; na Sprint 6, colocar no documento as tabelas com os números que você já mediu. Essas tarefas pequenas existem para o texto não ficar parado, porque **quem deixa os Resultados para o fim não entrega**.

As *issues* de uma semana estão agrupadas em um **marco** (*milestone*) com o nome e a data da sprint, por exemplo `Sprint 04 - Estratégia E3 com FTS5 (06/11 a 12/11)`. A página **Milestones** do repositório mostra quanto de cada sprint já foi concluído.

O **quadro do projeto** (aba *Projects* do repositório) tem quatro colunas:

| Coluna | Quando o card fica aqui |
|---|---|
| **A fazer** | a tarefa ainda não começou |
| **Em andamento** | você está trabalhando nela. **Mova o card assim que começar** |
| **Em revisão** | você terminou e avisou os orientadores |
| **Concluído** | os orientadores aprovaram e fecharam a *issue* |

### Como cada sprint está organizada neste documento

Cada sprint tem duas partes, **Desenvolvimento** e **Escrita**, e cada uma tem um endereço próprio (`#sprint-4-dev`, `#sprint-4-escrita`), que é para onde as *issues* apontam.

A parte de desenvolvimento tem sempre quatro blocos:

- **O que você vai entregar**: em uma frase, o que precisa estar funcionando no fim da semana;
- **Passo a passo**: a lista numerada do que fazer, na ordem. Siga na ordem, sem pular;
- **Como saber que deu certo**: o que você deve ver na tela ou no arquivo. Se não vir isso, ainda não terminou;
- **Entrega da sprint**: a lista de conferência que também está na *issue*.

**Neste documento eu não te dou os programas prontos.** Eu te digo o que cada programa precisa fazer, em que ordem, quais funções usar e onde pesquisar. Quem escreve o código é você, e é isso que faz o trabalho ser seu. Os trechos de código que aparecem aqui são **peças** (um comando SQL, uma chamada de função, um esqueleto com comentários), não a solução montada.

### Como entregar

**Desenvolvimento:**

1. abra um *pull request* (PR) da sua *branch* para a `develop`, seguindo a [seção 5](#fluxo-git), com `Closes #N` na descrição (o número N de cada sprint está indicado na própria sprint);
2. comente na *issue*: `@brunogomesifrn @franciscoentony entrega da Sprint N pronta para revisão - PR #X`;
3. mova o card para **Em revisão**.

Quando um de nós aprovar e fizer o *merge* do PR, a *issue* fecha sozinha e o card vai para **Concluído**. Se pedirmos ajustes, faça os ajustes na mesma *branch* (o PR se atualiza sozinho) e comente de novo.

**Escrita:**

1. escreva no documento do Google Drive (veja a [seção 8](#escrita-geral));
2. nomeie a versão no histórico do Drive (*Arquivo → Histórico de versões → Nomear versão atual*), por exemplo `Entrega 1 - Introdução - 29/10`;
3. comente na *issue*: `@brunogomesifrn @franciscoentony Introdução pronta para revisão - versão "Entrega 1 - Introdução - 29/10"`;
4. mova o card para **Em revisão**.

Nós comentamos no próprio documento do Drive. Quando a seção estiver aprovada, fechamos a *issue*.

### Regras de ouro

- **Entregue no prazo, mesmo incompleto.** Trabalho pela metade dá para revisar; trabalho que não chega, não. Na *issue*, diga o que ficou faltando.
- **Terminou antes? Não comece a próxima sprint.** Use o tempo para entender melhor o que fez e para adiantar a escrita.
- **Travou mais de 40 minutos no mesmo erro? Pare e peça ajuda.** Comente na *issue* da semana, marcando nós dois, com: o que você estava tentando fazer, o comando que rodou e **a mensagem de erro inteira, copiada e colada** (não um resumo, nem um print cortado). Pedir ajuda depois de 40 minutos não é desistir, é administrar o tempo.

---

<a id="ideia"></a>
## 2. A ideia do trabalho

Abra o print `docs/prototipos/narrativas.png`. É a tela de listagem do portal Narrativas, e no alto do filtro, à esquerda, há um campo **"Palavra-chave"** com o botão de buscar. A tela mostra "1.248 narrativas encontradas": o portal foi pensado para ter um acervo grande.

Só que **ninguém ainda decidiu como essa busca vai ser feita**. Quando alguém começa a programar, a saída natural é escrever algo como `WHERE texto LIKE '%boitatá%'` (no Django, que é o que a plataforma usa, isso se escreve `icontains`). Funciona bem com 20 narrativas de teste. O problema aparece depois, quando o acervo cresce: a busca fica lenta, não encontra a palavra digitada sem acento e traz resultados que não têm nada a ver.

A pergunta que o seu trabalho responde é:

> **Qual estratégia de busca textual atende melhor a um acervo de narrativas populares em português, considerando o tempo de resposta, o custo e a qualidade dos resultados?**

Para responder, você vai comparar **três estratégias**, sobre a **mesma base**, com as **mesmas buscas**, no **mesmo computador**, todas no banco **SQLite**, que já vem dentro do Python:

| Código | Estratégia | Como funciona |
|---|---|---|
| **E1** | `LIKE` sem índice | `SELECT ... WHERE texto LIKE '%termo%'`. É exatamente o que o `icontains` do Django gera |
| **E2** | `LIKE` com índice | a mesma consulta, depois de criar um índice nas colunas de texto |
| **E3** | **FTS5** | a busca em texto completo do SQLite, com índice invertido e ordenação por relevância |

**Use sempre esses códigos** (E1, E2, E3) no código, nas planilhas, nos gráficos e no texto do TCC.

E você vai medir quatro coisas:

| O que é medido | Como |
|---|---|
| **Tempo de resposta** | 8 buscas, em bases de 100, 1.000 e 10.000 narrativas, com 3 execuções de aquecimento descartadas e 10 medições válidas cada |
| **Custo** | o tamanho do banco em disco e o tempo para preparar cada estratégia (criar o índice) |
| **Acentos, maiúsculas e plurais** | uma matriz que mostra quantas narrativas cada estratégia encontra quando a pessoa digita "irmao", "IRMÃO" ou "irmãos" em vez de "irmão" |
| **Qualidade** | dos 10 primeiros resultados de cada busca, quantos realmente servem (a métrica se chama **P@10**) |

### Um aviso que já adianta um resultado

A E2 provavelmente **não vai melhorar nada** em relação à E1. Um índice comum organiza os textos pelo começo, como um dicionário organiza as palavras pela primeira letra. Uma busca `LIKE '%termo%'` começa com `%` (qualquer coisa), então o banco não tem por onde "entrar" no índice e lê a tabela inteira do mesmo jeito.

**Isso não é um erro seu.** É um dos achados mais interessantes do trabalho, e é justamente o que explica por que existem as tecnologias de busca em texto completo. Não tente "consertar": **meça, prove com o plano de execução da consulta (Sprint 4) e explique no TCC.**

### O que este trabalho **não** é

**Não é "fazer a busca do site Narrativas".** A plataforma é o **contexto** que justifica a pergunta; o objeto do seu trabalho é o **experimento comparativo**. O seu trabalho também **não** altera o código da plataforma: ele acontece todo no seu repositório.

Guarde esta frase, porque ela vale para o código e para o texto:

> O seu trabalho **não é** "fiz uma busca que funciona". O seu trabalho é **"descobri qual estratégia de busca textual é a mais adequada para o acervo do projeto Narrativas, e provei com medições"**.

### O que o seu trabalho tem a favor

1. **Ele produz números.** Tempo, tamanho em disco, quantidade de resultados, P@10: tudo medido, com tabelas e gráficos.
2. **Ele responde a uma pergunta real e em aberto.** A equipe do Narrativas ainda não escolheu como fazer a busca, e a sua recomendação vai orientar a implementação.
3. **Ele tem um resultado contraintuitivo e fácil de explicar:** o índice comum, que "deveria" acelerar a busca, não acelera. A banca gosta muito de achados assim, desde que bem explicados.

---

<a id="decisoes"></a>
## 3. Decisões já tomadas

Para você não perder tempo escolhendo ferramenta:

| Item | Decisão |
|---|---|
| Linguagem | **Python 3** |
| Onde você trabalha | **computadores do laboratório (Windows)**. Não é possível instalar programas, mas o `pip install` e o Git funcionam |
| Editor | **VS Code** |
| Banco de dados | **SQLite**, pelo módulo `sqlite3`, que já vem com o Python. Não precisa instalar nem configurar servidor, usuário ou senha |
| Estratégias | **E1** (`LIKE`), **E2** (`LIKE` com índice) e **E3** (FTS5), todas no SQLite |
| Gráficos | `matplotlib`, instalada com `pip` (é a única biblioteca que você instala) |
| Planilhas | módulo `csv`, que já vem com o Python |
| Estatística | módulo `statistics`, que já vem com o Python |
| Testes | dois programas de verificação simples, com o comando `assert` ([seção 5.5](#fluxo-git)) |
| Corpus | 30 contos de ***Contos populares do Brazil***, de **Sílvio Romero** (domínio público) |
| Bases de teste | 100, 1.000 e 10.000 narrativas, geradas por recombinação dos parágrafos dos 30 contos |
| Repositório | `nicifrn/mp_narrativas_buscador`, só seu, seguindo a política de desenvolvimento do NIC ([seção 5](#fluxo-git)) |
| Texto do TCC | **modelo de TCC do IFRN**, em um documento do Google Drive que eu compartilho com você |
| O que **não** entra | MySQL, Django, API, front-end, Docker, motores de busca dedicados (Elasticsearch, Meilisearch), inteligência artificial e busca semântica. Tudo isso vira "trabalho futuro" no TCC |

### Por que só o SQLite?

O portal Narrativas usa MySQL em produção, e o MySQL também tem a sua busca em texto completo (o índice FULLTEXT). Eu decidi deixar o MySQL de fora por três motivos, que você vai escrever na Metodologia:

1. **tempo:** o trabalho tem oito semanas, e configurar e medir um segundo banco dobraria a parte de medição;
2. **comparação justa:** com um banco só, a única coisa que muda entre E1, E2 e E3 é a estratégia. Comparar SQLite com MySQL misturaria duas perguntas (qual estratégia e qual banco);
3. **os conceitos são os mesmos:** a varredura completa da tabela no `LIKE`, a inutilidade do índice comum para `'%termo%'` e o índice invertido da busca em texto completo funcionam da mesma forma nos dois bancos. O que você descobrir no SQLite explica o que vai acontecer no MySQL.

A medição no MySQL fica registrada como **trabalho futuro**.

### Por que SQL puro, sem Django?

O `icontains` do Django gera exatamente a consulta `LIKE` da E1. Montar um projeto Django inteiro só para fazer a mesma consulta custaria semanas e **não mudaria nenhum resultado**. Essa é uma decisão de método, e também vai para a Metodologia, com essa justificativa.

### Uso de inteligência artificial

- **Pode:** usar uma ferramenta de IA para entender uma mensagem de erro ou um conceito, como faria com um colega.
- **Não pode:** pedir para a IA escrever os seus programas ou o texto do TCC. O código e o texto têm de ser seus, e você precisa saber explicar cada linha na apresentação.
- **Nunca:** colocar no TCC uma referência que você não abriu e leu. Ferramentas de IA inventam referências com naturalidade.

---

<a id="cronograma"></a>
## 4. Cronograma

Cada sprint vai de **sexta a quinta-feira**. O prazo de tudo é a **quinta-feira** que fecha a sprint.

| Sprint | Período | Desenvolvimento | Escrita |
|---|---|---|---|
| 1 | 16/10 a 22/10 | Ambiente, repositório e corpus | Preparar o documento e ler para a Introdução |
| 2 | 23/10 a 29/10 | As três bases de teste | **Entrega 1:** Introdução e Objetivo geral |
| 3 | 30/10 a 05/11 | E1 e E2 e o programa de medição | **Entrega 2:** Referencial 2.1 e 2.2 |
| 4 | 06/11 a 12/11 | E3 (FTS5) e os planos de execução | **Entrega 3:** Referencial 2.3, 2.4 e 2.5 |
| 5 | 13/11 a 19/11 | Medição oficial, consolidação e matriz de acentos | **Entrega 4:** Metodologia |
| 6 | 20/11 a 26/11 | Qualidade dos resultados (P@10) | Tarefa curta: colocar no documento as tabelas da Sprint 5 |
| 7 | 27/11 a 03/12 | Caracterização da base, gráficos e protótipo | **Entrega 5:** Resultados e discussão |
| 8 | 04/12 a 10/12 | Recomendação, README e fechamento | **Entrega 6:** Recomendação, Conclusão, Objetivos específicos, Resumo e Título |

**Tudo termina em 10/12.**

**Feriados:** 02/11 (segunda, Sprint 3) e 20/11 (sexta, primeiro dia da Sprint 6). Nenhum prazo cai em feriado, mas nessas duas semanas o laboratório fica fechado um dia: **a semana tem um dia útil a menos**, então comece cedo.

**Três avisos sobre o cronograma:**

1. **A Sprint 1 junta duas coisas demoradas:** preparar o ambiente e montar o corpus de 30 contos. Faça o ambiente na sexta e reserve terça e quarta só para o corpus.
2. **Os Resultados vencem em 03/12, na mesma semana dos gráficos.** Por isso a Sprint 6 já manda colocar as tabelas no documento, e a Sprint 7 manda terminar os gráficos **até segunda-feira, 30/11**: a terça, a quarta e a quinta ficam para escrever.
3. **A última semana é cheia.** A Conclusão precisa estar escrita até **segunda-feira, 07/12**, para sobrar a terça, a quarta e a quinta para o Resumo, o *Abstract*, o Título e a revisão final.

---

<a id="fluxo-git"></a>
## 5. Como trabalhar no repositório (fluxo do NIC)

O NIC tem uma política de desenvolvimento que vale para todos os projetos. Abaixo está o que ela significa no seu trabalho.

### 5.1 As *branches*

| *Branch* | Para que serve | Quem mexe |
|---|---|---|
| `main` | versão estável e aprovada | só os orientadores, no fim do trabalho |
| `develop` | onde as sprints aprovadas vão se juntando. É a *branch* padrão do repositório | ninguém envia direto: só entra por PR aprovado |
| `feature/...` | uma por sprint, onde você trabalha | você |

Os nomes das *branches* das sprints já estão definidos em cada sprint (por exemplo, `feature/fts5`). Se precisar corrigir algo de uma sprint que já foi aprovada, use `fix/` (por exemplo, `fix/acentos-gerador`).

### 5.2 O ciclo de cada sprint

**No começo da sprint** (sexta-feira), crie a *branch* da semana a partir da `develop` atualizada:

```
git checkout develop
git pull
git checkout -b feature/nome-da-sprint
```

**Durante a semana**, envie o trabalho **ao fim de cada dia**. Código que só existe na máquina do laboratório não foi entregue, e a máquina pode ser formatada.

```
git status
git add .
git commit -m "feat: adiciona gerador das bases de teste"
git push
```

Na primeira vez que der `git push` em uma *branch* nova, o Git pede `git push -u origin feature/nome-da-sprint`. Use exatamente o comando que ele mostrar.

**Antes do `git add .`, olhe sempre o `git status`.** Se aparecer `.venv/`, `bancos/` ou `__pycache__/`, o seu `.gitignore` está errado: corrija antes de continuar. Os bancos `.db` podem passar de 100 MB e **nunca** vão para o Git.

**No fim da sprint**, abra o PR (seção 5.4).

### 5.3 Mensagens de *commit*

Os *commits* devem ser **pequenos, objetivos e frequentes**: pelo menos 2 por semana. Use o padrão abaixo, com a mensagem em português e o verbo no presente:

```
feat: adiciona estratégia E3 com FTS5
fix: corrige leitura dos parágrafos com linhas em branco
docs: registra configuração da máquina
test: adiciona verificação das bases
refactor: separa as funções de busca em um módulo
```

| Prefixo | Quando usar |
|---|---|
| `feat:` | algo novo funcionando (um script, uma estratégia, o corpus) |
| `fix:` | correção de algo que estava errado |
| `docs:` | documentação, diário, `README.md`, prints, planilhas de resultado |
| `test:` | testes |
| `refactor:` | reorganizar código sem mudar o que ele faz |

**Mensagens proibidas pela política do NIC:** `ajustes`, `mudanças`, `update`, `correções`. Se você não consegue dizer em uma frase o que o *commit* faz, ele está grande demais.

### 5.4 O *pull request* do fim da sprint

1. Confira se tudo foi enviado (`git status` deve dizer `nothing to commit`).
2. Rode as verificações (a partir da Sprint 2; veja a seção 5.5). Elas precisam terminar com a mensagem `Tudo certo`.
3. No GitHub, abra o repositório. Vai aparecer uma faixa amarela com o botão **Compare & pull request**. Se não aparecer: aba **Pull requests → New pull request**, com **base: `develop`** e **compare: a sua *branch***.
4. Preencha a descrição. O repositório já traz um modelo com os campos que a política do NIC exige:
   - **Objetivo:** o que esta sprint entrega, em uma ou duas frases;
   - **O que foi feito:** a lista do que foi implementado;
   - **Possíveis impactos:** o que muda para quem roda o projeto (um script novo, uma pasta nova, uma ordem de execução diferente);
   - **Evidências de teste:** a saída das verificações (copiada do terminal) e os prints;
   - **Issue:** `Closes #N`, com o número indicado na sprint.
5. Em **Reviewers**, marque `brunogomesifrn` e `franciscoentony`.
6. Comente na *issue* e mova o card para **Em revisão** (veja a [seção 1](#como-usar)).

**Você não faz o *merge* do seu próprio PR.** A política do NIC exige que pelo menos um revisor aprove antes da integração. **Um PR por sprint**: não acumule duas sprints no mesmo PR.

### 5.5 Testes

A política do NIC pede que toda funcionalidade tenha testes compatíveis com a sua complexidade. No seu trabalho, isso significa **dois programas curtos de verificação**, na pasta `testes/`, que conferem sozinhos se as coisas estão certas:

- **`testes/verificar_bases.py` (Sprint 2):** confere se as três bases têm o número certo de narrativas, sem textos repetidos, com o tamanho combinado e com os acentos certos;
- **`testes/verificar_buscas.py` (Sprint 4):** confere se as três estratégias se comportam como esperado (por exemplo, se a E1 e a E2 encontram exatamente as mesmas narrativas).

Os dois usam só um comando do Python, o **`assert`**, que funciona assim:

```python
assert total == 100, "esperava 100 narrativas"
```

Se a condição for **verdadeira**, nada acontece e o programa segue. Se for **falsa**, o programa para na hora e mostra `AssertionError: esperava 100 narrativas`. Ou seja: se o programa chegar até a última linha e mostrar `Tudo certo`, todas as conferências passaram.

Rode sempre **a partir da raiz do repositório**, com o `.venv` ativo:

```
python testes\verificar_bases.py
python testes\verificar_buscas.py
```

### 5.6 Segurança

Nunca envie para o repositório senhas, *tokens*, chaves ou arquivos `.env`. Neste trabalho você não precisa de nenhum deles: o SQLite não tem usuário nem senha.

---

<a id="estrutura"></a>
## 6. A estrutura de pastas que você vai construir

Você não precisa criar tudo de uma vez: cada sprint cria a sua parte. Esta é a figura final, para você saber aonde está indo. Tudo fica **na raiz do repositório** `mp_narrativas_buscador/`:

```
mp_narrativas_buscador/
├── .github/
│   └── pull_request_template.md   ← já existe (modelo do PR)
├── corpus/                        ← Sprint 1
│   ├── narrativa_001.txt ... narrativa_030.txt
│   └── origem.csv
├── scripts/
│   ├── 00_verificar_ambiente.py   ← Sprint 1
│   ├── 01_gerar_base.py           ← Sprint 2
│   ├── contar_termo.py            ← Sprint 3
│   ├── buscas.py                  ← Sprints 3 e 4 (as funções das estratégias)
│   ├── 02_preparar_estrategias.py ← Sprints 3 e 4
│   ├── 03_medir.py                ← Sprints 3 e 4
│   ├── 04_planos.py               ← Sprint 4
│   ├── 05_consolidar.py           ← Sprint 5
│   ├── 06_matriz_acentos.py       ← Sprint 5
│   ├── 07_julgar.py               ← Sprint 6
│   ├── 08_qualidade.py            ← Sprint 6
│   ├── 09_caracterizar.py         ← Sprint 7
│   ├── 10_graficos.py             ← Sprint 7
│   └── 11_prototipo.py            ← Sprint 7
├── testes/
│   ├── verificar_bases.py         ← Sprint 2
│   └── verificar_buscas.py        ← Sprint 4
├── bancos/                        ← os arquivos .db gerados (NÃO vão para o Git)
├── resultados/                    ← planilhas com as medições (vão para o Git)
│   └── planos/                    ← as saídas do EXPLAIN QUERY PLAN
├── graficos/                      ← Sprint 7
├── docs/
│   ├── 01_italo_narrativas_geral.md  ← este documento (já existe)
│   ├── projeto_narrativas.md         ← já existe
│   ├── orientacoes_escrita_tcc.md    ← já existe
│   ├── prototipos/                   ← já existe (prints da plataforma)
│   ├── leituras.md            ← fichamento das leituras (Sprint 1 em diante)
│   ├── diario.md              ← Sprint 1 em diante
│   ├── ambiente.md            ← Sprint 1
│   ├── protocolo.md           ← Sprint 3
│   ├── consultas.csv          ← Sprint 3
│   ├── recomendacao.md        ← Sprint 8
│   └── evidencias/            ← prints de tela
├── .gitignore
├── requirements.txt
└── README.md
```

**Os scripts são numerados na ordem em que devem ser rodados.** O `buscas.py` e o `contar_termo.py` não têm número porque o primeiro não é rodado sozinho (os outros o importam) e o segundo é só uma ferramenta de consulta.

---

<a id="combinados"></a>
## 7. Combinados que valem para todas as sprints

- **Rode tudo a partir da raiz do repositório:** `python scripts\01_gerar_base.py`, e não de dentro da pasta `scripts`. Todos os caminhos dos programas (`corpus/`, `bancos/`, `resultados/`) partem da raiz.
- **Diário (`docs/diario.md`):** no fim de cada sprint, escreva 3 linhas: o que funcionou, o que deu errado e o que aprendi. Leva cinco minutos e vai escrever a sua Conclusão por você no fim do trabalho. Use este formato:

  ```
  ## Sprint 4 - 06/11 a 12/11
  - Funcionou: ...
  - Deu errado: ...
  - Aprendi: ...
  ```

- **Nunca apague uma medição.** A partir da Sprint 3, toda medição vai para `resultados/`. Se uma rodada saiu estranha, ela fica na planilha e você anota o motivo no diário. Rodada estranha vira observação no TCC, não lixo.
- **Anote todo erro e toda surpresa.** Neste trabalho, **surpresa é resultado**. Se o índice não acelerou, se a busca sem acento não achou nada, isso vai para uma tabela do TCC.
- **Prints (`docs/evidencias/`):** sempre que algo funcionar (ou falhar de um jeito interessante), tire um print (`Win + Shift + S`). Dê nomes que digam o que é: `s04_plano_e2_prefixo.png`. Eles viram figuras do TCC.
- **Acompanhamento semanal:** no começo de cada sprint, você mostra aos orientadores o que fez na anterior, **rodando na tela**. A partir da Sprint 3, "está funcionando" não basta: tem que ter número.

---

<a id="escrita-geral"></a>
## 8. Como escrever o TCC

### 8.1 Onde escrever: o documento compartilhado no Google Drive

Na Sprint 1 eu compartilho com você um documento do Google Drive que **já está no modelo de TCC do IFRN** (capa, folha de rosto, resumo, sumário e as seções). Você não cria arquivo novo nem trabalha em cópia local.

- **Escreva sempre no documento compartilhado.** Nada de escrever no Word e colar depois: o histórico do Drive é o que nos permite ver o que mudou de uma semana para outra.
- **Não crie cópias** ("TCC v2", "TCC final", "TCC final revisado"). O Drive já guarda tudo em **Arquivo → Histórico de versões**.
- **Marque cada entrega no histórico:** *Arquivo → Histórico de versões → Nomear versão atual*, com um rótulo como `Entrega 1 - Introdução - 29/10`.
- **Avise na *issue* quando entregar**, como explicado na [seção 1](#como-usar). Nós não ficamos olhando o documento: precisamos saber que há algo novo para ler.
- **Comentário se responde, não se apaga.** Responda a cada comentário dizendo o que você fez e só então marque como resolvido.
- **Resolva todos os comentários da entrega anterior antes de avisar sobre a próxima.**
- **Figuras e tabelas** vão dentro do documento, no lugar certo, com a identificação em cima e a fonte embaixo.
- **Não dê acesso ao documento a outras pessoas.**

### 8.2 As normas

Todas as regras de escrita e de ABNT estão em [`docs/orientacoes_escrita_tcc.md`](orientacoes_escrita_tcc.md): estrutura, citações, referências, figuras, tabelas, formatação e linguagem. **Leia esse arquivo inteiro na Sprint 1.** Este plano não repete as regras da ABNT; ele diz **o que pesquisar e o que escrever** em cada seção do seu trabalho.

> **Importante:** o que está neste plano são **orientações**, não o texto pronto. Não copie estas frases para o TCC. Elas dizem sobre o que é cada parágrafo; o texto tem de ser escrito por você, com as suas palavras e com as referências que você leu.

### 8.3 A estrutura do seu TCC

```
1 INTRODUÇÃO
1.1 Objetivo geral
1.2 Objetivos específicos
2 REFERENCIAL TEÓRICO
2.1 Narrativas populares e acervos digitais
2.2 Banco de dados, SQL e índices
2.3 Busca em texto completo
2.4 Avaliação de sistemas de busca
2.5 Trabalhos relacionados
3 METODOLOGIA
3.1 Classificação da pesquisa
3.2 Etapas do trabalho
3.3 Materiais e ambiente de execução
3.4 Corpus e bases de teste
3.5 Estratégias comparadas e protocolo de medição
3.6 Avaliação da qualidade dos resultados
4 RESULTADOS E DISCUSSÃO
4.1 A base de teste
4.2 Tempo de resposta
4.3 Por que o índice não ajudou
4.4 Custo em disco e de preparação
4.5 Acentos, maiúsculas e plurais
4.6 Qualidade dos resultados
4.7 O protótipo
4.8 Recomendação para o projeto Narrativas
4.9 Limitações do trabalho
5 CONCLUSÃO
REFERÊNCIAS
APÊNDICE A - Consultas de teste
```

Tamanho de referência da parte textual: **de 20 a 30 páginas**, mais ou menos assim: Introdução, 2 a 3; Referencial, 6 a 8; Metodologia, 5 a 6; Resultados, 7 a 10; Conclusão, 2.

### 8.4 As três perguntas de pesquisa

O trabalho inteiro gira em torno de três perguntas menores, que saem da pergunta principal da [seção 2](#ideia). Elas aparecem na Introdução, organizam os Resultados e são respondidas na Conclusão:

1. como o **tempo de resposta** de cada estratégia se comporta quando o acervo cresce de 100 para 1.000 e para 10.000 narrativas, e quanto cada estratégia **custa** em disco?
2. como cada estratégia se comporta diante de **acentos, maiúsculas e plurais**?
3. dos **10 primeiros resultados** de cada busca, quantos realmente servem?

### 8.5 Regras que valem para o texto inteiro

- **Toda afirmação técnica precisa de referência.**
- **Não empilhe citações.** Explique com as suas palavras, relacione os autores e amarre ao seu trabalho.
- **Documentação oficial** (SQLite, Python, Django) serve para descrever a ferramenta, não para fundamentar conceito. Para conceito, use livro ou artigo.
- **Nada de blog, Stack Overflow ou site sem autoria** nas Referências. Você vai usar muito esse material para resolver problemas de programação (isso é normal), mas ele não entra na lista.
- **Nunca cite uma referência que você não leu.**
- **Crie a seção "Referências" no primeiro dia** e acrescente cada obra assim que ler.
- O Zotero e o Mendeley (gratuitos, funcionam no navegador) ajudam a montar as referências, mas confira cada entrada com a NBR 6023:2018: esses programas erram com frequência.
- **Meta:** de 12 a 18 referências (lista mínima na [seção 12](#referencias-minimas)).
- **Fichamento:** tudo o que você ler vai para `docs/leituras.md`, no formato abaixo. É ele que transforma leitura em texto:

  ```
  ## BINDA; DA SILVA (2026)
  - Referência completa (ABNT): ...
  - Onde achei: (endereço)
  - Ideia principal, com as minhas palavras: ...
  - Trecho que posso citar (com página): "..." (p. X)
  - Vou usar na seção: 2.1
  ```

---

# Sprint 1: 16/10 a 22/10/2026

<a id="sprint-1-dev"></a>
## Sprint 1 · Desenvolvimento: ambiente, repositório e corpus

**Branch:** `feature/ambiente-corpus` · **No PR:** `Closes #1`

**O que você vai entregar:** o Git configurado, o repositório clonado, o ambiente virtual criado, a estrutura de pastas, a verificação do FTS5, a descrição da máquina, o `README.md` inicial e o **corpus**: 30 contos de domínio público em arquivos de texto, com a planilha de origem.

**Divida a semana assim:**

| Dia | O que fazer |
|---|---|
| sexta, 16/10 | passos 1 a 6 (Git, ambiente, pastas, verificação do ambiente) |
| segunda, 19/10 | passos 7 e 8 (`ambiente.md` e `README.md`) e passo 9 (encontrar o livro) |
| terça e quarta, 20 e 21/10 | passos 10 e 11 (os 30 contos e a planilha de origem). É a parte que mais demora |
| quinta, 22/10 | passo 12 (diário, *commits* e PR) |

### Passo a passo

**1. Se você nunca usou Git e GitHub,** assista antes às aulas iniciais do Curso de Git e GitHub do Curso em Vídeo (https://www.cursoemvideo.com/curso/curso-de-git-e-github/), até a parte em que o repositório é enviado para o GitHub. Depois leia a [seção 5](#fluxo-git) deste documento inteira.

**2. Configure o Git** na máquina do laboratório (uma vez só por máquina), com o mesmo e-mail da sua conta do GitHub. Abra o Prompt de Comando (tecle `Win`, digite `cmd`, Enter):

```
git config --global user.name "Seu Nome Completo"
git config --global user.email "seu-email-do-github@exemplo.com"
```

**3. Aceite o convite do repositório.** Você recebeu por e-mail um convite para o `nicifrn/mp_narrativas_buscador`. Aceite-o (ou abra https://github.com/nicifrn/mp_narrativas_buscador/invitations). Aceite também o convite do quadro do projeto, que chega no mesmo e-mail.

**4. Clone o repositório e crie a *branch* da sprint:**

```
cd %USERPROFILE%
git clone https://github.com/nicifrn/mp_narrativas_buscador.git
cd mp_narrativas_buscador
git checkout develop
git checkout -b feature/ambiente-corpus
```

Na primeira vez que o Git falar com o GitHub, abre uma janela do navegador pedindo login. Entre com a sua conta e autorize. Depois abra a pasta `mp_narrativas_buscador` no VS Code (*File → Open Folder*). A partir de agora, **é sempre essa pasta que você abre**.

**5. Crie o ambiente virtual e instale o `matplotlib`.** O ambiente virtual é uma "caixa" só deste projeto, onde as bibliotecas ficam instaladas sem bagunçar o Python da máquina. Na raiz do repositório, **no Prompt de Comando** (e não no PowerShell):

```
python -m venv .venv
.venv\Scripts\activate
pip install matplotlib
pip freeze > requirements.txt
```

Depois de ativar, o começo da linha passa a mostrar `(.venv)`. **Se não mostrar, o ambiente não está ativo**, e o que você instalar vai para o lugar errado. Toda vez que abrir um terminal novo, ative de novo.

> No terminal do VS Code (`` Ctrl + ` ``), abra o seletor de terminal (setinha ao lado do `+`) e escolha **Command Prompt**. No PowerShell, o `activate` costuma dar erro de "execução de scripts desabilitada".
>
> Se o comando `python` não for reconhecido, tente `py`. Se o `py` funcionar, use `py` no lugar de `python` em todos os comandos deste documento, e anote isso no diário.

**6. Crie as pastas, o `.gitignore` e a verificação do ambiente.**

1. Crie as pastas `corpus`, `scripts`, `testes`, `bancos`, `resultados\planos`, `graficos` e `docs\evidencias` (veja a [seção 6](#estrutura)). *Pesquise:* o comando `mkdir` no Windows. O Git não guarda pastas vazias; por isso, coloque dentro de cada pasta vazia um arquivo `.gitkeep` vazio (menos na `bancos`, que não vai para o Git).
2. Crie o arquivo `.gitignore` na raiz, com este conteúdo:

   ```
   .venv/
   __pycache__/
   *.pyc
   bancos/
   *.db
   ```

3. Escreva `scripts/00_verificar_ambiente.py`. Ele confere se o SQLite do seu Python tem o **FTS5**, que é a estratégia E3. Quase sempre tem, mas descobrir que não tem na Sprint 4 seria péssimo. O programa precisa, nesta ordem:
   1. importar os módulos `sys` e `sqlite3`;
   2. mostrar a versão do Python (`sys.version`) e a versão do SQLite (`sqlite3.sqlite_version`);
   3. abrir um banco temporário, só na memória: `sqlite3.connect(":memory:")`;
   4. tentar criar uma tabela de busca com o comando abaixo, dentro de um `try`. Se der certo, mostrar `FTS5: DISPONIVEL`; se der `sqlite3.OperationalError`, mostrar `FTS5: NAO DISPONIVEL` e a mensagem do erro.

   ```sql
   CREATE VIRTUAL TABLE teste USING fts5(conteudo, tokenize = "unicode61 remove_diacritics 2")
   ```

   *Pesquise:* `try` e `except` com o nome da exceção, e o método `execute` da conexão. Rode com `python scripts\00_verificar_ambiente.py`.

   > **Se aparecer `NAO DISPONIVEL`**, siga o plano B da [seção 10](#riscos) ainda nesta semana: instale `pip install sqlean.py` e troque, neste e em todos os programas do trabalho, a linha `import sqlite3` por `import sqlean as sqlite3`. Rode a verificação de novo e anote no diário e no `docs/ambiente.md`.

**7. Preencha `docs/ambiente.md`** com a configuração da máquina onde as medições oficiais serão feitas (a do laboratório que você usa sempre; anote também o número ou a identificação dela):

- processador e memória RAM: tecle `Win`, digite "Sobre o seu PC" e anote "Processador" e "RAM instalada";
- sistema operacional e versão: na mesma tela, "Edição" e "Versão";
- tipo de disco (SSD ou HD): abra o Gerenciador de Tarefas (`Ctrl + Shift + Esc`) → aba **Desempenho** → clique em **Disco 0**; o tipo aparece embaixo, à direita;
- versão do Python e do SQLite (a saída do `00_verificar_ambiente.py`);
- versão do `matplotlib` (`pip list`).

Isso vai para a Metodologia do TCC. Sem isso, os tempos medidos não significam nada: é a primeira coisa que um avaliador procura em trabalho de desempenho.

**8. Escreva o `README.md`** do repositório (se o GitHub já tiver criado um, substitua o conteúdo). Por enquanto, quatro partes, que a política do NIC exige:

1. **o que é este projeto**, em três linhas;
2. **responsáveis:** você (aluno) e os dois orientadores, com os usuários do GitHub;
3. **instalação:** como criar o ambiente virtual e instalar com `pip install -r requirements.txt`;
4. **como rodar:** por enquanto, só o `00_verificar_ambiente.py`. A cada sprint você acrescenta os programas novos.

**9. Encontre o livro.** O corpus vem de ***Contos populares do Brazil***, de **Sílvio Romero** (com a grafia da época, "Brazil"). Sílvio Romero morreu em 1914, e a obra está em **domínio público**: pela Lei nº 9.610/1998 (art. 41), a proteção dura 70 anos contados de 1º de janeiro do ano seguinte à morte do autor. A primeira edição é de 1885 (Lisboa, Nova Livraria Internacional), com introdução e notas de Teófilo Braga, que morreu em 1924 e também está em domínio público.

Procure pelo título exato, `Contos populares do Brazil`, nesta ordem:

1. **Wikisource em português** (`pt.wikisource.org`): se estiver lá, o texto já está digitado;
2. **Internet Archive** (`archive.org`): tem digitalizações de edições antigas, muitas com o texto para baixar (opção "FULL TEXT");
3. **Biblioteca Brasiliana Guita e José Mindlin**, da USP (`digital.bbm.usp.br`);
4. portal **Domínio Público**, do MEC (`dominiopublico.gov.br`).

Use **uma única edição** para todos os contos. **Anote no diário qual edição você usou** (cidade, editora, ano) e o endereço exato de onde baixou: isso vai para a Metodologia e para as Referências.

> **Cuidado:** as obras de **Luís da Câmara Cascudo** ainda **não** estão em domínio público (ele morreu em 1986). Não copie textos dele para o corpus. Citá-lo no Referencial Teórico, por outro lado, é recomendável.

**10. Escolha e salve 30 contos.**

Critérios de escolha:

- **prefira contos médios e longos** (mais de 1.500 caracteres): na Sprint 2 você vai recombinar os **parágrafos** dos contos, e quanto mais parágrafos, mais variadas ficam as bases;
- **escolha contos de várias partes do livro:** o livro separa os contos por origem (europeia, indígena, africana e mestiça). Pegue contos de mais de uma parte.

Salve cada conto em `corpus/narrativa_001.txt`, `narrativa_002.txt`, até `narrativa_030.txt`. O arquivo tem **só o texto do conto**, sem o título (o título vai para a planilha do passo 11), com **uma linha em branco entre os parágrafos**.

Antes de salvar, limpe o texto:

- tire números de página, notas de rodapé, cabeçalhos e o título do conto;
- **junte as quebras de linha no meio dos parágrafos.** Texto copiado de PDF ou do "FULL TEXT" do Internet Archive vem com uma quebra no fim de cada linha da página. Dentro de um parágrafo, não pode haver quebra de linha; entre dois parágrafos, tem de haver uma linha em branco. Dica: no VS Code, selecione as linhas de um parágrafo e use `Ctrl + J` para juntá-las;
- confira a acentuação: textos digitalizados por máquina trocam letras ("ã" vira "a", "ç" vira "c"). Corrija comparando com a imagem da página;
- **não modernize a grafia.** Transcreva como está na edição ("Brazil", "elle", "pharmacia"). Além de respeitar a obra, isso vai render um resultado curioso na Sprint 5: a busca por "princesa" não encontra "princeza".

**Salve em UTF-8.** No VS Code já é o padrão (confira no canto inferior direito: deve estar escrito `UTF-8`). Se errar isso, os acentos viram símbolos estranhos quando o Python for ler.

**11. Preencha `corpus/origem.csv`**, com uma linha por conto. Crie o arquivo no VS Code, com esta primeira linha (o cabeçalho) e uma linha para cada conto:

```
arquivo,titulo,obra,autor,ano,parte_do_livro,endereco,licenca,data_coleta
narrativa_001.txt,(título do conto),Contos populares do Brazil,Sílvio Romero,1885,Contos de origem europeia,https://...,dominio publico,2026-10-20
```

Se o título tiver vírgula, coloque o título entre aspas duplas (`"O rei, a rainha e o pastor"`), senão a planilha se desalinha. **Essa planilha sustenta a Metodologia do TCC:** sem ela, não há como provar que você usou material que podia usar.

**12. Faça os *commits*, um por assunto, e abra o PR.**

1. Crie `docs/diario.md` com as 3 linhas da semana ([seção 7](#combinados)).
2. Faça os *commits* separados, por exemplo:

   ```
   git status
   git add .gitignore requirements.txt
   git commit -m "feat: adiciona gitignore e dependências do projeto"
   git add scripts
   git commit -m "feat: adiciona verificação do ambiente e do FTS5"
   git add corpus
   git commit -m "feat: adiciona corpus de 30 contos de Sílvio Romero"
   git add docs README.md
   git commit -m "docs: adiciona ambiente, diário, leituras e README"
   git push -u origin feature/ambiente-corpus
   ```

   (Se você criou `.gitkeep` nas pastas vazias, inclua as pastas no `git add` de um desses *commits*.)
3. Abra o PR para a `develop`, seguindo a [seção 5.4](#fluxo-git), com `Closes #1`. Em **Evidências de teste**, cole a saída do `00_verificar_ambiente.py`.

### Como saber que deu certo

- O terminal mostra `(.venv)` no começo da linha, e o `pip list` mostra o `matplotlib`.
- `python scripts\00_verificar_ambiente.py` mostra as versões e `FTS5: DISPONIVEL`.
- O `git status` **não** mostra `.venv/` nem `bancos/`.
- A pasta `corpus/` tem 30 arquivos `.txt`, que abrem no VS Code com os acentos certos e com uma linha em branco entre os parágrafos.
- O `corpus/origem.csv` tem 31 linhas (o cabeçalho e uma por conto).

### Entrega da sprint

- [ ] Git configurado, repositório clonado e *branch* `feature/ambiente-corpus` criada.
- [ ] Ambiente virtual, `requirements.txt`, `.gitignore` e estrutura de pastas.
- [ ] `scripts/00_verificar_ambiente.py` mostrando `FTS5: DISPONIVEL`.
- [ ] `docs/ambiente.md` com processador, memória, disco, sistema e versões.
- [ ] `README.md` com as quatro primeiras partes.
- [ ] 30 contos em `corpus/`, limpos, em UTF-8, com parágrafos separados por linha em branco.
- [ ] `corpus/origem.csv` preenchido; edição do livro e endereço anotados no diário.
- [ ] `docs/diario.md` com a Sprint 1.
- [ ] PR aberto para a `develop`, com `Closes #1`.

### Erros comuns

- **Acentos quebrados (`Mossor├│`):** o arquivo não foi salvo em UTF-8. No VS Code, clique na codificação no canto inferior direito e escolha *Save with Encoding → UTF-8*.
- **`'python' não é reconhecido`:** use `py` (veja o passo 5).
- **O `activate` não funciona:** você está no PowerShell. Troque para o Command Prompt.

<a id="sprint-1-escrita"></a>
## Sprint 1 · Escrita: preparar o documento e ler para a Introdução

**O que você vai entregar:** o documento do TCC aberto e preparado, as normas lidas e as leituras da Introdução fichadas. Nesta semana não há entrega de capítulo.

### Passo a passo

**1. Abra o documento do TCC** que eu compartilhei com você no Google Drive (o convite chega no seu e-mail). Preencha a capa e a folha de rosto com o seu nome, o curso, o nome dos orientadores e o título provisório: *Avaliação de estratégias de busca textual em um acervo digital de narrativas populares*.

**2. Crie a seção "REFERÊNCIAS"** no fim do documento, ainda vazia. A partir de hoje, toda obra que você ler entra nela no mesmo dia.

**3. Leia as normas.** Leia [`docs/orientacoes_escrita_tcc.md`](orientacoes_escrita_tcc.md) inteiro, com atenção especial a: estrutura do trabalho, Introdução, objetivo geral, como citar e como referenciar.

**4. Leia o resumo do projeto pai** em [`docs/projeto_narrativas.md`](projeto_narrativas.md). Ele é o ponto de partida da sua Introdução e já traz referências que você vai reaproveitar.

**5. Pesquise e leia, fichando em `docs/leituras.md`** (no formato da [seção 8.5](#escrita-geral); este arquivo entra no PR de desenvolvimento da semana):

- **as referências do projeto:** Bezerra (2026), Binda e Da Silva (2026), Dos Santos Fernandes e Martins (2026), Pires (2025), Reis (2023) e Soave e Da Silva Lemos (2022). As referências completas estão no fim de `docs/projeto_narrativas.md`. Procure cada uma pelo título no **Google Acadêmico** (`scholar.google.com.br`); são artigos de revista e quase todos têm o PDF aberto. A de Soave e Da Silva Lemos (2022) é citada no texto do projeto, mas não aparece na lista do fim: procure-a no Google Acadêmico pelos sobrenomes dos autores e pelo ano, e monte você mesmo a referência completa;
- **a Convenção da UNESCO para a Salvaguarda do Patrimônio Cultural Imaterial (2003):** procure a versão em português no site do **IPHAN** (`gov.br/iphan`), pesquisando por "Convenção para a Salvaguarda do Patrimônio Cultural Imaterial". Leia os artigos 1 e 2 (finalidades e definições);
- **o Decreto nº 3.551, de 4 de agosto de 2000,** que instituiu o registro de bens culturais de natureza imaterial no Brasil: procure no portal da legislação federal (`planalto.gov.br`). É curto; leia inteiro;
- **um dado concreto para a Introdução:** no site do IPHAN, procure a página dos **bens registrados** como patrimônio imaterial e anote quantos são e a data da consulta. Número dá peso imediato ao texto;
- **Luís da Câmara Cascudo:** procure na biblioteca do campus ou no Google Livros o *Literatura oral no Brasil* ou o *Dicionário do folclore brasileiro*. Leia a apresentação ou a introdução e fiche a ideia central sobre o que é a literatura oral. É a referência obrigatória do folclore brasileiro, e ele é potiguar;
- **a Lei nº 9.610, de 19 de fevereiro de 1998** (direitos autorais), no `planalto.gov.br`: leia os artigos 41 e 45, que tratam do domínio público. Você vai citá-la para justificar o corpus.

### Como saber que deu certo

- O documento do Drive tem capa, folha de rosto e a seção de Referências criadas.
- O `docs/leituras.md` tem pelo menos **8 obras fichadas**, cada uma com a referência completa no formato ABNT.
- Você tem o número de bens registrados pelo IPHAN, com a data da consulta.

### Entrega

- [ ] Documento do Drive com capa, folha de rosto, título provisório e seção de Referências.
- [ ] `docs/orientacoes_escrita_tcc.md` e `docs/projeto_narrativas.md` lidos.
- [ ] Pelo menos 8 obras fichadas em `docs/leituras.md`, com referência ABNT.
- [ ] As obras lidas lançadas na seção de Referências do documento.

Para entregar, comente na *issue* dizendo quantas obras você fichou e mova o card para **Em revisão**.

---

# Sprint 2: 23/10 a 29/10/2026

<a id="sprint-2-dev"></a>
## Sprint 2 · Desenvolvimento: as três bases de teste

**Branch:** `feature/gerar-bases` · **No PR:** `Closes #3`

**O que você vai entregar:** o programa `scripts/01_gerar_base.py`, que gera três bancos SQLite com 100, 1.000 e 10.000 narrativas, e a verificação `testes/verificar_bases.py` terminando com `Tudo certo`.

### O problema a resolver

Você tem 30 contos, mas precisa de bases com 100, 1.000 e 10.000 narrativas. **Copiar o mesmo texto várias vezes invalidaria a medição:** o banco e o índice se comportam de forma completamente diferente quando os textos se repetem.

**A solução:** gerar narrativas novas **recombinando parágrafos** dos 30 contos. Cada narrativa gerada junta parágrafos sorteados de contos diferentes. O resultado é um texto com vocabulário, tamanho e estrutura de português real, mas que não se repete. Não é uma história que faça sentido do começo ao fim, e não precisa ser: para medir uma busca, o que importa são as palavras e o tamanho.

### Passo a passo

**1. Atualize a `develop` e crie a *branch*** `feature/gerar-bases` (veja a [seção 5.2](#fluxo-git)).

**2. Entenda o que o programa faz, antes de escrever.** O `01_gerar_base.py` vai:

1. ler os parágrafos dos 30 contos;
2. sortear, para cada narrativa nova, um título, um tipo, uma cidade e um texto feito de parágrafos;
3. garantir que nenhum texto se repete;
4. gravar tudo em `bancos/base_100.db` (ou `base_1000.db`, ou `base_10000.db`);
5. mostrar um resumo na tela.

**3. Comece pelo esqueleto.** Crie o arquivo com as partes abaixo e vá preenchendo uma função de cada vez, testando cada uma antes de passar para a próxima:

```python
import argparse
import hashlib
import os
import random
import sqlite3
import time

random.seed(42)   # faz o sorteio sair sempre igual

PASTA_CORPUS = "corpus"
TIPOS = ["Conto", "Lenda", "Mito", "Causo", "Fábula"]
CIDADES = [
    "Natal", "Mossoró", "Caicó", "Parnamirim", "Currais Novos",
    "Pau dos Ferros", "Açu", "Macau", "Santa Cruz", "João Câmara",
    "Apodi", "Ceará-Mirim", "Nova Cruz", "São Gonçalo do Amarante", "Extremoz",
    "Touros", "Martins", "Patu", "Jucurutu", "Acari",
]
MODELOS_TITULO = ["O caso", "A história", "A lenda", "O conto"]
PERSONAGENS = ["do macaco", "da onça", "do rei", "da princesa", "do jabuti",
               "da raposa", "do diabo", "da velha", "do padre", "do caçador",
               "da moura", "do sapo", "do vaqueiro", "da feiticeira", "do pescador"]


def carregar_paragrafos():
    """Le todos os .txt do corpus e devolve uma lista com os paragrafos."""
    ...


def gerar_texto(paragrafos):
    """Monta um texto novo, de 2.000 a 8.000 caracteres, sorteando paragrafos."""
    ...


def gerar_titulo():
    ...


def assinatura(texto):
    """Devolve o codigo SHA-256 do texto."""
    ...


def gravar_banco(caminho, narrativas):
    ...


def main():
    ...


if __name__ == "__main__":
    main()
```

**4. `carregar_paragrafos()`.** Para cada arquivo que termina em `.txt` na pasta `corpus` (em ordem alfabética):

- abra com `open(caminho, encoding="utf-8")` e leia tudo com `.read()`;
- separe os parágrafos pela linha em branco: `texto.split("\n\n")`;
- em cada parágrafo, tire os espaços das pontas (`strip()`) e troque qualquer `"\n"` que tenha sobrado por um espaço (`replace`);
- guarde só os parágrafos com **pelo menos 40 caracteres** (isso descarta títulos soltos e linhas vazias).

No fim, mostre na tela quantos parágrafos foram carregados. *Pesquise:* `os.listdir`, `sorted`, `str.endswith` e `os.path.join`.

> Você precisa de **pelo menos 150 parágrafos**. Com menos do que isso, as narrativas geradas ficam parecidas demais. Se der menos, confira se os seus arquivos têm mesmo uma linha em branco entre os parágrafos (o erro mais comum da Sprint 1).

**5. `gerar_texto(paragrafos)`.** A ideia:

1. sorteie um tamanho-alvo entre 2.000 e 8.000 caracteres: `alvo = random.randint(2000, 8000)`;
2. comece com uma lista vazia e vá acrescentando parágrafos sorteados com `random.choice(paragrafos)`, **sem repetir parágrafo dentro do mesmo texto**, até o total de caracteres passar do alvo;
3. junte os parágrafos com uma linha em branco entre eles: `"\n\n".join(escolhidos)`;
4. se o texto final passar de 8.000 caracteres (acontece quando o último parágrafo sorteado é muito grande), **descarte e comece de novo**. Um `while True` com `return` dentro resolve.

Por que de 2.000 a 8.000? Porque é o tamanho de uma narrativa real. Textos curtos demais não exigem nada da busca; longos demais deixam a geração lenta sem necessidade.

**6. `gerar_titulo()`, `assinatura(texto)` e os outros campos.**

- o título junta um modelo e um personagem sorteados: `"A lenda da onça"`, `"O caso do padre"`. Use `random.choice` duas vezes e uma *f-string*;
- o tipo e a cidade também são sorteados com `random.choice`, das listas `TIPOS` e `CIDADES`;
- a assinatura é o código SHA-256 do texto, uma espécie de "impressão digital": dois textos iguais têm sempre a mesma assinatura, e dois textos diferentes, na prática, nunca têm. Use `hashlib.sha256(texto.encode("utf-8")).hexdigest()`.

**7. A garantia de que nada se repete.** No `main()`, gere as narrativas em um laço até ter a quantidade pedida. Guarde as assinaturas já usadas em um **conjunto** (`set()`): antes de aceitar um texto novo, confira se a assinatura dele já está no conjunto; se estiver, descarte e sorteie outro. Cada narrativa vira uma tupla `(id, titulo, texto, tipo, cidade)`, com o `id` começando em 1.

*Pesquise:* `set`, o método `add` e o operador `in`.

**8. `gravar_banco(caminho, narrativas)`.**

1. se o arquivo do banco já existir, apague-o com `os.remove` (assim, rodar de novo sempre recria a base do zero);
2. conecte com `sqlite3.connect(caminho)` e crie a tabela:

   ```sql
   CREATE TABLE narrativa (
       id INTEGER PRIMARY KEY,
       titulo TEXT NOT NULL,
       texto TEXT NOT NULL,
       tipo TEXT,
       cidade TEXT
   )
   ```
3. grave todas as narrativas **de uma vez**, com `executemany` e um único `commit`. Inserir 10.000 linhas uma por uma, com um `commit` em cada, demora muito:

   ```python
   conexao.executemany("INSERT INTO narrativa VALUES (?, ?, ?, ?, ?)", narrativas)
   conexao.commit()
   ```
4. feche a conexão.

**9. O volume como parâmetro.** O programa deve aceitar o volume na linha de comando:

```
python scripts\01_gerar_base.py --volume 100
python scripts\01_gerar_base.py --volume 1000
python scripts\01_gerar_base.py --volume 10000
```

*Pesquise:* o módulo `argparse`, que já vem com o Python: `ArgumentParser`, `add_argument("--volume", type=int, required=True)` e `parse_args()`. Monte o caminho do banco com o volume: `f"bancos/base_{volume}.db"`.

**10. O resumo na tela.** No fim do `main()`, mostre:

```
Paragrafos carregados: 412
Narrativas geradas:    1000
Textos distintos:      1000
Assinatura da base:    3f9a0c1d2e4b5a67
Tempo de geracao:      1.84 s
Tamanho do banco:      5.12 MB
```

- **Textos distintos:** o tamanho do conjunto de assinaturas. Tem de ser igual ao número de narrativas;
- **Assinatura da base:** o SHA-256 de **todos os textos juntados em ordem** (`"".join(...)`), mostrando só os 16 primeiros caracteres (`[:16]`). Serve para provar que a base é reproduzível: rodar de novo tem de dar exatamente a mesma assinatura;
- **Tempo:** use `time.perf_counter()` no começo e no fim do `main()`;
- **Tamanho:** `os.path.getsize(caminho)` dá o tamanho em bytes; divida por `1024 * 1024` para ter MB.

**11. Por que a semente (`random.seed(42)`) é obrigatória.** Ela faz o programa gerar **sempre as mesmas bases**. Sem ela, quem rodar o seu programa vai obter outra base, e os números do TCC não poderão ser conferidos. **Faça o teste:** rode `--volume 100` duas vezes e confira se a "Assinatura da base" é a mesma. Depois comente a linha do `random.seed(42)`, rode duas vezes e veja a assinatura mudar. Volte a linha. Anote o resultado no diário: isso vai para a Metodologia.

**12. Gere as três bases e registre o resultado.** Rode os três volumes e copie as três saídas para `resultados/geracao.md`, em uma tabela:

```
| Volume | Narrativas | Textos distintos | Assinatura | Tempo (s) | Tamanho (MB) |
|---|---|---|---|---|---|
```

**13. Escreva `testes/verificar_bases.py`.** Releia a explicação do `assert` na [seção 5.5](#fluxo-git). Use este esqueleto e troque cada comentário numerado por uma linha com `assert`:

```python
import os
import sqlite3

for volume in [100, 1000, 10000]:
    caminho = f"bancos/base_{volume}.db"
    # 1. confira que o arquivo existe
    conexao = sqlite3.connect(caminho)
    total = conexao.execute("SELECT COUNT(*) FROM narrativa").fetchone()[0]
    # 2. confira que o total é igual ao volume
    # 3. confira que não há textos repetidos: COUNT(DISTINCT texto) igual ao volume
    # 4. confira que o menor texto tem pelo menos 2.000 caracteres: MIN(LENGTH(texto))
    # 5. confira que o maior texto tem no máximo 8.000 caracteres: MAX(LENGTH(texto))
    # 6. confira que os acentos chegaram: alguma narrativa tem "ã" (texto LIKE '%ã%')
    conexao.close()
    print(f"Base {volume}: ok")

print("Tudo certo: 3 bases verificadas.")
```

*Pesquise:* as funções `COUNT(DISTINCT ...)`, `MIN`, `MAX` e `LENGTH` do SQL. Coloque o volume na mensagem de cada `assert`, por exemplo `f"base {volume}: esperava {volume} narrativas, veio {total}"`.

Rode com `python testes\verificar_bases.py`. **Ele precisa terminar com `Tudo certo: 3 bases verificadas.`**

Para ter certeza de que a verificação funciona de verdade, faça uma sabotagem: troque temporariamente o 8.000 do item 5 por 3.000, rode e veja aparecer o `AssertionError`. Depois desfaça. Uma verificação que nunca falha não verifica nada.

**14. Olhe uma narrativa com os próprios olhos.** No terminal, com o `.venv` ativo, digite `python` para abrir o modo interativo e rode:

```python
import sqlite3
c = sqlite3.connect("bancos/base_100.db")
print(c.execute("SELECT titulo, tipo, cidade, texto FROM narrativa WHERE id = 1").fetchone())
```

Os acentos estão certos? Saia com `exit()`.

**15. Atualize o `README.md`** (como rodar o gerador e a verificação), escreva o diário, faça os *commits* e abra o PR para a `develop` com `Closes #3`. Em **Evidências de teste**, cole a saída do `verificar_bases.py` e a tabela do `resultados/geracao.md`.

### Como saber que deu certo

- As três execuções mostram "Textos distintos" igual a "Narrativas geradas".
- Rodar o mesmo volume duas vezes dá a mesma "Assinatura da base".
- `python testes\verificar_bases.py` mostra `Tudo certo: 3 bases verificadas.`
- O `git status` não mostra nenhum arquivo `.db`.

### Entrega da sprint

- [ ] `scripts/01_gerar_base.py` com semente fixa, parâmetro `--volume` e o resumo na tela.
- [ ] As três bases geradas, sem textos repetidos.
- [ ] Teste da semente feito e anotado no diário.
- [ ] `resultados/geracao.md` com a tabela dos três volumes.
- [ ] `testes/verificar_bases.py` terminando com `Tudo certo` (e a sabotagem testada).
- [ ] `README.md` atualizado e diário da semana.
- [ ] PR aberto para a `develop`, com `Closes #3`.

### Erros comuns

- **`IndexError` ou `random.choice` reclamando de lista vazia:** nenhum parágrafo foi carregado. Confira o nome da pasta e se você está rodando a partir da raiz do repositório.
- **O programa nunca termina:** o `gerar_texto` não consegue chegar a 2.000 caracteres sem repetir parágrafo, ou fica descartando textos acima de 8.000 sem parar. Mostre na tela o tamanho de cada tentativa para entender o que acontece.
- **`UnicodeDecodeError`:** algum arquivo do corpus não está em UTF-8.
- **`database is locked`:** outro programa está com o banco aberto. Feche o terminal interativo do passo 14.

<a id="sprint-2-escrita"></a>
## Sprint 2 · Escrita: Introdução e Objetivo geral (Entrega 1)

**Prazo: 29/10/2026**

A Introdução tem **cinco blocos de parágrafos, nesta ordem** (é a sequência definida nas orientações de escrita), e deve ocupar de **2 a 3 páginas**. Escreva no documento do Drive, nas seções `1 INTRODUÇÃO` e `1.1 Objetivo geral`.

### Bloco 1: Contextualização (2 parágrafos)

**Pesquise sobre:** você já fez isso na Sprint 1. Releia os fichamentos de Bezerra (2026), Dos Santos Fernandes e Martins (2026), Binda e Da Silva (2026), Soave e Da Silva Lemos (2022), Reis (2023), Câmara Cascudo, a Convenção da UNESCO e o Decreto nº 3.551/2000. Para o fim do bloco, procure também no Google Acadêmico por "acervo digital" e "recuperação da informação" e leia o resumo de dois ou três trabalhos.

**Escreva sobre:**

1. o valor das narrativas populares como patrimônio e **o risco de perdê-las**: elas vivem na memória de pessoas idosas e desaparecem com elas. Esse argumento já está no resumo do projeto. Use aqui o **número de bens registrados pelo IPHAN** que você anotou;
2. o projeto Narrativas como a iniciativa que busca preservar essas narrativas digitalmente.

**Depois faça a virada que leva ao seu tema: preservar não basta se ninguém consegue encontrar.** Um acervo digital com milhares de narrativas em que a busca não funciona é, na prática, um arquivo fechado. Quem procura uma história sobre o jabuti, ou as narrativas de uma cidade, precisa encontrá-la em segundos, senão desiste.

### Bloco 2: Problemática (2 a 3 parágrafos)

**Pesquise sobre:**

- como funciona a busca com `LIKE` em banco de dados e por que ela lê a tabela inteira. Comece pela página do operador `LIKE` na documentação do SQLite (`sqlite.org/lang_expr.html`, seção "The LIKE, GLOB, REGEXP, MATCH, and extract operators") e por um livro de banco de dados (veja a Sprint 3);
- o que é a **varredura completa de tabela** (*full table scan*);
- os problemas de busca em português: **acentuação**, **maiúsculas** e **plurais**. Procure no Google Acadêmico por "busca textual português acentuação" e "recuperação da informação língua portuguesa".

**Escreva sobre** o problema em três camadas, cada uma puxando a próxima:

1. **de onde vem o problema:** quem implementa uma busca pela primeira vez escreve `WHERE texto LIKE '%palavra%'` (no Django, `icontains`). E funciona perfeitamente durante o desenvolvimento, com vinte narrativas de teste;
2. **por que isso quebra depois:** para encontrar a palavra, o banco abre e lê o texto de **todas** as narrativas, uma por uma. Com 20, ninguém nota. Com 10.000 narrativas de milhares de caracteres, a busca demora, e demora justamente quando o acervo cresceu, ou seja, quando o portal está sendo usado;
3. **não é só velocidade, é qualidade:** o `LIKE` trata o texto como uma sequência de letras, não como língua. Ele não sabe que "irmao" e "irmão" são a mesma palavra, nem que "irmãos" é o plural de "irmão"; encontra "rei" dentro de "freira" e de "direito"; e devolve os resultados em qualquer ordem, sem saber qual narrativa interessa mais.

**Feche enunciando a pergunta de pesquisa** (a da [seção 2](#ideia)) e desdobre nas **três perguntas** da [seção 8.4](#escrita-geral).

**Não escreva** que "a busca do portal Narrativas é ruim". Ela ainda nem existe, e esse é exatamente o argumento: é o momento certo de decidir com base em medição, antes de a equipe escolher no escuro.

### Bloco 3: Caminho para a solução (1 a 2 parágrafos)

**Pesquise sobre:**

- as opções existentes para busca em um sistema web: `LIKE` simples, índices de banco de dados, busca em texto completo do próprio banco (SQLite, MySQL, PostgreSQL) e motores de busca dedicados (Elasticsearch, Meilisearch, Solr). Basta ler a página inicial da documentação de cada um;
- o que é **busca em texto completo** (*full-text search*) e o que é um **índice invertido**;
- o **FTS5** do SQLite, pela documentação oficial (`sqlite.org/fts5.html`, seção 1, "Overview of FTS5").

**Escreva sobre** as alternativas, do mais simples ao mais complexo, dizendo o que cada uma resolve e o que custa:

- **`LIKE` sem índice:** não custa nada para implementar, e é o que a maioria faz;
- **`LIKE` com índice:** parece a solução óbvia, e é aqui que mora a surpresa do trabalho;
- **busca em texto completo do próprio banco:** exige aprender o recurso e ocupa espaço em disco, mas não exige instalar nada novo;
- **motor de busca dedicado:** mais poderoso, mas exige instalar e manter mais um sistema, com servidor próprio.

**Justifique o recorte:** o trabalho avalia as três primeiras, no SQLite, porque não exigem instalar nenhum sistema novo. Os motores dedicados e a busca do MySQL ficam como trabalho futuro. **Recorte declarado é recorte defendido.**

### Bloco 4: Apresentação da solução (2 parágrafos)

Você ainda não fez quase nada disso. **Escreva no futuro** ("serão comparadas", "será medido") e, na revisão final (Sprint 8), passe para o passado.

**Escreva sobre:**

- **o que será feito:** a comparação de três estratégias de busca textual (E1, E2 e E3, descritas pelo nome, sem os códigos) sobre a mesma base de narrativas, com as mesmas consultas, no mesmo computador;
- **como será avaliado:** tempo de resposta em bases de 100, 1.000 e 10.000 narrativas, com repetições e descarte das execuções de aquecimento; custo em disco; comportamento diante de acentos, maiúsculas e plurais; e qualidade dos dez primeiros resultados;
- **de onde vêm os dados:** a base foi construída a partir de **contos populares em domínio público**, recombinados por programa para atingir os três volumes, com a origem de cada texto documentada. **Nenhum dado de usuário da plataforma foi usado e não houve participantes de pesquisa**, o que dispensa a submissão ao Comitê de Ética em Pesquisa.

### Bloco 5: Vínculo com o projeto e escopo (1 parágrafo)

**Escreva sobre** o vínculo com o projeto Narrativas, do IFRN, cuja etapa atual trata de autenticação, área administrativa e gerenciamento do acervo. Explique que:

- o trabalho foi feito **em um repositório separado**, sem alterar o sistema, porque o objetivo é **responder antecipadamente a uma decisão técnica** que a equipe vai precisar tomar: como a busca do portal será implementada;
- **implementar a busca na plataforma é trabalho futuro**; o que este trabalho entrega é uma recomendação fundamentada em medição.

Feche a Introdução com um parágrafo curto dizendo como o texto está organizado ("A seção 2 apresenta...; a seção 3 descreve...").

### 1.1 Objetivo geral

Uma **única frase**, com **uma única ação principal**. Modelo das orientações de escrita:

> "O objetivo principal do presente trabalho consiste [na ação] de [o quê] para [finalidade]."

- **O verbo não é "desenvolver".** Você não está entregando um sistema; está entregando conhecimento medido. Verbos adequados: **avaliar**, **comparar**, **analisar**;
- diga **o que** é avaliado (estratégias de busca textual), **sobre o quê** (um acervo digital de narrativas populares em português) e **em que dimensões** (tempo de resposta, custo e qualidade dos resultados). Sem a terceira parte, o objetivo fica vago;
- **não** empilhe ações: "avaliar, implementar e integrar" são três objetivos, não um;
- **não** prometa o que não vai medir.

Deixe a seção `1.2 Objetivos específicos` com o título e a linha "a ser escrito na Sprint 8".

### Entrega

- [ ] Os cinco blocos da Introdução escritos, na ordem, com citações.
- [ ] As três perguntas de pesquisa enunciadas no fim da problemática.
- [ ] Objetivo geral em uma frase, com um verbo só.
- [ ] Todas as obras citadas lançadas nas Referências, no formato ABNT.
- [ ] Versão nomeada no histórico: `Entrega 1 - Introdução - 29/10`.
- [ ] Comentário na *issue*, marcando os orientadores, e card em **Em revisão**.

---

# Sprint 3: 30/10 a 05/11/2026

<a id="sprint-3-dev"></a>
## Sprint 3 · Desenvolvimento: estratégias E1 e E2 e o programa de medição

**Branch:** `feature/medicao-e1-e2` · **No PR:** `Closes #5`

**O que você vai entregar:** as 8 consultas de teste definidas, o protocolo do experimento escrito, as estratégias E1 e E2 funcionando e o programa de medição gravando os primeiros números em `resultados/tempos.csv`.

> **Atenção:** 02/11 (segunda) é feriado. A semana tem um dia útil a menos.

**Divida a semana assim:**

| Dia | O que fazer |
|---|---|
| sexta, 30/10 | passos 1 a 4 (escolher as consultas e escrever o protocolo) |
| terça, 03/11 | passos 5 e 6 (as funções de busca e a preparação das estratégias) |
| quarta, 04/11 | passo 7 (o programa de medição) |
| quinta, 05/11 | passos 8 e 9 (rodar, registrar e abrir o PR) |

### Passo a passo

**1. Atualize a `develop` e crie a *branch*** `feature/medicao-e1-e2`.

**2. Escreva `scripts/contar_termo.py`**, uma ferramenta pequena para você escolher as consultas. Ela recebe um termo e mostra em quantas narrativas da base de 1.000 ele aparece:

```
python scripts\contar_termo.py --termo macaco
macaco: 287 de 1000 narrativas
```

O programa usa `argparse` (como na Sprint 2), conecta em `bancos/base_1000.db` e roda:

```sql
SELECT COUNT(*) FROM narrativa WHERE texto LIKE ?
```

passando `f"%{termo}%"` como parâmetro.

**3. Escolha as 8 consultas de teste.** Elas são as buscas que você vai repetir em tudo: tempo, acentos e qualidade. Cada uma testa uma situação diferente:

| Código | Tipo | Exemplo | Conceito |
|---|---|---|---|
| C1 | termo comum, sem acento | `macaco` | macaco |
| C2 | termo com acento, escrito como está no texto | `irmão` | irmão |
| C3 | o mesmo termo de C2, sem acento | `irmao` | irmão |
| C4 | o mesmo termo de C2, em maiúsculas | `IRMÃO` | irmão |
| C5 | o plural do termo de C2 | `irmãos` | irmão |
| C6 | palavra curta que aparece dentro de outras palavras | `rei` (está em "freira", "direito", "primeiro") | rei |
| C7 | termo raro | um termo que aparece em menos de 20 das 1.000 narrativas | o próprio termo |
| C8 | termo que não existe na base | `helicóptero` | helicóptero |

Os exemplos são **sugestões**: use o `contar_termo.py` para conferir se eles existem no **seu** corpus, e troque o que não servir. Regras:

- **C1:** aparece em pelo menos 100 das 1.000 narrativas;
- **C2:** uma palavra com acento (de preferência com "ã") que aparece em pelo menos 50 narrativas, **escrita exatamente como no texto** (lembre que a grafia é de 1885: confira no próprio corpus);
- **C5:** o plural da palavra de C2 também precisa aparecer no corpus;
- **C6:** confira que a contagem de `rei` é bem maior do que o número de narrativas em que "rei" aparece como palavra mesmo. Para ter uma ideia, compare com `contar_termo.py --termo " rei "` (com espaços em volta);
- **C7:** entre 1 e 20 narrativas;
- **C8:** zero narrativas.

A coluna **conceito** diz qual é a ideia procurada: C2, C3, C4 e C5 procuram a mesma coisa (o conceito "irmão"), só que digitada de jeitos diferentes. Ela vai ser usada na Sprint 6.

Salve em `docs/consultas.csv`:

```
codigo,termo,tipo,conceito
C1,macaco,termo comum,macaco
C2,irmão,termo com acento,irmão
...
```

**A partir do PR desta sprint, a lista de consultas não muda mais.** Mudar as consultas depois de medir é escolher o resultado.

**4. Escreva `docs/protocolo.md`**, o protocolo do experimento, em uma página. Ele responde:

1. quais são as estratégias (E1, E2, E3), com uma linha explicando cada uma;
2. quais são os volumes (100, 1.000 e 10.000 narrativas) e de onde vêm (Sprint 2);
3. quais são as consultas (aponte para `docs/consultas.csv`);
4. **quantas medições por consulta:** 3 execuções de aquecimento, descartadas, e depois 10 medições válidas;
5. o que é registrado em cada medição (as colunas do `tempos.csv`, passo 7);
6. em que máquina (aponte para `docs/ambiente.md`) e em que condições: **todos os outros programas fechados**, inclusive o navegador;
7. que a comparação usa a **mediana**, e que a média e o desvio padrão também são relatados;
8. que as medições desta sprint e da próxima são a **rodada preliminar**, e que a **rodada oficial**, usada no TCC, é feita na Sprint 5.

**Por que aquecimento e repetições?** Porque a primeira execução de uma consulta é sempre mais lenta (o banco ainda não carregou nada na memória), e porque uma medição sozinha pode sair distorcida se o antivírus resolver rodar naquele instante. **Por que mediana e não média?** Porque uma única execução muito lenta puxa a média para cima e dá uma impressão errada; a mediana não se deixa levar por um valor isolado. Escreva essas duas justificativas no protocolo: elas vão direto para a Metodologia.

**5. Escreva `scripts/buscas.py`**, com uma função para cada estratégia. Todas recebem os mesmos parâmetros e devolvem a mesma coisa: **uma lista com os `id` das narrativas encontradas**. Assim o programa de medição trata todas do mesmo jeito.

A E1 é a busca mais simples que existe:

```python
SQL_LIKE = "SELECT id FROM narrativa WHERE titulo LIKE ? OR texto LIKE ?"
```

A função `buscar_e1(conexao, termo)` deve:

1. montar o padrão `f"%{termo}%"`;
2. executar `SQL_LIKE` com o padrão nos dois `?`;
3. **ler o resultado inteiro com `fetchall()`**;
4. devolver a lista dos `id` (o primeiro item de cada linha).

A `buscar_e2(conexao, termo)` faz **exatamente a mesma coisa**. A diferença entre E1 e E2 não está no código: está no banco em que a busca roda (o banco da E2 tem índice; veja o passo 6). Escreva a função mesmo assim, separada, para que o programa de medição tenha uma função por estratégia.

**Sempre com consulta parametrizada.** Repare que o termo entra como parâmetro (`?`), e não colado dentro do texto do SQL. **Nunca** escreva algo como:

```python
# NAO FACA ISSO
conexao.execute(f"SELECT id FROM narrativa WHERE texto LIKE '%{termo}%'")
```

Se o termo vier de alguém digitando no site, essa pessoa pode digitar um pedaço de SQL e mudar o que a consulta faz. Isso se chama **injeção de SQL**, e é uma das falhas de segurança mais conhecidas que existem. Pesquise sobre o assunto: rende um parágrafo no Referencial Teórico.

**6. Escreva `scripts/02_preparar_estrategias.py`.** Ele prepara um banco separado para cada estratégia, a partir da base da Sprint 2. Ter um arquivo por estratégia deixa a comparação limpa e permite medir o tamanho de cada uma em disco. Para cada volume (100, 1.000 e 10.000):

1. **E1:** copie `bancos/base_{volume}.db` para `bancos/e1_{volume}.db`. Nada mais: a E1 é a base sem índice;
2. **E2:** copie a base para `bancos/e2_{volume}.db`, conecte e crie dois índices:

   ```sql
   CREATE INDEX idx_narrativa_texto ON narrativa(texto COLLATE NOCASE);
   CREATE INDEX idx_narrativa_titulo ON narrativa(titulo COLLATE NOCASE);
   ```

   Por que `COLLATE NOCASE`? Porque o `LIKE` do SQLite ignora maiúsculas e minúsculas, e o SQLite só consegue usar um índice para o `LIKE` se o índice também ignorar. É a forma de dar ao índice **a melhor chance possível** de ajudar: se nem assim ele ajudar, o resultado fica ainda mais forte;
3. para cada estratégia, meça o **tempo de preparação** (a cópia mais a criação do índice) com `time.perf_counter()` e o **tamanho do arquivo** com `os.path.getsize`;
4. grave tudo em `resultados/custos.csv`, com as colunas:

   ```
   volume,estrategia,tamanho_mb,tempo_preparo_s
   ```

*Pesquise:* `shutil.copyfile` e o módulo `csv` (`csv.writer`, `writerow`). Abra o arquivo de saída com `open(caminho, "w", newline="", encoding="utf-8")`: sem o `newline=""`, o Windows coloca uma linha em branco entre as linhas da planilha.

> O `custos.csv` é recriado a cada execução. Os valores que vão para o TCC são os da rodada oficial, na Sprint 5.

**7. Escreva `scripts/03_medir.py`, o coração do trabalho.** Ele será usado até o fim, e na Sprint 4 você só vai acrescentar a E3. A estrutura é de laços encaixados:

```
para cada volume (100, 1.000, 10.000):
    para cada estratégia (E1, E2):
        abrir a conexão com bancos/{estrategia}_{volume}.db
        para cada consulta de docs/consultas.csv:
            3 execuções de aquecimento (descartadas)
            10 medições válidas, gravando uma linha por medição
        fechar a conexão
```

Peças que você vai usar:

```python
from buscas import buscar_e1, buscar_e2

ESTRATEGIAS = {"E1": buscar_e1, "E2": buscar_e2}
VOLUMES = [100, 1000, 10000]
AQUECIMENTO = 3
REPETICOES = 10
```

Um dicionário de funções permite chamar a estratégia pelo código: `ESTRATEGIAS["E1"](conexao, termo)`. O `from buscas import ...` funciona porque o Python procura os módulos na mesma pasta do programa que está rodando (`scripts/`).

**Como cronometrar uma medição:**

```python
inicio = time.perf_counter()
resultados = funcao(conexao, termo)
tempo_ms = (time.perf_counter() - inicio) * 1000
```

Use `time.perf_counter()`, nunca `time.time()`: o primeiro é bem mais preciso para medir durações curtas.

**Uma armadilha que arruinaria o trabalho inteiro:** em Python, executar uma consulta **não** significa que o banco fez o trabalho. O SQLite entrega as linhas aos poucos, conforme você pede. Se a função só chamasse `execute` e não lesse o resultado, o tempo medido seria falso, pequeno demais. **É por isso que as funções de busca terminam com `fetchall()`**: o cronômetro só para depois de o resultado inteiro ter sido lido.

**Grave uma linha por medição**, não só a média. O arquivo `resultados/tempos.csv` tem estas colunas:

```
data,rodada,volume,estrategia,consulta,repeticao,tempo_ms,qtd_resultados
```

- `data`: `datetime.date.today().isoformat()`;
- `rodada`: `preliminar` ou `oficial`, recebida pela linha de comando (`--rodada`, com `argparse`);
- `consulta`: o código (C1 a C8);
- `repeticao`: de 1 a 10;
- `tempo_ms`: com 3 casas decimais (`round(tempo_ms, 3)`);
- `qtd_resultados`: o tamanho da lista devolvida.

**Nunca apague medições:** abra o arquivo em modo de **acréscimo** (`"a"`), para que cada execução acrescente linhas no fim. Escreva o cabeçalho só se o arquivo ainda não existir (*pesquise:* `os.path.exists`). Para ler as consultas, use `csv.DictReader`, que devolve cada linha como um dicionário (`linha["codigo"]`, `linha["termo"]`).

Mostre o progresso na tela, uma linha por consulta (`E1 | 10000 | C1 | mediana parcial 412.3 ms`), para saber que o programa não travou: a base de 10.000 com a E1 demora alguns minutos.

**8. Rode a rodada preliminar:**

```
python scripts\02_preparar_estrategias.py
python scripts\03_medir.py --rodada preliminar
```

Feche os outros programas antes. Depois abra o `resultados/tempos.csv` no VS Code e olhe os números. Anote no diário: **o tempo cresce quando a base cresce? A E2 ficou mais rápida que a E1?** Você provavelmente vai ver o tempo das duas crescer quase na mesma proporção da base, e a E2 sem vantagem nenhuma. É o aviso da [seção 2](#ideia) se confirmando. A explicação vem na Sprint 4.

**9. Atualize o `README.md`** (a ordem de execução dos programas até aqui), escreva o diário, faça os *commits* e abra o PR com `Closes #5`. Em **Evidências de teste**, cole a saída do `verificar_bases.py` e as primeiras linhas do `tempos.csv`.

### Como saber que deu certo

- `docs/consultas.csv` tem as 8 consultas, conferidas com o `contar_termo.py`.
- `resultados/custos.csv` tem 6 linhas (E1 e E2 nos três volumes), e o banco da E2 é maior que o da E1.
- `resultados/tempos.csv` tem 480 linhas de medição (3 volumes × 2 estratégias × 8 consultas × 10 repetições), todas com `rodada` igual a `preliminar`.
- Os tempos da base de 10.000 com a E1 são de dezenas ou centenas de milissegundos, não frações de milissegundo.

### Entrega da sprint

- [ ] `scripts/contar_termo.py` e `docs/consultas.csv` com as 8 consultas.
- [ ] `docs/protocolo.md` com os 8 itens.
- [ ] `scripts/buscas.py` com `buscar_e1` e `buscar_e2`, com consulta parametrizada e `fetchall()`.
- [ ] `scripts/02_preparar_estrategias.py` gerando os bancos da E1 e da E2 e o `resultados/custos.csv`.
- [ ] `scripts/03_medir.py` gravando em `resultados/tempos.csv`, em modo de acréscimo.
- [ ] Rodada preliminar da E1 e da E2 nos três volumes, com a impressão anotada no diário.
- [ ] `README.md` atualizado.
- [ ] PR aberto para a `develop`, com `Closes #5`.

### Erros comuns

- **Tempos absurdamente baixos (menos de 1 ms na base de 10.000):** faltou o `fetchall()`. A consulta não chegou a ser executada de verdade.
- **Tempos muito diferentes entre repetições:** tem outro programa pesado aberto. Feche tudo e rode de novo (sem apagar as linhas anteriores; anote no diário).
- **`ModuleNotFoundError: No module named 'buscas'`:** o `buscas.py` não está na pasta `scripts/`, ou o nome do arquivo está diferente.
- **Linhas em branco entre as linhas do CSV:** faltou `newline=""` no `open`.

<a id="sprint-3-escrita"></a>
## Sprint 3 · Escrita: Referencial Teórico, seções 2.1 e 2.2 (Entrega 2)

**Prazo: 05/11/2026**

**Vídeo com a explicação do Referencial (assista antes de começar):** https://youtu.be/8Qztq1Q5vb0

Uma regra prática resolve metade dos problemas do Referencial: **tudo o que vai aparecer nos Resultados precisa estar explicado antes, aqui.** Se a tabela vai mostrar "plano de execução", esse conceito tem de estar definido no Referencial. Se um conceito não reaparece depois, não precisa estar.

### 2.1 Narrativas populares e acervos digitais (cerca de 1,5 página)

**Pesquise:** você já fichou quase tudo na Sprint 1 (as referências do projeto, Câmara Cascudo, UNESCO, Decreto nº 3.551/2000). Acrescente uma ou duas leituras sobre **acervo digital** ou **biblioteca digital**: procure no Google Acadêmico e na SciELO por "acervo digital patrimônio cultural" e "curadoria digital". O Soave e Da Silva Lemos (2022) já trata de curadoria digital e serve bem aqui.

**Escreva:**

- o que são narrativas populares e por que preservá-las importa (Câmara Cascudo; Bezerra, 2026);
- o que é patrimônio cultural imaterial (Convenção da UNESCO; Decreto nº 3.551/2000);
- o que é um acervo digital e que papel ele cumpre na salvaguarda desse patrimônio (Soave e Da Silva Lemos, 2022; Reis, 2023);
- **por que organizar e permitir encontrar faz parte da preservação.** Um acervo em que nada é localizável preserva, mas não difunde. Este é o parágrafo que amarra o seu trabalho técnico ao projeto: não o trate como enfeite.

### 2.2 Banco de dados, SQL e índices (cerca de 2,5 páginas)

**Pesquise:**

- **um livro de banco de dados**, para os conceitos: *Sistemas de banco de dados*, de Elmasri e Navathe, ou *Sistema de banco de dados*, de Silberschatz, Korth e Sudarshan. Os dois têm edições em português e costumam estar na biblioteca do campus e na Biblioteca Virtual Pearson (se o IFRN der acesso pelo SUAP). Leia os capítulos de introdução (o que é um banco de dados e um SGBD), de SQL básico (`SELECT` com `WHERE`) e de **indexação** (índices e árvore B);
- **a documentação oficial do SQLite** (`sqlite.org`): a página "About SQLite" (o que é o SQLite e por que ele funciona como um arquivo, sem servidor), a página "Query Planning" (`sqlite.org/queryplanner.html`, que explica com desenhos como um índice é usado) e a página "The SQLite Query Optimizer Overview" (`sqlite.org/optoverview.html`), seção "The LIKE optimization";
- **injeção de SQL:** a página "SQL Injection" da OWASP (`owasp.org`) e um artigo ou livro de segurança da informação que trate do assunto (procure "injeção de SQL" no Google Acadêmico).

**Escreva, nesta ordem:**

1. **o que é um banco de dados relacional e o que faz um SGBD**, e o que é a linguagem SQL, com o comando `SELECT ... WHERE`. Apresente o **SQLite**: um banco que guarda tudo em um único arquivo, sem servidor, e que já vem com o Python;
2. **o operador `LIKE`** e o curinga `%`, e a **consulta parametrizada**: por que o termo da busca nunca deve ser colado no texto do SQL (**injeção de SQL**);
3. **o que é um índice**, começando por uma comparação simples: é como o índice remissivo no fim de um livro; sem ele, para achar um assunto você leria o livro inteiro. Explique o que é a **varredura completa da tabela** (*full table scan*) e por que ela fica mais cara conforme a tabela cresce;
4. **o que é o plano de execução** e para que serve o comando `EXPLAIN QUERY PLAN`: ele mostra como o banco decidiu buscar os dados, e é assim que se descobre se o índice foi usado;
5. **prepare o terreno para a descoberta do trabalho:** um índice comum (árvore B) organiza os valores **pelo começo**, como um dicionário organiza as palavras pela primeira letra. Por isso ele funciona para procurar o que *começa* com um termo (`LIKE 'boi%'`), mas **não** funciona quando a busca começa com o curinga (`LIKE '%boi%'`), porque não há por onde entrar no índice. Você vai comprovar isso nos Resultados; aqui, fundamente com o livro e com a documentação do SQLite.

### Entrega

- [ ] Seções 2.1 e 2.2 escritas, com citações.
- [ ] Pelo menos um livro de banco de dados citado na 2.2.
- [ ] As obras novas lançadas nas Referências e fichadas em `docs/leituras.md`.
- [ ] Comentários da Entrega 1 resolvidos.
- [ ] Versão nomeada: `Entrega 2 - Referencial 2.1 e 2.2 - 05/11`.
- [ ] Comentário na *issue*, marcando os orientadores, e card em **Em revisão**.

---

# Sprint 4: 06/11 a 12/11/2026

<a id="sprint-4-dev"></a>
## Sprint 4 · Desenvolvimento: estratégia E3 (FTS5) e os planos de execução

**Branch:** `feature/fts5` · **No PR:** `Closes #7`

**O que você vai entregar:** a estratégia E3 funcionando e medida (rodada preliminar), os planos de execução que explicam por que a E2 não ajudou e a verificação `testes/verificar_buscas.py` terminando com `Tudo certo`.

### Passo a passo

**1. Atualize a `develop` e crie a *branch*** `feature/fts5`.

**2. Entenda o que é o FTS5.** É um recurso do próprio SQLite para busca em texto completo. Em vez de ler todos os textos procurando o termo, ele monta antes um **índice invertido**: uma lista que diz, para cada palavra, em quais narrativas ela aparece. Buscar vira consultar essa lista, o que é muito mais rápido. Para montar a lista, o FTS5 quebra o texto em palavras (isso se chama **tokenização**), passa tudo para minúsculas e, se você pedir, remove os acentos.

Leia na documentação oficial (`sqlite.org/fts5.html`) as seções 1 ("Overview of FTS5"), 3 ("Full-text Query Syntax", só o começo, até "FTS5 Phrases") e 4.3 ("Tokenizers", a parte do `unicode61`).

**3. Acrescente a E3 ao `02_preparar_estrategias.py`.** Para cada volume, copie a base para `bancos/e3_{volume}.db`, conecte e crie a tabela de busca:

```sql
CREATE VIRTUAL TABLE narrativa_fts USING fts5(
    titulo,
    texto,
    tokenize = "unicode61 remove_diacritics 2"
);
```

O `remove_diacritics 2` é o que faz a busca por "irmao" encontrar "irmão". **É o parâmetro mais importante desta sprint.**

Depois preencha a tabela com as narrativas, usando o `id` da narrativa como identificador (`rowid`) da tabela de busca, e faça o `commit`:

```sql
INSERT INTO narrativa_fts(rowid, titulo, texto)
SELECT id, titulo, texto FROM narrativa;
```

Meça o tempo e o tamanho como nas outras estratégias e grave no `custos.csv`.

> **Uma simplificação que você vai declarar no TCC.** Desse jeito, o banco da E3 guarda o texto **duas vezes**: na tabela `narrativa` e na tabela de busca. Existe uma forma de evitar isso (a opção `content=` do FTS5), mas ela é mais complicada e não muda o tempo de busca, que é o que você está medindo. Use a forma simples, meça o espaço que ela custa e escreva no TCC que a versão sem duplicação fica como trabalho futuro. Limitação declarada não tira valor do trabalho; esconder, sim.

**4. Escreva `buscar_e3(conexao, termo)` no `buscas.py`:**

```python
SQL_FTS = """
SELECT rowid
FROM narrativa_fts
WHERE narrativa_fts MATCH ?
ORDER BY bm25(narrativa_fts)
"""
```

Dois cuidados:

- **coloque o termo entre aspas duplas** antes de passar para o `MATCH`: `f'"{termo}"'`. O FTS5 tem uma linguagem própria de consulta, em que alguns caracteres (o hífen, os dois-pontos, o asterisco) têm significado especial. Entre aspas, o termo é procurado literalmente. Se o próprio termo tiver aspas duplas, duplique-as antes (`termo.replace('"', '""')`);
- **o `bm25()`** é uma fórmula que ordena os resultados por **relevância**: uma narrativa em que o termo aparece cinco vezes, e que é curta, vem antes de outra em que ele aparece uma vez no meio de um texto longo. A E1 e a E2 não fazem isso: no `LIKE`, os resultados saem na ordem em que estão na tabela. **Esse é um ponto forte da E3 e precisa estar no TCC.**

Como as outras, a função termina com `fetchall()` e devolve a lista de `id`.

**5. Acrescente a E3 ao `03_medir.py`** (uma linha no dicionário `ESTRATEGIAS`) e rode a rodada preliminar de novo, para as três estratégias:

```
python scripts\02_preparar_estrategias.py
python scripts\03_medir.py --rodada preliminar
```

As medições antigas da E1 e da E2 continuam no arquivo, e as novas são acrescentadas no fim: tudo bem, é para isso que existe a coluna `data`. Anote no diário: **quantas vezes a E3 foi mais rápida que a E1 na base de 10.000? O tempo da E3 cresceu quando a base cresceu?**

**6. Escreva `scripts/04_planos.py`: a prova do porquê.** Este programa mostra **como** o SQLite decidiu fazer cada busca, usando o `EXPLAIN QUERY PLAN`. Ele usa a base de 10.000 e grava cada plano em um arquivo de texto em `resultados/planos/`:

| Arquivo | Banco | Consulta |
|---|---|---|
| `e1_10000.txt` | `e1_10000.db` | `SELECT id FROM narrativa WHERE texto LIKE '%macaco%'` |
| `e2_10000.txt` | `e2_10000.db` | a mesma consulta |
| `e2_prefixo_10000.txt` | `e2_10000.db` | `SELECT id FROM narrativa WHERE texto LIKE 'macaco%'` (sem o `%` no começo) |
| `e3_10000.txt` | `e3_10000.db` | `SELECT rowid FROM narrativa_fts WHERE narrativa_fts MATCH '"macaco"'` |

(Use o termo da sua C1 no lugar de "macaco".)

Para cada linha da tabela, o programa:

1. conecta no banco;
2. executa `"EXPLAIN QUERY PLAN " + consulta`;
3. lê todas as linhas com `fetchall()`. Cada linha tem quatro valores, e o que interessa é o **último**, o texto que descreve o plano;
4. grava a consulta e o plano no arquivo `.txt` e mostra na tela.

> **Aqui o termo vai escrito dentro do SQL, e não como parâmetro, de propósito.** Para mostrar o plano de uma busca por prefixo, o SQLite precisa ver o termo na hora de planejar. Isso não é injeção de SQL porque o termo está fixo no seu programa, e não vem de alguém digitando. Nas funções de busca, o parâmetro continua obrigatório.

**7. Leia os planos e entenda.** Você deve encontrar:

- **E1 e E2 com `'%termo%'`:** a palavra `SCAN narrativa`. Significa que o banco **leu a tabela inteira**. No caso da E2, pode aparecer `SCAN narrativa USING COVERING INDEX idx_narrativa_texto`: o banco percorreu o índice inteiro, do primeiro ao último item, em vez da tabela, o que dá no mesmo. Em nenhum dos dois casos o índice serviu para **pular** direto para o que interessa;
- **E2 com `'termo%'`:** a palavra `SEARCH` e o nome do índice (`USING ... INDEX idx_narrativa_texto`). Aqui o índice **foi** usado, porque a busca começa com letras conhecidas;
- **E3:** uma linha com `VIRTUAL TABLE INDEX`, mostrando que a busca foi feita pelo índice invertido do FTS5.

Comparar os dois planos da E2 lado a lado prova o argumento central: **o problema não é o índice, é o `%` no começo da busca**. Tire um print da saída e salve em `docs/evidencias/s04_planos.png`. Explique, com as suas palavras, no diário.

**8. Escreva `testes/verificar_buscas.py`.** Ele confere, na base de 1.000, se as três estratégias se comportam como o esperado. O esqueleto:

```python
import csv
import sqlite3
import sys

sys.path.insert(0, "scripts")   # deixa o Python encontrar o buscas.py
from buscas import buscar_e1, buscar_e2, buscar_e3

e1 = sqlite3.connect("bancos/e1_1000.db")
e2 = sqlite3.connect("bancos/e2_1000.db")
e3 = sqlite3.connect("bancos/e3_1000.db")

# leia docs/consultas.csv para uma lista ou um dicionário de código -> termo

# 1. para cada consulta, a E1 e a E2 encontram exatamente as mesmas narrativas
#    (compare como conjuntos: set(lista1) == set(lista2))
# 2. a consulta C8 (termo inexistente) não encontra nada em nenhuma das três
# 3. a consulta C1 encontra pelo menos uma narrativa nas três
# 4. na E3, a busca sem acento (C3) encontra as mesmas narrativas que a com acento (C2)
# 5. na E1, a busca sem acento (C3) encontra menos narrativas que a com acento (C2)

print("Tudo certo: buscas verificadas.")
```

Os itens 4 e 5 são a prova automática do comportamento com acentos, que você vai detalhar na Sprint 5.

**Sabotagem:** no `02_preparar_estrategias.py`, troque temporariamente o `remove_diacritics 2` por `remove_diacritics 0`, rode a preparação e a verificação, e veja o item 4 falhar. Desfaça e rode de novo.

**9. Atualize o `README.md`**, escreva o diário, faça os *commits* e abra o PR com `Closes #7`. Em **Evidências de teste**, cole a saída das duas verificações e o print dos planos.

### Como saber que deu certo

- O `custos.csv` tem 9 linhas (três estratégias × três volumes), e o banco da E3 é maior que o da E1.
- Na base de 10.000, a E3 é muitas vezes mais rápida que a E1.
- Os planos mostram `SCAN` na E1 e na E2 com `%` no começo, `SEARCH` com o índice na busca por prefixo e `VIRTUAL TABLE INDEX` na E3.
- `python testes\verificar_buscas.py` mostra `Tudo certo: buscas verificadas.`

### Entrega da sprint

- [ ] E3 no `02_preparar_estrategias.py`, com `remove_diacritics 2`, e no `custos.csv`.
- [ ] `buscar_e3` com `MATCH`, termo entre aspas e ordenação por `bm25`.
- [ ] Rodada preliminar com as três estratégias.
- [ ] `scripts/04_planos.py` e os 4 planos em `resultados/planos/`, com o print.
- [ ] `testes/verificar_buscas.py` terminando com `Tudo certo` (e a sabotagem testada).
- [ ] `README.md` atualizado e diário da semana.
- [ ] PR aberto para a `develop`, com `Closes #7`.

### Erros comuns

- **`no such table: narrativa_fts`:** a busca está rodando no banco errado. A tabela de busca só existe nos bancos `e3_...`.
- **`fts5: syntax error near ...`:** o termo não foi colocado entre aspas duplas.
- **O plano da busca por prefixo mostra `SCAN`, e não `SEARCH`:** o índice foi criado sem `COLLATE NOCASE`. Confira o passo 6 da Sprint 3 e rode a preparação de novo.

<a id="sprint-4-escrita"></a>
## Sprint 4 · Escrita: Referencial Teórico, seções 2.3, 2.4 e 2.5 (Entrega 3)

**Prazo: 12/11/2026**

Esta semana você escreve a parte do Referencial que explica a E3 e a avaliação de qualidade, justamente na semana em que está implementando a E3. Aproveite: escrever sobre o que se está fazendo sai mais fácil e melhor.

### 2.3 Busca em texto completo (cerca de 2 páginas)

**Pesquise:**

- **recuperação da informação:** o livro *Introduction to Information Retrieval*, de Manning, Raghavan e Schütze (Cambridge University Press, 2008), está **gratuito e completo** no site dos autores (`nlp.stanford.edu/IR-book`). Leia o capítulo 1 (índice invertido) e as seções 2.2 (tokenização e palavras vazias) e 2.2.4 (radicalização, *stemming*). Para o BM25, leia a seção 11.4.3. Procure também uma obra em português sobre recuperação da informação: *Recuperação de informação: conceitos e tecnologia das máquinas de busca*, de Baeza-Yates e Ribeiro-Neto, tem edição em português;
- **a documentação do FTS5** (`sqlite.org/fts5.html`), para descrever a ferramenta: o tokenizador `unicode61`, a opção `remove_diacritics`, a função `bm25()` e o tokenizador `porter` (que trata plurais, mas só em inglês).

**Escreva:**

1. o que é recuperação da informação e como ela difere de uma busca literal por caracteres (o `LIKE`);
2. como funciona um **índice invertido**: em vez de guardar "esta narrativa contém estas palavras", ele guarda "esta palavra aparece nestas narrativas". Buscar vira consultar uma lista pronta. Um exemplo pequeno, com três narrativas de uma frase cada e a lista invertida montada a partir delas, ajuda muito o leitor (pode virar um quadro);
3. **tokenização:** quebrar o texto em palavras, passar para minúsculas e, opcionalmente, remover acentos. Explique por que isso resolve o problema "irmao/irmão" e o problema "rei/freira" (no índice invertido, "freira" é uma palavra e "rei" é outra);
4. **radicalização** (*stemming*): reduzir "irmãos" e "irmão" a um mesmo radical. Diga que existe para o português, mas que o FTS5 só oferece a versão para o inglês (o `porter`). Isso prepara o resultado sobre plurais;
5. **ordenação por relevância:** o que o BM25 leva em conta (quantas vezes o termo aparece, em quantas narrativas ele aparece, o tamanho do texto), explicado em palavras, sem a fórmula;
6. por fim, apresente o **FTS5** do SQLite em um parágrafo.

### 2.4 Avaliação de sistemas de busca (cerca de 1 página)

**Pesquise:** o capítulo 8 do livro de Manning, Raghavan e Schütze (seções 8.1 a 8.4: avaliação, precisão, revocação e precisão nos *k* primeiros) e a parte de avaliação do Baeza-Yates e Ribeiro-Neto.

**Escreva:**

- que avaliar uma busca não é só medir velocidade: uma busca instantânea que traz resultados errados não serve;
- o que é **precisão** (do que a busca trouxe, quanto prestava) e **revocação** (do que prestava, quanto a busca trouxe);
- o que é **P@10** (precisão nos 10 primeiros): dos dez primeiros resultados, quantos prestavam. Explique por que ela é a métrica do seu trabalho: ninguém olha a quinta página de uma busca;
- o que é um **julgamento de relevância** (decidir, para cada resultado, se ele serve ou não) e a técnica de ***pooling***: como não dá para julgar 1.000 narrativas à mão, juntam-se os primeiros resultados de todas as estratégias e julga-se só esse conjunto.

### 2.5 Trabalhos relacionados (cerca de 1,5 página)

**Pesquise:** trabalhos que tenham **comparado** estratégias de busca em banco de dados, ou avaliado busca em acervos e bibliotecas digitais, ou busca textual em português. Onde procurar:

- **SBC OpenLib** (`sol.sbc.org.br`): procure nos anais do Simpósio Brasileiro de Banco de Dados (SBBD) e da Escola Regional de Computação do seu estado;
- **BDTD** (`bdtd.ibict.br`) e o **Memoria**, repositório institucional do IFRN (`memoria.ifrn.edu.br`): TCCs e dissertações;
- **Google Acadêmico** e **SciELO**.

Termos úteis: "full-text search desempenho", "comparação busca textual banco de dados", "LIKE versus full-text", "busca textual português", "recuperação da informação acervo digital".

**Escreva:** **3 trabalhos**, um parágrafo cada, dizendo o que foi comparado, **como foi medido** (esta é a informação que mais interessa) e quais as limitações. Feche com um **quadro comparativo** entre esses trabalhos e o seu, com as colunas: estratégias comparadas; banco usado; volumes testados; mediu tempo?; mediu qualidade?; testou acentos em português?

**Esse quadro é a justificativa do seu trabalho.** O seu diferencial provavelmente vai aparecer nas duas últimas colunas: a **avaliação conjunta de tempo e de qualidade** e o **teste específico de acentos e plurais em português**.

### Entrega

- [ ] Seções 2.3, 2.4 e 2.5 escritas, com citações.
- [ ] Quadro dos trabalhos relacionados, com identificação em cima e fonte embaixo.
- [ ] As obras novas lançadas nas Referências e fichadas.
- [ ] Comentários da Entrega 2 resolvidos.
- [ ] Versão nomeada: `Entrega 3 - Referencial 2.3 a 2.5 - 12/11`.
- [ ] Comentário na *issue*, marcando os orientadores, e card em **Em revisão**.

---

# Sprint 5: 13/11 a 19/11/2026

<a id="sprint-5-dev"></a>
## Sprint 5 · Desenvolvimento: medição oficial, consolidação e matriz de acentos

**Branch:** `feature/medicao-oficial` · **No PR:** `Closes #9`

**O que você vai entregar:** a **rodada oficial** de medições (os números que vão para o TCC), a tabela consolidada dos tempos e a matriz que mostra como cada estratégia lida com acentos, maiúsculas e plurais.

### Passo a passo

**1. Atualize a `develop` e crie a *branch*** `feature/medicao-oficial`.

**2. Faça a rodada oficial, logo no primeiro dia.** Ela tem de acontecer em condições controladas, e é ela que o TCC vai citar:

1. use **a mesma máquina** descrita em `docs/ambiente.md`. Se tiver de usar outra, atualize o `ambiente.md` antes de medir;
2. **reinicie o computador** e, depois de entrar, não abra nada além do terminal: nem navegador, nem VS Code (edite pelo Bloco de Notas se precisar);
3. rode, na ordem:

   ```
   python scripts\01_gerar_base.py --volume 100
   python scripts\01_gerar_base.py --volume 1000
   python scripts\01_gerar_base.py --volume 10000
   python scripts\02_preparar_estrategias.py
   python testes\verificar_bases.py
   python testes\verificar_buscas.py
   python scripts\03_medir.py --rodada oficial
   ```

4. anote no diário a data, a hora de início e de fim, e qualquer coisa estranha (o antivírus abriu uma janela, o computador travou um momento).

As bases são geradas de novo com a mesma semente, então são exatamente as mesmas das sprints anteriores: confira se as assinaturas batem com o `resultados/geracao.md`. O `custos.csv` gerado nesta execução é o **oficial**.

> **Se precisar repetir a rodada oficial** (faltou energia, o computador travou), não apague as linhas da primeira tentativa: rode de novo e anote o motivo no diário. O programa do passo 3 usa só a rodada oficial **mais recente**.

**3. Escreva `scripts/05_consolidar.py`.** Ele transforma as milhares de linhas do `tempos.csv` em uma tabela que cabe no TCC.

1. leia `resultados/tempos.csv` com `csv.DictReader` e fique só com as linhas em que `rodada` é `oficial` **e** a `data` é a mais recente entre as oficiais (*pesquise:* `max` em uma lista de textos no formato `2026-11-13`, que funciona porque a data está no formato ano-mês-dia);
2. agrupe os tempos por estratégia e volume, em um dicionário cuja chave é uma tupla: `tempos[("E1", 1000)]` é a lista com todos os tempos da E1 na base de 1.000 (8 consultas × 10 repetições = 80 valores). *Pesquise:* `dict.setdefault` ou `collections.defaultdict(list)`;
3. para cada grupo, calcule com o módulo `statistics`: mediana (`median`), média (`mean`), desvio padrão (`stdev`), mínimo, máximo e a quantidade de medições;
4. calcule o **fator de crescimento**: a mediana na base de 1.000 dividida pela mediana na de 100, e a mediana na de 10.000 dividida pela de 1.000. É o número mais importante da tabela: **se o tempo multiplica por 10 quando a base multiplica por 10, a estratégia cresce junto com o acervo** (ruim); se quase não muda, ela aguenta o crescimento (bom);
5. grave `resultados/tempos_consolidados.csv`:

   ```
   estrategia,volume,n,mediana_ms,media_ms,desvio_ms,minimo_ms,maximo_ms,fator_crescimento
   ```

   (na base de 100, o fator fica vazio);
6. grave também `resultados/tempos_por_consulta_10000.csv`, com a mediana de cada consulta em cada estratégia, só na base de 10.000 (uma linha por consulta e uma coluna por estratégia). Ela mostra se alguma consulta se comporta diferente das outras;
7. no fim, mostre na tela quantas vezes a E3 foi mais rápida que a E1 na base de 10.000 (mediana da E1 dividida pela mediana da E3).

**4. Escreva `scripts/06_matriz_acentos.py`.** Esta é uma das tabelas mais interessantes do TCC. A pergunta é: **quando a pessoa digita a palavra de um jeito diferente do que está no texto, cada estratégia ainda encontra as narrativas?**

O programa usa a base de 1.000 e quatro bancos: os da E1, E2 e E3 e um quarto, que o próprio programa cria no começo:

- **E3-SA** (FTS5 **s**em remoção de **a**centos): copie `base_1000.db` para `bancos/e3sa_1000.db` e crie a tabela de busca igual à da E3, mas com `tokenize = "unicode61 remove_diacritics 0"`. Ela serve para mostrar que é o `remove_diacritics` que faz a diferença. Como a tabela tem o mesmo nome (`narrativa_fts`), a busca nela é feita com a própria `buscar_e3`.

Escolha **3 palavras** do corpus (confira cada uma com o `contar_termo.py`):

1. a palavra da sua consulta C2 (por exemplo, `irmão`);
2. uma palavra terminada em "ão" cujo plural termina em "ões", com as duas formas presentes no corpus (por exemplo, `coração` e `corações`, `leão` e `leões`, `ladrão` e `ladrões`);
3. uma palavra com acento agudo ou circunflexo (por exemplo, `príncipe` ou `pássaro`).

Para cada palavra, monte 5 variantes à mão, em uma lista no começo do programa:

```python
CASOS = [
    # (palavra, variante, o que é digitado)
    ("irmão", "como no texto", "irmão"),
    ("irmão", "sem acento", "irmao"),
    ("irmão", "maiúsculas", "IRMÃO"),
    ("irmão", "inicial maiúscula", "Irmão"),
    ("irmão", "plural", "irmãos"),
    # ... as outras duas palavras
]
```

Se o seu corpus tiver alguma palavra na grafia antiga (por exemplo, `princeza`), acrescente um sexto caso só para ela: a palavra digitada na grafia atual (`princesa`).

Para cada caso e cada estratégia (E1, E2, E3, E3-SA), registre **quantas narrativas foram encontradas** (o tamanho da lista devolvida). Grave em `resultados/matriz_acentos.csv`:

```
palavra,variante,busca,E1,E2,E3,E3_SA
```

e mostre a tabela na tela.

**5. Leia a matriz e anote no diário o que ela mostra.** Os achados esperados (confira cada um nos seus números, em vez de supor):

- **acentos:** a E1 e a E2 não encontram nada ao buscar "irmao", porque para o `LIKE` "a" e "ã" são letras diferentes. A E3 encontra as mesmas narrativas da busca com acento. A E3-SA se comporta como a E1: **é o `remove_diacritics` que resolve**;
- **maiúsculas:** o `LIKE` do SQLite só ignora maiúsculas nas letras sem acento (as do alfabeto inglês). "Irmão" funciona (o "I" é igualado ao "i"), mas "IRMÃO" não, porque o "Ã" não é igualado ao "ã". A E3 encontra as três formas;
- **plurais:** **nenhuma** estratégia trata plural em português de verdade. Repare em um detalhe: no `LIKE`, a busca pelo singular "irmão" encontra também "irmãos", porque "irmão" é um pedaço de "irmãos". Mas a busca por "corações" não encontra "coração", e a busca por "coração" não encontra "corações". Na E3, cada forma só encontra a si mesma, porque o índice guarda palavras inteiras.

**Essas limitações não são falhas do trabalho: são o resultado dele.** Elas mostram exatamente onde cada tecnologia para, e é isso que a equipe do Narrativas precisa saber antes de escolher.

**6. Atualize o `README.md`**, escreva o diário, faça os *commits* (inclua o `tempos.csv` com a rodada oficial) e abra o PR com `Closes #9`. Em **Evidências de teste**, cole a saída das duas verificações, a tabela consolidada e a matriz.

### Como saber que deu certo

- O `tempos.csv` tem 720 linhas novas com `rodada` igual a `oficial` (3 volumes × 3 estratégias × 8 consultas × 10 repetições).
- O `tempos_consolidados.csv` tem 9 linhas, com o fator de crescimento nas de 1.000 e 10.000.
- O `matriz_acentos.csv` tem 15 linhas (ou 16, com o caso da grafia antiga), com números nas quatro colunas de estratégia.
- Você consegue explicar, em voz alta, cada um dos três achados do passo 5.

### Entrega da sprint

- [ ] Rodada oficial feita nas condições do passo 2, com data e horários no diário.
- [ ] `resultados/custos.csv` da rodada oficial.
- [ ] `scripts/05_consolidar.py` gerando `tempos_consolidados.csv` (com fator de crescimento) e `tempos_por_consulta_10000.csv`.
- [ ] `scripts/06_matriz_acentos.py` com a E3-SA e as 3 palavras × 5 variantes, gerando `matriz_acentos.csv`.
- [ ] Os achados da matriz anotados no diário.
- [ ] `README.md` atualizado.
- [ ] PR aberto para a `develop`, com `Closes #9`.

### Erros comuns

- **`statistics.StatisticsError`:** algum grupo ficou vazio. Confira se o filtro da rodada e da data está certo (mostre na tela quantas linhas sobraram depois do filtro).
- **Todos os números da coluna E3 iguais aos da E3-SA:** o `e3sa_1000.db` foi criado com `remove_diacritics 2`. Apague o arquivo e rode de novo.

<a id="sprint-5-escrita"></a>
## Sprint 5 · Escrita: Metodologia (Entrega 4)

**Prazo: 19/11/2026**

Como o trabalho foi feito. **Verbos no passado e linguagem impessoal** ("foi realizado", "realizou-se"). De 5 a 6 páginas. A seção 3.6 descreve algo que você só vai fazer na Sprint 6: escreva-a no futuro e passe para o passado na Sprint 8.

**Pasta com metodologias prontas para consulta:** https://drive.google.com/drive/folders/1OwAjk47aQWuRKLf-ktesizSax9csEtXO?usp=sharing

### 3.1 Classificação da pesquisa

**Pesquise:** Gil (2017) e Prodanov e Freitas (2013), com as referências completas em `docs/orientacoes_escrita_tcc.md`. Leia os capítulos de classificação antes de escrever; não classifique de ouvido.

**Escreva** a classificação pelos quatro critérios, **justificando cada uma** com uma frase ligada ao seu trabalho (o erro mais comum é só listar os rótulos):

- **natureza:** aplicada, porque o resultado responde a uma decisão concreta do projeto Narrativas;
- **objetivos:** exploratória e descritiva, porque investiga uma questão ainda não respondida neste contexto e descreve o comportamento medido das estratégias;
- **abordagem:** quantitativa, porque os resultados são números (tempos, tamanhos, contagens, P@10);
- **procedimentos:** pesquisa bibliográfica combinada com **pesquisa experimental**: as mesmas consultas foram executadas sobre a mesma base, nas mesmas condições, variando apenas a estratégia.

### 3.2 Etapas do trabalho

**Escreva** as etapas em ordem, com uma **figura com o fluxo** (faça no `app.diagrams.net`, que funciona no navegador; identificação em cima, centralizada, e fonte embaixo):

1. levantamento bibliográfico;
2. montagem do corpus de contos em domínio público;
3. geração das bases de teste em três volumes;
4. definição das consultas e do protocolo de medição;
5. implementação das três estratégias;
6. medição do tempo e do custo;
7. avaliação do comportamento com acentos, maiúsculas e plurais;
8. avaliação da qualidade dos resultados;
9. consolidação dos resultados e elaboração da recomendação.

Diga também onde o código e os dados estão: no repositório `https://github.com/nicifrn/mp_narrativas_buscador`.

### 3.3 Materiais e ambiente de execução

Vale a analogia da receita de bolo das orientações de escrita: **lista de ingredientes**. Para **cada** item, escreva **o que é** (uma ou duas frases, com referência; a documentação oficial serve), **para que foi usado** e **por que foi escolhido**. Escrever só "foi utilizado Python" não vale nada.

| Item | O que dizer além da versão |
|---|---|
| Python 3 | linguagem dos programas; é a linguagem da plataforma Narrativas |
| SQLite (módulo `sqlite3`) | banco embutido, que já vem com o Python e não exige servidor; usado nas três estratégias |
| FTS5 | recurso de busca em texto completo do SQLite; qual tokenizador e qual opção de acentos |
| `matplotlib` | geração dos gráficos |
| Módulos `csv`, `statistics`, `hashlib`, `random`, `argparse` | da biblioteca padrão: planilhas, estatística, verificação de textos repetidos, sorteio com semente e parâmetros dos programas |
| VS Code e Git/GitHub | editor e versionamento |

**O ambiente de execução, sem o qual nada é replicável:** processador, memória RAM, tipo de disco, sistema operacional e versões, copiados do `docs/ambiente.md`. Diga que as medições foram feitas com todos os outros programas fechados e informe a data da rodada oficial.

**Declare também o que não foi usado e por quê** (a [seção 3](#decisoes) tem as justificativas): MySQL, Django e motores de busca dedicados.

### 3.4 Corpus e bases de teste

**Escreva:**

- **o corpus:** quantos contos, de que obra, de que edição, por que estão em domínio público (cite a Lei nº 9.610/1998), como foram escolhidos e limpos, e que a grafia original foi mantida. A planilha `corpus/origem.csv` pode virar um quadro resumido (ou ir para um apêndice);
- **a geração das bases:** por que recombinar parágrafos, e não copiar textos (copiar distorceria a medição, porque o índice se comporta de forma diferente com textos repetidos); a faixa de 2.000 a 8.000 caracteres; a **semente fixa** e por que ela garante que qualquer pessoa obtém a mesma base; a **comprovação de que não há textos repetidos**, pelo código SHA-256, com o número de textos distintos (está no `resultados/geracao.md`).

### 3.5 Estratégias comparadas e protocolo de medição

**Escreva:**

- **as três estratégias**, uma por parágrafo, **com a consulta SQL usada** e o que foi criado no banco (nada, dois índices com `COLLATE NOCASE`, a tabela FTS5 com `unicode61 remove_diacritics 2`). Mostrar a consulta é informação que dá para repetir; dizer "foi implementada a busca" não é. Justifique o `COLLATE NOCASE` (dar ao índice a melhor chance) e declare a duplicação do texto no banco da E3;
- **por que o experimento foi feito em SQL puro:** o `icontains` do Django gera a mesma consulta da E1;
- **as consultas de teste:** as 8 consultas, o que cada uma testa e como foram escolhidas. A lista completa vai para o **Apêndice A**;
- **o protocolo,** em prosa, a partir do `docs/protocolo.md`: os três volumes; 3 execuções de aquecimento descartadas e 10 medições válidas por consulta; o uso de `time.perf_counter()`; a leitura completa do resultado (`fetchall`) antes de parar o cronômetro; a mediana nas comparações, com a média e o desvio padrão também relatados; o fator de crescimento.

**Justifique, não apenas declare.** Por que descartar o aquecimento? Por que dez repetições? Por que mediana? Por que ler o resultado até o fim? Cada uma dessas frases mostra que você entendeu o que estava fazendo, e é isso que separa um experimento de um punhado de números.

### 3.6 Avaliação da qualidade dos resultados

**Escreva** (no futuro, por enquanto):

- que a qualidade será avaliada na base de 1.000 narrativas, pela métrica P@10;
- como o conjunto julgado será montado: os 10 primeiros resultados de cada estratégia, para cada consulta, reunidos sem repetição e **embaralhados**, sem mostrar de qual estratégia veio cada um (*pooling* com avaliação cega);
- **o critério de relevância**, escrito antes do julgamento (está no passo 1 da Sprint 6);
- que o julgamento será feito pelo autor, e que isso é uma limitação, reduzida pelo critério objetivo e pela avaliação cega;
- que a consulta C8 fica fora da avaliação de qualidade, porque não há resposta certa para ela.

### Entrega

- [ ] Seções 3.1 a 3.6 escritas, com a figura do fluxo.
- [ ] As consultas SQL das três estratégias no texto.
- [ ] Ambiente de execução completo, com a data da rodada oficial.
- [ ] Apêndice A com as 8 consultas.
- [ ] Comentários da Entrega 3 resolvidos.
- [ ] Versão nomeada: `Entrega 4 - Metodologia - 19/11`.
- [ ] Comentário na *issue*, marcando os orientadores, e card em **Em revisão**.

---

# Sprint 6: 20/11 a 26/11/2026

<a id="sprint-6-dev"></a>
## Sprint 6 · Desenvolvimento: qualidade dos resultados

**Branch:** `feature/qualidade` · **No PR:** `Closes #11`

**O que você vai entregar:** o julgamento de relevância feito e a métrica P@10 calculada para as três estratégias.

> **Atenção:** 20/11 (sexta, primeiro dia da sprint) é feriado. Comece na segunda.

### A ideia

Medir velocidade é fácil. Medir **qualidade** exige saber, para cada busca, quais narrativas **deveriam** aparecer. Esse "deveria" é o julgamento de relevância, e é você quem o faz, olhando os textos.

Julgar as 1.000 narrativas para cada consulta é impossível. Por isso você vai usar a técnica padrão da área, o ***pooling***: juntar os 10 primeiros resultados de cada estratégia, para cada consulta, e julgar só esse conjunto. São no máximo 7 consultas × 3 estratégias × 10 resultados, mas, como muitos resultados se repetem entre as estratégias, na prática sobra bem menos.

### Passo a passo

**1. Atualize a `develop`, crie a *branch*** `feature/qualidade` **e escreva o critério de relevância antes de julgar qualquer coisa.** Acrescente ao `docs/protocolo.md` uma seção "Critério de relevância", com este critério:

> Uma narrativa é **relevante** (1) para uma consulta se o seu título ou o seu texto contém a palavra procurada **como palavra inteira**, no singular ou no plural, com ou sem acento, em maiúsculas ou minúsculas, com o sentido procurado. Não é relevante (0) se a sequência de letras aparece só **dentro de outra palavra** (por exemplo, "rei" dentro de "freira", "direito" ou "primeiro").

E acrescente dois exemplos tirados do seu corpus, um relevante e um não relevante. **Por que escrever antes?** Se você definir o critério depois de ver os resultados, acaba criando uma régua que favorece uma das estratégias. Isso se chama **viés**, e invalida a avaliação. **Depois do primeiro *commit* desta seção, o critério não muda mais.**

**2. Escreva `scripts/07_julgar.py`.** Ele monta a lista do que precisa ser julgado e mostra, uma por uma, as narrativas para você dar a nota.

*Parte A: montar a lista.*

1. leia as consultas de `docs/consultas.csv`, deixando de fora a C8;
2. conecte nos bancos `e1_1000.db`, `e2_1000.db` e `e3_1000.db`, e também na `base_1000.db` (de onde vai ler os textos);
3. para cada consulta e cada estratégia, pegue os 10 primeiros resultados: `buscar_e1(conexao, termo)[:10]`;
4. guarde cada resultado como o par `(conceito, id)` em um **conjunto**. O conceito, e não a consulta, porque C2, C3, C4 e C5 procuram o mesmo conceito: se a narrativa 532 é relevante para "irmão", ela é relevante também para "irmao" e "IRMÃO". Assim você julga cada par uma vez só;
5. transforme o conjunto em uma lista ordenada (`sorted`), fixe a semente com `random.seed(7)` e **embaralhe** a lista com `random.shuffle`. O embaralhamento faz com que você não saiba de qual estratégia veio cada item (avaliação cega), e a semente faz a ordem ser sempre a mesma.

*Parte B: retomar de onde parou.* O julgamento leva mais de uma sessão. Se o arquivo `resultados/julgamento.csv` já existir, leia os pares que já foram julgados e pule-os.

*Parte C: mostrar e perguntar.* Para cada par ainda não julgado:

1. leia o título e o texto da narrativa na `base_1000.db`;
2. encontre **todas as ocorrências** do conceito no texto, ignorando acentos e maiúsculas. Para isso, escreva uma função que "simplifica" um texto:

   ```python
   import unicodedata

   def simplificar(texto):
       # 1. decompor as letras acentuadas: unicodedata.normalize("NFD", texto)
       #    (o "ã" vira "a" seguido de um sinal "~" separado)
       # 2. jogar fora os sinais: manter só os caracteres c em que
       #    unicodedata.category(c) != "Mn"
       # 3. passar para minúsculas
       ...
   ```

   Aplique a função ao texto e ao conceito, e procure o conceito no texto simplificado com `str.find`, em um laço (*pesquise:* o segundo parâmetro do `find`, que diz a partir de onde procurar). Para os textos em português, o texto simplificado tem o mesmo tamanho do original, então as posições batem;
3. mostre na tela o número do item (`Item 12 de 87`), o conceito, o título e **até 5 trechos**, cada um com 60 caracteres antes e 60 depois da ocorrência, com a ocorrência entre colchetes:

   ```
   Item 12 de 87 | conceito: rei | narrativa 532
   Título: A lenda da raposa
     ...mandou chamar a [rei]ra do convento para ver o menino...
     ...e o [rei] disse que ninguem sairia do palacio antes de...
   Relevante? (1 = sim, 0 = não, s = sair):
   ```

4. leia a resposta com `input`. Aceite só `1`, `0` ou `s` (se vier outra coisa, pergunte de novo). Com `s`, o programa termina;
5. **grave a resposta na hora**, acrescentando uma linha em `resultados/julgamento.csv` (modo `"a"`), com as colunas `conceito,narrativa_id,relevante`. Assim, se o programa fechar no meio, nada se perde.

**3. Faça o julgamento.** Reserve duas sessões de uma hora. Siga o critério à risca, e quando ficar em dúvida, anote o caso no diário (número da narrativa, conceito e por que ficou em dúvida): os casos difíceis rendem um parágrafo nos Resultados. Anote também quanto tempo levou o julgamento inteiro.

**4. Escreva `scripts/08_qualidade.py`.**

1. leia o `julgamento.csv` para um dicionário: `julgamento[(conceito, id)] = 1 ou 0`. Cuidado: o `id` vem do CSV como texto; converta com `int`;
2. para cada consulta (menos a C8) e cada estratégia, pegue os 10 primeiros resultados na base de 1.000 e calcule:
   - `relevantes_top10`: quantos deles têm nota 1 no julgamento;
   - **P@10** = `relevantes_top10 / 10`;
3. grave `resultados/qualidade.csv`:

   ```
   consulta,estrategia,qtd_resultados,relevantes_top10,p_at_10
   ```

4. calcule o **P@10 médio** de cada estratégia (a média das 7 consultas) e grave em `resultados/qualidade_media.csv`.

Duas observações que vão para o TCC:

- **a divisão é sempre por 10**, mesmo quando a estratégia trouxe menos de 10 resultados. É a definição padrão: se a pessoa buscou "irmao" e a busca não trouxe nada, a busca falhou para ela, e o P@10 dessa consulta é zero;
- na consulta rara (C7), pode haver menos de 10 narrativas relevantes na base inteira. Então nenhuma estratégia chega a 1,0 nela. Como isso vale igualmente para as três, a comparação continua justa.

Se aparecer um `KeyError`, algum resultado não foi julgado: rode o `07_julgar.py` de novo, que ele mostra só o que falta.

**5. Atualize o `README.md`**, escreva o diário, faça os *commits* e abra o PR com `Closes #11`. Em **Evidências de teste**, cole a saída das verificações e o `qualidade_media.csv`.

### Como saber que deu certo

- O `julgamento.csv` tem uma linha para cada par do conjunto, e rodar o `07_julgar.py` de novo diz que não há nada pendente.
- O `qualidade.csv` tem 21 linhas (7 consultas × 3 estratégias).
- A E1 e a E2 têm o mesmo P@10 (elas devolvem os mesmos resultados, como a sua verificação da Sprint 4 já mostrou).
- Na consulta C6 ("rei"), a E1 traz resultados irrelevantes ("freira", "direito"), e a E3 não.

### Entrega da sprint

- [ ] Critério de relevância escrito no `docs/protocolo.md` **antes** do julgamento, com dois exemplos.
- [ ] `scripts/07_julgar.py` com *pooling*, embaralhamento com semente, retomada e gravação a cada resposta.
- [ ] Julgamento completo em `resultados/julgamento.csv`, com o tempo gasto e os casos de dúvida no diário.
- [ ] `scripts/08_qualidade.py` gerando `qualidade.csv` e `qualidade_media.csv`.
- [ ] `README.md` atualizado.
- [ ] PR aberto para a `develop`, com `Closes #11`.

<a id="sprint-6-escrita"></a>
## Sprint 6 · Escrita: colocar no documento as tabelas com os dados da Sprint 5

**O que você vai entregar:** o capítulo 4 montado no documento, com as tabelas e a figura da rodada oficial no lugar. Nesta semana não há entrega de capítulo, e não é para escrever a análise ainda: é para os números já estarem no texto quando a semana dos Resultados chegar.

### Passo a passo

**1. Monte a estrutura do capítulo 4** no documento, com os títulos de 4.1 a 4.9 (veja a [seção 8.3](#escrita-geral)).

**2. Coloque as tabelas**, cada uma na sua seção, com os números de `resultados/` (rodada oficial):

| Seção | Tabela ou figura | De onde vêm os números |
|---|---|---|
| 4.1 | Tabela: geração das bases (volume, textos distintos, tamanho) | `resultados/geracao.md` |
| 4.2 | Tabela: tempos por estratégia e volume (mediana, média, desvio padrão, mínimo, máximo, fator de crescimento) | `resultados/tempos_consolidados.csv` |
| 4.3 | Figura: os planos de execução da E2, com `%` no começo e por prefixo | o print `docs/evidencias/s04_planos.png` |
| 4.4 | Tabela: tamanho em disco e tempo de preparação por estratégia e volume | `resultados/custos.csv` |
| 4.5 | Tabela: matriz de acentos, maiúsculas e plurais | `resultados/matriz_acentos.csv` |

Regras para todas (estão em `docs/orientacoes_escrita_tcc.md`, na parte de tabelas e imagens):

- identificação **em cima**, centralizada (`Tabela 2 - Tempo de resposta por estratégia e volume da base`);
- fonte **embaixo** (`Fonte: elaborada pelo autor (2026).`);
- **vírgula** como separador decimal e o **mesmo número de casas decimais** na coluna inteira (use uma casa para milissegundos e para MB);
- unidade no título da coluna (`Mediana (ms)`).

**3. Embaixo de cada tabela, escreva uma frase só**, dizendo o que ela mostra ("A Tabela 2 apresenta os tempos de resposta das três estratégias nos três volumes da base."). A análise vem na Sprint 7.

**4. Resolva os comentários da Entrega 4 (Metodologia).**

### Entrega

- [ ] Estrutura do capítulo 4 no documento.
- [ ] As quatro tabelas e a figura no lugar, no padrão ABNT, com os números da rodada oficial.
- [ ] Uma frase de apresentação embaixo de cada uma.
- [ ] Comentários da Entrega 4 resolvidos.
- [ ] Versão nomeada: `Tabelas dos Resultados - 26/11`.

Para entregar, comente na *issue* marcando os orientadores e mova o card para **Em revisão**.

---

# Sprint 7: 27/11 a 03/12/2026

<a id="sprint-7-dev"></a>
## Sprint 7 · Desenvolvimento: caracterização da base, gráficos e protótipo

**Branch:** `feature/graficos-prototipo` · **No PR:** `Closes #13`

**O que você vai entregar:** a caracterização da base, os quatro gráficos do TCC e um protótipo de busca de linha de comando, usando a estratégia E3.

**Os gráficos têm de estar prontos até segunda-feira, 30/11**, porque os Resultados vencem na quinta e você precisa deles para escrever. Divida a semana assim:

| Dia | O que fazer |
|---|---|
| sexta, 27/11 | passo 2 (caracterização) |
| segunda, 30/11 | passo 3 (gráficos) |
| terça e quarta, 01 e 02/12 | passo 4 (protótipo) |
| quinta, 03/12 | passo 5 (README, diário e PR) |

### Passo a passo

**1. Atualize a `develop` e crie a *branch*** `feature/graficos-prototipo`.

**2. Escreva `scripts/09_caracterizar.py`.** Ele descreve a base, para mostrar ao leitor que ela não é artificial demais.

1. **Tabela de caracterização**, para cada volume: número de narrativas, total de palavras (*pesquise:* `len(texto.split())`), média e mediana do tamanho dos textos em caracteres, e número de cidades distintas. Grave em `resultados/caracterizacao.csv`;
2. **As 30 palavras mais frequentes** na base de 1.000, sem as palavras vazias. Para cada texto: passe para minúsculas, separe em palavras com `split()`, tire a pontuação das pontas de cada palavra com `strip(".,;:!?\"'()-")` e descarte as que estiverem na lista abaixo. Conte com `collections.Counter` e pegue as 30 primeiras com `most_common(30)`. Grave em `resultados/palavras_frequentes.csv`.

   ```python
   PALAVRAS_VAZIAS = {
       "a", "o", "e", "de", "do", "da", "dos", "das", "que", "um", "uma",
       "em", "no", "na", "nos", "nas", "para", "por", "com", "se", "não",
       "nao", "ao", "os", "as", "mas", "como", "lhe", "ele", "ella", "elle",
       "ela", "foi", "era", "seu", "sua", "me", "eu", "já", "mais", "quando",
   }
   ```

   (A lista tem "elle" e "ella" porque o corpus está na grafia de 1885. Se aparecerem outras palavras vazias na grafia antiga no topo da lista, acrescente-as e anote no diário.)
3. **Um histograma do tamanho dos textos** na base de 10.000, com `matplotlib`: `plt.hist(tamanhos, bins=30)`. Eixo horizontal: `Tamanho do texto (caracteres)`; eixo vertical: `Número de narrativas`. Salve em `graficos/g4_histograma_tamanhos.png`. Se todos os textos tivessem o mesmo tamanho, seria sinal de base mal gerada; o histograma mostra que não é o caso.

**3. Escreva `scripts/10_graficos.py`**, com os outros três gráficos. Use **sempre a mesma cor para a mesma estratégia**, em todos os gráficos:

```python
CORES = {"E1": "#c0392b", "E2": "#e67e22", "E3": "#2471a3"}
```

1. **G1, tempo mediano × volume** (`graficos/g1_tempo_volume.png`): uma linha com marcadores para cada estratégia, a partir do `tempos_consolidados.csv`. **Use escala logarítmica nos dois eixos** (`plt.xscale("log")` e `plt.yscale("log")`): sem isso, a E1 fica tão alta que a E3 vira uma linha colada no chão, e o gráfico não comunica nada. Nos rótulos dos eixos, avise da escala: `Volume da base (narrativas, escala logarítmica)` e `Tempo mediano (ms, escala logarítmica)`. Mostre os três volumes no eixo horizontal com `plt.xticks([100, 1000, 10000], ["100", "1.000", "10.000"])`;
2. **G2, tamanho em disco** (`graficos/g2_tamanho_disco.png`): barras com o tamanho de cada estratégia na base de 10.000, a partir do `custos.csv`. Eixo vertical: `Tamanho do banco (MB)`;
3. **G3, qualidade** (`graficos/g3_p_at_10.png`): barras com o P@10 médio de cada estratégia, a partir do `qualidade_media.csv`, com o eixo vertical de 0 a 1 (`plt.ylim(0, 1)`). Eixo vertical: `P@10 médio`.

Regras para todos os gráficos:

- eixos com nome e **unidade**;
- legenda identificando as estratégias (no G1); nos gráficos de barras, o nome da estratégia embaixo de cada barra basta;
- **sem título dentro da imagem**: na ABNT, o título vai na identificação acima da figura, no documento;
- salve em PNG com boa resolução: `plt.savefig(caminho, dpi=150, bbox_inches="tight")`, e depois `plt.close()`, para o gráfico seguinte começar limpo.

**4. Escreva `scripts/11_prototipo.py`**, um protótipo de busca de linha de comando que usa a E3 na base de 10.000. Ele repete até a pessoa apertar Enter sem digitar nada:

```
Buscar (Enter para sair): macaco

Encontrados 2871 resultados em 4,2 ms

 1. O caso do macaco
    ...e o [macaco] subiu na arvore e de la gritou para a onça que...
 2. A história do jabuti
    ...quando o [macaco] chegou, o jabuti ja estava sentado...
 ...
```

Peças que você vai usar:

- a quantidade de resultados: `SELECT COUNT(*) FROM narrativa_fts WHERE narrativa_fts MATCH ?`;
- os 10 primeiros, com o título e um **trecho do texto em volta do termo encontrado**, usando a função `snippet()` do FTS5:

  ```sql
  SELECT titulo, snippet(narrativa_fts, 1, '[', ']', '...', 12)
  FROM narrativa_fts
  WHERE narrativa_fts MATCH ?
  ORDER BY bm25(narrativa_fts)
  LIMIT 10
  ```

  Leia na documentação (`sqlite.org/fts5.html`, seção "The snippet() Function") o que é cada um dos parâmetros: a coluna (o `1` é a coluna `texto`, porque a contagem começa em 0), os marcadores em volta do termo, as reticências e o número de palavras do trecho;
- o termo entre aspas duplas, como na `buscar_e3`;
- o tempo das duas consultas juntas, com `time.perf_counter()`, mostrado com vírgula decimal (*pesquise:* `f"{tempo:.1f}".replace(".", ",")`).

Teste com as suas consultas, inclusive "irmao" sem acento e "helicóptero". Tire um print do protótipo funcionando e salve em `docs/evidencias/s07_prototipo.png`.

**O protótipo é ilustração, não é o trabalho.** Uma tela e meia página no TCC bastam. Não gaste tempo com interface gráfica nem com Flask: o valor do trabalho está nas medições.

**5. Atualize o `README.md`**, escreva o diário, faça os *commits* (inclua a pasta `graficos/`) e abra o PR com `Closes #13`. Em **Evidências de teste**, cole as verificações e os prints dos gráficos e do protótipo.

### Como saber que deu certo

- A pasta `graficos/` tem os quatro PNGs, sem título dentro da imagem, com eixos nomeados e com unidade.
- No G1, as três linhas aparecem separadas e legíveis, e dá para ver a E1 subindo e a E3 quase reta.
- O protótipo mostra os 10 primeiros resultados com o trecho destacado e o tempo, encontra "irmao" sem acento e diz que não encontrou nada para "helicóptero" sem dar erro.

### Entrega da sprint

- [ ] `scripts/09_caracterizar.py` gerando `caracterizacao.csv`, `palavras_frequentes.csv` e o histograma.
- [ ] `scripts/10_graficos.py` gerando G1, G2 e G3, com as cores fixas e as regras de formatação.
- [ ] Gráficos prontos até segunda-feira, 30/11.
- [ ] `scripts/11_prototipo.py` com contagem, tempo e trechos destacados, e o print em `docs/evidencias/`.
- [ ] `README.md` atualizado e diário da semana.
- [ ] PR aberto para a `develop`, com `Closes #13`.

<a id="sprint-7-escrita"></a>
## Sprint 7 · Escrita: Resultados e discussão (Entrega 5)

**Prazo: 03/12/2026**

O capítulo mais importante. Ele responde às **três perguntas** da Introdução, na ordem. As tabelas você já colocou na Sprint 6; agora entram os gráficos, os números do julgamento e, principalmente, a **discussão**. Discutir é mais do que apresentar: é dizer o que o número significa e por que ele saiu assim.

> **Regra sem exceção:** toda figura, tabela ou quadro é **anunciado no texto antes** de aparecer e **explicado depois**. Nunca duas figuras seguidas sem texto entre elas.

Escreva as seções 4.1 a 4.7 e a 4.9. A 4.8 (Recomendação) fica para a Sprint 8.

### 4.1 A base de teste

Curta: a tabela de caracterização (`caracterizacao.csv`), o histograma (G4) e a tabela de geração. **Informe que não há textos repetidos**, com o número de textos distintos, e que a base é reproduzível (mesma assinatura em execuções diferentes). É uma frase, mas é ela que sustenta a validade de tudo o que vem depois. Comente também as palavras mais frequentes, se alguma chamar a atenção (por exemplo, a grafia antiga).

### 4.2 Tempo de resposta

A primeira pergunta. A tabela de tempos e o gráfico G1.

**Discuta:**

- **como cada estratégia se comporta quando a base cresce.** Use o fator de crescimento para dizer isso com número: se o tempo da E1 multiplica por cerca de 10 quando a base multiplica por 10, e o da E3 quase não muda, isso responde à pergunta;
- **quantas vezes a E3 é mais rápida que a E1** na base de 10.000;
- **a partir de que volume a diferença começa a importar.** Se com 100 narrativas todas são rápidas o bastante, diga isso: é uma informação honesta e útil (para um acervo pequeno, a solução simples basta);
- se alguma consulta se comportou diferente das outras (`tempos_por_consulta_10000.csv`), e por quê. Por exemplo: na E3, a consulta sem resultados (C8) costuma ser a mais rápida de todas.

### 4.3 Por que o índice não ajudou

Merece uma seção própria, porque é o achado mais didático do trabalho. A figura dos planos de execução, já no documento.

**Explique o mecanismo, não só o resultado:** o índice organiza os valores pelo começo, e uma busca que começa com o curinga `%` não tem por onde entrar nele, então o banco percorre tudo (`SCAN`). Mostre o contraste com a busca por prefixo, em que o índice é usado (`SEARCH`). Retome o que você fundamentou na seção 2.2.

**Feche com a conclusão prática:** é exatamente essa limitação que justifica a existência da busca em texto completo. Essa frase liga a seção ao resto do trabalho.

### 4.4 Custo em disco e de preparação

A tabela de custos e o gráfico G2. **Discuta:** quanto cada estratégia aumentou o banco, em MB e em porcentagem em relação à E1; quanto tempo levou para preparar; e o caso da E2, que **custou espaço e tempo sem trazer benefício**. Lembre a duplicação do texto no banco da E3 (declarada na Metodologia) e diga que parte do tamanho vem dela.

### 4.5 Acentos, maiúsculas e plurais

A segunda pergunta, a mais específica do português. A matriz de acentos.

**Discuta os três achados** (os que você anotou no diário na Sprint 5):

- **acentos:** a E3 encontra "irmão" quando se digita "irmao", e a E1 e a E2 não. Mostre, com a coluna da E3-SA, que é o `remove_diacritics` que faz a diferença: é uma configuração, e não a tecnologia em si;
- **maiúsculas:** o `LIKE` do SQLite só iguala maiúsculas e minúsculas nas letras sem acento ("Irmão" funciona, "IRMÃO" não);
- **plurais:** **nenhuma** estratégia trata plural em português. Explique o detalhe do singular dentro do plural no `LIKE`, e que o FTS5 oferece um tratamento de plural (o `porter`), mas para o inglês. **Como essa limitação é comum a todas, a solução não é escolher outra estratégia, e sim tratar o problema de outra forma** (trabalho futuro).

Traduza para o problema real: uma pessoa que digita "corações" no portal não encontraria as narrativas que dizem "coração". Esse é o impacto concreto. Se tiver o caso da grafia antiga, comente-o aqui: é um problema real de acervos de textos antigos.

### 4.6 Qualidade dos resultados

A terceira pergunta. Uma tabela com o P@10 por consulta e estratégia (`qualidade.csv`) e o gráfico G3.

**Discuta:**

- qual estratégia teve o melhor P@10 médio;
- **a consulta C6 ("rei")**: a E1 e a E2 trazem narrativas com "freira" e "direito", e a E3 não, porque o índice invertido trabalha com palavras inteiras. É o exemplo mais claro de diferença de qualidade;
- **as consultas C3 e C4** (sem acento e em maiúsculas): a E1 e a E2 têm P@10 zero porque não trazem nada;
- **a ordenação por relevância:** a E3 ordena pelo BM25, e a E1 e a E2 devolvem na ordem da tabela. Comente se isso apareceu nos seus números;
- informe quantos pares foram julgados, quanto tempo levou e os casos em que você ficou em dúvida.

### 4.7 O protótipo

Meia página: o print do protótipo funcionando, com o tempo e os trechos destacados visíveis, e uma frase dizendo que ele mostra como a E3 ficaria do ponto de vista de quem busca. Não gaste mais espaço do que isso.

### 4.9 Limitações do trabalho

Subseção curta e honesta. Reconhecer limite aumenta a confiança no trabalho:

- a base foi **gerada por recombinação** de parágrafos, e não é um acervo real;
- o corpus veio de **uma única obra**, de 1885, com grafia antiga;
- o **julgamento de relevância foi feito pelo próprio autor**, ainda que às cegas e com critério escrito antes;
- a qualidade foi avaliada **só nos 10 primeiros resultados** e só na base de 1.000;
- as medições foram feitas em **uma única máquina** e **só no SQLite**;
- o maior volume testado foi de **10.000 narrativas**.

Depois de listar, acrescente o argumento que sustenta o trabalho: como o estudo é **comparativo**, essas limitações valem igualmente para as três estratégias, nas mesmas condições.

### Entrega

- [ ] Seções 4.1 a 4.7 e 4.9 escritas, com os quatro gráficos e as tabelas.
- [ ] As três perguntas respondidas, com número, nas seções 4.2, 4.5 e 4.6.
- [ ] Toda figura e tabela anunciada antes e explicada depois.
- [ ] Comentários das entregas anteriores resolvidos.
- [ ] Versão nomeada: `Entrega 5 - Resultados - 03/12`.
- [ ] Comentário na *issue*, marcando os orientadores, e card em **Em revisão**.

---

# Sprint 8: 04/12 a 10/12/2026

<a id="sprint-8-dev"></a>
## Sprint 8 · Desenvolvimento: recomendação, README e fechamento

**Branch:** `feature/fechamento` · **No PR:** `Closes #15`

**O que você vai entregar:** a recomendação técnica para a equipe do Narrativas, o `README.md` completo e a prova de que o trabalho inteiro roda do zero, seguindo o README.

### Passo a passo

**1. Atualize a `develop` e crie a *branch*** `feature/fechamento`.

**2. Escreva `docs/recomendacao.md`**, em uma página, **para a equipe de desenvolvimento do Narrativas** (escreva para quem vai programar, não para a banca):

- qual estratégia adotar e por quê, em três frases e com os números principais;
- **com quais configurações:** o tokenizador e a opção de acentos, quais campos indexar (título e texto) e o cuidado de colocar o termo digitado entre aspas antes do `MATCH`;
- **a partir de qual tamanho de acervo ela compensa.** Se com 100 narrativas todas são rápidas o bastante, dizer isso é honesto e útil;
- quanto ela custa em espaço em disco e em tempo de preparação;
- **o que ainda fica por resolver:** plurais em português, a duplicação do texto (opção `content=`), volumes acima de 10.000 e a verificação equivalente no MySQL (o índice FULLTEXT), que é o banco do portal;
- as limitações do que foi medido.

Termine com o **quadro-resumo**, que é a figura mais útil do trabalho:

| Estratégia | Tempo mediano com 10.000 (ms) | Crescimento de 1.000 para 10.000 | P@10 médio | Ordena por relevância? | Encontra sem acento? | Tamanho com 10.000 (MB) | Recomendada? |
|---|---|---|---|---|---|---|---|
| E1 | | | | Não | | | |
| E2 | | | | Não | | | |
| E3 | | | | Sim | | | |

**3. Complete o `README.md`.** Ele precisa permitir que outra pessoa repita tudo:

- o que é o trabalho e a que projeto pertence;
- responsáveis;
- pré-requisitos (Python com a versão) e instalação (`pip install -r requirements.txt`);
- **a ordem dos programas, numerada**, com uma linha explicando o que cada um faz, o que ele gera e **quanto tempo demora** (anote os tempos na reprodução do passo 4);
- quanto espaço em disco é preciso (some o tamanho da pasta `bancos/`: botão direito → Propriedades);
- de onde veio o corpus e qual a situação de direitos autorais;
- a máquina onde as medições oficiais foram feitas (aponte para `docs/ambiente.md`) e a data da rodada oficial;
- onde estão os resultados (`resultados/` e `graficos/`).

**4. Rode tudo do zero, em uma pasta limpa, seguindo só o README.** Esta é a prova final de que o trabalho é reproduzível:

```
cd %USERPROFILE%
git clone https://github.com/nicifrn/mp_narrativas_buscador.git teste_reproducao
cd teste_reproducao
git checkout feature/fechamento
```

Crie o ambiente virtual, instale as dependências e rode cada programa na ordem do README (na medição, use `--rodada reproducao`). Confira:

- as assinaturas das bases batem com as do `resultados/geracao.md`?
- as duas verificações terminam com `Tudo certo`?
- algum programa deu erro ou dependia de algo que não está no README?

Se algo falhar, **corrija na sua pasta de trabalho** (não na `teste_reproducao`), faça o *commit* e repita. Quando tudo rodar, anote no diário e **apague a pasta `teste_reproducao`**: ela não vai para o repositório.

**5. Organize o código:**

- cada programa com um comentário no topo dizendo o que faz, como rodar e o que gera;
- sem código morto (trechos comentados que não servem mais) e sem `print` de depuração esquecido;
- sem caminho fixo da sua máquina (`C:\Users\...`) dentro do código.

**6. Confira o que foi para o repositório:** `git ls-files` não pode listar nenhum arquivo `.db`, nem nada de `.venv/`.

**7. Escreva o diário da última sprint**, faça os *commits* e abra o PR com `Closes #15`. Depois da aprovação, os orientadores levam a `develop` para a `main` e registram a versão final.

### Como saber que deu certo

- Outra pessoa, lendo só o `README.md`, conseguiria rodar tudo na ordem.
- A reprodução em pasta limpa funcionou, com as mesmas assinaturas.
- `docs/recomendacao.md` tem o quadro-resumo preenchido com os números da rodada oficial.

### Entrega da sprint

- [ ] `docs/recomendacao.md` com a recomendação e o quadro-resumo.
- [ ] `README.md` completo, com a ordem dos programas e o tempo de cada um.
- [ ] Reprodução do zero feita em pasta limpa, anotada no diário.
- [ ] Código organizado, sem caminho fixo e sem código morto.
- [ ] Nenhum `.db` nem `.venv/` no repositório.
- [ ] PR aberto para a `develop`, com `Closes #15`.

<a id="sprint-8-escrita"></a>
## Sprint 8 · Escrita: Recomendação, Conclusão, Objetivos específicos, Resumo e Título (Entrega 6)

**Prazo: 10/12/2026** · **Conclusão pronta até segunda-feira, 07/12**

### Antes de tudo: atualize o que mudou

- passe para o passado o que foi escrito no futuro: o bloco 4 da Introdução e a seção 3.6 da Metodologia;
- confira se todos os números do texto são **exatamente** os da rodada oficial e do `qualidade.csv`.

### 4.8 Recomendação para o projeto Narrativas

O quadro-resumo do `docs/recomendacao.md`, como quadro do TCC, e a recomendação em um ou dois parágrafos diretos: qual estratégia adotar, com quais configurações, a partir de qual tamanho de acervo ela compensa e o que ainda ficaria por resolver. **Este quadro é a contribuição prática do seu TCC**: é o que a equipe do Narrativas vai olhar.

### 5 Conclusão (cerca de 2 páginas)

Nada de resultado, conceito ou citação que não tenha aparecido antes. **Escreva, nesta ordem:**

1. **retomada do problema e do objetivo geral**, afirmando que ele foi alcançado **e dizendo por quê, com número** ("o objetivo foi alcançado, uma vez que a comparação mostrou que, com 10.000 narrativas, o tempo mediano variou de X ms, na E3, a Y ms, na E1, e o P@10 médio variou de Z a W");
2. **um comentário por objetivo específico**, na mesma ordem em que foram apresentados, cada um apontando o resultado que o comprova;
3. **a resposta às três perguntas** da Introdução, uma ou duas frases cada;
4. **contribuições:** uma base de teste construída e documentada, que outros trabalhos podem reaproveitar; a medição conjunta de tempo, custo e qualidade sobre a mesma base; a verificação de acentos e plurais em português; e uma recomendação técnica concreta para o projeto Narrativas;
5. **limitações e dificuldades:** retome brevemente as limitações (seção 4.9) e acrescente as dificuldades reais que você enfrentou, tiradas do `docs/diario.md`: a limpeza do corpus, a armadilha do `fetchall`, o julgamento de relevância;
6. **trabalhos futuros**, concretos e ligados ao que você encontrou:
   - implementar a busca recomendada no portal Narrativas (o principal);
   - repetir a comparação no MySQL, com o índice FULLTEXT;
   - tratar plurais em português;
   - evitar a duplicação do texto com a opção `content=` do FTS5;
   - testar volumes acima de 10.000 narrativas e a busca combinada com os filtros da tela (tipo, público, região);
   - avaliar motores de busca dedicados, quando o acervo justificar;
   - avaliar a busca com usuários reais do portal.

**Não escreva** que "a estratégia X é a melhor" sem dizer em qual critério e sobre qual base. E não generalize para "sistemas web" o que você mediu em um acervo de narrativas, um banco e uma máquina.

### 1.2 Objetivos específicos

Agora que o trabalho terminou, escreva o que foi **realmente alcançado**:

- de 4 a 5 itens, verbo no infinitivo, minúscula no início, ponto e vírgula no fim de cada um e ponto no último;
- na **mesma ordem** das etapas da Metodologia e das seções dos Resultados;
- cada um **verificável**: na Conclusão você mostrou, com número, que foi atingido;
- não confunda objetivo com tarefa ("instalar o matplotlib" não é objetivo específico).

O que os itens devem cobrir (redija com as suas palavras): revisar a literatura sobre acervos digitais, bancos de dados, índices e recuperação da informação; construir uma base de teste com contos em domínio público, em três volumes; implementar as três estratégias sobre a mesma base; medir o tempo, o custo, o comportamento com acentos e plurais e a qualidade dos resultados; recomendar como a busca do portal Narrativas deve ser implementada.

### Resumo, *Abstract* e palavras-chave

Escritos **por último**, com o texto todo pronto. Parágrafo único, de 150 a 500 palavras, linguagem impessoal, sem citações e sem menção a figuras ou tabelas (NBR 6028:2021). Uma ou duas frases para cada item:

1. **contexto e problema:** acervos digitais de narrativas populares e a dificuldade de encontrar informação neles quando o acervo cresce;
2. **objetivo;**
3. **método:** três estratégias de busca, três volumes de base, consultas definidas antes, medição de tempo, custo e qualidade;
4. **resultados:** os números principais;
5. **conclusão:** a recomendação.

**Coloque números no resumo.** Em um trabalho que mede coisas, resumo sem número é resumo fraco.

O ***Abstract*** é a versão em inglês. Os termos da área têm forma consagrada em inglês (*full-text search*, *inverted index*, *precision at 10*); use-os, e não a tradução literal. Não entregue tradução automática sem revisar.

**Palavras-chave:** de 3 a 5, separadas por ponto e vírgula, equilibrando o lado técnico e o cultural. Campo de ideias: busca textual; recuperação da informação; banco de dados; acervo digital; narrativas populares.

### Título

O título provisório é *"Avaliação de estratégias de busca textual em um acervo digital de narrativas populares"*. Ele funciona e pode ser refinado. Deve indicar a ação (avaliação ou comparação), o objeto (estratégias de busca textual) e o contexto (acervo de narrativas populares), e combinar com o objetivo geral. Se houver subtítulo, separe com dois-pontos. Proponha a versão final no comentário da *issue*.

### Revisão final

Além do checklist de `docs/orientacoes_escrita_tcc.md`:

- [ ] O objetivo geral, os objetivos específicos, as perguntas de pesquisa, as seções dos Resultados e os parágrafos da Conclusão estão na mesma ordem e falam das mesmas coisas?
- [ ] Todos os números do Resumo, dos Resultados e da Conclusão são **exatamente** os da rodada oficial? (Erro mais comum: mudar um número nos Resultados e esquecer de atualizar o Resumo.)
- [ ] Toda métrica que aparece nos Resultados (mediana, fator de crescimento, P@10) foi explicada antes?
- [ ] A origem e a situação de direitos autorais do corpus estão declaradas?
- [ ] Está comprovado, com número, que não há textos repetidos na base?
- [ ] O tokenizador do FTS5 e a opção de acentos estão informados?
- [ ] O critério de relevância está no texto, e está dito que foi definido antes do julgamento?
- [ ] O ambiente de execução está completo (máquina, sistema, versões, data da rodada oficial)?
- [ ] Toda tabela e figura é citada no texto antes de aparecer e explicada depois?
- [ ] Todas as tabelas e figuras têm identificação em cima, centralizada, e fonte embaixo?
- [ ] Os gráficos têm unidade nos eixos, e os rótulos avisam da escala logarítmica no G1?
- [ ] As limitações estão declaradas?
- [ ] As siglas (SQL, SGBD, FTS, BM25, IPHAN, UNESCO) foram escritas por extenso na primeira vez que aparecem?
- [ ] A numeração das seções está sem ponto depois do número ("2.1 Narrativas populares...")?
- [ ] O texto está impessoal e no passado?
- [ ] O Apêndice A (consultas de teste) está incluído?
- [ ] O endereço do repositório está no texto, na seção 3.2?
- [ ] Todos os comentários dos orientadores foram respondidos e resolvidos?

### Entrega

- [ ] Textos passados para o passado e números conferidos com a rodada oficial.
- [ ] Seção 4.8 e Conclusão escritas até 07/12.
- [ ] Objetivos específicos, Resumo, *Abstract*, palavras-chave e Título.
- [ ] Revisão final feita, item por item.
- [ ] Versão nomeada: `Entrega 6 - Versão final - 10/12`.
- [ ] Comentário na *issue*, marcando os orientadores, com a proposta de título, e card em **Em revisão**.

---

<a id="quadro-resumo"></a>
## 9. Quadro-resumo

| Sprint | Período | Desenvolvimento | O que você aprende | Escrita |
|---|---|---|---|---|
| 1 | 16/10 a 22/10 | Ambiente, repositório e corpus | Git, ambiente virtual, domínio público, UTF-8 | preparar documento e ler |
| 2 | 23/10 a 29/10 | As três bases de teste | funções, `argparse`, sorteio com semente, SHA-256, `executemany`, `assert` | Introdução e Objetivo geral |
| 3 | 30/10 a 05/11 | E1, E2 e o programa de medição | consulta parametrizada, injeção de SQL, índices, cronometragem, CSV | Referencial 2.1 e 2.2 |
| 4 | 06/11 a 12/11 | E3 (FTS5) e planos de execução | índice invertido, relevância, `EXPLAIN QUERY PLAN` | Referencial 2.3 a 2.5 |
| 5 | 13/11 a 19/11 | Medição oficial, consolidação e matriz | mediana, desvio padrão, fator de crescimento, acentos | Metodologia |
| 6 | 20/11 a 26/11 | Qualidade (P@10) | *pooling*, avaliação cega, critério definido antes | tabelas no documento |
| 7 | 27/11 a 03/12 | Caracterização, gráficos e protótipo | `Counter`, `matplotlib`, escala logarítmica, `snippet()` | Resultados |
| 8 | 04/12 a 10/12 | Recomendação, README e fechamento | síntese, reprodutibilidade | Recomendação, Conclusão, Resumo e Título |

### Relação entre o código e o texto

| Seção do TCC | Sprints que geram o conteúdo |
|---|---|
| Referencial Teórico | leituras das Sprints 1 a 4 |
| Metodologia | 1 (corpus, ambiente), 2 (bases), 3 (consultas e protocolo), 4 (estratégias) e 6 (critério de relevância) |
| Resultados | 2 (geração), 4 (planos), 5 (tempos, custos, matriz), 6 (qualidade) e 7 (caracterização, gráficos, protótipo) |
| Conclusão | `docs/diario.md` acumulado e `docs/recomendacao.md` |

**Nunca apague uma medição, não mude as consultas depois da Sprint 3 e não mude o critério de relevância depois de começar a julgar.** A confiabilidade do seu trabalho inteiro está nesses três lugares.

---

<a id="riscos"></a>
## 10. Riscos e planos B

| Risco | Sinal de alerta | O que fazer |
|---|---|---|
| FTS5 não disponível no Python da máquina | `00_verificar_ambiente.py` mostra `NAO DISPONIVEL` (Sprint 1) | Instale `pip install sqlean.py` e troque `import sqlite3` por `import sqlean as sqlite3` em todos os programas. O `sqlean.py` traz um SQLite completo, com FTS5. Anote no `ambiente.md` e declare na Metodologia |
| Máquina do laboratório formatada | `.venv` ou `bancos/` sumiram | Normal: o código está no GitHub e as bases são geradas de novo com a mesma semente. Clone, recrie o `.venv`, rode `pip install -r requirements.txt` e gere as bases |
| Não achar o livro de Sílvio Romero com o texto digitado | Sprint 1 sem os textos na terça (20/10) | Use uma digitalização do Internet Archive com "FULL TEXT" e corrija a acentuação comparando com a imagem da página |
| Montar 30 contos demora demais | quarta (21/10) com menos de 15 contos | Feche a sprint com **20 contos**, desde que a Sprint 2 consiga carregar pelo menos 150 parágrafos. Anote no diário e declare na Metodologia |
| Gerar ou medir a base de 10.000 demora demais | a medição da E1 passa de 30 minutos | Durante o desenvolvimento, teste só com 100 e 1.000 (deixe o 10.000 fora da lista `VOLUMES` temporariamente) e rode o 10.000 só na rodada oficial |
| Medições muito instáveis | repetições da mesma consulta variando mais do que o dobro | Reinicie a máquina, feche tudo e rode de novo, sem apagar as linhas anteriores. Anote no diário |
| Julgamento atrasado | quarta (25/11) com menos da metade julgada | Reduza o *pooling* para os **5 primeiros** resultados de cada estratégia e calcule P@5 no lugar de P@10. Declare na Metodologia |
| Atraso geral | sprint terminando sem a entrega | Entregue o PR no prazo com o que tiver, diga na *issue* o que faltou e termine na semana seguinte **antes** de começar a próxima. Se precisar cortar, corte o protótipo (Sprint 7). **Não corte** as repetições das medições, a matriz de acentos nem o julgamento |

**Se precisar cortar, corte quantidade, não qualidade.** Três estratégias bem medidas em duas bases valem mais que três estratégias medidas às pressas em três.

---

<a id="extras"></a>
## 11. Se sobrar tempo (opcional)

Só depois de a sprint da semana estar entregue e de a escrita estar em dia:

- **Extra 1.** Testar a busca por **prefixo** no FTS5 (`"assombra"*`, com o asterisco fora das aspas) e ver se ela resolve o problema de "assombração" e "assombrações". É um caminho simples para os plurais.
- **Extra 2.** Testar o tokenizador `trigram` do FTS5, que permite buscar pedaços de palavras, e comparar o tamanho do banco com o da E3.
- **Extra 3.** Medir a busca combinada com filtro por tipo ou por cidade (`... AND tipo = 'Lenda'`), que é o que a tela do portal realmente vai fazer.
- **Extra 4.** Gerar uma base de 50.000 narrativas e ver se a ordem das estratégias se mantém.
- **Extra 5.** Implementar a E3 sem duplicar o texto, com a opção `content=` do FTS5, e medir quanto espaço se economiza.

---

<a id="referencias-minimas"></a>
## 12. Referências mínimas do TCC

- **2 obras de metodologia científica:** Gil (2017) e Prodanov e Freitas (2013);
- **3 a 4 obras sobre narrativas populares, patrimônio imaterial e acervos digitais** (seção 2.1), incluindo Câmara Cascudo e as do `docs/projeto_narrativas.md`;
- **a obra de Sílvio Romero** usada como corpus;
- **1 a 2 livros de banco de dados** (seção 2.2), por exemplo Elmasri e Navathe ou Silberschatz, Korth e Sudarshan;
- **1 fonte sobre injeção de SQL** (seção 2.2);
- **2 obras de recuperação da informação** (seções 2.3 e 2.4): Manning, Raghavan e Schütze (2008) e Baeza-Yates e Ribeiro-Neto;
- **3 trabalhos relacionados** (seção 2.5);
- **a documentação oficial** do SQLite (LIKE, otimizador de consultas e FTS5) e do Django (`icontains`), para descrever as ferramentas;
- **a legislação citada:** Lei nº 9.610/1998 (direitos autorais, que justifica o corpus) e Decreto nº 3.551/2000.

Registre a referência completa de **tudo** o que ler, na seção de Referências do documento do Drive, desde o primeiro dia.
