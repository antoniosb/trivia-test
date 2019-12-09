# Boas vindas ao repositório do projeto de Trivia!

Você já usa o GitHub diariamente para desenvolver os exercícios, certo? Agora, para desenvolver os projetos, você deverá seguir as instruções a seguir. Fique atento a cada passo, e se tiver qualquer dúvida, nos envie por _Slack_! #vqv 🚀

Aqui você vai encontrar os detalhes de como estruturar o desenvolvimento do seu projeto a partir desse repositório, utilizando uma branch específica e um _Pull Request_ para colocar seus códigos.

## O que deverá ser desenvolvido

Você deverá desenvolver um jogo de perguntas e respostas baseado no jogo **Trivia** (tipo um show do milhão americano rs) utilizando React e Redux.

O app começa com uma tela onde o jogador coloca seu nome. Logo após, ele é redirecionado para o jogo onde ele deve escolher uma das respostas disponiveis para cada uma das perguntas. Cada acerto dá ao jogador 10 pontos que deverão ser computados num placar no header da aplicação. Após 10 perguntas respondidas, o jogador é redirecionado para uma tela de score, onde o texto mostrado vai depender do número de acertos.

Você pode acessar um protótipo no link abaixo:

https://www.figma.com/file/MxuXDNVbiZb69kM9NI0jhZ/Trivia-project?node-id=0%3A1


Lembre-se de escrever testes unitários e sinta-se livre para alterar a UI, só respeito os atributos `data-testid`, eles serão usados na correção do exercicio. 

Para ver os comentários sobre cada componente, basta clickar no icone de comentários no Figma (lado esquerdo superior).

