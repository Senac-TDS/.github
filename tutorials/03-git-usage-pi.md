# Git e GitHub: Uso no Projeto Integrador

Durante o desenvolvimento do Projeto Integrador, utilizaremos um fluxo de trabalho baseado em branches para organizar as atividades da equipe, reduzir conflitos e facilitar o processo de revisão de código.

<br />

## Estrutura de Branches

O projeto utilizará duas branches principais:

### Main

```text
main
```

Representa a versão oficial do projeto.

Deve conter apenas funcionalidades revisadas, testadas e aprovadas pela equipe.

### Homologação

```text
homolog
```

Representa o ambiente de testes da equipe.

Todas as funcionalidades desenvolvidas pelos integrantes deverão passar por essa branch antes de serem incorporadas à versão principal.

<br />

## Fluxo de Desenvolvimento

### 1. Atualizar a branch principal

Antes de iniciar qualquer atividade:

```bash
git checkout main
git pull origin main
```

<br />

### 2. Criar uma branch para sua tarefa

A nova branch deve ser criada a partir da branch principal.

#### Nova funcionalidade

```bash
git checkout -b feat/nome-da-funcionalidade
```

Exemplos:

```text
feat/login
feat/cadastro-cliente
feat/dashboard
```

#### Correção de problema

```bash
git checkout -b fix/nome-do-problema
```

Exemplos:

```text
fix/login-error
fix/menu-mobile
fix/validacao-cadastro
```

<br />

### 3. Desenvolver a atividade

Durante o desenvolvimento:

```bash
git add .
git commit -m "feat: descricao da alteracao"
```

Ou:

```bash
git commit -m "fix: descricao da correcao"
```

<br />

### 4. Enviar a branch para o GitHub

```bash
git push origin nome-da-branch
```

Exemplo:

```bash
git push origin feat/login
```

<br />

## Finalizando uma tarefa

Quando a funcionalidade estiver concluída:

### Criar uma Pull Request

A Pull Request deverá ser criada da sua branch para a branch:

```text
homolog
```

Exemplo:

```text
feat/login
        ↓
      homolog
```

ou

```text
fix/menu-mobile
        ↓
      homolog
```

Para aprender o processo completo de criação da Pull Request, consulte o tutorial:

```text
Git e GitHub: Fluxo Básico de Trabalho Colaborativo
```

Na seção:

```text
Criando uma Pull Request
```

<br />

## Processo de Revisão

Após criar a Pull Request:

1. Solicite revisão para um colega da equipe.
2. Aguarde análise do código.
3. Verifique os comentários realizados.

### Caso seja aprovada

A Pull Request poderá ser mesclada na branch:

```text
homolog
```

```text
feat/login
        ↓
      homolog
```

### Caso sejam solicitados ajustes

Realize as correções na mesma branch.

Exemplo:

```text
feat/login
```

Faça novos commits:

```bash
git add .
git commit -m "fix: adjust login validation"
git push origin feat/login
```

A Pull Request será atualizada automaticamente.

Após isso:

* Solicite nova revisão.
* Aguarde nova aprovação.

<br />

## Fluxo de Trabalho da Equipe

```text
main
  │
  ├── feat/login
  ├── feat/dashboard
  ├── feat/client-register
  └── fix/menu-mobile
```

Após aprovação:

```text
feat/*
fix/*
    │
    ▼
 homolog
```

A branch de homologação passa a reunir todas as funcionalidades aprovadas para testes integrados.

<br />

## Liberação de Versão

Quando a equipe decidir disponibilizar uma nova versão do sistema:

O líder da equipe deverá criar uma Pull Request:

```text
homolog
      ↓
     main
```

Exemplo:

```text
Base: main
Compare: homolog
```

Após validar os testes:

```text
Merge Pull Request
```

As alterações serão incorporadas à branch principal.

<br />

## Importante

Após realizar o merge:

### Não excluir a branch homolog

A branch:

```text
homolog
```

deve permanecer ativa durante todo o projeto.

Ela continuará sendo utilizada para:

* Receber novas funcionalidades.
* Centralizar testes.
* Preparar futuras versões.

Fluxo contínuo:

```text
feat/*
fix/*
    │
    ▼
 homolog
    │
    ▼
   main
```

<br />

## Fluxo Resumido

### Desenvolvedor

```text
main
  │
  └── cria feat/* ou fix/*
            │
            ├── desenvolve
            ├── commit
            ├── push
            │
            └── PR para homolog
```

### Revisão

```text
PR
 │
 ├── Reprovada → Ajustar → Nova revisão
 │
 └── Aprovada → Merge em homolog
```

### Liberação de versão

```text
homolog
    │
    └── PR para main
            │
            └── Merge realizado pelo líder
```

<br />

## Boas Práticas

* Sempre crie uma branch para cada tarefa.
* Nunca desenvolva diretamente na `main`.
* Nunca desenvolva diretamente na `homolog`.
* Solicite revisão antes de realizar merges.
* Utilize nomes padronizados com `feat/` e `fix/`.
* Faça commits pequenos e objetivos.
* Teste sua funcionalidade antes de abrir uma Pull Request.
* Mantenha sua branch atualizada com as alterações da equipe.
* Preserve a branch `homolog` durante todo o projeto.

Seguindo esse fluxo, a equipe terá maior controle sobre as entregas, melhor qualidade de código e um processo de integração mais próximo das práticas utilizadas em ambientes profissionais.
