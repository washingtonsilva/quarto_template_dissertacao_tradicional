# Template de Dissertacao Tradicional

Template Quarto para dissertacoes tradicionais do Mestrado Profissional em
Administracao do IFMG - Campus Formiga.

Este projeto foi preparado para PDF e segue uma estrutura simples, pensada
para orientandos que vao editar o trabalho principalmente no RStudio.

O template nao usa capitulo de produto tecnico.

## Antes De Comecar

Antes de usar o template, instale:

- a versao mais recente do Quarto
- o RStudio
- o TinyTeX para gerar PDF

Recomendacao importante:

- use sempre a versao mais recente do Quarto, porque ele e um sistema novo e
  evolui rapidamente
- se o PDF parar de compilar por pacote ausente ou erro do TeX Live, atualize
  o TinyTeX

## Como Criar Seu Repositorio

Se este projeto estiver publicado no GitHub como template:

1. Abra a pagina do repositorio no GitHub.
2. Clique em `Use this template`.
3. Crie um novo repositorio seu, em vez de usar fork.
4. Clone o repositorio criado para o seu computador.
5. Abra o projeto no RStudio pelo arquivo
   `quarto_template_dissertacao_tradicional.Rproj`.

Observacao:

- mesmo no seu repositorio proprio, o arquivo `.Rproj` pode continuar com o
  nome original do template

Referencia oficial:

- [Creating a repository from a template](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)

## Arquivos Principais

- `quarto_template_dissertacao_tradicional.Rproj`: arquivo do projeto para
  abrir no RStudio
- `template_dissertacao_tradicional.qmd`: arquivo principal da dissertacao
- `pre_textuais.tex`: camada de formatacao LaTeX dos elementos pre-textuais
- `referencias.bib`: bibliografia do trabalho
- `associacao-brasileira-de-normas-tecnicas-ipea.csl`: estilo de citacao

## Primeiro Uso No RStudio

1. Abra `quarto_template_dissertacao_tradicional.Rproj`.
2. Abra `template_dissertacao_tradicional.qmd`.
3. Edite primeiro o bloco `DADOS EDITAVEIS DA DISSERTACAO` no topo do arquivo.
4. Depois edite os textos dos elementos pre-textuais e dos capitulos.
5. Renderize o PDF com o botao Render do RStudio ou com:

```bash
quarto render template_dissertacao_tradicional.qmd
```

Na maior parte do tempo, voce deve editar apenas `template_dissertacao_tradicional.qmd`.
O arquivo `pre_textuais.tex` so precisa ser alterado quando for necessario
ajustar a formatacao do template.

## O Que Editar Primeiro

No topo de `template_dissertacao_tradicional.qmd`, revise estes campos:

- nome do discente
- titulo e subtitulo
- cidade, estado e ano
- orientador
- coorientador, se houver
- area de concentracao
- texto de apresentacao da folha de rosto, se precisar ajustar
- data de aprovacao
- palavras-chave em portugues
- keywords em ingles
- nomes, funcoes e instituicoes da banca

Regras praticas:

- se nao houver coorientador, deixe `\\CoorientadorDissertacao{}` vazio
- na folha de aprovacao, use apenas a sigla da instituicao de cada membro, por
  exemplo `IFMG`, `UFMG` ou `UFLA`
- nao e necessario escrever "membro titular"
- prefira funcoes curtas, como `Orientador`, `Coorientador`, `Avaliador interno`
  e `Avaliador externo`

Depois disso, edite o corpo do trabalho:

- dedicatoria, se quiser usar
- agradecimentos, se quiser usar
- resumo
- abstract
- introducao
- referencial teorico
- metodologia
- resultados e discussao
- consideracoes finais

## Elementos Pre-Textuais Do Template

Sequencia atual do template:

1. capa
2. folha de rosto
3. ficha catalografica
4. folha de aprovacao
5. dedicatoria, se mantida
6. agradecimentos, se mantidos
7. resumo com palavras-chave
8. abstract com keywords
9. lista de figuras
10. lista de tabelas
11. sumario

Observacoes:

- a dedicatoria e opcional
- os agradecimentos sao opcionais
- a lista de figuras so deve ser mantida se houver figuras no trabalho
- a lista de tabelas so deve ser mantida se houver tabelas no trabalho

Se nao houver figuras ou tabelas, remova do arquivo principal os comandos:

- `\inserirListaDeFigurasDissertacao`
- `\inserirListaDeTabelasDissertacao`

## Ficha Catalografica

A ficha catalografica nao e escrita dentro do template.

Fluxo recomendado:

1. Receba o arquivo da bibliotecaria.
2. Converta esse arquivo para PDF.
3. Salve o PDF com o nome `ficha_catalografica.pdf` na raiz do projeto.
4. Renderize novamente a dissertacao.

Se esse arquivo nao existir, o template mostra apenas um placeholder na posicao
correta.

## Folha De Aprovacao

A folha de aprovacao faz parte do PDF gerado pelo proprio Quarto.

Isso foi feito para permitir que o PDF final seja assinado digitalmente pelos
membros da banca, por exemplo via `gov.br`.

Fluxo recomendado:

1. Preencha corretamente os dados da banca no topo do `.qmd`.
2. Gere o PDF final da dissertacao.
3. Use esse PDF para a coleta das assinaturas digitais.

Importante:

- nao renderize novamente o PDF depois que ele for assinado
- qualquer alteracao posterior invalida o arquivo que foi assinado

## Estrutura Do Texto

Nesta versao do template, toda a dissertacao permanece em um unico arquivo
`.qmd`.

Isso foi mantido de proposito para reduzir a complexidade inicial. Se o texto
ficar muito grande no futuro, os capitulos podem ser separados depois.

## Observacoes Finais

- o template foi configurado para PDF com `xelatex`
- isso e compativel com o uso de `TinyTeX`
- o arquivo `.Rproj` deve permanecer versionado
- PDFs gerados nao devem ser versionados no repositorio
- o `.gitignore` do projeto ja foi preparado para ignorar os arquivos gerados
