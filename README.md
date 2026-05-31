# Template de dissertação

Template Quarto para a elaboração das dissertações dos meus orientandos do
[Mestrado Profissional em Administração do IFMG - Campus Formiga](https://formiga.ifmg.edu.br/mestrado).

Este projeto foi preparado para gerar um único arquivo PDF e não contém capítulo 
dedicado ao produto técnico.



## Antes de começar

Este template assume que você já tem **R**, **RStudio**, **Quarto** e **TinyTeX** instalados.

Antes de começar a usá-lo, recomenda-se fortemente atualizar:

- o **RStudio**;
- o **Quarto**.



## Uso em resumo

Depois de criar sua cópia do template:

1. abra o arquivo `dissertacao.qmd`;
2. revise o bloco `DADOS EDITÁVEIS DA DISSERTAÇÃO`, no topo do arquivo;
3. escreva o texto da dissertação nas seções indicadas;
4. preencha resumo, abstract, palavras-chave e keywords;
5. adicione suas referências em `referencias.bib`;
6. renderize `dissertacao.qmd` para gerar `dissertacao.pdf`;
7. revise visualmente o PDF antes de enviar qualquer versão para avaliação ou assinatura.

Na maior parte do trabalho, você editará apenas `dissertacao.qmd` e
`referencias.bib`.



## Como criar seu repositório a partir deste template

Este projeto foi publicado no **GitHub** como um **template**.

Para criar sua cópia:

1. Acesse esta página do repositório no **GitHub**.
2. Clique em `Use this template`.
3. Crie um novo repositório em sua conta com um nome simples, de preferência no padrão `dissertacao_nome_sobrenome`, sem acentos e sem espaços, por exemplo: `dissertacao_joao_silva`.
4. Mantenha o repositório como **público**, salvo orientação diferente do orientador.
5. Copie a URL do repositório criado.
6. Abra o **RStudio**.
7. Clique em `Project > New Project > Version Control > Git`.
8. Na janela de clonagem do **RStudio**, cole a URL do repositório no campo `Repository URL`.
9. No campo `Project directory name`, verifique se apareceu o nome do repositório criado, 
por exemplo: `dissertacao_joao_silva`. Se não, escreva o nome que você escolheu 
para o repositório neste campo (por exemplo: `dissertacao_joao_silva`).
10. Escolha a pasta em que o projeto será criado no seu computador.
11. Clique em `Create Project` para criar o projeto no seu computador. O 
**RStudio** fará a clonagem do repositório e abrirá o projeto localmente.
12. Renderize o arquivo `dissertacao.qmd` para verificar se tudo está funcionando.
13. Adicione o orientador como colaborador do repositório no **GitHub**.

A renderização criará o arquivo `dissertacao.pdf` na pasta do projeto. Esse **PDF** não é versionado no **Git**, pois é gerado automaticamente a partir do arquivo-fonte da dissertação.

Observações:

- ao clonar pelo **RStudio**, o próprio **RStudio** criará automaticamente o arquivo de projeto `.Rproj` com o nome do repositório local;

- esse arquivo `.Rproj` é apenas local e não faz parte do conteúdo versionado do template;



## Estrutura do projeto

As principais pastas e arquivos do projeto são:

- `dissertacao.qmd`: arquivo principal da dissertação;
- `pre_textuais.tex`: arquivo com os elementos pré-textuais;
- `dados-limpos/`: pasta para armazenar os dados limpos finais, em arquivos `.rds`, usados na dissertação;
- `referencias.bib`: arquivo da bibliografia, inicialmente sem referências específicas;
- `associacao-brasileira-de-normas-tecnicas-ipea.csl`: arquivo de estilo das citações.

Não altere o arquivo `pre_textuais.tex`, salvo orientação expressa do orientador.



## O que editar primeiro?

Abra `dissertacao.qmd` e revise primeiro o bloco `DADOS EDITÁVEIS DA DISSERTAÇÃO`, 
no topo do arquivo.

Os campos editáveis estão definidos como comandos LaTeX nesta forma:

```tex
\newcommand{\NomeDoCampo}{valor do campo}
```

Edite apenas o texto entre o segundo par de chaves, isto é, o conteúdo de
`{valor do campo}`.

Exemplo:

```tex
\newcommand{\DataAprovacaoDissertacao}{15 de março de 2026}
```

No exemplo acima, o texto editável é apenas `15 de março de 2026`.
Não altere o nome do comando.

Revise principalmente:

- nome do discente;
- título e subtítulo;
- cidade, estado e ano;
- orientador;
- coorientador;
- instituição do coorientador;
- data de aprovação;
- instituições e funções da banca;
- texto da folha de rosto;
- palavras-chave em português;
- keywords em inglês;


Regras práticas:

- a folha de rosto usa diretamente os valores definidos em `\newcommand{\OrientadorDissertacao}{...}` e `\newcommand{\CoorientadorDissertacao}{...}`;
- se não houver subtítulo, deixe `\newcommand{\SubtituloDissertacao}{}` vazio;
- se houver subtítulo, ele será exibido automaticamente na capa e na folha de rosto;
- o caso padrão da folha de aprovação usa quatro campos de assinatura: orientador, coorientador, avaliador interno e avaliador externo;
- se não houver coorientador, mantenha `\newcommand{\CoorientadorDissertacao}{}` e `\newcommand{\CoorientadorInstituicaoDissertacao}{}` vazios;
- quando houver coorientador, preencha nome e instituição para que ele apareça também na folha de aprovação;
- se o nome do coorientador for preenchido, mas a instituição ficar vazia, ele aparecerá na folha de rosto, mas não aparecerá na folha de aprovação;
- na folha de aprovação, o primeiro campo da banca já herda automaticamente o nome definido em `\newcommand{\OrientadorDissertacao}{...}`;
- na folha de aprovação, use apenas a sigla da instituição de cada membro, como `IFMG`, `UFMG` ou `UFLA`;
- não é necessário escrever “membro titular”;
- prefira funções curtas, como `Orientador`, `Coorientador`, `Avaliador interno` e `Avaliador externo`.

Campos mais usados:

| Campo | O que preencher | Exemplo |
| --- | --- | --- |
| `\NomeAutorDissertacao` | nome completo do discente | `Maria Silva` |
| `\TituloDissertacao` | título da dissertação | `Determinantes do Desempenho Financeiro` |
| `\SubtituloDissertacao` | subtítulo, se houver | `Evidências para Empresas Brasileiras` |
| `\AnoDissertacao` | ano exibido na capa e na folha de rosto | `2026` |
| `\DataAprovacaoDissertacao` | data da defesa por extenso | `15 de março de 2026` |
| `\PalavrasChaveDissertacao` | palavras-chave em português | `finanças; desempenho; empresas.` |
| `\KeywordsDissertation` | keywords em inglês | `finance; performance; firms.` |

Campos institucionais:

| Campo | O que preencher | Observação |
| --- | --- | --- |
| `\TextoApresentacaoDissertacao` | texto de apresentação da folha de rosto | altere apenas se houver orientação específica |
| `\LinhaPesquisaDissertacao` | linha de pesquisa | confira se está correta para sua dissertação |
| `\AreaConcentracaoDissertacao` | área de concentração | confira se está correta para sua dissertação |
| `\TituloObtidoDissertacao` | título obtido | em geral, mantenha `Mestre em Administração` |

Campos da orientação e da banca:

| Campo | O que preencher | Exemplo |
| --- | --- | --- |
| `\OrientadorDissertacao` | nome do orientador | `Prof. Dr. Nome do Orientador` |
| `\CoorientadorDissertacao` | nome do coorientador | `Prof. Dr. Nome do Coorientador` |
| `\CoorientadorInstituicaoDissertacao` | sigla da instituição do coorientador | `IFMG` |
| `\MembroBancaUmInstituicao` | sigla da instituição do orientador | `IFMG` |
| `\MembroBancaDoisNome` | nome do avaliador interno | `Prof. Dr. Nome do Examinador Interno` |
| `\MembroBancaDoisFuncao` | função do avaliador interno | `Avaliador interno` |
| `\MembroBancaDoisInstituicao` | sigla da instituição do avaliador interno | `IFMG` |
| `\MembroBancaTresNome` | nome do avaliador externo | `Prof. Dr. Nome do Examinador Externo` |
| `\MembroBancaTresFuncao` | função do avaliador externo | `Avaliador externo` |
| `\MembroBancaTresInstituicao` | sigla da instituição do avaliador externo | `UFMG` |

Para a data de aprovação, substitua todo o conteúdo `dia de mês de ano`
pela data real da defesa, escrita por extenso.

Após finalizar as principais seções da dissertação (introdução, 
revisão da literatura, metodologia, etc.):

- escreva o resumo e o abstract;
- ative ou mantenha desativados os elementos opcionais;
- gere o PDF com o botão `Render` do **RStudio** ou com:

```bash
quarto render dissertacao.qmd
```



## Dados e código no template

Este projeto da dissertação não substitui o projeto analítico da pesquisa.

Regra de uso:

- o projeto analítico continua sendo o local para importar, limpar, organizar e explorar os dados;
- o template da dissertação deve ser usado para redigir o texto e reproduzir os resultados finais que entram no PDF;
- utilize neste projeto apenas os dados limpos finais, em arquivos `.rds`, na pasta `dados-limpos/`;
- no projeto analítico, recomenda-se salvar esses dados finais com `readr::write_rds()`;
- no arquivo `dissertacao.qmd`, reutilize apenas os códigos finais necessários para reproduzir os modelos, tabelas e gráficos que aparecem na dissertação;
- para carregar dados limpos em `dissertacao.qmd`, recomenda-se usar o pacote `readr`, primeiro criando um objeto com o caminho relativo do arquivo e depois lendo o `.rds` com `read_rds()`;
- é permitido estimar novamente, em `dissertacao.qmd`, os modelos finais reportados no texto, por exemplo para gerar tabelas com `modelsummary`, tabelas com `gt` e gráficos finais;
- não use este projeto para limpar dados, montar bases, testar várias especificações ou conduzir análise exploratória.

Observações:

- neste template, as legendas das figuras ficam abaixo e os títulos das tabelas ficam acima, conforme a configuração atual do Quarto;
- arquivos `.rds` salvos em `dados-limpos/` não devem ser versionados no Git;
- isso é especialmente importante quando os dados finais vierem de bases licenciadas ou com restrição de redistribuição, como a Economatica;
- se for necessário compartilhar esses arquivos com o orientador, combine diretamente a forma de envio.

O chunk `setup` em `dissertacao.qmd` começa com `eval: false`. Mantenha assim
até ter certeza de que os pacotes e o arquivo `.rds` indicados existem no seu
computador. Se você mudar para `eval: true` antes disso, a renderização pode
falhar.

Exemplo mínimo de carga de dados limpos finais em `dissertacao.qmd`:

```r
# carrega os pacotes utilizados
library(tidyverse) # readr, dplyr, ggplot2, etc.

# define o caminho relativo para o arquivo de dados limpos
path_limpos <- here::here("dados-limpos/arquivo_limpo.rds")

# importa o arquivo de dados limpos
dados_limpos <- readr::read_rds(path_limpos)
```

## Referências e citações

As referências bibliográficas ficam no arquivo `referencias.bib`. Esse arquivo
começa sem referências reais para evitar que o template traga bibliografia de
uma pesquisa específica.

Fluxo básico:

1. adicione uma entrada BibTeX em `referencias.bib`;
2. use a chave da entrada para citar no texto;
3. renderize o PDF.

Exemplo de entrada em `referencias.bib`:

```bibtex
@book{sobrenome2026,
  author    = {Sobrenome, Nome},
  title     = {Título do livro},
  year      = {2026},
  publisher = {Editora}
}
```

Exemplo de citação em `dissertacao.qmd`:

```markdown
Texto da dissertação com citação entre parênteses [@sobrenome2026].
```

A seção `Referências` do PDF é gerada automaticamente a partir das citações
feitas no texto. Não digite manualmente a lista de referências no final do
arquivo `dissertacao.qmd`.

Se uma referência não aparecer no PDF, verifique se ela foi citada no texto
com a chave correta.


## Elementos Pré-textuais

A sequência atual do template é a seguinte:

1. capa;
2. folha de rosto;
3. ficha catalográfica;
4. folha de aprovação;
5. dedicatória, se ativada;
6. agradecimentos, se ativados;
7. resumo com palavras-chave;
8. abstract com keywords;
9. lista de figuras, se ativada;
10. lista de tabelas, se ativada;
11. sumário.

Na versão inicial do template:

- a dedicatória está comentada;
- os agradecimentos estão comentados;
- os comandos de lista de figuras e lista de tabelas também estão comentados.

Se quiser ativar esses elementos opcionais no arquivo principal:

- remova `<!--` antes do bloco da dedicatória e `-->` depois desse bloco;
- remova `<!--` antes do bloco dos agradecimentos e `-->` depois desse bloco;
- descomente `\inserirListaDeFigurasDissertacao` se houver figuras no trabalho;
- descomente `\inserirListaDeTabelasDissertacao` se houver tabelas no trabalho.

As linhas das listas de figuras e tabelas começam dentro de um comentário HTML.
Para ativá-las, remova os marcadores `<!--` e `-->` que envolvem esse bloco.

Exemplo: para ativar a dedicatória, transforme isto:

```markdown
<!--
\begin{dedicatoriadissertacao}

Dedique este trabalho a quem fez parte da sua trajetória acadêmica,
profissional ou pessoal.

\end{dedicatoriadissertacao}
-->
```

nisto:

```tex
\begin{dedicatoriadissertacao}

Dedique este trabalho a quem fez parte da sua trajetória acadêmica,
profissional ou pessoal.

\end{dedicatoriadissertacao}
```



## Ficha catalográfica

A ficha catalográfica não é escrita diretamente no template.

Procedimento:

1. após receber o arquivo da bibliotecária;
2. converta esse arquivo para PDF;
3. salve o PDF com o nome `ficha_catalografica.pdf` na raiz do projeto;
4. renderize novamente a dissertação.

Se esse arquivo não existir, o template exibirá apenas um marcador de posição no local correspondente.



## Folha de rosto

A folha de rosto é preenchida automaticamente a partir dos campos do topo de `dissertacao.qmd`.

Preencha os seguintes campos:

1. `\newcommand{\OrientadorDissertacao}{...}` para o nome do orientador;
2. `\newcommand{\CoorientadorDissertacao}{...}` para o nome do coorientador;
3. `\newcommand{\TextoApresentacaoDissertacao}{...}` se for necessário ajustar o texto-padrão de apresentação;
4. `\newcommand{\LinhaPesquisaDissertacao}{...}` para a linha de pesquisa exibida ao final do bloco.

Importante:

- se `\newcommand{\CoorientadorDissertacao}{}` estiver vazio, a folha de rosto exibirá apenas o orientador;
- no estado atual do template, a folha de rosto usa os rótulos `Orientador:` e `Coorientador:`;
- não é necessário editar `pre_textuais.tex` para alterar nomes ou funções na folha de rosto.



## Folha de aprovação

A folha de aprovação faz parte do PDF gerado pelo próprio **Quarto**. Isso permite que o PDF final seja assinado digitalmente pelos membros da banca, por exemplo, via `gov.br`.

O caso padrão deste template contém quatro campos de assinatura:

1. orientador;
2. coorientador;
3. avaliador interno;
4. avaliador externo.

O espaçamento da folha de aprovação foi calibrado para esse caso, com área
vertical suficiente acima de cada linha para assinatura digital visível.

Importante:

- preencha a data de aprovação e os dados da banca apenas quando essas informações estiverem definidas;
- preencha corretamente os dados da banca no topo do arquivo `dissertacao.qmd` antes de gerar a versão final;
- a ordem atual dos campos na folha de aprovação é: orientador, coorientador, avaliador interno, avaliador externo e membros adicionais opcionais;
- o nome do orientador na folha de aprovação já é herdado automaticamente de `\newcommand{\OrientadorDissertacao}{...}`;
- para exibir o coorientador na folha de aprovação, preencha `\newcommand{\CoorientadorDissertacao}{...}` e `\newcommand{\CoorientadorInstituicaoDissertacao}{...}`;
- se não houver coorientador, ou se a instituição dele não estiver preenchida, o campo adicional de assinatura não será exibido na folha de aprovação;
- use `\newcommand{\MembroBancaUmInstituicao}{...}` para a instituição do orientador na folha de aprovação;
- preencha nome, função e instituição do avaliador interno nos campos `\MembroBancaDoisNome`, `\MembroBancaDoisFuncao` e `\MembroBancaDoisInstituicao`;
- preencha nome, função e instituição do avaliador externo nos campos `\MembroBancaTresNome`, `\MembroBancaTresFuncao` e `\MembroBancaTresInstituicao`;
- use os campos de quarto e quinto membros apenas se a banca tiver membros adicionais oficialmente definidos;
- quando houver quarto ou quinto membro, título longo ou subtítulo longo, revise visualmente a folha de aprovação antes de enviar o arquivo para assinatura;
- a folha de aprovação prioriza espaço para assinatura digital visível no caso padrão de quatro campos;
- se uma banca ampliada deixar a folha de aprovação excessivamente comprimida ou quebrar a página, ajuste manualmente os dados exibidos ou confirme com a instituição se a folha de aprovação pode ocupar mais de uma página;
- não renderize novamente o PDF depois que ele for assinado;
- qualquer alteração posterior invalida o arquivo assinado.


## Problemas comuns

Se o PDF não for gerado:

- verifique se **Quarto** e **TinyTeX** estão instalados;
- confira se você está renderizando `dissertacao.qmd`;
- leia a mensagem de erro exibida no painel de renderização do **RStudio**.

Se o erro mencionar um pacote do R:

- verifique se o pacote está instalado;
- se o pacote não for necessário, remova ou comente a linha correspondente no chunk `setup`.

Se o erro mencionar um arquivo `.rds`:

- confira se o arquivo existe em `dados-limpos/`;
- confira se o nome usado em `path_limpos <- here::here("dados-limpos/arquivo_limpo.rds")` é igual ao nome real do arquivo;
- mantenha `eval: false` no chunk `setup` até o arquivo estar disponível.

Se a ficha catalográfica não aparecer:

- salve o arquivo oficial como `ficha_catalografica.pdf`;
- coloque esse arquivo na raiz do projeto, na mesma pasta de `dissertacao.qmd`;
- renderize novamente.

Se uma referência não aparecer:

- confira se a entrada está em `referencias.bib`;
- confira se a chave foi citada no texto, por exemplo `[@sobrenome2026]`;
- confira se não há erro de digitação na chave.

Se o PDF for gerado, mas ainda aparecer com dados genéricos:

- revise o bloco `DADOS EDITÁVEIS DA DISSERTAÇÃO` no topo de `dissertacao.qmd`;
- confira nome, título, coorientador, data de aprovação, banca, palavras-chave e keywords;
- renderize novamente depois de corrigir esses campos.

Se a folha de aprovação ficar apertada:

- revise se todos os membros adicionais são realmente necessários;
- encurte funções e siglas institucionais quando possível;
- revise visualmente o PDF antes de enviar para assinatura digital.
