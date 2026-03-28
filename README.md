# Template de Dissertação

Template Quarto para a elaboração de dissertações tradicionais dos meus orientandos do
[Mestrado Profissional em Administração do IFMG - Campus Formiga](https://formiga.ifmg.edu.br/mestrado).

Este projeto foi preparado para gerar um único arquivo PDF e não contém capítulo dedicado ao produto técnico.

## Antes de Começar

Este template assume que você já tem `R`, `RStudio`, `Quarto` e `TinyTeX` instalados.

Antes de começar a usá-lo, recomenda-se atualizar:

- o `RStudio`;
- o `Quarto`.

Importante:

- use, de preferência, a versão mais recente do `Quarto`, pois ele está em evolução constante;
- se o PDF parar de compilar por falta de pacote ou erro do TeX Live, atualize primeiro o `Quarto` e depois o `TinyTeX`;
- se o `RStudio` estiver muito desatualizado, atualize-o antes de editar o trabalho.

## Como Criar seu Repositório a partir deste Template

Este projeto foi publicado no GitHub como um **template**.

Para criar sua cópia:

1. Abra a página do repositório no GitHub.
2. Clique em `Use this template`.
3. Crie um novo repositório em sua conta.
4. Mantenha o repositório como **público**, salvo orientação diferente do orientador.
5. Copie a URL do repositório criado.
6. Abra o `RStudio`.
7. Vá em `Project > New Project > Version Control > Git`.
8. Na janela de clonagem do `RStudio`, cole a URL do repositório no campo `Repository URL`.
9. No campo `Project directory name`, escolha um nome simples para a pasta do projeto no seu computador. Recomenda-se usar o padrão `dissertacao_nome_sobrenome`, sem acentos e sem espaços.
10. Escolha a pasta em que o projeto será criado no seu computador.
11. Conclua a criação do projeto.
12. Adicione o orientador como colaborador do repositório.

Observações:

- o `RStudio` fará a clonagem do repositório e abrirá o projeto localmente;
- o arquivo `.Rproj` pode continuar com o nome original do template.


## Estrutura do Projeto

As principais pastas e arquivos do projeto são:

- `quarto_template_dissertacao_tradicional.Rproj`: arquivo do projeto para abrir no `RStudio`;
- `template_dissertacao_tradicional.qmd`: arquivo principal da dissertação;
- `pre_textuais.tex`: arquivo com os elementos pré-textuais;
- `dados-limpos/`: pasta para armazenar os dados limpos finais, em arquivos `.rds`, usados na dissertação;
- `referencias.bib`: arquivo da bibliografia;
- `associacao-brasileira-de-normas-tecnicas-ipea.csl`: arquivo de estilo das citações.

Na maior parte do tempo, você precisará editar apenas o arquivo `template_dissertacao_tradicional.qmd`.

Não altere o arquivo `pre_textuais.tex`, salvo orientação expressa do orientador.

## O que Editar Primeiro

Abra `template_dissertacao_tradicional.qmd` e revise primeiro o bloco `DADOS EDITÁVEIS DA DISSERTAÇÃO`, no topo do arquivo.

Revise principalmente:

- nome do discente;
- título e subtítulo;
- cidade, estado e ano;
- orientador;
- coorientador, se houver;
- texto da folha de rosto;
- palavras-chave em português;
- keywords em inglês;


Regras práticas:

- se não houver subtítulo, deixe `\\SubtituloDissertacao{}` vazio;
- se houver subtítulo, ele será exibido automaticamente na capa e na folha de rosto;
- se não houver coorientador, deixe `\\CoorientadorDissertacao{}` vazio;
- na folha de aprovação, use apenas a sigla da instituição de cada membro, como `IFMG`, `UFMG` ou `UFLA`;
- não é necessário escrever “membro titular”;
- prefira funções curtas, como `Orientador`, `Coorientador`, `Avaliador interno` e `Avaliador externo`.

Em seguida:

- edite resumo, abstract;
- ative ou mantenha desativados os elementos opcionais;
- gere o PDF com o botão `Render` do `RStudio` ou com:

```bash
quarto render template_dissertacao_tradicional.qmd
```

## Dados e Código no Template

Este projeto da dissertação não substitui o projeto analítico da pesquisa.

Regra de uso:

- o projeto analítico continua sendo o local para importar, limpar, organizar e explorar os dados;
- o template da dissertação deve ser usado para redigir o texto e reproduzir os resultados finais que entram no PDF;
- utilize neste projeto apenas os dados limpos finais, em arquivos `.rds`, na pasta `dados-limpos/`;
- no projeto analítico, recomenda-se salvar esses dados finais com `readr::write_rds()`;
- no arquivo `.qmd`, reutilize apenas os códigos finais necessários para reproduzir os modelos, tabelas e gráficos que aparecem na dissertação;
- para carregar dados limpos no `.qmd`, recomenda-se usar o pacote `readr`, primeiro criando um objeto com o caminho relativo do arquivo e depois lendo o `.rds` com `read_rds()`;
- é permitido estimar novamente, no `.qmd`, os modelos finais reportados no texto, por exemplo para gerar tabelas com `modelsummary`, tabelas com `gt` e gráficos finais;
- não use este projeto para limpar dados, montar bases, testar várias especificações ou conduzir análise exploratória.

Observações:

- neste template, as legendas das figuras ficam abaixo e os títulos das tabelas ficam acima, conforme a configuração atual do Quarto;
- arquivos `.rds` salvos em `dados-limpos/` não devem ser versionados no Git;
- isso é especialmente importante quando os dados finais vierem de bases licenciadas ou com restrição de redistribuição, como a Economatica;
- se for necessário compartilhar esses arquivos com o orientador, combine diretamente a forma de envio.

Exemplo mínimo de carga de dados limpos finais no `.qmd`:

```r
library(readr)

caminho_base_final <- "dados-limpos/base_final.rds"
base_final <- read_rds(caminho_base_final)
```

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

- a dedicatória já fica comentada;
- os agradecimentos já ficam comentados;
- os comandos de lista de figuras e lista de tabelas também já ficam comentados.

Se quiser ativar esses elementos opcionais no arquivo principal:

- remova `<!--` antes do bloco da dedicatória e `-->` depois desse bloco;
- remova `<!--` antes do bloco dos agradecimentos e `-->` depois desse bloco;
- descomente `\inserirListaDeFigurasDissertacao` se houver figuras no trabalho;
- descomente `\inserirListaDeTabelasDissertacao` se houver tabelas no trabalho.

## Ficha Catalográfica

A ficha catalográfica não é escrita diretamente no template.

Procedimento:

1. após receber o arquivo da bibliotecária;
2. converta esse arquivo para PDF;
3. salve o PDF com o nome `ficha_catalografica.pdf` na raiz do projeto;
4. renderize novamente a dissertação.

Se esse arquivo não existir, o template exibirá apenas um marcador de posição no local correspondente.

## Folha de Aprovação

A folha de aprovação faz parte do PDF gerado pelo próprio `Quarto`. Isso permite que o PDF final seja assinado digitalmente pelos membros da banca, por exemplo, via `gov.br`.

Importante:

- preencha a data de aprovação e os dados da banca apenas quando essas informações estiverem definidas;
- preencha corretamente os dados da banca no topo do arquivo `.qmd` antes de gerar a versão final;
- não renderize novamente o PDF depois que ele for assinado;
- qualquer alteração posterior invalida o arquivo assinado.
