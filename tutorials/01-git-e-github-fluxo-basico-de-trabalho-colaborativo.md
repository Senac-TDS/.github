# Git e GitHub: Fluxo Básico de Trabalho Colaborativo

## Configurando seu usuário

Antes de começar a utilizar Git e GitHub, é importante verificar se sua máquina já está configurada com seu nome e e-mail.

Abra o terminal e execute:

```bash
git config --list
```

Se aparecerem as propriedades abaixo com seus dados, a configuração já está concluída:

```text
user.name
user.email
```

Caso não estejam configuradas, execute os comandos abaixo substituindo pelos seus dados do GitHub:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
```

<br />

## Baixando um projeto do GitHub

Acesse o repositório desejado no GitHub.

1. Clique no botão verde **Code**.
2. Selecione a aba **HTTPS**.
3. Copie o endereço do repositório.

Execute o comando:

```bash
git clone https://github.com/organizacao/repositorio.git
```

Exemplo:

```bash
git clone https://github.com/Turma-Senac-TDS-1-Testes-e-PI/constack.git
```

O projeto será baixado para a pasta onde o terminal está aberto.

<br />

## Verificando em qual versão (branch) você está

Para visualizar a branch atual:

```bash
git branch
```

Exemplo:

```text
* main
```

O caractere `*` indica a branch atualmente selecionada.

Com o tempo, o projeto pode possuir várias branches:

```text
* main
  homolog
  feat/initial-setup
  feat/create-user
  fix/update-list
```

<br />

## Entendendo as branches

Os projetos normalmente possuem diferentes versões de trabalho.

### Main

```text
main
```

É a versão principal do sistema.

Normalmente contém o código mais estável e validado.

### Homologação

```text
homolog
```

Utilizada para testes internos antes de enviar para produção.

### Desenvolvimento

```text
develop
```

Utilizada pela equipe durante o desenvolvimento.

Para fins didáticos, trabalharemos principalmente com a branch:

```text
main
```

<br />

## Iniciando uma nova tarefa

Antes de criar uma nova branch, atualize sua branch principal.

Acesse a branch principal:

```bash
git checkout main
```

Baixe as alterações mais recentes:

```bash
git pull origin main
```

Agora crie sua branch:

```bash
git checkout -b feat/initial-setup
```

### Convenções utilizadas

#### Nova funcionalidade

```text
feat/
```

Exemplos:

```text
feat/login-page
feat/create-user
feat/product-list
```

#### Correção de problemas

```text
fix/
```

Exemplos:

```text
fix/login-error
fix/header-style
fix/update-table
```

Utilize nomes curtos e objetivos, preferencialmente em inglês.

<br />

## Enviando alterações para o GitHub

Após realizar suas alterações, execute:

### Adicionar arquivos

```bash
git add .
```

### Criar commit

```bash
git commit -m "feat: initial setup to share with class"
```

### Enviar para a nuvem

```bash
git push origin nome-da-branch
```

Exemplo:

```bash
git push origin feat/initial-setup
```

Após o envio, a branch aparecerá no GitHub.

<br />

## Criando uma Pull Request

Após concluir sua tarefa:

1. Acesse o GitHub.
2. Clique em **Pull Requests**.
3. Clique em **New Pull Request**.

Configure:

### Branch de destino (base)

```text
main
```

### Branch de origem (compare)

```text
sua-branch
```

Exemplo:

```text
feat/initial-setup
```

O GitHub exibirá todas as alterações realizadas.

Clique em:

```text
Create Pull Request
```

Após isso:

* Compartilhe a Pull Request para revisão.
* Aguarde aprovação.
* Realize ajustes se necessário.

Quando aprovada:

```text
Merge Pull Request
```

Suas alterações serão incorporadas à branch principal.

<br />

## Preciso utilizar alterações feitas por outra pessoa

Em equipes de desenvolvimento isso acontece frequentemente.

Primeiro atualize sua branch principal local:

```bash
git checkout main
git pull origin main
```

Depois retorne para sua branch:

```bash
git checkout minha-branch
```

Agora execute o merge:

```bash
git merge main
```

O Git irá comparar as diferenças e incorporar as atualizações da branch principal.

<br />

## Resolvendo conflitos

Conflitos acontecem quando duas pessoas alteram a mesma região do código.

Quando isso ocorrer:

1. Abra o editor de código.
2. Localize os arquivos com conflito.
3. Escolha a versão final que atenda ambas as alterações.

Após resolver os conflitos:

```bash
git add .
```

Continue o processo de merge:

```bash
git merge --continue
```

Em alguns casos será aberta uma tela para confirmar a mensagem do merge.

Para salvar e sair:

```text
:wq
```

<br />

## Atualizando sua branch na nuvem

Após concluir o merge:

```bash
git push origin minha-branch
```

Agora sua branch estará atualizada com:

* Suas alterações.
* Alterações dos colegas já enviadas para a branch principal.

<br />

## Fluxo resumido

### Nova tarefa

```bash
git checkout main
git pull origin main
git checkout -b feat/nova-funcionalidade
```

### Subir alterações

```bash
git add .
git commit -m "feat: descricao da alteracao"
git push origin minha-branch
```

### Atualizar branch com alterações da principal

```bash
git checkout main
git pull origin main

git checkout minha-branch
git merge main
git push origin minha-branch
```

### Finalizar tarefa

```text
Criar Pull Request
↓
Revisão
↓
Merge
```

<br />

## Boas práticas

* Atualize a branch principal antes de iniciar uma tarefa.
* Crie uma branch para cada tarefa.
* Utilize commits pequenos e objetivos.
* Utilize mensagens de commit claras.
* Solicite revisão antes de realizar merge.
* Resolva conflitos com atenção.
* Nunca desenvolva diretamente na branch principal.

Seguindo esse fluxo, o trabalho em equipe se torna mais organizado, seguro e próximo das práticas utilizadas no mercado de desenvolvimento de software.
