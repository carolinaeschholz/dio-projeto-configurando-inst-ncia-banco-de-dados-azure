# Infraestrutura no Azure: Máquinas Virtuais, SQL Database e Estimativas de Custo

Este repositório tem oferece um resumo direto ao ponto sobre como configurar máquinas virtuais no Azure, incluindo escolha da imagem e arquitetura, como criar um banco de dados SQL com autenticação segura, e como usar a calculadora de custos para estimar investimentos em nuvem.

---

## 🖼 Escolhendo a Imagem e Arquitetura da Máquina Virtual

Ao criar uma VM no Azure, duas das escolhas mais importantes são:

### 📌 Imagem do Sistema Operacional

A imagem define qual sistema será instalado na sua VM. Alguns exemplos:

- **Windows Server 2022**
- **Ubuntu 20.04 LTS**
- **Debian, CentOS, Oracle Linux**
- **Imagens customizadas (Marketplace ou criadas por você)**

### 🏗 Arquitetura da Máquina

A arquitetura determina o tamanho da VM, sua capacidade de processamento, memória, GPU etc.

As séries mais comuns são:

| Série   | Indicação                          |
|---------|------------------------------------|
| **B**   | Baixo custo, ideal para testes     |
| **D**   | Uso geral, apps de negócios        |
| **E**   | Otimizada para memória             |
| **F**   | Otimizada para CPU                 |
| **N**   | Alta performance com GPU (IA, ML)  |

---

## 🧱 Criando um Banco de Dados SQL no Azure

Para criar um SQL Database gerenciado no Azure:

1. Vá até **SQL Databases** no portal.
2. Clique em **+ Criar**.
3. Preencha:
   - Nome do banco
   - Servidor lógico (pode criar um novo)
   - Camada de performance (Basic, Standard, Premium)
4. Defina as configurações de backup, segurança e rede.
5. Revise e crie.

> O Azure SQL Database é um serviço PaaS (Platform as a Service), ou seja, a Microsoft cuida de manutenção, atualizações e alta disponibilidade.

---

## 🔐 Métodos de Autenticação

Ao criar o servidor SQL, você precisará definir como os usuários se conectam ao banco.

### Opções disponíveis:

- **SQL Authentication**  
  Você define um nome de usuário e senha que serão usados para login. Simples, mas exige cuidado com a gestão de senhas.

- **Azure Active Directory (AAD)**  
  Integração com identidade corporativa. Ideal para organizações que já usam o Azure AD. Permite controle baseado em grupos e políticas de segurança.

- **Autenticação multifator (MFA)**  
  Pode ser habilitada via AAD para reforçar a segurança do login.

---

## 💰 Estimando Custos com a Calculadora do Azure

Antes de colocar qualquer recurso em produção, vale a pena simular os custos usando a calculadora oficial da Microsoft:

### Como usar:

1. Acesse: [calculadora.azure.com](https://azure.microsoft.com/pt-br/pricing/calculator/)
2. Selecione os serviços que pretende usar (ex: Máquinas Virtuais, SQL Database, Armazenamento).
3. Configure:
   - Região
   - Tipo e tamanho de VM
   - Tempo estimado de uso (horas por mês)
   - Tipo de licenciamento (incluso ou BYOL)
4. Veja o total estimado em tempo real.
