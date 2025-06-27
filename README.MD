# ✅ Casos de Teste - SauceDemo

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Robot Framework](https://img.shields.io/badge/robot%20framework-automation-green)

### 👤 Dados do Aluno
- **Nome:** Gabriel Queiroz de Souza  
- **Matrícula:** UC23200732  

---

### 🔍 Visão Geral

Este repositório contém testes automatizados desenvolvidos com **Robot Framework** seguindo a abordagem **BDD (Behavior-Driven Development)** para o site [SauceDemo](https://www.saucedemo.com/).

---

### 🗂️ Estrutura do Projeto

```
📦 ProvaTesteSoftware
├── Login e Logout/       # Testes de login e logout
├── Produtos/             # Testes de visualização e ordenação
├── Carrinho/             # Testes de adicionar/remover itens
└── Checkout/             # Testes de finalização de compra
```

> 📸 **Evidências de Teste:**  
> As capturas de tela são geradas automaticamente e armazenadas na pasta `evidencias/` dentro de cada diretório correspondente.

---

### 🧪 Casos de Teste

#### 🔐 Login e Logout

**Cenário: Login Válido e Logout**
```gherkin
Dado que eu abro a página da SauceDemo
E preencho o campo Username com um usuário válido
E preencho o campo Password com uma senha válida
Quando eu acesso a plataforma
E acesso o menu de opções
Então eu clico no botão de Logout para sair
```

**Cenário: Tentativa de Login com Usuário Bloqueado**
```gherkin
Dado que eu abro a página da SauceDemo
E preencho o campo Username com um usuário bloqueado
E preencho o campo Password com uma senha
Quando eu tento acessar a plataforma
Então devo ver uma mensagem de erro informando que o usuário está bloqueado
```
> 💡 *O teste `LoginInvalido_Logout` tenta seguir o fluxo completo, mas a falha no login bloqueado impede o logout. O BDD acima representa o comportamento ideal.*

---

#### 🛍️ Produtos

**Cenário: Visualizar e Ordenar Produtos na Loja**
```gherkin
Dado que eu estou logado na plataforma SauceDemo
Quando eu vejo os detalhes de um produto
E retorno a página inicial
E ordeno os produtos por preço (menor para maior)
E ordeno os produtos por nome (A-Z)
E ordeno os produtos por preço (maior para menor)
Então a ordenação dos produtos por nome (Z-A) deve ser aplicada corretamente
```

---

#### 🛒 Carrinho de Compras

**Cenário: Adicionar e Remover Itens do Carrinho**
```gherkin
Dado que eu estou logado na plataforma SauceDemo
Quando eu vejo os detalhes de um produto
E adiciono o produto ao carrinho
E retorno a página inicial
E vejo os detalhes de um outro produto
E adiciono o outro produto ao carrinho
E acesso o carrinho
Então eu removo um dos produtos do carrinho
```

---

#### 📦 Checkout

**Cenário: Finalizar uma Compra com Sucesso**
```gherkin
Dado que eu adicionei um produto ao carrinho
Quando eu acesso o carrinho
E realizo o checkout
E preencho o campo First Name
E preencho o campo Last Name
E preencho o campo Zip/Postal Code
E vejo os detalhes do checkout
Então eu finalizo a compra
```

---

### ▶️ Como Executar os Testes

📌 **Pré-requisitos**
- [Python](https://www.python.org/)
- [Robot Framework](https://robotframework.org/)
- [SeleniumLibrary](http://robotframework.org/SeleniumLibrary/)

📥 **1. Instale as dependências**
```bash
pip install robotframework robotframework-seleniumlibrary
```

🚀 **2. Execute os testes**
No terminal, dentro da pasta raiz do projeto:

- Executar um teste específico:
```bash
robot Carrinho/carrinho.robot
```

- Executar todos os testes:
```bash
robot .
```

---

🧾 Para mais informações sobre o Robot Framework, consulte a [documentação oficial](https://robotframework.org/).
