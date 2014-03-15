# Deploy automatizado de instalações Wordpress

Esse repositório mantém um software que instala automaticamente
servidores com o Wordpress funcionando com alto desempenho.

Esse software reproduz em alto nível o mesmo sistema de configuração
utilizado por Ewan Leith, em seu artigo
[10 Million hits a day with WordPress using a $15 server](http://ewan.im/900/10-million-hits-a-day-with-wordpress-using-a-15-server). Além
de desempenho, essa instalação também visa segurança e estabilidade,
portanto várias outras técnicas estão sendo ou vão ser aplicadas para
garantir que, com poucos comandos, qualquer pessoa tenha um servidor
com Wordpress funcionando em qualquer computador.

## Como funciona

A palavra de ordem é automatização. O primeiro passo pra entender como
tudo aqui funciona é ver funcionando!

Para reproduzir todo o ambiente disponibilizado aqui e ter um
wordpress funcionando no seu computador em alguns minutos (vai
depender da velocidade do seu computador e da sua conexão), siga os
seguintes passos:

## Obtenha o código!

Pra baixar esse repositório você precisa do
[Git](http://git-scm.com). Caso você não tenha o git instalado e não
saiba muito bem o que isso significa, chame um programador ou espere
um pouco até as que imagens pré-compiladas sejam disponiblizadas.

Depois de instalar o Git, baixe o repositório através do seu cliente
preferido. Se você optar pela linha de comando, execute o seguinte
comando no terminal:

```bash
$ git clone https://github.com/MarcoCivil/deploy.git
```

## Instale as dependências

### Ansible

Todo a automatização é orquestrada pelo software
[Ansible](http://www.ansible.com). Que precisa de um ambiente especial
para ser executado. Você precisa ter o
[Virtualenvwrapper](http://virtualenvwrapper.readthedocs.org/en/latest/)
funcionando no seu computador para que você possa executar os
seguintes comandos:

Entre no diretório em que você baixou o código:

```bash
$ cd deploy
```

Construa um `virtualenv`:

```bash
$ mkvirtualenv deploywordpress
```

Instale as dependências do `ansible`:

```bash
$ pip install -r requirements.txt
```

### Vagrant

O `ansible` normalmente não é operado manualmente. No nosso caso, o
[Vagrant](http://www.vagrantup.com/) é quem faz esse trabalho. Depois
de instalar o vagrant, execute o seguinte comando:

```bash
$ vagrant up
```

Tenha algo interessante pra fazer. Essa operação pode demorar
bastante. Uma maquina virtual inteira com [Ubuntu](http://ubuntu.com)
será criada, todas as dependências e configurações serão instaladas e
executadas automáticamente. Só aguarde e confira se a execução do
comando procede sem erros.

Caso algum erro aconteça, tente ler a documentação novamente e ver se
você esqueçeu algum passo. Todos os passos dessa instalação são
idempotentes, ou seja, se algum comando falhar, você pode tentar
resolver o problema e depois executar o comando que falhou novamente.

Use a
[interface do GitHub](https://github.com/MarcoCivil/deploy/issues/new)
para criar um ticket reportando um problema ou pedindo ajuda.

# Navegue pelo blog

Se tudo deu certo até agora, você será capaz de ver tudo funcionando
através do seu navegador preferido. Abra o Firefox, Chrome ou qualquer
outro navegador e acesse o endereço
[http://localhost:2000](http://localhost:2000).

A interface administrativa pode ser encontrada no endereço
[http://localhost:2000/wp-admin](http://localhost:2000/wp-admin).
