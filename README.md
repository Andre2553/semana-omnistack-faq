<h1 align="center">
    <img alt="Semana Omnistack" src="./.github/assets/download.svg" width="400px" />
</h1>

<h2 align="center">
  FAQ referente à Semana Omnistack
</h2>

## Issues

- [00 - Workshop Iniciantes](#00-workshop-iniciantes)
  - [Onde estão os arquivos do Workshop?](#onde-estão-os-arquivos-do-workshop)
  - [Onde encontro a logo?](#onde-encontro-a-logo)
- [01 - Ambiente](#01-ambiente)
  - [Erro app.ps1 não pode ser carregado](#erro-appps1-não-pode-ser-carregado)
  - [Erro npm ERR! code EPERM ao tentar executar um comando](#erro-npm-err-code-eperm-ao-tentar-executar-um-comando)
  - [Erro ENOENT quando executa o comando npm start no Frontend](#erro-enoent-quando-executa-o-comando-npm-start-no-frontend)
  - [Dificuldade para sair da system32/navegar entre as pastas](#dificuldade-para-sair-da-system32navegar-entre-as-pastas)
  - [Erro na instalação do chocolatey: Impossível converter o valor '3312' para o tipo 'System...](#erro-na-instalação-do-chocolatey-impossível-converter-o-valor-3312-para-o-tipo-system)
  - [JSON do Diego no Google Chrome está com aparência diferente](#json-do-diego-no-google-chrome-está-com-aparência-diferente)
  - [Erro Error: listen EADDRINUSE :::3333](#erro-error-listen-eaddrinuse-3333)
  - [Erro System limit for number of file watchers reached](#erro-system-limit-for-number-of-file-watchers-reached)
  - [Erro Could not install from.. ao tentar executar o create-react-app com o npx](#erro-could-not-install-from-ao-tentar-executar-o-create-react-app-com-o-npx)
  - [Erro O termo node não é reconhecido como nome de cmdlet ou O termo npm não é reconhecido como nome de cmdlet](#erro-o-termo-node-não-é-reconhecido-como-nome-de-cmdlet-ou-o-termo-npm-não-é-reconhecido-como-nome-de-cmdlet)  
- [02 - Base da Aplicação](#02-base-da-aplicação)
  - [Erro Error: Undefined binding(s) when compiling FIRST](#erro-error-undefined-bindings-when-compiling-first)
  - [Erro Make sure you configure your 'user.name' and 'user.email' in git](#erro-make-sure-you-configure-your-username-and-useremail-in-git)
  - [Erro nas migrações](#erro-nas-migrações)
  - [Erro ao utilizar o Postman ou o Insomnia](#erro-ao-utilizar-o-postman-ou-o-insomnia)
- [03 - Interface Web](#03-interface-web)
- [04 - App Mobile](#app-mobile)

### **00 - Workshop Iniciantes**

#### Onde estão os arquivos do Workshop?
https://gist.github.com/maykbrito/4ed2051eab0d6f8dc96083a00996abf4

#### Onde encontro a logo?
https://i.imgur.com/27pdZLL.png

### **01 - Ambiente**

#### Erro `app.ps1 não pode ser carregado`

Execute esse comando como administrador no seu powershell:

```bash
Set-ExecutionPolicy Unrestricted
```
E depois tente executar o comando anterior novamente

#### Erro `npm ERR! code EPERM` ao tentar executar um comando

Execute o comando fora do VSCode com o seu Powershell em modo Administrador

#### Erro `ENOENT` quando executa o comando `npm start` no Frontend 

Tente adicionar o seguinte na variável de ambiente Path:

`C:\Windows\System32`

#### Dificuldade para sair da system32/navegar entre as pastas

Execute os comandos no terminal:

1 - `cd ~/` (Isso irá pra usa pasta de **Documentos**)
2 - `mkdir semanaomnistack11` (Isso irá criar um diretório chamado **omnistack11**) 
3 - `cd semanaomnistack11`
4 - `mkdir aulas`
5 - `cd aulas` 
6 - `mkdir backend`
7 - `cd backend`

#### Erro na instalação do chocolatey: `Impossível converter o valor '3312' para o tipo 'System...`

1 - Abra o Powershell no modo administrador e execute `get-host`. 

2 - Na linha `Version` verifique se a versão do seu Powershell está abaixo da 3. Se estiver, siga os passos abaixo.

3 - Baixe o Windows Management Framework 3.0 (https://www.microsoft.com/en-us/download/details.aspx?id=34595) para atualizar seu Powershell.

4 - Reinicie sua máquina e tente instalar o chocolatey novamente usando o Powershell no modo administrador

#### JSON do Diego no Google Chrome está com aparência diferente

Instale a Extensão JSON Viewer - https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh/related?hl=pt-BR

#### Erro `Error: listen EADDRINUSE :::3333`

A porta já está em uso, para resolver isso você pode encerrar o processo que está rodando nessa porta executando o comando:

- Linux
```bash
pkill node
```
-  Windows
```bash
taskkill /f /im node.exe
```

#### Erro `System limit for number of file watchers reached`

Execute o seguinte comando no terminal:

```bash
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

#### Erro `Could not install from..` ao tentar executar o create-react-app com o npx

Esse erro está acontecendo porque o seu usuário tem um espaço no nome. Mas você pode fazer o seguinte:

```bash
npm install -g create-react-app
```

E depois você pode rodar o comando:

```bash
create-react-app frontend
```

Se não der certo, tente pelo Yarn. Abra o powershell como admin e rode o comando:

```bash
cinst yarn
```

Feche o powershell e abra novamente como admin. Execute:

```bash
yarn -v
```

Se retornar a versão do yarn, funcionou corretamente. Por fim rode:

```bash
yarn global add create-react-app
npm uninstall -g create-react-app
create-react-app frontend
```

#### Erro `O termo node não é reconhecido como nome de cmdlet` ou `O termo npm não é reconhecido como nome de cmdlet`

Tente reiniciar o powershell e abrir como administrador. Se não funcionar, sigam esses passos:

1 - Aperte a tecla Windows e na barra de pesquisa busque por Variáveis de ambiente e abra o a primeira opção do sistema;
2 - Na janela que for aberta clique em Variáveis de Ambiente;
3 - Na janela das variáveis use a segunda opção, Variáveis do Sistema e procure pela variável Path e clique em Editar ;
4 - A janela com os valores das variáveis de ambiente pode abrir de 2 formas: a primeira é uma janela com os valores separados por linha, se for essa opção basta adicionar mais uma linha com o valor: `C:\Program Files\nodejs`. Mas caso abra apenas uma pequena janela com uma linha só com os valores separados por `;` vá até o final dessa linha, adicione mais um `;`  e depois o valor `C:\Program Files\nodejs`, lembrando que não pode ter espaço após o `;`  que você adicionou.
5 - Feito isso salve, reinicie o seu PowerShell e tudo deve estar funcionando.

Se mesmo assim não tiver funcionando, tente mais esses passos (lembre-se de tomar a mesma precaução com o `;`):

`C:\Program Files\nodejs\node_modules\npm\bin`

e

`C:\Users\{yourName}\AppData\Roaming\npm`

obs: Troque o `{yourName}` do comando acima pelo nome do usuário da sua máquina

### **02 - Base da Aplicação**

#### Erro `Error: Undefined binding(s) when compiling FIRST`

Verifique se você está passando as informações corretamente no body do insomnia e se está desestruturando corretamente do `request.body`. Se o erro persistir, apague a requisição no insomnia e a crie novamente.

#### Erro `Make sure you configure your 'user.name' and 'user.email' in git`

Execute esses comandos no terminal (Lembre de trocar John Doe para seu nome, e o e-mail para o email que você utiliza no github):
```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

#### Erro nas migrações

Provavelmente é algum erro de digitação na hora de criar as migrations, caso queiram comparar, podem utilizar esse repositório para ver a diferença entre os códigos:

https://github.com/josepholiveira/be-the-hero/

Se mesmo assim o erro persistir, siga os seguintes passos:

1 - Execute o comando: 
```bash
npx knex migrate:rollback --all
```
2 - Delete o arquivo `db.sqlite` (caso o arquivo não esteja aparecendo, reinicie o VSCODE)

3 - Rode o comando 
```bash
npx knex migrate:list
```
4 - Rode o comando 
```bash
npx knex migrate:latest
```

#### Erro ao utilizar o Postman ou o Insomnia

Você pode utilizar o https://postwoman.io/.

Para isso, você precisa sempre lembrar de usar 127.0.0.1 no lugar de localhost e adicionar o CORS no seu backend (se você não adicionar ocorrer o erro **Error: Network Error. Check console for details**):

1 - Adicione o CORS executando o seguinte comando no terminal: 
```bash
npm install cors
```
2 - No seu arquivo index.js, adicione o seguinte no início do arquivo: 
```js
const cors = require("cors");
```
3 - Logo após o seu `const app = express();` adicione o seguinte:
```js
app.use(cors());
```

### **03 - Interface Web**

### **04 - App Mobile**
