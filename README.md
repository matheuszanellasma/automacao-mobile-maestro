# 📱 Automação Mobile com Maestro - Qazandofood

Este repositório contém o projeto de automação de testes mobile para o aplicativo **Qazandofood** utilizando o framework **Maestro**. O objetivo principal é garantir a qualidade do fluxo de Login e Fechamento de Pedidos

---

## 🚀 Tecnologias e Ferramentas Utilizadas

- **Maestro CLI / Cloud:** 
- **YAML:** Linguagem adotada para a escrita dos fluxos de teste.
- **Android Studio (Emulador):** Utilizado para validar o comportamento do aplicativo em diferentes telas
- **Vysor:** Utilizado para o espelhamento em tempo real em dispositivo físico (celular real).
- **GitHub Actions:** Ferramenta de CI/CD para automatizar o ciclo de testes.

---

## 📋 Estrutura de Testes

### 🔑 Módulo de Login
- `login_sucesso.yaml`: Validação do fluxo principal de autenticação com dados corretos. (smoke)
- `login_email_em_branco.yaml`: Validação do comportamento do sistema ao omitir o e-mail.
- `login_sem_arroba.yaml`: Teste de validação sintática do campo de e-mail (ausência do `@`).
- `login_sem_dominio.yaml`: Teste de validação de estrutura do e-mail incompleto (ex: `usuario@`).
- `login_senha_em_branco.yaml`: Validação de comportamento ao omitir o campo de senha.

### 🛒 Módulo de Pedidos
- `pedido_cartao_sucesso.yaml`: Fluxo completo de ponta a ponta realizando pagamento via cartão de crédito. (smoke)
- `pedido_dinheiro_sucesso.yaml`: Fluxo completo realizando o pagamento em dinheiro diretamente na entrega. (smoke)

---

## ⚙️ Integração Contínua (CI/CD)

O projeto possui uma esteira automatizada de integração contínua integrada diretamente ao **Maestro Cloud**:

- **Gatilho:** A esteira é disparada automaticamente a cada evento de `push` realizado na branch `master`.
- **Ação:** O pipeline executa os **Smoke Tests** na infraestrutura em nuvem do Maestro Cloud

---

## 📦 APK do Aplicativo

Para garantir a portabilidade e facilitar auditorias ou execuções de terceiros, o arquivo executável compilado (`.apk`) do Qazandofood está disponibilizado diretamente na aba de **Releases** deste repositório.

---

## 🛠️ Como Executar os Testes Localmente

### Pré-requisitos
- **Maestro CLI** instalado na máquina.
- **Emulador Android** ou celular físico conectado com a Depuração USB ativa.
- **Arquivo APK** do aplicativo (disponível na aba de Releases) baixado e colocado na raiz do projeto.

### Passo a Passo (Configuração e Execução)
```bash
git clone https://github.com/matheuszanellasma/automacao-mobile-maestro.git
cd automacao-mobile-maestro
maestro test login/
```

---

## 👤 Autor

* **Matheus Koehler Zanella** - Quality Assurance Engineer
