# README.md - Sistema de Atendimento ao Público Municipal

<div align="center">

**Sistema de atendimento ao público para prefeituras municipais**

[🚀 Começar](#-instalação) -  [📖 Documentação](#-documentação) -  [🤝 Contribuir](#-contribuindo) -  [📝 Licença](#-licença)

</div>

***

## 📋 Sobre o Projeto

O **Sistema de Atendimento ao Público Municipal** é uma solução completa e modular desenvolvida para modernizar e digitalizar o atendimento aos cidadãos em prefeituras. O sistema oferece controle total do fluxo de atendimento, desde a emissão de protocolos até a avaliação final do serviço prestado.

### 🎯 Principais Objetivos

- **Digitalização completa** do atendimento presencial e remoto
- **Rastreabilidade total** de protocolos e documentos
- **Integração unificada** entre todas as secretarias
- **Conformidade com a LGPD** e legislação vigente
- **Experiência cidadã** otimizada e acessível

### ⭐ Funcionalidades Principais

<details>
<summary><strong>🔖 Protocolo Eletrônico</strong></summary>

- Emissão automática de protocolos únicos
- Classificação por setor, tipo e prioridade  
- Acompanhamento em tempo real
- Histórico completo de movimentações
- Encerramento com avaliação NPS

</details>

<details>
<summary><strong>👥 Gestão de Cidadãos</strong></summary>

- Cadastro unificado de munícipes
- Integração com Receita Federal
- Proteção de dados sensíveis (LGPD)
- Histórico centralizado de atendimentos
- Aplicativo móvel para o cidadão

</details>

<details>
<summary><strong>🎫 Senhas e Filas</strong></summary>

- Sistema de senhas com prioridade legal
- Painéis em tempo real (TVs/Totens)
- Previsão de tempo de espera
- Controle de desempenho por operador
- Integração com agendamentos

</details>

<details>
<summary><strong>📅 Agendamento de Serviços</strong></summary>

- Agenda online para cidadãos
- Controle por servidor/setor
- Notificações automáticas (e-mail, SMS, push)
- Check-in em totens
- Reagendamentos controlados

</details>

<details>
<summary><strong>📄 Gestão de Documentos</strong></summary>

- Upload seguro com antivírus integrado
- Controle de versão e auditoria
- Assinatura digital opcional
- Conformidade com padrões governamentais
- Backup automático

</details>

<details>
<summary><strong>📊 Painéis Gerenciais</strong></summary>

- Indicadores em tempo real
- Relatórios de produtividade
- Métricas de qualidade (NPS)
- Comparativos entre setores
- Exportação automatizada

</details>

***

## 🏗️ Arquitetura do Sistema

### 📐 Arquitetura Modular

```
Sistema de Atendimento Municipal
├── 🔖 Módulo de Protocolo Eletrônico
├── 📄 Módulo de Gestão de Documentos  
├── 👥 Módulo de Cadastro de Cidadãos
├── 💾 Módulo de Banco de Dados Compartilhado
├── 🚪 Módulo de Gestão de Visitantes
├── 🎫 Módulo de Senhas e Atendimento
├── 📅 Módulo de Agendamento
├── 🔍 Módulo de Consulta Pública
├── 📊 Módulo de Painéis Gerenciais
├── 📺 Módulo de Publicidade Institucional
├── 🔧 Módulo de Pedidos Internos
├── 🔐 Módulo de Controle de Permissões
├── 🔌 Módulo de Integração (APIs)
└── 📱 Aplicativo do Cidadão
```

### 🛠️ Stack Tecnológico

| Componente | Tecnologia | Versão |
|------------|-----------|---------|
| **Backend** | FastAPI + Python | 3.11+ |
| **Banco de Dados** | PostgreSQL | 15+ |
| **Cache/Filas** | Redis | 7+ |
| **Frontend Web** | React + TypeScript | 18+ |
| **App Mobile** | React Native | 0.72+ |
| **Containerização** | Docker + Compose | 24+ |
| **Documentação** | Swagger/OpenAPI | Auto |

### 🔐 Segurança e Conformidade

- **Autenticação**: JWT com refresh tokens
- **2FA**: TOTP (Google/Microsoft Authenticator)
- **Hashing**: Argon2 para senhas
- **LGPD**: Criptografia, auditoria e consentimento
- **RBAC**: Controle granular de permissões
- **Antivírus**: Integração com ClamAV

***

## 🚀 Instalação

### 📋 Pré-requisitos

- [Docker](https://www.docker.com/get-started) 20.10+
- [Docker Compose](https://docs.docker.com/compose/) 2.0+
- [Git](https://git-scm.com/downloads) 2.30+
- [Node.js](https://nodejs.org/) 18+ (para desenvolvimento)
- [Python](https://www.python.org/) 3.11+ (para desenvolvimento)

### ⚡ Instalação Rápida com Docker

```bash
# Clone o repositório
git clone https://github.com/ltitelecom/PortalCidadao.git
cd sistema-atendimento-municipal

# Configure as variáveis de ambiente
cp .env.example .env
# Edite o arquivo .env com suas configurações

# Execute o sistema completo
docker-compose up -d

# Aguarde alguns segundos para inicialização e acesse:
# Frontend: http://localhost:3000
# API: http://localhost:8000
# Documentação da API: http://localhost:8000/docs
```

### 🔧 Instalação para Desenvolvimento

<details>
<summary><strong>Configuração Detalhada</strong></summary>

```bash
# 1. Clone e entre no diretório
git clone https://github.com/ltitelecom/PortalCidadao.git
cd sistema-atendimento-municipal

# 2. Configure o backend
cd backend
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate   # Windows
pip install -r requirements.txt

# 3. Configure o banco de dados
# Crie um banco PostgreSQL e configure DATABASE_URL no .env
alembic upgrade head

# 4. Configure o frontend
cd ../frontend
npm install

# 5. Execute em modo desenvolvimento
# Terminal 1 - Backend
cd backend
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

# Terminal 2 - Frontend  
cd frontend
npm start
```

</details>

***

## 📖 Documentação

### 📚 Documentação Técnica

- **[API Documentation](http://localhost:8000/docs)** - Swagger interativo
- **[Guia de Instalação](docs/installation.md)** - Instalação detalhada
- **[Arquitetura do Sistema](docs/architecture.md)** - Visão técnica
- **[Guia de Desenvolvimento](docs/development.md)** - Para desenvolvedores

### 👨‍💼 Documentação de Usuário

- **[Manual do Gestor](docs/user-guides/gestor.md)** - Para gestores municipais
- **[Manual do Operador](docs/user-guides/operador.md)** - Para atendentes
- **[Manual do Cidadão](docs/user-guides/cidadao.md)** - Para cidadãos

### 🔧 Configuração e Deploy

- **[Configuração de Ambiente](docs/configuration.md)** - Variáveis e settings
- **[Deploy em Produção](docs/deployment.md)** - Deploy com Docker
- **[Backup e Recuperação](docs/backup.md)** - Estratégias de backup
- **[Monitoramento](docs/monitoring.md)** - Logs e métricas

***

## 🎯 Roadmap de Desenvolvimento

### 📅 Fases de Implementação

<details>
<summary><strong>📌 Fase 1: Fundação (2-3 meses)</strong></summary>

- ✅ Sistema de autenticação e RBAC
- ✅ Módulo de protocolo eletrônico  
- ✅ Cadastro de cidadãos
- ✅ Banco de dados compartilhado
- 🔄 Testes unitários e integração

</details>

<details>
<summary><strong>📌 Fase 2: Atendimento (2-3 meses)</strong></summary>

- 🔄 Sistema de senhas e filas
- 🔄 Agendamento de serviços
- 🔄 Painéis em tempo real
- ⏳ Integração com totens/TVs
- ⏳ Aplicativo móvel básico

</details>

<details>
<summary><strong>📌 Fase 3: Gestão (2 meses)</strong></summary>

- ⏳ Gestão de documentos
- ⏳ Consulta pública de protocolos
- ⏳ Painéis gerenciais
- ⏳ Relatórios automatizados

</details>

<details>
<summary><strong>📌 Fase 4: Integração (2 meses)</strong></summary>

- ⏳ Publicidade institucional
- ⏳ Pedidos internos
- ⏳ Integrações externas (APIs)
- ⏳ Aplicativo móvel completo

</details>

**Legenda**: ✅ Concluído | 🔄 Em andamento | ⏳ Planejado

***

## 🤝 Contribuindo

Valorizamos e incentivamos contribuições da comunidade! Existem várias maneiras de contribuir:

### 🐛 Reportando Bugs

1. Verifique se o bug já não foi reportado
2. Use nosso [template de bug report](.github/ISSUE_TEMPLATE/bug_report.md)
3. Seja descritivo e inclua steps para reprodução

### 💡 Sugerindo Melhorias

1. Verifique se a sugestão já existe
2. Use nosso [template de feature request](.github/ISSUE_TEMPLATE/feature_request.md)
3. Explique o problema e a solução proposta

### 👨‍💻 Contribuindo com Código

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Add: minha nova feature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

### 📖 Melhorando a Documentação

Documentação nunca está completa! Sinta-se à vontade para:
- Corrigir erros de digitação
- Adicionar exemplos
- Melhorar explicações
- Traduzir conteúdo

***

## 👥 Equipe e Colaboradores

### 🏛️ Equipe Principal

- **Arquiteto do Sistema** - [@username](https://github.com/username)
- **Desenvolvedor Backend** - [@username](https://github.com/username)  
- **Desenvolvedor Frontend** - [@username](https://github.com/username)
- **DevOps Engineer** - [@username](https://github.com/username)

### 🙏 Agradecimentos

Agradecemos a todos que contribuíram para este projeto:

- Prefeituras que forneceram feedback e requisitos
- Comunidade open source pelas ferramentas utilizadas
- Beta testers que ajudaram a identificar melhorias

***

## 📊 Status do Projeto

### 🔄 Build Status

![Build](https://img.shields.io/github/actions/workflow/status/prefe Testes**: 87%
- **Módulos Implementados**: 8/14
- **Issues Abertas**: 12
- **Pull Requests**: 3

***

## 📝 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

### ⚖️ Sobre a Licença MIT

A Licença MIT é uma licença permissiva que permite uso comercial, modificação, distribuição e uso privado. Ela requer apenas que o copyright e a licença sejam incluídos em todas as cópias ou partes substanciais do software.

***

## 📞 Contato e Suporte

### 🆘 Precisa de Ajuda?

- **📋 Issues**: Para bugs e sugestões
- **💬 Discussions**: Para dúvidas gerais
- **📧 E-mail**: suporte@sistema-municipal.gov.br
- **📞 Telefone**: (xx) xxxx-xxxx

### 🌐 Links Úteis

- **[Site Oficial](https://sistema-atendimento.gov.br)**
- **[Documentação Online](https://docs.sistema-atendimento.gov.br)**  
- **[Status do Sistema](https://status.sistema-atendimento.gov.br)**
- **[Changelog](CHANGELOG.md)**

***

<div align="center">

**⭐ Se este projeto foi útil para você, considere dar uma estrela!**

**Feito com ❤️ para modernizar o atendimento público brasileiro**

</div>

***

## LICENSE

```
MIT License

Copyright (c) 2025 Sistema de Atendimento ao Público Municipal

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

***
