# Git e GitHub: Comandos Básicos do Dia a Dia

Após instalar e configurar o Git, é importante conhecer os comandos mais utilizados durante o desenvolvimento de projetos.

Este guia apresenta o fluxo básico utilizado em equipes de desenvolvimento.

<br />

## Verificando o status do projeto

Antes de realizar qualquer operação, é comum verificar a situação atual dos arquivos.

```bash
git status
```

Exemplo:

```text
On branch main

Changes not staged for commit:
  modified: index.html
```

Esse comando informa:

* Branch atual.
* Arquivos alterados.
* Arquivos preparados para commit.
* Arquivos não rastreados.

<br />

## Clonando um repositório

Para baixar um projeto do GitHub para sua máquina:

```bash
git clone https://github.com/organizacao/repositorio.git
```

Exemplo:

```bash
git clone https://github.com/Turma-Senac-TDS-1-Testes-e-PI/constack.git
```

Após a clonagem:

```bash
cd constack
```

<br />

## Verificando a branch atual

Para visualizar em qual branch você está:

```bash
git branch
```

Exemplo:

```text
* main
```

O caractere `*` indica a branch atualmente selecionada.

<br />

## Listando todas as branches

```bash
git branch
```

Exemplo:

```text
* main
  feat/create-user
  fix/header-style
```

Para visualizar também as branches remotas:

```bash
git branch -a
```

<br />

## Trocando de branch

Para mudar para uma branch existente:

```bash
git checkout nome-da-branch
```

Exemplo:

```bash
git checkout main
```

Ou:

```bash
git checkout feat/create-user
```

<br />

## Atualizando a branch principal

Antes de iniciar uma tarefa, atualize sua branch principal local.

Acesse a branch principal:

```bash
git checkout main
```

Atualize com a versão mais recente do servidor:

```bash
git pull origin main
```

<br />

## Criando uma nova branch

Após atualizar a branch principal:

```bash
git checkout -b feat/create-user
```

Exemplo:

```bash
git checkout -b feat/login-page
```

O comando cria a branch e já troca para ela automaticamente.

<br />

## Padrão de nomenclatura das branches

### Nova funcionalidade

Utilize o prefixo:

```text
feat/
```

Exemplos:

```text
feat/login-page
feat/create-user
feat/product-list
feat/dashboard
```

### Correção de problemas

Utilize o prefixo:

```text
fix/
```

Exemplos:

```text
fix/login-error
fix/header-style
fix/product-filter
fix/update-table
```

### Recomendações

* Utilize letras minúsculas.
* Separe palavras com hífen.
* Utilize nomes curtos e objetivos.
* Evite espaços e caracteres especiais.

<br />

## Adicionando alterações

Após modificar arquivos:

```bash
git add .
```

Esse comando adiciona todas as alterações para o próximo commit.

Também é possível adicionar apenas um arquivo:

```bash
git add index.html
```

<br />

## Criando um commit

Após adicionar os arquivos:

```bash
git commit -m "feat: create login page"
```

Exemplos:

```bash
git commit -m "feat: create user registration"
```

```bash
git commit -m "fix: correct login validation"
```

### Padrão recomendado

Nova funcionalidade:

```text
feat: descricao da alteracao
```

Correção:

```text
fix: descricao da alteracao
```

<br />

## Enviando alterações para o GitHub

Após realizar o commit:

```bash
git push origin nome-da-branch
```

Exemplo:

```bash
git push origin feat/login-page
```

Sua branch será enviada para o GitHub.

<br />

## Atualizando sua branch com alterações da principal

Em projetos colaborativos, outras pessoas podem realizar alterações enquanto você desenvolve.

Primeiro atualize a branch principal:

```bash
git checkout main
git pull origin main
```

Retorne para sua branch:

```bash
git checkout minha-branch
```

Realize o merge:

```bash
git merge main
```

Exemplo:

```bash
git checkout feat/login-page
git merge main
```

<br />

## Resolvendo conflitos

Caso duas pessoas alterem o mesmo trecho do código, o Git poderá gerar conflitos.

Após ajustar os arquivos:

```bash
git add .
```

Continue o merge:

```bash
git merge --continue
```

Se necessário, confirme a mensagem de merge.

<br />

## Enviando a branch atualizada

Após concluir o merge:

```bash
git push origin minha-branch
```

Exemplo:

```bash
git push origin feat/login-page
```

<br />

## Fluxo básico de desenvolvimento

### Atualizar projeto

```bash
git checkout main
git pull origin main
```

### Criar nova tarefa

```bash
git checkout -b feat/nova-funcionalidade
```

### Trabalhar e salvar alterações

```bash
git add .
git commit -m "feat: descricao da alteracao"
git push origin minha-branch
```

### Atualizar branch com alterações dos colegas

```bash
git checkout main
git pull origin main

git checkout minha-branch
git merge main

git push origin minha-branch
```

<br />

## Comandos mais utilizados

### Status

```bash
git status
```

### Clonar projeto

```bash
git clone URL_DO_REPOSITORIO
```

### Atualizar branch

```bash
git pull origin main
```

### Trocar de branch

```bash
git checkout nome-da-branch
```

### Criar branch

```bash
git checkout -b nome-da-branch
```

### Adicionar alterações

```bash
git add .
```

### Criar commit

```bash
git commit -m "feat: descricao"
```

### Enviar alterações

```bash
git push origin nome-da-branch
```

### Realizar merge

```bash
git merge main
```

### Listar branches

```bash
git branch
```

<br />

## Boas práticas

* Sempre atualize a branch principal antes de iniciar uma tarefa.
* Utilize uma branch para cada atividade.
* Faça commits pequenos e frequentes.
* Utilize mensagens de commit claras.
* Mantenha sua branch sincronizada com a principal.
* Nunca desenvolva diretamente na branch principal.
* Revise suas alterações utilizando `git status` antes de realizar commits.

Seguindo esse fluxo, o trabalho em equipe se torna mais organizado, seguro e alinhado às práticas utilizadas no mercado de desenvolvimento de software.
