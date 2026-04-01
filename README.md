# 🐳 Docker Compose - Exemplo Prático

<div align="center">

![Docker](https://img.shields.io/badge/Docker-20.10+-2496ED?logo=docker&logoColor=white)
![Docker Compose](https://img.shields.io/badge/Docker_Compose-3.1-2496ED?logo=docker&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-Latest-E95420?logo=ubuntu&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)

**Exemplo básico e didático de containerização usando Docker Compose**

[O que é Docker](#-o-que-é-docker) • [Como Usar](#-como-usar) • [Estrutura](#-estrutura-do-projeto) • [Comandos](#-comandos-docker-compose)

</div>

---

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [O que é Docker](#-o-que-é-docker)
- [O que é Docker Compose](#-o-que-é-docker-compose)
- [Funcionalidades](#-funcionalidades)
- [Tecnologias Utilizadas](#%EF%B8%8F-tecnologias-utilizadas)
- [Pré-requisitos](#-pré-requisitos)
- [Instalação](#-instalação)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Como Usar](#-como-usar)
- [Entendendo o docker-compose.yml](#-entendendo-o-docker-composeyml)
- [Entendendo o Dockerfile](#-entendendo-o-dockerfile)
- [Comandos Docker Compose](#-comandos-docker-compose)
- [Variáveis de Ambiente](#-variáveis-de-ambiente)
- [Exemplos Práticos](#-exemplos-práticos)
- [Casos de Uso](#-casos-de-uso)
- [Docker Compose Avançado](#-docker-compose-avançado)
- [Boas Práticas](#-boas-práticas)
- [Troubleshooting](#-troubleshooting)
- [Recursos Adicionais](#-recursos-adicionais)
- [Próximos Passos](#-próximos-passos)
- [Contribuindo](#-contribuindo)
- [Licença](#-licença)
- [Autor](#%E2%80%8D-autor)

---

## 📖 Sobre o Projeto

Este projeto é um **exemplo didático e prático** de uso do **Docker Compose** para gerenciar containers Docker de forma declarativa. O projeto demonstra conceitos fundamentais de containerização, incluindo:

- 🐳 Criação de imagens Docker customizadas
- 📋 Orquestração de containers com Docker Compose
- 🌍 Configuração de variáveis de ambiente
- 🔧 Build de imagens a partir de Dockerfiles
- 📦 Container Ubuntu minimalista mantido em execução

### 🎯 Objetivos

- 📚 Ensinar conceitos básicos de Docker e Docker Compose
- 🔨 Demonstrar criação de Dockerfile simples
- 🎛️ Mostrar configuração de docker-compose.yml
- 🌐 Exemplificar uso de variáveis de ambiente
- 💡 Fornecer base para projetos mais complexos

### 🌟 O que o Projeto Faz

O projeto cria um **container Ubuntu** que permanece em execução continuamente, configurado com variáveis de ambiente personalizadas. É um ponto de partida ideal para aprender Docker Compose ou testar aplicações em ambiente containerizado.

**Fluxo:**
```
Dockerfile-Ubuntu → Build Imagem → docker-compose.yml → Container em execução
                                    ↓
                           Variáveis de Ambiente injetadas
```

---

## 🐳 O que é Docker

### Descrição

**Docker** é uma plataforma open-source que automatiza a implantação de aplicações dentro de **containers** de software. Containers permitem empacotar uma aplicação com todas as suas dependências em uma unidade padronizada.

### Conceitos Fundamentais

```
┌─────────────────────────────────────────────────────┐
│                    HOST OS (Linux/Windows/Mac)      │
├─────────────────────────────────────────────────────┤
│                    Docker Engine                    │
├──────────────┬──────────────┬───────────────────────┤
│  Container 1 │  Container 2 │     Container 3       │
│  ┌────────┐  │  ┌────────┐  │     ┌─────────┐       │
│  │  App   │  │  │  App   │  │     │   App   │       │
│  │  Deps  │  │  │  Deps  │  │     │   Deps  │       │
│  └────────┘  │  └────────┘  │     └─────────┘       │
└──────────────┴──────────────┴───────────────────────┘
```

### Docker vs Máquinas Virtuais

| Aspecto | Docker Container | Máquina Virtual |
|---------|------------------|-----------------|
| **Tamanho** | Megabytes | Gigabytes |
| **Inicialização** | Segundos | Minutos |
| **Performance** | Nativa | Overhead |
| **Isolamento** | Processos | Sistema completo |
| **Portabilidade** | Alta | Média |

### Vantagens do Docker

- ⚡ **Rápido** - Containers iniciam em segundos
- 📦 **Leve** - Compartilha kernel do host
- 🔄 **Portátil** - "Funciona na minha máquina" → Funciona em qualquer lugar
- 🔒 **Isolado** - Aplicações não interferem entre si
- 📈 **Escalável** - Fácil replicar containers
- 🎯 **Consistente** - Mesmo ambiente em dev/test/prod

---

## 🎼 O que é Docker Compose

### Descrição

**Docker Compose** é uma ferramenta para definir e executar aplicações Docker **multi-container**. Com um único arquivo YAML (`docker-compose.yml`), você configura todos os serviços da sua aplicação e os inicia com um único comando.

### Arquitetura

```
docker-compose.yml
├── Service 1 (Ex: Web App)
│   ├── Image/Build
│   ├── Ports
│   ├── Volumes
│   └── Environment
├── Service 2 (Ex: Database)
│   ├── Image/Build
│   ├── Volumes
│   └── Environment
└── Service 3 (Ex: Cache)
    ├── Image
    └── Ports
```

### Por que usar Docker Compose?

| Benefício | Descrição |
|-----------|-----------|
| **Simplicidade** | Um arquivo define tudo |
| **Reprodutibilidade** | Mesma stack em qualquer lugar |
| **Isolamento** | Ambientes isolados por projeto |
| **Produtividade** | Start/stop com um comando |
| **Versionamento** | docker-compose.yml no Git |

---

## ✨ Funcionalidades

### Implementadas no Projeto

- ✅ **Container Ubuntu** - Sistema base Linux
- ✅ **Dockerfile Custom** - Imagem personalizada
- ✅ **Variáveis de Ambiente** - Configuração dinâmica
- ✅ **Container Persistente** - Mantém-se em execução
- ✅ **Build Automático** - Constrói imagem ao subir
- ✅ **Nome Customizado** - Container com nome definido

### Recursos Docker Compose

- 🔨 **Build** - Construir imagens a partir de Dockerfiles
- 🌐 **Networks** - Rede isolada entre containers
- 💾 **Volumes** - Persistência de dados
- 🔗 **Links** - Comunicação entre containers
- 🎚️ **Environment** - Variáveis de ambiente
- 📊 **Logging** - Gerenciamento de logs
- ⚖️ **Scaling** - Escalar serviços horizontalmente

---

## 🛠️ Tecnologias Utilizadas

### Containerização

- **[Docker](https://www.docker.com/)** - Plataforma de containers
  - Docker Engine 20.10+
  - Container runtime
  - Image management

- **[Docker Compose](https://docs.docker.com/compose/)** - Orquestração multi-container
  - Versão 3.1
  - Definição declarativa de serviços
  - Gerenciamento de stack completa

### Sistema Operacional

- **[Ubuntu](https://ubuntu.com/)** - Distribuição Linux
  - Imagem base oficial
  - Sistema leve e estável
  - Ampla compatibilidade

### Ferramentas

- **YAML** - Formato de configuração
- **Bash/Shell** - Scripts e comandos
- **Git** - Versionamento (opcional)

---

## 📋 Pré-requisitos

### Software Necessário

#### Docker Desktop (Windows/Mac)

- **[Docker Desktop](https://www.docker.com/products/docker-desktop)** - Inclui Docker e Docker Compose
  - Windows 10/11 Pro, Enterprise ou Education
  - macOS 10.15 ou superior
  - 4GB RAM mínimo (8GB recomendado)

#### Docker Engine (Linux)

- **[Docker Engine](https://docs.docker.com/engine/install/)**
- **[Docker Compose](https://docs.docker.com/compose/install/)**

### Requisitos de Sistema

| Recurso | Mínimo | Recomendado |
|---------|--------|-------------|
| **RAM** | 2GB | 4GB+ |
| **Disco** | 10GB livre | 20GB+ |
| **CPU** | 2 cores | 4+ cores |
| **SO** | Windows 10/Linux/macOS 10.15 | Atualizados |

### Verificar Instalações

```bash
# Verificar Docker
docker --version
docker version

# Verificar Docker Compose
docker-compose --version

# Verificar que Docker está rodando
docker ps

# Informações do sistema
docker info
```

**Saída esperada:**
```
Docker version 20.10.x
docker-compose version 1.29.x (ou 2.x.x)
```

---

## 🚀 Instalação

### Windows

#### Opção 1: Docker Desktop (Recomendado)

1. **Baixar Docker Desktop:**
   - Acesse [docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)
   - Baixe o instalador para Windows

2. **Instalar:**
   - Execute o instalador
   - Siga o assistente
   - Reinicie se solicitado

3. **Habilitar WSL 2:**
   - Windows Subsystem for Linux
   - Docker Desktop solicitará automaticamente

4. **Iniciar Docker Desktop:**
   - Abra o aplicativo
   - Aguarde Docker iniciar (ícone na bandeja)

5. **Verificar:**
   ```bash
   docker --version
   docker-compose --version
   ```

### Linux (Ubuntu/Debian)

```bash
# 1. Atualizar pacotes
sudo apt update

# 2. Instalar dependências
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

# 3. Adicionar chave GPG do Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# 4. Adicionar repositório Docker
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# 5. Instalar Docker Engine
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io

# 6. Instalar Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/download/v2.20.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# 7. Adicionar usuário ao grupo docker
sudo usermod -aG docker $USER

# 8. Relogar ou executar
newgrp docker

# 9. Verificar
docker --version
docker-compose --version
```

### macOS

```bash
# 1. Instalar com Homebrew
brew install --cask docker

# 2. Ou baixar Docker Desktop
# https://www.docker.com/products/docker-desktop

# 3. Abrir Docker Desktop
open /Applications/Docker.app

# 4. Verificar
docker --version
docker-compose --version
```

---

## 📁 Estrutura do Projeto

```
docker-compose-master/
│
├── docker-compose.yml          # Arquivo de orquestração
├── Dockerfile-Ubuntu           # Definição da imagem Ubuntu
└── README.md                   # Documentação original
```

### Descrição dos Arquivos

| Arquivo | Descrição | Função |
|---------|-----------|--------|
| `docker-compose.yml` | Configuração de serviços | Define containers, redes, volumes |
| `Dockerfile-Ubuntu` | Receita da imagem | Instruções para construir imagem |
| `README.md` | Documentação | Informações do projeto |

---

## 🔧 Como Usar

### Início Rápido

```bash
# 1. Navegar até o diretório
cd docker-compose-master

# 2. Iniciar os containers (build + start)
docker-compose up -d

# 3. Verificar status
docker-compose ps

# 4. Ver logs
docker-compose logs

# 5. Acessar o container
docker exec -it ubuntu_container bash

# 6. Parar containers
docker-compose down
```

### Passo a Passo Detalhado

#### 1. Construir e Iniciar

```bash
# Construir imagens e iniciar containers em background
docker-compose up -d

# Ou construir antes de iniciar
docker-compose build
docker-compose up -d

# Ver logs em tempo real
docker-compose up  # Sem -d para ver logs
```

**Saída esperada:**
```
Creating network "docker-compose-master_default" with the default driver
Building ubuntu_service
Step 1/2 : FROM ubuntu
 ---> a8780b506fa4
Step 2/2 : CMD ["tail", "-f", "/dev/null"]
 ---> Running in xyz123
Successfully built abc456def789
Successfully tagged docker-compose-master_ubuntu_service:latest
Creating ubuntu_container ... done
```

#### 2. Verificar Containers

```bash
# Listar containers do projeto
docker-compose ps

# Ou com Docker
docker ps
```

**Saída:**
```
      Name                Command          State   Ports
-----------------------------------------------------------
ubuntu_container   tail -f /dev/null   Up
```

#### 3. Acessar Container

```bash
# Entrar no container Ubuntu
docker exec -it ubuntu_container bash

# Dentro do container, você está no shell Ubuntu
root@abc123:/# 

# Verificar variáveis de ambiente
root@abc123:/# echo $NOME
JuniorApp

root@abc123:/# echo $DESCRICAO
Plataforma para programadores

# Sair do container
root@abc123:/# exit
```

#### 4. Ver Logs

```bash
# Logs de todos os serviços
docker-compose logs

# Logs em tempo real (follow)
docker-compose logs -f

# Logs de serviço específico
docker-compose logs ubuntu_service

# Últimas 50 linhas
docker-compose logs --tail=50
```

#### 5. Parar e Remover

```bash
# Parar containers (mantém containers e redes)
docker-compose stop

# Parar e remover containers
docker-compose down

# Remover tudo (containers, redes, imagens)
docker-compose down --rmi all

# Remover volumes também
docker-compose down -v
```

---

## 📄 Entendendo o docker-compose.yml

### Arquivo Completo

```yaml
version: "3.1"

services:
  ubuntu_service:
    container_name: ubuntu_container
    build:
      context: .
      dockerfile: Dockerfile-Ubuntu
    environment:
      - NOME=JuniorApp
      - DESCRICAO=Plataforma para programadores
```

### Explicação Linha por Linha

#### version: "3.1"
```yaml
version: "3.1"
```
- **Define a versão** do formato do Docker Compose
- Versão 3.1 é compatível com Docker Engine 17.06.0+
- Diferentes versões suportam diferentes recursos

**Versões disponíveis:**
- `3.x` - Produção (recomendado)
- `2.x` - Legado
- `1.x` - Obsoleto

#### services:
```yaml
services:
```
- **Inicia a definição de serviços**
- Cada serviço é um container
- Pode haver múltiplos serviços

#### ubuntu_service:
```yaml
ubuntu_service:
```
- **Nome do serviço** (interno)
- Usado para referenciar o serviço
- Exemplo: `docker-compose logs ubuntu_service`

#### container_name:
```yaml
container_name: ubuntu_container
```
- **Nome do container** (externo)
- Nome que aparece em `docker ps`
- Se omitido, Docker gera nome automático
- Útil para identificação

#### build:
```yaml
build:
  context: .
  dockerfile: Dockerfile-Ubuntu
```
- **Instrução de build** da imagem
- `context: .` - Diretório de contexto (atual)
- `dockerfile: Dockerfile-Ubuntu` - Arquivo Dockerfile a usar
- Docker Compose construirá a imagem automaticamente

#### environment:
```yaml
environment:
  - NOME=JuniorApp
  - DESCRICAO=Plataforma para programadores
```
- **Variáveis de ambiente** injetadas no container
- Formato: `VARIAVEL=valor`
- Acessíveis dentro do container
- Útil para configuração dinâmica

---

## 🐋 Entendendo o Dockerfile

### Arquivo Completo

```dockerfile
FROM ubuntu

CMD ["tail", "-f", "/dev/null"]
```

### Explicação das Instruções

#### FROM ubuntu
```dockerfile
FROM ubuntu
```
- **Imagem base** para construir
- Usa a última versão do Ubuntu oficial
- Equivalente a `FROM ubuntu:latest`
- Baixa do Docker Hub se não existir localmente

**Outras opções:**
```dockerfile
FROM ubuntu:22.04        # Versão específica
FROM ubuntu:jammy        # Por codinome
FROM alpine              # Alternativa leve
FROM scratch             # Imagem vazia
```

#### CMD ["tail", "-f", "/dev/null"]
```dockerfile
CMD ["tail", "-f", "/dev/null"]
```
- **Comando padrão** ao iniciar container
- `tail -f /dev/null` - Lê arquivo vazio infinitamente
- **Propósito:** Manter o container rodando
- Sem esse comando, container terminaria imediatamente

**Por que isso é necessário?**
- Containers Docker rodam enquanto o processo principal está ativo
- Sem processo, container para automaticamente
- `tail -f /dev/null` é um truque para manter container vivo
- Alternativas: `sleep infinity`, `while true; do sleep 30; done`

**Alternativas:**
```dockerfile
# Opção 1: Sleep infinito
CMD ["sleep", "infinity"]

# Opção 2: Bash interativo
CMD ["/bin/bash"]

# Opção 3: Loop infinito
CMD ["sh", "-c", "while true; do sleep 30; done"]
```

---

## 📖 Comandos Docker Compose

### Gerenciamento de Containers

```bash
# Iniciar serviços (build se necessário)
docker-compose up

# Iniciar em background (detached)
docker-compose up -d

# Forçar rebuild das imagens
docker-compose up --build

# Parar serviços (mantém containers)
docker-compose stop

# Iniciar serviços parados
docker-compose start

# Reiniciar serviços
docker-compose restart

# Parar e remover containers, redes
docker-compose down
```

### Informações e Logs

```bash
# Listar containers do projeto
docker-compose ps

# Ver logs de todos os serviços
docker-compose logs

# Seguir logs em tempo real
docker-compose logs -f

# Logs de serviço específico
docker-compose logs ubuntu_service

# Últimas N linhas
docker-compose logs --tail=100 ubuntu_service
```

### Build e Imagens

```bash
# Construir/reconstruir imagens
docker-compose build

# Build sem cache
docker-compose build --no-cache

# Build de serviço específico
docker-compose build ubuntu_service

# Listar imagens do projeto
docker-compose images

# Remover imagens não usadas
docker image prune
```

### Execução de Comandos

```bash
# Executar comando em container rodando
docker-compose exec ubuntu_service bash

# Executar comando único
docker-compose exec ubuntu_service ls -la

# Executar como usuário específico
docker-compose exec -u root ubuntu_service bash

# Executar comando em novo container
docker-compose run ubuntu_service echo "Hello"
```

### Volumes e Dados

```bash
# Listar volumes
docker volume ls

# Remover volumes não usados
docker volume prune

# Remover tudo (containers, redes, volumes)
docker-compose down -v
```

### Scaling

```bash
# Escalar serviço (múltiplas instâncias)
docker-compose up -d --scale ubuntu_service=3

# Escalar para zero (parar sem remover)
docker-compose up -d --scale ubuntu_service=0
```

### Validação

```bash
# Validar sintaxe do docker-compose.yml
docker-compose config

# Validar e mostrar configuração resolvida
docker-compose config --services

# Validar específico
docker-compose -f docker-compose.yml config
```

---

## 🌍 Variáveis de Ambiente

### Como Funcionam

As variáveis definidas em `docker-compose.yml` são injetadas no container:

```yaml
environment:
  - NOME=JuniorApp
  - DESCRICAO=Plataforma para programadores
```

### Acessar Variáveis

#### Dentro do Container

```bash
# Entrar no container
docker exec -it ubuntu_container bash

# Listar todas as variáveis
env

# Ver variável específica
echo $NOME
echo $DESCRICAO

# Usar em script
#!/bin/bash
echo "Nome da aplicação: $NOME"
echo "Descrição: $DESCRICAO"
```

#### Em Scripts

```bash
# Script dentro do container
if [ "$NOME" = "JuniorApp" ]; then
    echo "Aplicação identificada: $NOME"
    echo "Descrição: $DESCRICAO"
fi
```

### Diferentes Formas de Definir

```yaml
# Formato 1: Array
environment:
  - VARIAVEL1=valor1
  - VARIAVEL2=valor2

# Formato 2: Map
environment:
  VARIAVEL1: valor1
  VARIAVEL2: valor2

# Formato 3: Arquivo .env
env_file:
  - .env
  - arquivo-config.env

# Formato 4: Variáveis do host
environment:
  - HOST_VAR=${HOST_VAR}
```

### Arquivo .env

Criar `.env` na raiz do projeto:

```env
NOME=JuniorApp
DESCRICAO=Plataforma para programadores
VERSAO=1.0.0
AMBIENTE=desenvolvimento
```

Usar em `docker-compose.yml`:

```yaml
services:
  ubuntu_service:
    environment:
      - NOME=${NOME}
      - DESCRICAO=${DESCRICAO}
      - VERSAO=${VERSAO}
      - AMBIENTE=${AMBIENTE}
```

---

## 💡 Exemplos Práticos

### Exemplo 1: Adicionar Volume

```yaml
version: "3.1"
services:
  ubuntu_service:
    container_name: ubuntu_container
    build:
      context: .
      dockerfile: Dockerfile-Ubuntu
    environment:
      - NOME=JuniorApp
      - DESCRICAO=Plataforma para programadores
    volumes:
      - ./dados:/app/dados          # Volume local
      - dados_persistentes:/var/data # Volume nomeado

volumes:
  dados_persistentes:
```

**Benefícios:**
- Persistir dados entre reinicializações
- Compartilhar arquivos entre host e container
- Backup facilitado

### Exemplo 2: Expor Portas

```yaml
version: "3.1"
services:
  ubuntu_service:
    container_name: ubuntu_container
    build:
      context: .
      dockerfile: Dockerfile-Ubuntu
    environment:
      - NOME=JuniorApp
    ports:
      - "8080:80"      # Host:Container
      - "3306:3306"    # Múltiplas portas
```

**Uso:**
- Acessar serviços do container no host
- Expor aplicações web
- Conectar a bancos de dados

### Exemplo 3: Múltiplos Serviços

```yaml
version: "3.1"

services:
  web:
    image: nginx:alpine
    ports:
      - "80:80"
    volumes:
      - ./html:/usr/share/nginx/html
    depends_on:
      - app

  app:
    container_name: ubuntu_container
    build:
      context: .
      dockerfile: Dockerfile-Ubuntu
    environment:
      - NOME=JuniorApp
      - DESCRICAO=Plataforma para programadores

  db:
    image: postgres:13-alpine
    environment:
      POSTGRES_PASSWORD: senha123
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data:
```

### Exemplo 4: Rede Customizada

```yaml
version: "3.1"

services:
  ubuntu_service:
    container_name: ubuntu_container
    build:
      context: .
      dockerfile: Dockerfile-Ubuntu
    networks:
      - minha_rede
    environment:
      - NOME=JuniorApp

networks:
  minha_rede:
    driver: bridge
```

### Exemplo 5: Health Check

```yaml
version: "3.1"

services:
  ubuntu_service:
    container_name: ubuntu_container
    build:
      context: .
      dockerfile: Dockerfile-Ubuntu
    environment:
      - NOME=JuniorApp
    healthcheck:
      test: ["CMD", "echo", "ok"]
      interval: 30s
      timeout: 10s
      retries: 3
      start_period: 40s
```

---

## 🎯 Casos de Uso

### 1. Ambiente de Desenvolvimento 💻

**Objetivo:** Ambiente isolado para desenvolvimento

```yaml
version: "3.1"

services:
  dev:
    build: .
    volumes:
      - ./projeto:/workspace
      - /workspace/node_modules  # Não sobrescrever
    ports:
      - "3000:3000"
    command: npm run dev
```

**Vantagens:**
- Cada projeto tem seu ambiente
- Não poluir máquina local
- Fácil replicar para time

### 2. Stack Completa Web 🌐

**Objetivo:** Aplicação web completa

```yaml
version: "3.1"

services:
  frontend:
    image: nginx:alpine
    ports:
      - "80:80"
    volumes:
      - ./frontend:/usr/share/nginx/html

  backend:
    build: ./backend
    ports:
      - "8080:8080"
    environment:
      DB_HOST: database
    depends_on:
      - database

  database:
    image: postgres:13
    environment:
      POSTGRES_PASSWORD: senha
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data:
```

### 3. Microservices 🔗

**Objetivo:** Arquitetura de microserviços

```yaml
version: "3.1"

services:
  api-users:
    build: ./users-service
    ports:
      - "8001:8080"

  api-products:
    build: ./products-service
    ports:
      - "8002:8080"

  api-orders:
    build: ./orders-service
    ports:
      - "8003:8080"

  gateway:
    image: nginx:alpine
    ports:
      - "80:80"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
```

### 4. Banco de Dados de Desenvolvimento 💾

**Objetivo:** Banco local para testes

```yaml
version: "3.1"

services:
  postgres:
    image: postgres:13-alpine
    container_name: dev-postgres
    environment:
      POSTGRES_USER: dev
      POSTGRES_PASSWORD: dev123
      POSTGRES_DB: mydb
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data

  mysql:
    image: mysql:8
    container_name: dev-mysql
    environment:
      MYSQL_ROOT_PASSWORD: root123
      MYSQL_DATABASE: mydb
    ports:
      - "3306:3306"
    volumes:
      - mysql_data:/var/lib/mysql

volumes:
  postgres_data:
  mysql_data:
```

### 5. Ambiente de Testes 🧪

**Objetivo:** Ambiente isolado para CI/CD

```yaml
version: "3.1"

services:
  test:
    build:
      context: .
      dockerfile: Dockerfile.test
    volumes:
      - ./src:/app/src
      - ./tests:/app/tests
    command: npm test
    environment:
      NODE_ENV: test
```

---

## 🎓 Docker Compose Avançado

### 1. Múltiplos Arquivos Compose

```bash
# Usar múltiplos arquivos (sobrescreve configurações)
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d

# Arquivo base + override
# docker-compose.yml (base)
# docker-compose.override.yml (desenvolvimento - carregado automaticamente)
# docker-compose.prod.yml (produção)
```

**docker-compose.yml (base):**
```yaml
version: "3.1"
services:
  app:
    build: .
    environment:
      - APP_NAME=MinhaApp
```

**docker-compose.override.yml (dev - automático):**
```yaml
version: "3.1"
services:
  app:
    volumes:
      - ./src:/app/src  # Hot reload
    ports:
      - "3000:3000"
```

**docker-compose.prod.yml (produção):**
```yaml
version: "3.1"
services:
  app:
    image: minha-app:latest
    restart: always
```

### 2. Dependências Entre Serviços

```yaml
version: "3.1"

services:
  web:
    image: nginx
    depends_on:
      - app
      - db

  app:
    build: .
    depends_on:
      db:
        condition: service_healthy

  db:
    image: postgres
    healthcheck:
      test: ["CMD", "pg_isready"]
      interval: 10s
```

### 3. Restart Policies

```yaml
version: "3.1"

services:
  ubuntu_service:
    build: .
    restart: always  # Sempre reiniciar
    # Opções:
    # no - Nunca reiniciar (padrão)
    # always - Sempre reiniciar
    # on-failure - Apenas em falha
    # unless-stopped - Sempre, exceto se parado manualmente
```

### 4. Limites de Recursos

```yaml
version: "3.1"

services:
  ubuntu_service:
    build: .
    deploy:
      resources:
        limits:
          cpus: '0.5'      # Máximo 50% de 1 CPU
          memory: 512M     # Máximo 512MB RAM
        reservations:
          cpus: '0.25'     # Mínimo garantido
          memory: 256M
```

### 5. Networks Customizadas

```yaml
version: "3.1"

services:
  frontend:
    image: nginx
    networks:
      - frontend_net

  backend:
    build: .
    networks:
      - frontend_net
      - backend_net

  database:
    image: postgres
    networks:
      - backend_net

networks:
  frontend_net:
    driver: bridge
  backend_net:
    driver: bridge
    internal: true  # Sem acesso externo
```

---

## 📚 Boas Práticas

### 1. Estrutura de Arquivos

```
projeto/
├── docker-compose.yml              # Configuração principal
├── docker-compose.override.yml     # Dev (automático)
├── docker-compose.prod.yml         # Produção
├── .env                            # Variáveis de ambiente
├── .dockerignore                   # Arquivos a ignorar
├── Dockerfile                      # Dockerfile principal
└── services/
    ├── service1/
    │   └── Dockerfile
    └── service2/
        └── Dockerfile
```

### 2. Usar .dockerignore

Criar `.dockerignore`:

```
node_modules
npm-debug.log
.git
.gitignore
README.md
.env
.vscode
*.log
target/
.DS_Store
```

**Benefícios:**
- Build mais rápido
- Imagens menores
- Não incluir arquivos sensíveis

### 3. Não Expor Credenciais

```yaml
# ❌ Evitar - Credenciais no arquivo
environment:
  DB_PASSWORD: senha123

# ✅ Usar arquivo .env (não comitar)
environment:
  DB_PASSWORD: ${DB_PASSWORD}

# ✅ Ou Docker secrets (produção)
secrets:
  - db_password
```

### 4. Versionar Imagens

```yaml
# ❌ Evitar - latest pode mudar
services:
  app:
    image: postgres:latest

# ✅ Usar versão específica
services:
  app:
    image: postgres:13.8-alpine
```

### 5. Usar Imagens Oficiais

```yaml
# ✅ Preferir imagens oficiais e verificadas
services:
  web:
    image: nginx:alpine      # Oficial
  db:
    image: postgres:13       # Oficial
  cache:
    image: redis:alpine      # Oficial
```

### 6. Otimizar Dockerfile

```dockerfile
# ✅ Usar multi-stage build
FROM maven:3.8-openjdk-11 AS build
WORKDIR /app
COPY pom.xml .
RUN mvn dependency:go-offline
COPY src ./src
RUN mvn package -DskipTests

FROM openjdk:11-jre-slim
COPY --from=build /app/target/*.jar app.jar
CMD ["java", "-jar", "app.jar"]
```

---

## 🔍 Exemplos Completos

### Stack MEAN (MongoDB, Express, Angular, Node)

```yaml
version: "3.1"

services:
  mongodb:
    image: mongo:5
    container_name: mean-mongo
    environment:
      MONGO_INITDB_ROOT_USERNAME: admin
      MONGO_INITDB_ROOT_PASSWORD: admin123
    volumes:
      - mongo_data:/data/db
    ports:
      - "27017:27017"
    networks:
      - mean-network

  backend:
    build: ./backend
    container_name: mean-backend
    environment:
      - MONGO_URL=mongodb://admin:admin123@mongodb:27017
      - PORT=3000
    ports:
      - "3000:3000"
    depends_on:
      - mongodb
    networks:
      - mean-network

  frontend:
    build: ./frontend
    container_name: mean-frontend
    ports:
      - "4200:80"
    depends_on:
      - backend
    networks:
      - mean-network

volumes:
  mongo_data:

networks:
  mean-network:
    driver: bridge
```

### Stack Java Spring Boot + PostgreSQL

```yaml
version: "3.1"

services:
  postgres:
    image: postgres:13-alpine
    container_name: app-postgres
    environment:
      POSTGRES_DB: appdb
      POSTGRES_USER: appuser
      POSTGRES_PASSWORD: ${DB_PASSWORD:-defaultpass}
    volumes:
      - postgres_data:/var/lib/postgresql/data
      - ./init.sql:/docker-entrypoint-initdb.d/init.sql
    ports:
      - "5432:5432"
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U appuser"]
      interval: 10s
      timeout: 5s
      retries: 5

  app:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: spring-app
    environment:
      - SPRING_DATASOURCE_URL=jdbc:postgresql://postgres:5432/appdb
      - SPRING_DATASOURCE_USERNAME=appuser
      - SPRING_DATASOURCE_PASSWORD=${DB_PASSWORD:-defaultpass}
    ports:
      - "8080:8080"
    depends_on:
      postgres:
        condition: service_healthy
    restart: unless-stopped

volumes:
  postgres_data:
```

### Stack WordPress

```yaml
version: "3.1"

services:
  db:
    image: mysql:8
    container_name: wordpress-db
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wpuser
      MYSQL_PASSWORD: wppass
    volumes:
      - db_data:/var/lib/mysql
    restart: always

  wordpress:
    image: wordpress:latest
    container_name: wordpress-app
    ports:
      - "8000:80"
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wpuser
      WORDPRESS_DB_PASSWORD: wppass
      WORDPRESS_DB_NAME: wordpress
    volumes:
      - wp_data:/var/www/html
    depends_on:
      - db
    restart: always

volumes:
  db_data:
  wp_data:
```

---

## 🐛 Troubleshooting

### Problema: docker-compose: command not found

**Solução:**
```bash
# Verificar instalação
which docker-compose

# Instalar Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/download/v2.20.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Ou com pip
pip install docker-compose
```

### Problema: Cannot connect to Docker daemon

**Solução:**
```bash
# Linux - Iniciar Docker
sudo systemctl start docker
sudo systemctl enable docker

# Verificar status
sudo systemctl status docker

# Adicionar usuário ao grupo docker
sudo usermod -aG docker $USER
newgrp docker

# Windows/Mac - Abrir Docker Desktop
```

### Problema: Port already in use

**Solução:**
```bash
# Ver o que está usando a porta
# Linux/Mac
lsof -i :8080

# Windows
netstat -ano | findstr :8080

# Matar processo
kill -9 <PID>

# Ou mudar porta no docker-compose.yml
ports:
  - "8081:8080"  # Usar porta diferente no host
```

### Problema: Volume permission denied

**Solução:**
```bash
# Ajustar permissões do diretório
sudo chmod -R 755 ./dados

# Ou executar container como usuário específico
services:
  app:
    user: "${UID}:${GID}"
    volumes:
      - ./dados:/app/dados
```

### Problema: Container exits immediately

**Solução:**
```yaml
# Adicionar comando para manter rodando
services:
  ubuntu_service:
    command: tail -f /dev/null
    # Ou
    command: sleep infinity
    # Ou
    tty: true
    stdin_open: true
```

### Problema: Changes not reflected

**Solução:**
```bash
# Forçar rebuild
docker-compose up --build

# Rebuild sem cache
docker-compose build --no-cache

# Limpar tudo e reconstruir
docker-compose down
docker system prune -a
docker-compose up --build
```

---

## 📖 Comandos Docker Essenciais

### Gerenciamento de Containers

```bash
# Listar containers rodando
docker ps

# Listar todos (incluindo parados)
docker ps -a

# Parar container
docker stop ubuntu_container

# Iniciar container
docker start ubuntu_container

# Reiniciar container
docker restart ubuntu_container

# Remover container
docker rm ubuntu_container

# Forçar remoção
docker rm -f ubuntu_container
```

### Gerenciamento de Imagens

```bash
# Listar imagens
docker images

# Remover imagem
docker rmi nome-imagem

# Remover imagens não usadas
docker image prune

# Remover todas as imagens
docker image prune -a
```

### Logs e Debugging

```bash
# Ver logs
docker logs ubuntu_container

# Seguir logs
docker logs -f ubuntu_container

# Últimas N linhas
docker logs --tail=100 ubuntu_container

# Inspecionar container
docker inspect ubuntu_container

# Ver processos no container
docker top ubuntu_container

# Estatísticas de uso
docker stats ubuntu_container
```

### Limpeza

```bash
# Remover containers parados
docker container prune

# Remover imagens não usadas
docker image prune

# Remover volumes não usados
docker volume prune

# Remover networks não usadas
docker network prune

# Limpar tudo de uma vez
docker system prune

# Limpar TUDO (cuidado!)
docker system prune -a --volumes
```

---

## 🎨 Dockerfile Avançado

### Melhorias no Dockerfile-Ubuntu

```dockerfile
# Versão melhorada
FROM ubuntu:22.04

# Metadados
LABEL maintainer="junior@email.com"
LABEL version="1.0"
LABEL description="Container Ubuntu customizado"

# Evitar prompts interativos
ENV DEBIAN_FRONTEND=noninteractive

# Atualizar e instalar pacotes
RUN apt-get update && \
    apt-get install -y \
    curl \
    wget \
    vim \
    git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Criar diretório de trabalho
WORKDIR /app

# Copiar scripts (se houver)
# COPY scripts/ /app/scripts/

# Definir variáveis de ambiente padrão
ENV NOME="DefaultApp" \
    DESCRICAO="Descrição padrão"

# Expor porta (se necessário)
# EXPOSE 8080

# Comando para manter container rodando
CMD ["tail", "-f", "/dev/null"]
```

### Dockerfile Multi-Stage

```dockerfile
# Stage 1: Build
FROM ubuntu:22.04 AS builder

RUN apt-get update && \
    apt-get install -y build-essential

COPY src/ /build/
WORKDIR /build
RUN make

# Stage 2: Runtime
FROM ubuntu:22.04

COPY --from=builder /build/output /app/

WORKDIR /app
CMD ["./app"]
```

---

## 🌐 Networking no Docker Compose

### Tipos de Network Drivers

| Driver | Descrição | Uso |
|--------|-----------|-----|
| `bridge` | Rede privada isolada | Padrão, containers comunicam entre si |
| `host` | Usa rede do host | Performance, sem isolamento |
| `none` | Sem rede | Containers isolados |
| `overlay` | Rede entre hosts | Docker Swarm, multi-host |

### Comunicação Entre Containers

```yaml
version: "3.1"

services:
  app:
    build: .
    networks:
      - app-network
    environment:
      # Usar nome do serviço como hostname
      - DB_HOST=database
      - DB_PORT=5432

  database:
    image: postgres
    networks:
      - app-network

networks:
  app-network:
    driver: bridge
```

**Dentro do container `app`:**
```bash
# Conectar ao database usando nome do serviço
ping database
curl http://database:5432
```

---

## 📊 Monitoramento e Logs

### Docker Stats

```bash
# Estatísticas em tempo real
docker stats ubuntu_container

# Todas os containers
docker stats

# Formato customizado
docker stats --format "table {{.Container}}\t{{.CPUPerc}}\t{{.MemUsage}}"
```

### Logs Estruturados

```yaml
version: "3.1"

services:
  app:
    build: .
    logging:
      driver: "json-file"
      options:
        max-size: "10m"
        max-file: "3"
```

**Drivers de logging:**
- `json-file` (padrão)
- `syslog`
- `journald`
- `gelf` (Graylog)
- `fluentd`
- `awslogs` (AWS CloudWatch)

---

## 🚀 Deploy e Produção

### Docker Compose em Produção

**docker-compose.prod.yml:**
```yaml
version: "3.1"

services:
  ubuntu_service:
    build: .
    restart: always
    environment:
      - NOME=${NOME}
      - DESCRICAO=${DESCRICAO}
    logging:
      driver: "json-file"
      options:
        max-size: "50m"
        max-file: "5"
    deploy:
      resources:
        limits:
          cpus: '1.0'
          memory: 1G
```

**Executar em produção:**
```bash
# Usar arquivo de produção
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d

# Com variáveis de ambiente
export NOME="ProdApp"
export DESCRICAO="Aplicação em produção"
docker-compose -f docker-compose.prod.yml up -d
```

### CI/CD com Docker Compose

**GitHub Actions:**
```yaml
name: Deploy

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Build images
      run: docker-compose build
    
    - name: Run tests
      run: docker-compose run app npm test
    
    - name: Deploy
      run: |
        docker-compose -f docker-compose.prod.yml up -d
```

---

## 🎯 Melhorias Sugeridas

### Para Este Projeto

- [ ] Adicionar volume para persistir dados
- [ ] Expor porta para acessar serviços
- [ ] Adicionar health check
- [ ] Criar múltiplos serviços
- [ ] Implementar restart policy
- [ ] Adicionar logging configurável
- [ ] Criar arquivo .env
- [ ] Adicionar .dockerignore

### Exemplos de Expansão

#### Adicionar Nginx

```yaml
version: "3.1"

services:
  ubuntu_service:
    container_name: ubuntu_container
    build:
      context: .
      dockerfile: Dockerfile-Ubuntu
    environment:
      - NOME=JuniorApp
      - DESCRICAO=Plataforma para programadores
    networks:
      - app-network

  nginx:
    image: nginx:alpine
    container_name: nginx_server
    ports:
      - "80:80"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf:ro
      - ./html:/usr/share/nginx/html:ro
    depends_on:
      - ubuntu_service
    networks:
      - app-network

networks:
  app-network:
    driver: bridge
```

#### Adicionar PostgreSQL

```yaml
version: "3.1"

services:
  ubuntu_service:
    container_name: ubuntu_container
    build:
      context: .
      dockerfile: Dockerfile-Ubuntu
    environment:
      - NOME=JuniorApp
      - DESCRICAO=Plataforma para programadores
      - DB_HOST=postgres
    depends_on:
      - postgres

  postgres:
    image: postgres:13-alpine
    container_name: postgres_db
    environment:
      POSTGRES_USER: app_user
      POSTGRES_PASSWORD: app_pass
      POSTGRES_DB: app_db
    volumes:
      - postgres_data:/var/lib/postgresql/data
    ports:
      - "5432:5432"

volumes:
  postgres_data:
```

---

## 📚 Recursos Adicionais

### Documentação Oficial

- **[Docker Documentation](https://docs.docker.com/)** - Documentação completa
- **[Docker Compose Docs](https://docs.docker.com/compose/)** - Referência Compose
- **[Docker Hub](https://hub.docker.com/)** - Imagens oficiais
- **[Dockerfile Reference](https://docs.docker.com/engine/reference/builder/)** - Referência Dockerfile

### Tutoriais

- [Docker Get Started](https://docs.docker.com/get-started/)
- [Docker Compose Tutorial](https://docs.docker.com/compose/gettingstarted/)
- [Docker for Beginners](https://docker-curriculum.com/)
- [Play with Docker](https://labs.play-with-docker.com/) - Ambiente online

### Cursos

- **Docker para Desenvolvedores** - Alura
- **Docker Mastery** - Udemy
- **Docker Deep Dive** - Pluralsight
- **Descomplicando o Docker** - LINUXtips (YouTube)

### Livros

- "Docker Deep Dive" - Nigel Poulton
- "Docker em Prática" - Ian Miell
- "Using Docker" - Adrian Mouat
- "Docker para Desenvolvedores" - Rafael Gomes

### Comunidades

- [Docker Community Forums](https://forums.docker.com/)
- [Stack Overflow - Docker](https://stackoverflow.com/questions/tagged/docker)
- [Reddit - r/docker](https://www.reddit.com/r/docker/)
- [Discord - Docker](https://discord.gg/docker)

---

## 🔖 Cheat Sheet Docker Compose

### Comandos Essenciais

```bash
# Iniciar
docker-compose up -d

# Parar
docker-compose down

# Logs
docker-compose logs -f

# Status
docker-compose ps

# Rebuild
docker-compose up --build

# Executar comando
docker-compose exec <service> <comando>

# Escalar
docker-compose up -d --scale web=3

# Validar
docker-compose config
```

### docker-compose.yml Básico

```yaml
version: "3.1"

services:
  app:
    image: ubuntu           # Imagem pronta
    # ou
    build: .                # Build de Dockerfile
    container_name: meu-app
    ports:
      - "8080:80"
    volumes:
      - ./data:/app/data
    environment:
      - VAR=valor
    networks:
      - minha-rede
    depends_on:
      - db
    restart: always

  db:
    image: postgres:13
    environment:
      POSTGRES_PASSWORD: senha
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data:

networks:
  minha-rede:
```

---

## 🎓 Conceitos Importantes

### Container vs Imagem

```
┌─────────────────────────────────────┐
│           Imagem Docker             │
│  (Template imutável, receita)       │
│                                     │
│  - Sistema operacional base         │
│  - Aplicação instalada              │
│  - Dependências                     │
│  - Configurações padrão             │
└──────────────┬──────────────────────┘
               │
               │ docker run / docker-compose up
               │
               ↓
┌──────────────────────────────────────┐
│         Container Docker             │
│  (Instância em execução)             │
│                                      │
│  - Processo rodando                  │
│  - Estado mutável                    │
│  - Dados temporários                 │
│  - Configurações específicas         │
└──────────────────────────────────────┘
```

**Analogia:**
- **Imagem** = Classe (template)
- **Container** = Objeto (instância)

### Ciclo de Vida do Container

```
[Criado] → docker start → [Rodando] → docker stop → [Parado]
                             ↓
                       docker restart
                             ↑
```

### Volumes

**Tipos de volumes:**

1. **Named Volume** (gerenciado pelo Docker)
   ```yaml
   volumes:
     - dados:/app/dados
   ```

2. **Bind Mount** (mapeia diretório do host)
   ```yaml
   volumes:
     - ./local:/container/path
   ```

3. **Tmpfs Mount** (memória RAM)
   ```yaml
   tmpfs:
     - /app/cache
   ```

---

## 💻 Integração com IDEs

### VS Code

**Extensões recomendadas:**
- Docker (Microsoft)
- Remote - Containers (Microsoft)

**Usar:**
1. Instalar extensão Docker
2. Ver containers na sidebar
3. Clicar com botão direito → Start/Stop/Attach
4. Desenvolver dentro do container (Remote - Containers)

### IntelliJ IDEA

**Features:**
- Docker plugin integrado
- View de containers
- Logs integrados
- Deploy direto da IDE

### Eclipse

**Plugin:**
- Eclipse Docker Tooling
- Gerenciar containers pela IDE

---

## 🎯 Próximos Passos

### Aprender Mais

1. **Docker Básico:**
   - Comandos essenciais
   - Criar imagens
   - Gerenciar containers

2. **Docker Compose:**
   - Múltiplos serviços
   - Networks e volumes
   - Variáveis e secrets

3. **Docker em Produção:**
   - Docker Swarm
   - Kubernetes
   - Monitoramento

4. **DevOps:**
   - CI/CD com Docker
   - Registry privado
   - Segurança

### Projetos Práticos

1. **Stack LAMP/LEMP**
   - Linux + Apache/Nginx + MySQL + PHP

2. **Aplicação Node.js**
   - Node + MongoDB + Redis

3. **API Java Spring Boot**
   - Spring Boot + PostgreSQL

4. **WordPress**
   - WordPress + MySQL

5. **Microservices**
   - Múltiplos serviços comunicando

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Para contribuir:

1. Fork o projeto
2. Crie uma branch (`git checkout -b feature/melhoria`)
3. Commit suas mudanças (`git commit -m 'feat: adiciona serviço nginx'`)
4. Push para a branch (`git push origin feature/melhoria`)
5. Abra um Pull Request

### Ideias de Contribuição

- 📝 Adicionar mais exemplos de docker-compose.yml
- 🐛 Melhorar Dockerfiles
- 📚 Expandir documentação
- 🎨 Criar stacks completas
- ✅ Adicionar testes

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

---

## 👨‍💻 Autor

**Júnior Moreira Martins**

Projeto de exemplo para demonstrar o uso do Docker Compose.

---

## 🙏 Agradecimentos

- **[Docker Inc.](https://www.docker.com/)** - Pela plataforma incrível
- **[Comunidade Docker](https://www.docker.com/community)** - Por todo suporte e conhecimento
- **[Docker Hub](https://hub.docker.com/)** - Por hospedar imagens públicas
- **Comunidade Open Source** - Por compartilhar conhecimento

---

## 📊 Estatísticas do Projeto

| Métrica | Valor |
|---------|-------|
| **Docker Compose Version** | 3.1 |
| **Serviços** | 1 (Ubuntu) |
| **Imagens Base** | Ubuntu latest |
| **Variáveis de Ambiente** | 2 configuradas |
| **Complexidade** | Baixa (didático) |
| **Linhas de código** | ~10 linhas |

---

## 🔖 Glossário

| Termo | Descrição |
|-------|-----------|
| **Container** | Instância em execução de uma imagem |
| **Image** | Template imutável para criar containers |
| **Dockerfile** | Arquivo com instruções para build de imagem |
| **docker-compose.yml** | Arquivo de configuração de múltiplos containers |
| **Service** | Definição de um container no Compose |
| **Volume** | Persistência de dados |
| **Network** | Rede virtual entre containers |
| **Registry** | Repositório de imagens (Docker Hub) |
| **Build Context** | Diretório enviado ao Docker para build |
| **Layer** | Camada em uma imagem Docker |

---

## 🎯 Casos de Uso do Docker

### Desenvolvimento

- ✅ Ambiente consistente para todo o time
- ✅ Múltiplas versões de linguagens/ferramentas
- ✅ Isolamento de projetos
- ✅ Onboarding rápido de novos desenvolvedores

### Testes

- ✅ Ambiente de teste isolado
- ✅ CI/CD pipelines
- ✅ Testes de integração
- ✅ Ambientes descartáveis

### Produção

- ✅ Deployment consistente
- ✅ Escalabilidade horizontal
- ✅ Rollback rápido
- ✅ Microservices

---

## 🔐 Segurança

### Boas Práticas de Segurança

```dockerfile
# ✅ Usar imagens oficiais
FROM ubuntu:22.04

# ✅ Não rodar como root
RUN useradd -m appuser
USER appuser

# ✅ Usar imagens slim/alpine
FROM node:16-alpine

# ✅ Atualizar pacotes
RUN apt-get update && apt-get upgrade -y

# ✅ Remover cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*
```

### Secrets (Docker Swarm)

```yaml
version: "3.1"

services:
  app:
    image: myapp
    secrets:
      - db_password

secrets:
  db_password:
    file: ./secrets/db_password.txt
```

---

## 📈 Escalabilidade

### Escalar Serviços

```bash
# Escalar para 3 instâncias
docker-compose up -d --scale ubuntu_service=3

# Escalar múltiplos serviços
docker-compose up -d --scale web=5 --scale worker=10
```

**Nota:** Remover `container_name` para escalar (cada instância precisa de nome único)

```yaml
version: "3.1"

services:
  web:
    # SEM container_name para permitir scaling
    build: .
    ports:
      - "8080-8090:8080"  # Range de portas
```

---

## 🏆 Comandos Avançados

### Docker Compose V2

```bash
# Nova sintaxe (docker compose sem hífen)
docker compose up -d
docker compose down
docker compose ps

# Converter compose file v2 para v3
docker-compose convert
```

### Profiles

```yaml
version: "3.1"

services:
  app:
    build: .
    
  debug:
    image: debugger
    profiles:
      - debug

  test:
    build: .
    command: npm test
    profiles:
      - test
```

```bash
# Iniciar apenas serviços sem profile
docker-compose up

# Iniciar com profile específico
docker-compose --profile debug up
docker-compose --profile test up
```

### Extend e Override

```yaml
# docker-compose.base.yml
version: "3.1"
services:
  app:
    image: ubuntu

# docker-compose.override.yml (carregado automaticamente)
version: "3.1"
services:
  app:
    environment:
      - DEBUG=true
```

---

<div align="center">

## 🐳 Containerize Tudo com Docker! 🚀

**Desenvolvido com Docker e Docker Compose**

### ⭐ Se este projeto foi útil, considere dar uma estrela!

### 📚 Continue aprendendo sobre containerização!

---

**"Build once, run anywhere!"** 🌍

**Docker + Compose = Desenvolvimento Simplificado ❤️**

![Docker Logo](https://www.docker.com/wp-content/uploads/2022/03/vertical-logo-monochromatic.png)

</div>

---

## 📞 Suporte

### Precisa de Ajuda?

- 📖 Consulte a [documentação oficial do Docker](https://docs.docker.com/)
- 🔍 Pesquise no [Stack Overflow](https://stackoverflow.com/questions/tagged/docker)
- 💬 Participe dos [Docker Forums](https://forums.docker.com/)
- 📧 Abra uma issue neste repositório

### Comunidades Brasileiras

- [Docker Brasil](https://docker-br.github.io/)
- [DevOps Brasil](https://t.me/devopsbr)
- [Kubernetes Brasil](https://t.me/kubernetesbr)

---

## 🏅 Certificações Docker

- **Docker Certified Associate (DCA)**
- **Kubernetes Administrator (CKA)**
- **Kubernetes Developer (CKAD)**

---

## 🔗 Ferramentas Relacionadas

### Orquestração

- **[Kubernetes](https://kubernetes.io/)** - Orquestração em produção
- **[Docker Swarm](https://docs.docker.com/engine/swarm/)** - Orquestração nativa Docker
- **[Nomad](https://www.nomadproject.io/)** - Orquestrador HashiCorp

### Monitoramento

- **[Portainer](https://www.portainer.io/)** - UI para Docker
- **[cAdvisor](https://github.com/google/cadvisor)** - Métricas de containers
- **[Prometheus](https://prometheus.io/)** - Monitoramento
- **[Grafana](https://grafana.com/)** - Visualização de métricas

### Registro de Imagens

- **[Docker Hub](https://hub.docker.com/)** - Registro público
- **[Harbor](https://goharbor.io/)** - Registry privado
- **[AWS ECR](https://aws.amazon.com/ecr/)** - Registry AWS
- **[Google Container Registry](https://cloud.google.com/container-registry)** - Registry GCP

---

## 🎯 Roadmap de Aprendizado

### Nível 1: Iniciante

- [ ] Entender o que são containers
- [ ] Executar primeiro container
- [ ] Usar Docker Hub
- [ ] Criar Dockerfile básico
- [ ] Usar docker-compose.yml simples

### Nível 2: Intermediário

- [ ] Multi-stage builds
- [ ] Networks customizadas
- [ ] Volumes e persistência
- [ ] Docker Compose com múltiplos serviços
- [ ] Variáveis de ambiente e secrets

### Nível 3: Avançado

- [ ] Docker Swarm
- [ ] Kubernetes básico
- [ ] CI/CD com Docker
- [ ] Registry privado
- [ ] Security scanning

### Nível 4: Expert

- [ ] Kubernetes avançado
- [ ] Service mesh (Istio)
- [ ] GitOps (ArgoCD, Flux)
- [ ] Observability completa
- [ ] Arquitetura cloud-native

---

## 📝 Notas Importantes

> 💡 **Dica:** Este projeto é um ponto de partida. Expanda-o adicionando mais serviços como banco de dados, cache, web server, etc.

> 🔒 **Segurança:** Nunca commite credenciais ou secrets no docker-compose.yml. Use arquivos .env (no .gitignore) ou Docker secrets.

> 📦 **Produção:** Docker Compose é ideal para desenvolvimento. Para produção em larga escala, considere Kubernetes ou Docker Swarm.

> 🚀 **Performance:** Containers compartilham o kernel do host, então são muito mais leves que VMs.

> 🎯 **Portabilidade:** O mesmo docker-compose.yml funciona em Windows, Linux e Mac com Docker instalado.

---

## 🌟 Por que Docker é Revolucionário?

### Antes do Docker

```
Desenvolvedor: "Funciona na minha máquina!" 🤷
DevOps: "Mas não funciona em produção..." 😤

Problemas:
- Ambientes inconsistentes
- "Dependency hell"
- Deploy complicado
- Difícil replicar bugs
```

### Com Docker

```
Desenvolvedor: "Aqui está o container!" 🐳
DevOps: "Perfeito, vou fazer deploy!" 😊

Soluções:
✅ Ambiente idêntico em dev/test/prod
✅ Todas as dependências empacotadas
✅ Deploy simplificado
✅ Bugs reproduzíveis
✅ Rollback em segundos
```

---

<div align="center">

**📅 Última atualização:** Abril 2026  
**📌 Versão Docker Compose:** 3.1  
**✅ Status:** Funcional e educacional  
**🐳 Tecnologia:** Docker + Docker Compose

---

**"Se funciona no container, funciona em qualquer lugar!"** 🌍

**#Docker #DockerCompose #Containers #DevOps #Ubuntu #Containerization**

</div>
