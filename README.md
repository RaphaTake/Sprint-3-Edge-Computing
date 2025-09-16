# Sprint 3 - Edge Computing And Computer Systems

**Desenvolvimento da primeira versão da arquitetura da aplicação IoT voltada para o projeto Challenge "Passa a Bola".**

## 👥 Integrantes

- **Felipe Andrade**
- **Guilherme Augusto**
- **Raphael Taketa**
- **Victor Guimarães**

## 📌 Descrição do Projeto

O projeto aplica conceitos de Internet das Coisas (IoT) ao esporte, desenvolvendo uma solução que permite detectar gols automaticamente e registrar os dados em um banco de dados em tempo real.

Para isso, utilizamos o ESP32 conectado a sensores, que capturam eventos durante o jogo e enviam essas informações para a nuvem. A arquitetura permite que os dados sejam processados, armazenados e disponibilizados de forma rápida para websites, dashboards e sistemas externos, garantindo monitoramento e análise em tempo real.

## 🏗️ Arquitetura Proposta

### Diagrama da Arquitetura

![ArquiteturaIot](https://github.com/user-attachments/assets/52f81c9a-7eda-46b5-b502-f1bea1102c03)

Na camada IoT, utilizamos sensores conectados ao ESP32, que enviam os dados para a nuvem. 
No back-end, usamos a plataforma FIWARE, onde o IoT Agent se comunica via protocolo MQTT com o Orion Context Broker. 
As informações são armazenadas no MongoDB, tanto para consultas imediatas quanto para histórico, por meio do STH-Comet. 
Na camada de aplicação, dashboards e sistemas externos podem acessar e visualizar os dados em tempo real. 

## 🛠️ Recursos Necessários

- ESP32
- Sensores
- Máquina Virtual (VMware Workstation Pro)
- Sistema Operacional Ubuntu
- Docker
- MongoDB
- FIWARE (Orion Context Broker, IoT Agent)
- Broker MQTT (Mosquitto)
  
## 📋 Instruções de Uso

1. Configurar a máquina virtual com Ubuntu.
2. Instalar Docker e levantar os containers do FIWARE e MongoDB.
3. Configurar o IoT Agent para comunicação com o ESP32 via MQTT.
4. Conectar os sensores ao ESP32 e enviar os dados para o Orion Context Broker.
5. Acessar websites, dashboards ou sistemas externos para visualização dos dados em tempo real.

## 💻 Códigos usados dentro do Prompt do Sistema Operacional Ubuntu

```
$ sudo apt update
$ sudo apt-get install net-tools
$ ifconfig
$ sudo apt install git
$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
$ sudo apt update
$ apt-cache policy docker-ce
$ sudo apt install docker-ce
$ sudo systemctl status docker
$ git clone https://github.com/fabiocabrini/fiware
$ cd fiware
$ sudo docker compose up -d
$ sudo docker stats
```
## ✅ Health Check

**- Utilizando Postman**

http://192.168.0.245:4041/iot/about
```json
{
    "libVersion": "4.7.0",
    "port": "4041",
    "baseRoot": "/",
    "version": "3.7.0"
}
```
http://192.168.0.245:1026/version
```json
{
    "orion": {
        "version": "3.11.0",
        "uptime": "0 d, 0 h, 6 m, 28 s",
        "git_hash": "c505fdc0616ce559c01e19b7130b019d85c4feba",
        "compile_time": "Mon Jan 29 08:45:34 UTC 2024",
        "compiled_by": "root",
        "compiled_in": "buildkitsandbox",
        "release_date": "Mon Jan 29 08:45:34 UTC 2024",
        "machine": "x86_64",
        "doc": "https://fiware-orion.rtfd.io/en/3.11.0/",
        "libversions": {
            "boost": "1_74",
            "libcurl": "libcurl/7.88.1 OpenSSL/3.0.11 zlib/1.2.13 brotli/1.0.9 zstd/1.5.4 libidn2/2.3.3 libpsl/0.21.2 (+libidn2/2.3.3) libssh2/1.10.0 nghttp2/1.52.0 librtmp/2.3 OpenLDAP/2.5.13",
            "libmosquitto": "2.0.15",
            "libmicrohttpd": "0.9.76",
            "openssl": "3.0.11",
            "rapidjson": "1.1.0",
            "mongoc": "1.24.3",
            "bson": "1.24.3"
        }
    }
}

```

## 📽️ Vídeo Explicativo

Link para o Vídeo

**https://youtu.be/VXDmV-NkHL4**

