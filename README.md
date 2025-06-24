<!--
Projeto de Recurso de Linguagens de Programação I 2019/2020 (c) by Nuno Fachada

Projeto de Recurso de Linguagens de Programação I 2019/2020 is licensed under a
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-nc-sa/4.0/>.
-->

# Projeto de Recurso de Linguagens de Programação I 2024/2025

## Introdução

Os grupos devem implementar o jogo **Wolf and Sheep** na forma de uma
aplicação de consola .NET 8.0 / C# 8.0. O jogo deve ser PvP (_Player vs Player_),
sem qualquer tipo de inteligência artificial.

## Regras do Jogo

* O jogo **Wolf and Sheep** é jogado num tabuleiro 8x8 apenas nos quadrados
  escuros.
* As quatro peças brancas, as ovelhas, são colocadas nos quadrados escuros num
  dos lados do tabuleiro.
* A peça preta, o lobo, é colocada em qualquer um dos quadrados escuros do lado
  oposto. A seguinte imagem mostra um possível tabuleiro inicial:

![Possível tabuleiro inicial, imagem obtida de https://ludii.games/details.php?keyword=Wolf%20and%20Sheep](img/board-start.png "Possível tabuleiro inicial")

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

## Funcionamento da Aplicação

O funcionamento exato da aplicação é da responsabilidade de cada estudante. No
entanto, quando a aplicação começa, **deve ser claro como cada jogador joga**,
ou seja, o jogo deve ter instruções muito claras sobre que teclas fazem o quê.
Por outras palavras, os estudantes devem ter em conta as regras importantes do
_game design_, pois serão tidas em conta na avaliação do projeto. **Toda a
interface de utilizador (UI) deve ser implementada exclusivamente com a
biblioteca [Spectre.Console](https://spectreconsole.net/)**.

<!--A aplicação deve funcionar em Windows, macOS e Linux. A melhor estratégia para
garantir que assim seja é testar o jogo em Linux (e.g., numa máquina virtual).
Algumas instruções incompatíveis com macOS e Linux são, por exemplo:

* [Console.Beep()](https://docs.microsoft.com/dotnet/api/system.console.beep)
* [Console.SetBufferSize()](https://docs.microsoft.com/dotnet/api/system.console.setbuffersize)
* [Console.SetWindowPosition()](https://docs.microsoft.com/dotnet/api/system.console.setwindowposition)
* [Console.SetWindowSize()](https://docs.microsoft.com/dotnet/api/system.console.setwindowsize)
* Entre outras.

As instruções que só funcionam em Windows têm a seguinte indicação na sua
documentação:

![The current operating system is not Windows.](img/notsupported.png "The current operating system is not Windows.")-->

## Organização do Código

O projeto deve estar devidamente organizado usando a abordagem MVC discutida nas
aulas, fazendo uso de classes, _structs_ e enumerações. Cada classe, _struct_ ou
enumeração deve ser colocada num ficheiro com o mesmo nome. Por exemplo, uma
classe chamada `Piece` deve ser colocada no ficheiro `Piece.cs`. A estrutura de
classes deve ser bem pensada usando a abordagem MVC, e [cada classe deve ter
uma responsabilidade específica e bem definida][SRP].

## Objetivos e Critério de Avaliação

Este projeto tem os seguintes objetivos:

* $O_1$ - Programa deve funcionar como especificado e deve ter em conta as
  regras básicas do _game design_.
* $O_2$ - Projeto e código bem organizados, nomeadamente:
  * Estrutura de classes bem pensada (ver secção [Organização do Código](#organização-do-código)).
  * Código devidamente comentado e indentado.
  * Inexistência de código "morto", que não faz nada, como por exemplo
    variáveis, propriedades ou métodos nunca usados.
  * Projeto compila e executa sem erros e/ou *warnings*.
* $O_3$ - Projeto adequadamente documentado com [comentários de documentação XML][XML].
* $O_4$ - Repositório Git deve refletir boa utilização do mesmo, nomeadamente:
  * Devem existir *commits* frequentes, _commits_ esses
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
  * *Assets* binários necessários, como é o caso da imagem do diagrama UML,
    devem ser integrados no repositório em modo Git LFS.
* $O_5$ - Relatório em formato [Markdown] (ficheiro `README.md`),
  organizado da seguinte forma:
  * Título do projeto.
  * Autoria:
    * Nome do autor (primeiro e último) e respetivo número de estudante.
    <!-- * Informação de quem fez o quê no projeto. Esta informação é
      **obrigatória** e deve refletir os *commits* feitos no Git.
    * Indicação do repositório Git utilizado. Esta indicação é
      opcional, pois podem preferir manter o repositório privado após a
      entrega. -->
  * Arquitetura da solução:
    * Descrição da solução, com breve explicação de como o código foi
      organizado, bem como dos algoritmos não triviais que tenham sido
      implementados.
    * Um diagrama UML de classes simples (i.e., sem indicação dos
      membros da classe) descrevendo a estrutura de classes.
  * Referências, incluindo trocas de ideias com colegas, código aberto
    reutilizado (e.g., do StackOverflow) e bibliotecas de terceiros
    utilizadas. Devem ser o mais detalhados possível.
  * **Nota:** o relatório deve ser simples e breve, com informação mínima e
    suficiente para que seja possível ter uma boa ideia do que foi feito.
    Atenção aos erros ortográficos e à correta formatação [Markdown], pois
    ambos serão tidos em conta na nota final.

O projeto tem um peso de 10 valores na nota final da disciplina e será avaliado
de forma qualitativa. Isto significa que todos os objetivos têm de ser
parcialmente ou totalmente cumpridos. A cada objetivo, O1 a O5, será atribuída
uma nota entre 0 e 1. A nota do projeto será dada pela seguinte fórmula:

$N = 10 \times O_1 \times O_2 \times O_3 \times O_4 \times O_5 \times D$

Em que $D$ corresponde à nota da discussão e percentagem equitativa de
realização do projeto, também entre 0 e 1. Isto significa que se os alunos
ignorarem completamente um dos objetivos, não tenham feito nada no projeto ou
não comparerecem na discussão, a nota final será zero.

## Entrega

O projeto deve ser entregue **individualmente** via Moodle até às
17h de 26 de junho de 2025. Deve ser submetido um ficheiro `zip` com a
solução completa do projeto, nomeadamente:

* Pasta escondida `.git` com o repositório Git local do projeto.
* Código do projeto (ficheiros `.cs`), ficheiro do projeto (`.csproj`) e, caso
  tenham criado uma solução, o ficheiro da solução (`.sln`).
* Ficheiro `README.md` contendo o relatório do projeto em formato [Markdown].
* Ficheiro de imagem contendo o diagrama UML, incluído no repositório em modo
  Git LFS. Em alternativa podem (e devem) usar o [Mermaid] para fazer o diagrama
  UML.

Não serão aceites projetos sem estes elementos e que não sejam entregues via
Moodle.

## Honestidade Académica

Nesta disciplina, espera-se que cada aluno siga os mais altos padrões de
honestidade académica. Isto significa que cada ideia que não seja do
aluno deve ser claramente indicada, com devida referência ao respetivo
autor. O não cumprimento desta regra constitui plágio.

O plágio inclui a utilização de ideias, código ou conjuntos de soluções
de outros alunos ou indivíduos, ou quaisquer outras fontes para além
dos textos de apoio à disciplina, sem dar o respetivo crédito a essas
fontes. Os alunos são encorajados a discutir os problemas com outros
alunos e devem mencionar essa discussão quando submetem os projetos.
Essa menção **não** influenciará a nota. Os alunos não deverão, no
entanto, copiar códigos, documentação e relatórios de outros alunos, ou dar os
seus próprios códigos, documentação e relatórios a outros em qualquer
circunstância. De facto, não devem sequer deixar códigos, documentação e
relatórios em computadores de uso partilhado.

**Sobre IAs generativas (e.g. ChatGPT):** Podem usar este tipo de ferramentas
para esclarecer dúvidas, ou até para obter sugestões de código e/ou organização
do projeto, desde de que as ideias e organização geral do mesmo sejam originais.
Podem também usar estas ferramentas para corrigir o Português (ou Inglês) do
relatório. Código, arquiteturas de projeto, e relatórios completamente escritos
por uma IA generativa serão facilmente detetáveis, pelo que sugerimos muito
cuidado no uso deste tipo de ferramentas. De qualquer forma, toda a utilização
de IA generativa deve ser indicada em forma de comentários no código e nas
explicitamente indicada no relatório.

Nesta disciplina, a desonestidade académica é considerada fraude, com
todas as consequências legais que daí advêm. Qualquer fraude terá como
consequência imediata a anulação dos projetos de todos os alunos envolvidos
(incluindo os que possibilitaram a ocorrência). Qualquer suspeita de
desonestidade académica será relatada aos órgãos superiores da escola
para possível instauração de um processo disciplinar. Este poderá
resultar em reprovação à disciplina, reprovação de ano ou mesmo suspensão
temporária ou definitiva da [Universidade Lusófona].

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

* Autores: [Nuno Fachada], [Afonso Oliveira]
* Curso:  [Licenciatura em Videojogos][lamv]
* Instituição: [Universidade Lusófona - Centro Universitário de Lisboa][Universidade Lusófona]

[CC BY-NC-SA 4.0]:https://creativecommons.org/licenses/by-nc-sa/4.0/
[lamv]:https://www.ulusofona.pt/licenciatura/videojogos
[Nuno Fachada]:https://github.com/fakenmc
[Afonso Oliveira]:https://github.com/afe-oliveira/
[Universidade Lusófona]:https://www.ulusofona.pt/
[aed]:https://fenix.tecnico.ulisboa.pt/disciplinas/AED-2/2009-2010/2-semestre/honestidade-academica
[ist]:https://tecnico.ulisboa.pt/pt/
[Markdown]:https://guides.github.com/features/mastering-markdown/
[XML]:https://docs.microsoft.com/dotnet/csharp/codedoc
[SRP]:https://en.wikipedia.org/wiki/Single_responsibility_principle
[Mermaid]:http://mermaid.js.org/
