# 📚 Tradutor de Livros

> **Traduza livros em EPUB e PDF direto no navegador.** Sem instalação, sem cadastro, sem servidor próprio. Gratuito e open source.

<img align="center" src="imagens-tradutor-de-livros/tela inicial.png" width="100%" alt="Tela inicial do Tradutor de Livros"><br>

---
## 🖼️ Demonstração

### Tela inicial

<img align="center" src="imagens-tradutor-de-livros/Tela inicial.gif" width="500" alt="Tela inicial">

### Processo de tradução

<img align="center" src="imagens-tradutor-de-livros/Processo.gif" width="500" alt="Processo de tradução">

### Resultado final

<img align="center" src="imagens-tradutor-de-livros/Resultado final.gif" width="500" alt="Resultado final">

---
## ✨ Sobre o projeto

O **Tradutor de Livros** é uma aplicação web de arquivo único (HTML + CSS + JS) que permite traduzir livros completos nos formatos **EPUB** e **PDF**.

- O **processamento do arquivo** (leitura, extração de texto, imagens, montagem do livro traduzido) acontece **inteiramente no seu navegador**.
- Os **trechos de texto** são enviados a serviços públicos de tradução durante o processo (Google, Lingva, MyMemory e outros, com fallback automático).
- Quando o navegador suporta a **API nativa de tradução** (Chrome/Edge recentes), ela é usada primeiro — e nesse caso a tradução acontece **100% no aparelho**.

---
## 🚀 Funcionalidades

### 📖 Leitura de arquivos
- Suporte a **EPUB** e **PDF**
- Extração de texto **e** imagens, preservando a posição original das imagens
- Detecção automática do tipo de arquivo (mesmo quando o MIME ou a extensão vêm errados)
- Detecção automática do **idioma do livro**

### 🌍 Tradução
- **8 idiomas** de destino: Português, Inglês, Espanhol, Francês, Alemão, Italiano, Chinês e Japonês
- **7 serviços de tradução** com fallback automático:
  - Tradutor nativo do navegador (100% local, quando disponível)
  - Google Translate (3 endpoints)
  - Lingva (2 instâncias)
  - MyMemory
  - Proxy AllOrigins (último recurso)
- **Verificação anti-falha**: detecta quando o serviço devolve o texto sem traduzir e refaz em outro serviço
- **3 modos de velocidade**: Rápida / Equilibrada / Segura (com ajuste automático se o serviço limitar)

### 👤 Proteção de nomes próprios
- Lista manual de nomes que não devem ser traduzidos
- **Detecção automática** de nomes recorrentes do livro (personagens, lugares)
- Nomes são substituídos por marcadores neutros antes do envio e restaurados depois

### 💾 Retomada de tradução
- Cancela quando quiser; o progresso é preservado
- Botão **"Continuar"** retoma exatamente de onde parou
- Nada de texto **sem tradução** é exibido: se um trecho não puder ser traduzido, o app avisa

### 📖 Pré-visualização
- Leitura capítulo a capítulo dentro do app
- Sumário navegável
- Barra de progresso por capítulo
- **Tema claro/escuro automático** (segue o sistema)
- Acessibilidade: foco visível, `aria-live`, `role="progressbar"`, navegação por teclado

### 📥 Exportação
- **EPUB** válido (EPUB 3, com sumário, capítulos e imagens)
- **PDF** (via janela de impressão do navegador → "Salvar como PDF")
- **Copiar texto** traduzido para a área de transferência

### 📱 Interface
- Totalmente responsiva (desktop e celular)
- Suporte a **arrastar-e-soltar** no computador
- Funciona em arquivo único — basta abrir o `index.html`

---

## ⚠️ Limitações

- **Precisa de internet** para traduzir (exceto quando o tradutor nativo do navegador está disponível)
- **PDFs escaneados** (compostos apenas de imagem, sem camada de texto) **não são suportados**
- Alguns serviços de tradução podem **limitar requisições** ou ficar **indisponíveis** temporariamente — o app troca de serviço automaticamente
- **Bloqueadores de anúncios / extensões de privacidade** podem interferir nas chamadas às APIs de tradução
- A **detecção automática de nomes** funciona melhor em inglês, português, espanhol, francês e italiano; para chinês, japonês e alemão é desativada
