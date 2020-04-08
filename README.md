<!--
Projeto 1 de Linguagens de Programação I 2019/2020 (c) by Nuno Fachada

Projeto 1 de Linguagens de Programação I 2019/2020 is licensed under a
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-nc-sa/4.0/>.
-->

# Projeto 1 de Linguagens de Programação I 2019/2020

## Introdução

Os grupos devem implementar o jogo **Wolf and Sheep** na forma de uma
aplicação de consola .NET Core. O jogo deve ser PvP (_Player vs Player_), sem
qualquer tipo de inteligência artificial.

## Regras do jogo

* O jogo **Wolf and Sheep** é jogado num tabuleiro 8x8 apenas nos quadrados
  escuros.
* As quatro peças brancas, as ovelhas, são colocadas nos quadrados escuros num
  dos lados do tabuleiro.
* A peça preta, o lobo, é colocada em qualquer um dos quadrados escuros do lado
  oposto. A seguinte imagem mostra um possível tabuleiro inicial:

![Tabuleiro inicial, imagem obtida de https://ludii.games/details.php?keyword=Wolf%20and%20Sheep](img/board-start.png "Tabuleiro inicial")

* O objetivo do lobo é chegar a um dos quadrados originais das ovelhas.
* O objetivo das ovelhas é bloquear o lobo, impedindo-o de chegar a um dos
  seus quadrados originais.
* As ovelhas movem-se na diagonal e para a frente, um quadrado por turno.
* O lobo move-se na diagonal, um quadrado por turno, não só para a frente como
  as ovelhas, como também para trás. Isto é, o lobo pode recuar, as ovelhas
  não.
* **O lobo move-se sempre primeiro**.
* No turno das ovelhas, só é possível mover **uma** ovelha.
* As peças só se podem mover para quadrados escuros **vazios**.
* O lobo vence se chegar a um dos quadrados originais das ovelhas.
* As ovelhas vencem se bloquearem o lobo de modo a que o mesmo não se consiga
  mover, tal como exemplificado na imagem seguinte:

![Possível tabuleiro final, imagem obtida de https://ludii.games/details.php?keyword=Wolf%20and%20Sheep](img/board-end.png "Possível tabuleiro final")

## Funcionamento da aplicação

O funcionamento exato da aplicação é da responsabilidade de cada grupo. No
entanto, quando a aplicação começa, **deve ser claro como cada jogador joga**,
ou seja, o jogo deve ter instruções muito claras sobre que teclas fazem o quê.
Por outras palavras, os grupos devem ter em conta as regras importantes do
_game design_.

## Organização do código

Para este primeiro projeto, aceita-se que a maior parte do código (ou mesmo
todo o código), esteja incluído num único ficheiro `Program.cs`. No entanto,
o código deverá estar bem organizado e dividido em vários métodos (funções).
Todos os métodos e variáveis da classe `Program` devem ser `private static`
(atenção que variáveis declaradas dentro dos métodos não podem ser nem
`private` nem `static`).

Caso usem enumerações, cada enumeração deverá estar num ficheiro com o mesmo
nome. Por exemplo, uma possível enumeração `Player` deverá ser colocada no
ficheiro `Player.cs`. O uso correto de enumerações será bonificado na nota
final.

## Objetivos e critério de avaliação

Este projeto tem os seguintes objetivos:

* **O1** - Programa deve funcionar como especificado.
* **O2** - Projeto e código bem organizados, nomeadamente:
  * Código bem dividido em métodos (funções), eventualmente fazendo uso de
    enumerações, cada uma no seu ficheiro.
  * Código devidamente comentado e indentado.
  * Inexistência de código "morto", que não faz nada, como por exemplo
    variáveis, propriedades ou métodos nunca usados.
  * Projeto compila e executa sem erros e/ou *warnings*.
* **O3** - Projeto adequadamente documentado. Documentação deve ser feita com
  [comentários de documentação XML][XML].
  * Para este projeto não é preciso, para já, gerar a documentação em [Doxygen]
    ou [DocFX].
* **O4** - Repositório Git deve refletir boa utilização do mesmo, nomeadamente:
  * Devem existir *commits* de todos os elementos do grupo, _commits_ esses
    com mensagens que sigam as melhores práticas para o efeito (como indicado
    [aqui](https://chris.beams.io/posts/git-commit/),
    [aqui](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53),
    [aqui](https://github.com/erlang/otp/wiki/writing-good-commit-messages) e
    [aqui](https://stackoverflow.com/questions/2290016/git-commit-messages-50-72-formatting)).
  * Ficheiros binários não necessários, como por exemplo todos os que são
    criados nas pastas `bin` e `obj`, bem como os ficheiros de configuração
    do Visual Studio (na pasta `.vs` ou `.vscode`), não devem estar no
    repositório. Ou seja, devem ser ignorados ao nível do ficheiro
    `.gitignore`.
  * *Assets* binários necessários, como é o caso da imagem do fluxograma, deve
    ser integrados no repositório em modo Git LFS.
* **O5** - Relatório em formato [Markdown] (ficheiro `README.md`),
  organizado da seguinte forma:
  * Título do projeto.
  * Autoria:
    * Nome dos autores (primeiro e último) e respetivos números de aluno.
    * Informação de quem fez o quê no projeto. Esta informação é
      **obrigatória** e deve refletir os *commits* feitos no Git.
    * Indicação do repositório público Git utilizado. Esta indicação é
      opcional, pois podem preferir desenvolver o projeto num repositório
      privado.
  * Arquitetura da solução:
    * Descrição da solução, com breve explicação de como o programa foi
      organizado, indicação dos métodos/funções e enumerações criadas.
    * Um fluxograma mostrando a sequência do programa.
  * Referências, incluindo trocas de ideias com colegas, código aberto
    reutilizado (e.g., do StackOverflow) e bibliotecas de terceiros
    utilizadas. Devem ser o mais detalhados possível.
  * **Nota:** o relatório deve ser simples e breve, com informação mínima e
    suficiente para que seja possível ter uma boa ideia do que foi feito.
    Atenção aos erros ortográficos e à correta formatação [Markdown], pois
    ambos serão tidos em conta na nota final.

O projeto tem um peso de 3 valores na nota final da disciplina e será avaliado
de forma qualitativa. Isto significa que todos os objetivos têm de ser
parcialmente ou totalmente cumpridos. A cada objetivo, O1 a O5, será atribuída
uma nota entre 0 e 1. A nota do projeto será dada pela seguinte fórmula:

*N = 3 x O1 x O2 x O3 x O4 x O5 x D*

Em que *D* corresponde à nota da discussão e percentagem equitativa de
realização do projeto, também entre 0 e 1. Isto significa que se os alunos
ignorarem completamente um dos objetivos, não tenham feito nada no projeto ou
não comparerecem na discussão, a nota final será zero.

## Entrega

O projeto deve ser entregue por **grupos de 2 a 3 alunos** via Moodle até às
23h de 19 de abril de 2020. Deve ser submetido um ficheiro `zip` com a
solução completa do projeto, nomeadamente:

* Pasta escondida `.git` com o repositório Git local do projeto.
* Ficheiro `README.md` contendo o relatório do projeto em formato [Markdown].
* Ficheiro de imagem contendo o fluxograma. Este ficheiro deve ser incluído no
  repositório em modo Git LFS.

<!--* Documentação HTML ou CHM gerada com [Doxygen], [Sandcastle] ou ferramenta
  similar.-->

## Honestidade académica

Nesta disciplina, espera-se que cada aluno siga os mais altos padrões de
honestidade académica. Isto significa que cada ideia que não seja do
aluno deve ser claramente indicada, com devida referência ao respectivo
autor. O não cumprimento desta regra constitui plágio.

O plágio inclui a utilização de ideias, código ou conjuntos de soluções
de outros alunos ou indivíduos, ou quaisquer outras fontes para além
dos textos de apoio à disciplina, sem dar o respectivo crédito a essas
fontes. Os alunos são encorajados a discutir os problemas com outros
alunos e devem mencionar essa discussão quando submetem os projetos.
Essa menção **não** influenciará a nota. Os alunos não deverão, no
entanto, copiar códigos, documentação e relatórios de outros alunos, ou dar os
seus próprios códigos, documentação e relatórios a outros em qualquer
circunstância. De facto, não devem sequer deixar códigos, documentação e
relatórios em computadores de uso partilhado.

Nesta disciplina, a desonestidade académica é considerada fraude, com
todas as consequências legais que daí advêm. Qualquer fraude terá como
consequência imediata a anulação dos projetos de todos os alunos envolvidos
(incluindo os que possibilitaram a ocorrência). Qualquer suspeita de
desonestidade académica será relatada aos órgãos superiores da escola
para possível instauração de um processo disciplinar. Este poderá
resultar em reprovação à disciplina, reprovação de ano ou mesmo suspensão
temporária ou definitiva da ULHT.

*Texto adaptado da disciplina de [Algoritmos e
Estruturas de Dados][aed] do [Instituto Superior Técnico][ist]*

## Referências

* \[1\] **Wolf and Sheep**. Retrieved from
  <https://ludii.games/details.php?keyword=Wolf%20and%20Sheep>.
* \[2\] **Fox and Hounds**. Retrieved from
  <https://boardgamegeek.com/boardgame/148180/fox-and-hounds>.
* \[3\] Whitaker, R. B. (2016). **The C# Player's Guide** (3rd Edition).
  Starbound Software.
* \[4\] Albahari, J. (2017). **C# 7.0 in a Nutshell**. O’Reilly Media.
* \[5\] Dorsey, T. (2017). **Doing Visual Studio and .NET Code Documentation
  Right**. Visual Studio Magazine. Retrieved from
  <https://visualstudiomagazine.com/articles/2017/02/21/vs-dotnet-code-documentation-tools-roundup.aspx>.

## Licenças

* Este enunciado é disponibilizado através da licença [CC BY-NC-SA 4.0].

## Metadados

* Autor: [Nuno Fachada]
* Curso:  [Licenciatura em Videojogos][lamv]
* Instituição: [Universidade Lusófona de Humanidades e Tecnologias][ULHT]

[CC BY-NC-SA 4.0]:https://creativecommons.org/licenses/by-nc-sa/4.0/
[lamv]:https://www.ulusofona.pt/licenciatura/videojogos
[Nuno Fachada]:https://github.com/fakenmc
[ULHT]:https://www.ulusofona.pt/
[aed]:https://fenix.tecnico.ulisboa.pt/disciplinas/AED-2/2009-2010/2-semestre/honestidade-academica
[ist]:https://tecnico.ulisboa.pt/pt/
[Markdown]:https://guides.github.com/features/mastering-markdown/
[Doxygen]:https://www.stack.nl/~dimitri/doxygen/
[DocFX]:https://dotnet.github.io/docfx/
[XML]:https://docs.microsoft.com/dotnet/csharp/codedoc
[2º projeto de LP1 2018/19]:https://github.com/VideojogosLusofona/lp1_2018_p2_solucao
