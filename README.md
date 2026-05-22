# CP02 — Compliance & QA

MVP de testes para um sistema de login, aplicando testes manuais e validações automatizadas com **Katalon Recorder**.

> **Disciplina:** Compliance & QA · **Professora:** Larissa Schauer · **Instituição:** FIAP

---

## Sobre o projeto

O sistema sob teste é uma tela de login simples (HTML/JS) com as seguintes funcionalidades:

- Autenticação por e-mail e senha
- Validação de campos obrigatórios
- Validação de formato de e-mail
- Validação de tamanho mínimo da senha
- Mensagens de erro contextuais
- Toggle de mostrar/ocultar senha
- Tela de boas-vindas após login
- Logout (botão Sair)

**Credenciais de teste:**

| E-mail | Senha |
|---|---|
| `jennyfer@fiap.com.br` | `senha123` |
| `admin@teste.com` | `admin123` |

---

## Estrutura do repositório

```
cp02-qa/
├── login.html                           # Sistema sob teste
├── README.md                            # Este arquivo
│
├── manual-tests/
│   └── Casos_de_Teste_Manuais.xlsx     # 4 casos de teste (Parte A)
│
├── automation/
│   ├── CT01_Login_Valido.html          # Teste automatizado 1
│   └── CT02_Senha_Incorreta.html       # Teste automatizado 2
│
└── evidencias/
    ├── CT01_login_valido.png
    ├── CT02_senha_incorreta.png
    ├── CT03_usuario_nao_cadastrado.png
    ├── CT04_campos_vazios.png
    ├── automacao_playback.mp4
    └── automacao_resultado.png
```

---

## Parte A — Testes Manuais

Os 4 casos de teste estão documentados em `manual-tests/Casos_de_Teste_Manuais.xlsx`.

**Cobertura:**

| ID | Funcionalidade | Cenário |
|---|---|---|
| CT01 | Login | Login com credenciais válidas |
| CT02 | Login | Login com senha incorreta |
| CT03 | Validação de Campos | Login com e-mail não cadastrado |
| CT04 | Validação de Campos | Login com campos vazios |

Cada caso contém: ID, funcionalidade, cenário, pré-condições, passos detalhados, dados de entrada, resultado esperado, resultado obtido, status, evidência associada e responsável.

A aba **Resumo** consolida estatísticas (total, aprovados, reprovados, bloqueados, taxa de aprovação) com fórmulas que se atualizam automaticamente ao alterar o status dos casos.

---

## Parte B — Validação Automatizada (Katalon Recorder)

### 1. Hospedar o sistema no GitHub Pages

1. Faça push deste repositório para o GitHub (público).
2. Vá em **Settings → Pages**.
3. Em **Source**, selecione a branch `main` e a pasta `/ (root)`.
4. Clique em **Save**.
5. Aguarde alguns minutos. O sistema ficará disponível em:
   ```
   https://SEU-USUARIO.github.io/cp02-qa/login.html
   ```

### 2. Atualizar a URL base nos testes

Nos arquivos `automation/CT01_Login_Valido.html` e `automation/CT02_Senha_Incorreta.html`, localize a linha:

```html
<link rel="selenium.base" href="https://SEU-USUARIO.github.io/cp02-qa/" />
```

Substitua `SEU-USUARIO` pelo seu usuário do GitHub e `cp02-qa` pelo nome do seu repositório.

### 3. Instalar a extensão Katalon Recorder

1. Abrir o **Google Chrome**
2. Acessar a [Chrome Web Store](https://chromewebstore.google.com/)
3. Pesquisar por **"Katalon Recorder"**
4. Clicar em **Adicionar ao Chrome**
5. Confirmar a instalação

### 4. Importar os testes

1. Abrir a extensão Katalon Recorder no Chrome.
2. No menu lateral, clicar em **Test Cases**.
3. Clicar no ícone de **importar** (seta para cima).
4. Selecionar os arquivos `CT01_Login_Valido.html` e `CT02_Senha_Incorreta.html`.
5. Os testes aparecerão na lista de Test Cases.

### 5. Executar os testes

1. Selecionar o caso de teste desejado.
2. Clicar em **Play** (ícone de play verde) — pode ser "Play Test Case" para rodar só esse, ou "Play Test Suite" para rodar todos.
3. Acompanhar a execução: o Katalon abrirá a tela de login, preencherá os campos, clicará no botão e validará os resultados.
4. O resultado aparece no painel **Log**:
   - **Verde:** teste aprovado
   - **Vermelho:** teste falhou

### 6. Exportar a suíte de testes (formato .html)

Conforme orientado em aula:

1. Clicar nos **três pontinhos** ao lado do nome da Test Suite.
2. Selecionar **Save Test Suite**.
3. Clicar novamente nos três pontinhos.
4. Selecionar **Export → HTML (.html)**.

---

## Evidências

Conforme o checklist apresentado em aula, a pasta `evidencias/` deve conter:

- **Screenshots** de cada caso de teste manual executado
- **Vídeo do playback** dos testes automatizados rodando no Katalon Recorder
- **Screenshot do resultado** mostrando os logs de execução do Katalon (verde = aprovado)

**Como gravar o playback no Windows:**

1. Pressionar `Win + G` para abrir a Xbox Game Bar
2. Clicar no botão de **Capturar**
3. Iniciar a gravação antes de clicar em Play no Katalon
4. Parar a gravação após o término
5. O vídeo será salvo em `Vídeos/Capturas`

Como alternativa: [Loom](https://www.loom.com/) (gratuito) ou OBS Studio.

---

## Ferramentas utilizadas

| Categoria | Ferramenta |
|---|---|
| Sistema sob teste | HTML5 + JavaScript |
| Organização dos testes manuais | Microsoft Excel |
| Automação | Katalon Recorder (extensão Chrome) |
| Hospedagem | GitHub Pages |
| Evidências | Xbox Game Bar / Screenshots |
| Versionamento | Git + GitHub |

---

## Checklist de entrega

- [ ] Repositório GitHub público criado
- [ ] `login.html` na raiz do repositório
- [ ] GitHub Pages habilitado e funcionando
- [ ] URL base atualizada nos arquivos `.html` da pasta `automation/`
- [ ] Pasta `manual-tests/` com o Excel dos 4 casos de teste
- [ ] Pasta `automation/` com os 2 testes do Katalon Recorder
- [ ] Pasta `evidencias/` com screenshots + vídeo do playback
- [ ] README.md atualizado com seu nome e link do GitHub Pages

---
