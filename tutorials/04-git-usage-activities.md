# Git e GitHub: Uso em atividades das UC's

Este fluxo foi definido para organizar as entregas das atividades da disciplina e facilitar o processo de correção.

Neste modelo, cada aluno possui sua própria branch permanente e trabalha exclusivamente dentro dela.

A branch principal do projeto será utilizada apenas pelo professor.

<br />

## Estrutura das Branches

### Branch Principal

```text
main
```

Utilizada exclusivamente pelo professor.

Nenhum aluno deverá criar commits, realizar merges ou desenvolver diretamente nesta branch.

<br />

### Branch do Aluno

Cada aluno possuirá uma branch própria:

```text
aluno/nome-do-aluno
```

Exemplos:

```text
aluno/maria-silva
aluno/joao-santos
aluno/pedro-lima
```

Esta branch representa o espaço principal de trabalho do aluno durante toda a disciplina.

<br />

## Regra Principal

O aluno nunca desenvolverá diretamente na sua branch principal.

Para cada atividade, deverá criar uma branch específica.

Fluxo:

```text
aluno/nome-do-aluno
            │
            └── aluno/nome-do-aluno/atividade-01
```

<br />

## Iniciando uma Nova Atividade

Primeiramente, atualize sua branch principal de aluno.

Acesse sua branch:

```bash
git checkout aluno/nome-do-aluno
```

Atualize-a:

```bash
git pull origin aluno/nome-do-aluno
```

<br />

### Criando a branch da atividade

Crie uma nova branch a partir da sua branch principal:

```bash
git checkout -b aluno/nome-do-aluno/atividade-01
```

Exemplos:

```text
aluno/maria-silva/atividade-01
aluno/maria-silva/atividade-02
aluno/maria-silva/atividade-03
```

ou

```text
aluno/joao-santos/atividade-01
aluno/joao-santos/atividade-02
```

Após criar a branch, todo o desenvolvimento será realizado nela.

<br />

## Desenvolvendo a Atividade

Durante o desenvolvimento:

```bash
git add .
```

```bash
git commit -m "atividade 01: implementa algoritmo de cálculo"
```

Realize quantos commits forem necessários.

<br />

## Enviando a Atividade para o GitHub

Após finalizar:

```bash
git push origin aluno/nome-do-aluno/atividade-01
```

Exemplo:

```bash
git push origin aluno/maria-silva/atividade-01
```

<br />

## Criando a Pull Request

Quando a atividade estiver concluída:

Crie uma Pull Request com a seguinte configuração:

### Base

```text
aluno/nome-do-aluno
```

### Compare

```text
aluno/nome-do-aluno/atividade-01
```

Exemplo:

```text
Base:
aluno/maria-silva

Compare:
aluno/maria-silva/atividade-01
```

Visualmente:

```text
aluno/maria-silva/atividade-01
                    │
                    ▼
          aluno/maria-silva
```

<br />

## Processo de Correção

Após criar a Pull Request:

1. Solicite revisão ao professor.
2. Aguarde a análise da atividade.
3. Verifique os comentários realizados.

<br />

### Caso sejam solicitadas correções

Continue trabalhando na mesma branch da atividade.

Exemplo:

```text
aluno/maria-silva/atividade-01
```

Realize os ajustes:

```bash
git add .
git commit -m "corrige observacoes da atividade 01"
git push origin aluno/maria-silva/atividade-01
```

A Pull Request será atualizada automaticamente.

Após isso, aguarde nova revisão.

<br />

### Caso a atividade seja aprovada

O professor realizará o merge da Pull Request.

```text
aluno/maria-silva/atividade-01
                    │
                    ▼
          aluno/maria-silva
```

Após o merge, a atividade passa a fazer parte da branch principal do aluno.

<br />

## Iniciando a Próxima Atividade

Após a aprovação da atividade anterior:

Atualize sua branch principal:

```bash
git checkout aluno/nome-do-aluno
```

```bash
git pull origin aluno/nome-do-aluno
```

Crie a próxima branch:

```bash
git checkout -b aluno/nome-do-aluno/atividade-02
```

Fluxo:

```text
aluno/maria-silva
          │
          ├── atividade-01 ✓
          │
          └── atividade-02
```

<br />

## O que o Aluno Não Deve Fazer

### Não desenvolver diretamente na branch do aluno

Evite:

```text
aluno/nome-do-aluno
```

Toda atividade deve possuir uma branch própria.

<br />

### Não abrir Pull Request para a main

Evite:

```text
aluno/maria-silva
        │
        ▼
      main
```

A branch:

```text
main
```

é utilizada exclusivamente pelo professor.

<br />

### Não realizar merges manualmente

O merge das atividades será realizado pelo professor após a correção.

<br />

## Fluxo Resumido

### Nova atividade

```bash
git checkout aluno/nome-do-aluno
git pull origin aluno/nome-do-aluno

git checkout -b aluno/nome-do-aluno/atividade-01
```

<br />

### Desenvolver e enviar

```bash
git add .
git commit -m "descricao da atividade"
git push origin aluno/nome-do-aluno/atividade-01
```

<br />

### Abrir Pull Request

```text
Compare:
aluno/nome-do-aluno/atividade-01

Base:
aluno/nome-do-aluno
```

<br />

### Correção

```text
Professor revisa
       │
       ├── Solicita ajustes
       │
       └── Aprova
              │
              ▼
            Merge
```

<br />

## Fluxo Visual Completo

```text
main
 │
 └── (Professor)

aluno/maria-silva
        │
        ├── atividade-01
        │         │
        │         └── PR
        │                ▼
        │      aluno/maria-silva
        │
        ├── atividade-02
        │         │
        │         └── PR
        │                ▼
        │      aluno/maria-silva
        │
        └── atividade-03
```

<br />

## Boas Práticas

* Crie uma branch para cada atividade.
* Utilize nomes padronizados para as branches.
* Faça commits frequentes.
* Envie sua branch para o GitHub antes de abrir a Pull Request.
* Leia atentamente os comentários da correção.
* Realize os ajustes na mesma branch da atividade.
* Atualize sua branch principal antes de iniciar uma nova atividade.
* Nunca desenvolva diretamente na `main`.
* Nunca realize merges por conta própria.

Seguindo esse fluxo, cada atividade ficará organizada, rastreável e simples de corrigir, permitindo que o professor acompanhe a evolução do aluno ao longo do curso.
