<p align="center"><img src="https://www.shareicon.net/data/128x128/2015/10/06/112721_development_512x512.png"></p>

- [Docker](#docker)
    - [Sobre este projeto](#sobre-este-projeto)
    - [TL;DR (Too Long, Didn't Read)](#tldr-too-long-didnt-read)
    - [Como obter Docker?](#como-obter-docker)
    - [Como criar uma imagem](#como-criar-uma-imagem)
    - [Como publicar o site](#como-publicar-o-site)
    - [Como rodar um servidor](#como-rodar-um-servidor)
- [Editando informações do site](#editando-informa%C3%A7%C3%B5es-do-site)


<a name="docker"></a>
# Docker

Abaixo estão informações de como buildar, rodar e publicar o site utilizando Docker.

<a name="sobre-este-projeto"></a>
## Sobre este projeto

Este repositório é para o site do http://fossday.org. Um evento comunitário que é realizado
em Lajeado/RS.

Caso tenha interesse em contribuir, deixe sem Pull Request :-)


<a name="too-long"></a>
## TL;DR (Too Long, Didn't Read)

Baixe Docker com o comando mágico (funciona somente em Sistemas Operacionais). Windows, sorry :-)

```bash
curl -fsSL https://get.docker.com/ | sh
```

<a name="como-obter-docker"></a>
## Como obter Docker?

- [Link para documentação oficial](https://docs.docker.com/install/)
    - [Instalando em Windows](https://docs.docker.com/docker-for-windows/install/)
    - [Instalando em Debian](https://docs.docker.com/install/linux/docker-ce/debian/)
    - [Instalando em Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
    - [Instalando em MacOS](https://docs.docker.com/docker-for-mac/install/)

<a name="como-criar-imagem"></a>
## Como criar uma imagem

Construa a imagem que irá rodar com o comando abaixo

```bash
docker build -t fossday/gohugo .
```

<a name="como-publicar-site"></a>
## Como publicar o site

Publicação de código, ou seja, transforma todos os arquivos.md para HTML

```bash
docker run -it -v $(pwd)/site:/src -v $(pwd)/public:/src/public fossday/gohugo
```

<a name="como-rodar-um-servidor"></a>
## Como rodar um servidor

Aqui é possível rodar Hugo em modo servidor

```bash
docker run -it -v $(pwd)/site:/src -v $(pwd)/public:/src/public -p 1313:1313 fossday/gohugo /gohugo.sh -s
```

<a name="editando-informa%C3%A7%C3%B5es-do-site"></a>
# Editando informações do site

[Gerenciando site](docs/manage_site.md)