![image](https://res.cloudinary.com/drdpedroso/image/upload/c_scale,w_400/v1575815877/Screenshot_2019-12-08_at_11.37.25_kzt7rl.png)

## Desenvolvimento e testes

Este repositório já contem um _template_ com um App React criado e configurado. Após clonar o projeto e instalar as dependências (mais sobre isso abaixo), você não precisará realizar nenhuma configuração adicional. Você deverá completar este _template_ implementando os requisitos listados na próxima seção.

Será necessário criar quatro `React Components`:

   - Header
   - MovieList
   - MovieCard
   - Rating

Cada componente representa uma parte específica do site, conforme ilustrado abaixo:

![image](site-outline.png)

Todos os componentes devem ser criados dentro da pasta `src/components`. **É importante que seus componentes tenham exatamente os nomes listados acima**.

Todos os requisitos do projeto serão testados automaticamente. Os testes para cada requisitos estão no arquivo `src/App.test.js`. Gaste um tempo lendo-o para entender como os testes estão organizados.

Para executar os testes localmente, digite no terminal o comando `npm test`. Inicialmente, seus testes estarão assim:

![image](failing-tests.png)

A primeira parte da saída mostra um sumário de cada teste e seu status. Um ❌ representa um teste falhando, enquanto um ✅ representa um teste correto. Naturalmente, no início todos os testes estarão falhando.

Abaixo do sumário, para cada teste falhando, há uma mensagem explicativa sobre o motivo que causou a falha do teste, assim como a linha em que a falha ocorreu. Na imagem, vemos que o teste falha porque o componente `Header`, utilizado na linha 38, não está definido.

Se fizermos uma implementação simples do componente `Header`, que não renderiza nada:

```jsx
import React from 'react';

class Header extends React.Component {
  render() {
  }
}

export default Header;
```

E descomentarmos a linha que importa o componente `Header` em `App.test.js`:

```js
// import App from './App';
import Header from './components/Header';
// import MovieCard from './components/MovieCard';
// import MovieList from './components/MovieList';
// import Rating from './components/Rating';
```

Veremos que o primeiro teste agora passa:

![image](first-green-test.png)

Quando seu projeto estiver terminado, todos os testes deverão estar passando:

![image](all-green.png)


## Requisitos do projeto

⚠️ Lembre-se que o seu projeto só será avaliado se estiver passando pelos _checks_ do **CodeClimate** e do **TravisCI**

Nesse projeto, o jogador deve conseguir completar o jogo e conseguir ver seu placar depois de responder todas as 5 perguntas.

### Tela de inicio:
   - Todos os elementos devem respeitar os atributos descritos no protótipo.
   - O jogador deve conseguir escrever seu nome no input de texto.
   - Após clickar no botão "Jogar", ele deve ser redirecionado para a tela do jogo.
   - Ao clickar no botão "Jogar", uma requisição para a API do Trivia deve ser feita para pegar o token de jogador.
   - O token deve ser armazenado na aplicação e enviado a todas as requisições seguintes.
### Tela do jogo:
   - Todos os elementos devem respeitar os atributos descritos no protótipo.
   - O header deve conter o nome do usuario e o placar.
   - A perguntas e suas respostas devem ser recebidas da API do Trivia.
   - A categoria da pergunta junto com seu texto devem ser mostradas para o usuario.
   - As respostas devem ser mostradas em ordem aleatoria.
   - 
   - Para perguntas com `type:"boolean"`, mostrar somente 2 campos (uma para cada resposta possivel).
   - Para perguntas com `type:"multiple"`, mostrar a quantidade necessaria de campos (uma para cada resposta possivel).
   - Ao clickar na resposta correta, ela deve ficar verde e as incorretas, vermelhas.
   - Ao clickar na resposta incorreta, todas as incorretas devem ficar vermelhas e a correta, verde.
   - Ao clickar na resposta correta, 10 pontos devem ser somados no placar do jogador.
   - Ao clickar na resposta incorreta, nenhum ponto é computador no placar.
   - Após responder 5 perguntas, o jogador deve ser redirecionado para a tela de feedback.
### Tela de feedback:


## Instruções para entregar seu projeto:

### ANTES DE COMEÇAR A DESENVOLVER:

1. Clone o repositório
  * `git clone git@github.com:tryber/sd-01-week10-movie-card-library.git`.
  * Entre na pasta do repositório que você acabou de clonar:
    * `cd sd-01-week10-movie-card-library`

2. Instale as dependências, inicialize o projeto e rode os testes
  * Instale as dependências:
    * `npm install`
  * Inicialize o projeto:
    * `npm start` (uma nova página deve abrir no seu navegador com um texto simples)
  * Verifique que os testes estão executando:
    * `npm test` (os testes devem rodar e falhar)

3. Crie uma branch a partir da branch `master`
  * Verifique que você está na branch `master`
    * Exemplo: `git branch`
  * Se não estiver, mude para a branch `master`
    * Exemplo: `git checkout master`
  * Agora, crie uma branch onde você vai guardar os `commits` do seu projeto
    * Você deve criar uma branch no seguinte formato: `nome-de-usuario-nome-do-projeto`
    * Exemplo: `git checkout -b joaozinho-movie-card-library`

4. Crie a pasta `components` dentro da pasta `src` e um arquivo `Header.jsx` dentro dessa pasta:
  * Verifique que você está na raiz do projeto
    * Exemplo: `pwd` -> o retorno vai ser algo tipo _/Users/joaozinho/code/**sd-01-week10-movie-card-library**_
  * Crie a pasta `components` e o arquivo `Header.jsx`
    * Exemplo:
      * `mkdir src/components`
      * `touch src/components/Header.jsx`
      * `echo "// Iniciando o projeto 🚀" > src/components/Header.jsx`

5. Adicione as mudanças ao _stage_ do Git e faça um `commit`
  * Verifique que as mudanças ainda não estão no _stage_
    * Exemplo: `git status` (deve aparecer listada a pasta _components_ em vermelho)
  * Adicione o novo arquivo ao _stage_ do Git
      * Exemplo:
        * `git add .` (adicionando todas as mudanças - _que estavam em vermelho_ - ao stage do Git)
        * `git status` (deve aparecer listado o arquivo _components/Header.jsx_ em verde)
  * Faça o `commit` inicial
      * Exemplo:
        * `git commit -m 'iniciando o projeto. VAMOS COM TUDO :rocket:'` (fazendo o primeiro commit)
        * `git status` (deve aparecer uma mensagem tipo _nothing to commit_ )

6. Adicione a sua branch com o novo `commit` ao repositório remoto
  * Usando o exemplo anterior: `git push -u origin joaozinho-movie-cards-library`

7. Crie um novo `Pull Request` _(PR)_
  * Vá até a página de _Pull Requests_ do [repositório no GitHub](https://github.com/tryber/sd-01-week10-movie-cards-library/pulls)
  * Clique no botão verde _"New pull request"_
  * Clique na caixa de seleção _"Compare"_ e escolha a sua branch **com atenção**
  * Clique no botão verde _"Create pull request"_
  * Adicione uma descrição para o _Pull Request_ e clique no botão verde _"Create pull request"_
  * **Não se preocupe em preencher mais nada por enquanto!**
  * Volte até a [página de _Pull Requests_ do repositório](https://github.com/tryber/sd-01-week10-movie-cards-library/pulls) e confira que o seu _Pull Request_ está criado

---

### DURANTE O DESENVOLVIMENTO

* ⚠ **LEMBRE-SE DE CRIAR TODOS OS ARQUIVOS DENTRO DA PASTA COM O SEU NOME** ⚠


* Faça `commits` das alterações que você fizer no código regularmente

* Lembre-se de sempre após um (ou alguns) `commits` atualizar o repositório remoto

* Os comandos que você utilizará com mais frequência são:
  1. `git status` _(para verificar o que está em vermelho - fora do stage - e o que está em verde - no stage)_
  2. `git add` _(para adicionar arquivos ao stage do Git)_
  3. `git commit` _(para criar um commit com os arquivos que estão no stage do Git)_
  5. `git push -u nome-da-branch` _(para enviar o commit para o repositório remoto na primeira vez que fizer o `push` de uma nova branch)_
  4. `git push` _(para enviar o commit para o repositório remoto após o passo anterior)_

---

### DEPOIS DE TERMINAR O DESENVOLVIMENTO

Para **"entregar"** seu projeto, siga os passos a seguir:

* Vá até a página **DO SEU** _Pull Request_, adicione a label de _"code-review"_ e marque seus colegas
  * No menu à direita, clique no _link_ **"Labels"** e escolha a _label_ **code-review**
  * No menu à direita, clique no _link_ **"Assignees"** e escolha **o seu usuário**
  * No menu à direita, clique no _link_ **"Reviewers"** e digite `students`, selecione o time `tryber/students`

Se ainda houver alguma dúvida sobre como entregar seu projeto, [aqui tem um video explicativo](https://vimeo.com/362189205).

---

### REVISANDO UM PULL REQUEST

⚠⚠⚠

À medida que você e os outros alunos forem entregando os projetos, vocês serão alertados **via Slack** para também fazer a revisão dos _Pull Requests_ dos seus colegas. Fiquem atentos às mensagens do _"Pull Reminders"_ no _Slack_!

Os monitores também farão a revisão de todos os projetos, e irão avaliar tanto o seu _Pull Request_, quanto as revisões que você fizer nos _Pull Requests_ dos seus colegas!!!

Use o material que você já viu sobre [Code Review](https://course.betrybe.com/real-life-engineer/code-review/) para te ajudar a revisar os projetos que chegaram para você.
