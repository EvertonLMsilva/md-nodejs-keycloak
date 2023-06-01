# Instalando o Docker no Ubuntu

- O Docker é uma plataforma de conteinerização extremamente popular que permite que os desenvolvedores criem e implantem aplicativos dentro de contêineres. Os contêineres são ambientes isolados que empacotam um aplicativo inteiro junto com suas dependências, bibliotecas, arquivos de configuração e tudo o que é necessário para executá-lo independentemente do ambiente de computação.

## Atualizando o Sistema.

```
sudo apt update && apt upgrade
```

## Instalando as Dependências.

Algumas dependências são necessárias para que a instalação ocorra sem problemas.

```
sudo apt install apt-transport-https curl gnupg-agent ca-certificates software-properties-common -y
```

## Instalando o Docker no Ubuntu 22.04.

Com os requisitos instalados, a próxima etapa é instalar o Docker. Instalaremos o Docker Community Edition ( Docker CE ), que é de código aberto e gratuito para download e uso.

Para fazer isso, adicionaremos a chave GPGK

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Como o Ubuntu 22.04 ainda não foi lançado oficialmente, adicione o repositório para o Ubuntu 20.04 Stable.

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

Com a chave GPG e o repositório adicionados, execute o comando a seguir para instalar o Docker e os pacotes associados.

```
sudo apt install docker-ce docker-ce-cli containerd.io -y
```

Isso instala o Docker e todos os pacotes, bibliotecas e dependências adicionais exigidos pelo Docker e pacotes associados.

Depois que o comando for executado com êxito, considere adicionar o usuário conectado no momento ao grupo docker. Isso permite que você execute o docker sem invocar o sudo.

```
sudo usermod -aG docker $USER
newgrp docker
```

Verificando a versão do Docker

```
docker --version
```
