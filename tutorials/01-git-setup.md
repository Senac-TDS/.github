# Git e GitHub: Instalação e Configuração Inicial

## O que é Git?

O Git é um sistema de controle de versão utilizado para registrar alterações em arquivos e permitir o trabalho colaborativo entre desenvolvedores.

Ele é amplamente utilizado em conjunto com o GitHub para armazenar projetos na nuvem.

Antes de começar a utilizar Git e GitHub, é necessário instalar o Git e configurar seu usuário na máquina.

<br />

## Instalando o Git

### Windows

1. Acesse o site oficial do Git.
2. Baixe o instalador para Windows.
3. Execute o arquivo baixado.
4. Mantenha as opções padrão durante a instalação.
5. Finalize o processo.

Após a instalação, abra o **Git Bash** ou o **Prompt de Comando**.

Verifique se a instalação foi concluída corretamente:

```bash
git --version
```

Exemplo:

```text
git version 2.51.0
```

<br />

### Linux (Debian, Ubuntu e derivados)

Atualize os repositórios:

```bash
sudo apt update
```

Instale o Git:

```bash
sudo apt install git -y
```

Verifique a instalação:

```bash
git --version
```

<br />

### Fedora

```bash
sudo dnf install git -y
```

Verifique a instalação:

```bash
git --version
```

<br />

### Arch Linux

```bash
sudo pacman -S git
```

Verifique a instalação:

```bash
git --version
```

<br />

## Criando uma conta no GitHub

Caso ainda não possua uma conta:

1. Acesse o GitHub.
2. Clique em **Sign Up**.
3. Informe seu e-mail.
4. Escolha um nome de usuário.
5. Defina uma senha.
6. Conclua o cadastro.

Após criar a conta, guarde:

```text
Nome de usuário
E-mail utilizado no cadastro
```

Essas informações serão utilizadas na configuração do Git.

<br />

## Configurando seu usuário

O Git registra quem realizou cada alteração no projeto.

Configure seu nome:

```bash
git config --global user.name "Seu Nome"
```

Exemplo:

```bash
git config --global user.name "Maria Silva"
```

Configure seu e-mail:

```bash
git config --global user.email "seuemail@exemplo.com"
```

Exemplo:

```bash
git config --global user.email "maria@email.com"
```

<br />

## Verificando a configuração

Para conferir todas as configurações atuais:

```bash
git config --list
```

Você deverá visualizar algo semelhante:

```text
user.name=Maria Silva
user.email=maria@email.com
```

Também é possível verificar individualmente:

### Nome

```bash
git config user.name
```

### E-mail

```bash
git config user.email
```

<br />

## Onde o Git salva essas configurações?

Ao utilizar a opção:

```bash
--global
```

As configurações ficam disponíveis para todos os projetos do usuário.

Exemplo:

```bash
git config --global user.name "Maria Silva"
git config --global user.email "maria@email.com"
```

Você só precisa realizar essa configuração uma única vez na máquina.

<br />

## Alterando suas informações

Caso seja necessário atualizar seu nome:

```bash
git config --global user.name "Novo Nome"
```

Para alterar o e-mail:

```bash
git config --global user.email "novoemail@exemplo.com"
```

<br />

## Configuração mínima concluída

Se os comandos abaixo retornarem seus dados corretamente:

```bash
git config user.name
git config user.email
```

Sua máquina já está pronta para utilizar Git e GitHub.

<br />

## Resumo

### Instalar Git

```bash
git --version
```

### Configurar nome

```bash
git config --global user.name "Seu Nome"
```

### Configurar e-mail

```bash
git config --global user.email "seuemail@exemplo.com"
```

### Verificar configurações

```bash
git config --list
```

<br />

## Boas práticas

* Utilize o mesmo e-mail cadastrado no GitHub.
* Configure seu nome completo para facilitar a identificação dos commits.
* Verifique suas configurações antes de iniciar um projeto.
* Não compartilhe suas credenciais do GitHub.
* Mantenha o Git atualizado.

Com o Git instalado e configurado, sua máquina estará pronta para clonar repositórios, criar branches, realizar commits e colaborar em projetos utilizando GitHub.
