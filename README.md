# Template de Dissertacao

Template Quarto para a elaboração das dissertaçoões (artigos científicos) 
dos meus orientandos do 
[Mestrado Profissional em Administracao do IFMG - Campus Formiga](https://formiga.ifmg.edu.br/mestrado).

Este projeto foi preparado para gerar um único arquivo PDF e segue uma estrutura 
simples. Este template não contém um capíttulo dedicado ao produto técnico.


## Antes de Começar

Este template assume que você já tem `R`, `RStudio`, `Quarto` e 
`TinyTeX` instalados.

Antes de começar a usá-lo, recomenda-se atualizar:

- o `RStudio`;
- o `Quarto`.

Importante:

- use, de preferência, a versão mais recente do `Quarto`, pois ele está em 
evolução constante;

- se o PDF parar de compilar por falta de pacote ou erro do TeX Live, 
atualize primeiro o `Quarto` e depois o `TinyTeX`;

- se o `RStudio` estiver muito desatualizado, atualize-o antes de editar 
o trabalho.




## Como Criar seu Repositório

Este projeto foi publicado no GitHub como um **template**.

Para criar sua cópia:

1. Abra a página do repositório no GitHub.
2. Clique em `Use this template`.
3. Crie um novo repositório em sua conta.
4. Copie a URL do repositório criado.
5. Abra o `RStudio`.
6. Vá em `Project > New Project > Version Control > Git`.
7. Cole a URL do repositório.
8. Escolha a pasta em que o projeto será criado no seu computador.
9. Conclua a criação do projeto.

Observações:

- o `RStudio` fará a clonagem do repositório e abrirá o projeto localmente;
- o arquivo `.Rproj` pode continuar com o nome original do template.




## Arquivos Principais

Os arquivos mais importantes do projeto são:

- `quarto_template_dissertacao_tradicional.Rproj`: arquivo do projeto para abrir no `RStudio`;
- `template_dissertacao_tradicional.qmd`: arquivo principal da dissertação;
- `pre_textuais.tex`: arquivo com os elementos pré-textuais;
- `referencias.bib`: arquivo da bibliografia;
- `associacao-brasileira-de-normas-tecnicas-ipea.csl`: arquivo de estilo das citações.




## Primeiro Uso no RStudio

Depois de clonar o repositório:

1. Abra seu projeto RStudio do template que você clonou.
2. Abra `template_dissertacao_tradicional.qmd`.
3. Preencha primeiro o bloco `DADOS EDITÁVEIS DA DISSERTAÇÃO`, no topo do arquivo.
4. Em seguida, edite os elementos pré-textuais e os capítulos.
5. Gere o PDF usando o botão `Render` do `RStudio` ou o comando:

```bash
quarto render template_dissertacao_tradicional.qmd
```

Se a primeira renderização falhar, verifique:

- se o `Quarto` está atualizado;
- se o `RStudio` está atualizado;
- se o `TinyTeX` precisa ser atualizado.

Na maior parte do tempo, você precisará editar apenas o arquivo 
`template_dissertacao_tradicional.qmd`.

O arquivo `pre_textuais.tex` só deve ser alterado quando for 
necessário ajustar a formatação do template.




## O que Editar Primeiro

No início de `template_dissertacao_tradicional.qmd`, revise principalmente:

- nome do discente;
- título e subtítulo;
- cidade, estado e ano;
- orientador;
- coorientador, se houver;
- texto da folha de rosto;
- data de aprovação;
- palavras-chave em português;
- keywords em inglês;
- nomes, funções e instituições dos membros da banca.

Regras práticas:

- se não houver subtítulo, deixe `\\SubtituloDissertacao{}` vazio;
- se houver subtítulo, ele será exibido automaticamente na capa e na folha de rosto;
- se não houver coorientador, deixe `\\CoorientadorDissertacao{}` vazio;
- na folha de aprovação, use apenas a sigla da instituição de cada membro, como `IFMG`, `UFMG` ou `UFLA`;
- não é necessário escrever “membro titular”;
- prefira funções curtas, como `Orientador`, `Coorientador`, `Avaliador interno` e `Avaliador externo`.

Depois disso, edite o texto da dissertação:

- dedicatória, se desejar;
- agradecimentos, se desejar;
- resumo;
- abstract;
- introdução;
- referencial teórico;
- metodologia;
- resultados e discussão;
- considerações finais.




## Elementos Pré-textuais

A sequência atual do template é a seguinte:

1. capa;
2. folha de rosto;
3. ficha catalográfica;
4. folha de aprovação;
5. dedicatória, se mantida;
6. agradecimentos, se mantidos;
7. resumo com palavras-chave;
8. abstract com keywords;
9. lista de figuras;
10. lista de tabelas;
11. sumário.

Observações importantes:

- a dedicatória é opcional;
- os agradecimentos são opcionais;
- a lista de figuras só deve ser mantida se houver figuras no trabalho;
- a lista de tabelas só deve ser mantida se houver tabelas no trabalho;
- neste template, não use `lof` nem `lot` no YAML.

Se não houver figuras ou tabelas, remova do arquivo principal os comandos:

- `\inserirListaDeFigurasDissertacao`
- `\inserirListaDeTabelasDissertacao`




## Ficha Catalográfica

A ficha catalográfica não é escrita diretamente no template.

Procedimento que deve ser seguido:

1. após receber o arquivo da bibliotecária;
2. converta esse arquivo para PDF;
3. salve o PDF com o nome `ficha_catalografica.pdf` na raiz do projeto;
4. renderize novamente a dissertação.

Se esse arquivo não existir, o template exibirá apenas um marcador de 
posição no local correspondente.




## Folha de Aprovação

A folha de aprovação faz parte do PDF gerado pelo próprio `Quarto`.

Isso permite que o PDF final seja assinado digitalmente pelos membros 
da banca, por exemplo, via `gov.br`.

Procedimento recomendado:

1. preencha corretamente os dados da banca no topo do arquivo `.qmd`;
2. gere o PDF final da dissertação;
3. use esse PDF para coletar as assinaturas digitais.

Importante:

- não renderize novamente o PDF depois que ele for assinado;
- qualquer alteração posterior invalida o arquivo assinado.




## Estrutura do Texto

Nesta versão do template, toda a dissertação fica em um único arquivo `.qmd`.

Essa escolha foi feita para simplificar o uso inicial do projeto. 

Caso o texto fique muito grande no futuro, os capítulos poderão ser 
separados em arquivos diferentes.




## Observações Finais

- o template foi configurado para gerar PDF com `xelatex`;
- isso é compatível com o uso do `TinyTeX`;
- o arquivo `.Rproj` deve permanecer versionado;
- os PDFs gerados não devem ser versionados no repositório;
- o arquivo `.gitignore` já foi preparado para ignorar arquivos 
desnecessários gerados durante a edição do trabalho.



