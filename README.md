# 🔢 Byte Counter

> **Analisador preciso de bytes, encodings, BOM, quebras de linha e graphemes em tempo real — 100% client-side e sem dependências de build.**

![Versão](https://img.shields.io/badge/versão-2.4-0550AE?style=flat-square)
![Arquitetura](https://img.shields.io/badge/arquitetura-Single--File%20HTML-116329?style=flat-square)
![Privacidade](https://img.shields.io/badge/privacidade-100%25%20Local%20%2F%20Offline-3B444E?style=flat-square)
![Licença](https://img.shields.io/badge/licença-MIT-blue?style=flat-square)

O **Byte Counter** é uma ferramenta web leve e responsiva projetada para desenvolvedores, analistas de dados e engenheiros de software que precisam inspecionar com exatidão o tamanho real de strings, arquivos e payloads antes de enviá-los para APIs, bancos de dados ou sistemas legados.

---

## ✨ Principais Funcionalidades

### 🔍 Análise Técnica em Tempo Real
* **Múltiplos Encodings Simultâneos:** Calcule o tamanho exato em **UTF-8**, **UTF-16 LE**, **UTF-16 BE**, **ASCII (7-bit lossy)** e **ISO-8859-1 / Latin-1**.
* **Simulação de BOM (*Byte Order Mark*):** Adicione ou remova o BOM (`EF BB BF` para UTF-8 e `FF FE` / `FE FF` para UTF-16) com atualização instantânea na contagem de bytes e no preview hexadecimal.
* **Controle de Quebra de Linha (`LF` vs `CRLF`):** Alterne entre o padrão Unix/macOS (`\n` — 1 byte) e Windows (`\r\n` — 2 bytes) ou preserve a estrutura original do texto.
* **Contagem por Graphemes (`Intl.Segmenter`):** Diferencia *code points* de caracteres visíveis reais (ex.: emojis compostos como `👨‍👩‍👧‍👦` ou bandeiras `🇧🇷` contam como `1` grapheme, revelando seu custo real em bytes).
* **Conversão Automática de Escalas:** Exibição simultânea em **Bytes (B)**, **Kilobytes (KB)**, **Megabytes (MB)** e **Gigabytes (GB)**, além da estimativa de tamanho após codificação **Base64**.
* **Inspetor Hexadecimal (Preview 16 Bytes):** Visualização imediata dos primeiros 16 bytes codificados em hexadecimal para diagnosticar caracteres invisíveis, BOMs e terminadores de linha.

### 📂 Importação e Exportação Inteligente
* **Detecção Automática na Entrada:** Suporta seleção de arquivo ou *Drag & Drop* (`.txt`, `.json`, `.csv`, `.xml`, `.sql`, `.log`, etc.), lendo os bytes brutos (`ArrayBuffer`) para detectar automaticamente o **encoding**, presença de **BOM** e padrão de **quebra de linha**.
* **Exportação Versátil:**
  * **`.TXT`:** Exporta o texto convertido aplicando exatamente o encoding, BOM e quebras de linha selecionados.
  * **`.JSON`:** Exporta um relatório estruturado completo com configurações, todas as métricas e diagnósticos.
  * **`.CSV`:** Gera planilha separada por ponto e vírgula (`;`) com BOM UTF-8, pronta para abrir no Microsoft Excel ou Google Sheets sem quebra de acentuação.

### 🎨 Interface e Experiência de Uso
* **Design System GitHub Primer:** Paleta de alto contraste pensada para leitura prolongada, com **Modo Claro Suave (*Paper Soft*)** e **Modo Escuro (*GitHub Dark*)**.
* **Layout Responsivo (Mobile-First):** Navegação otimizada por abas (*Editor de Texto* vs *Métricas & Hex*) em telas pequenas, sem perda de visibilidade.
* **Privacidade Total:** Todo o processamento ocorre na memória do navegador (`TextEncoder`, `TextDecoder`, `Intl.Segmenter`). Nenhum dado é enviado para servidores externos.

---

## 🚀 Como Usar

Por ser construído em arquitetura **Single-File** (`appByteCalc.html`), não há necessidade de instalar Node.js, bundlers ou dependências:

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/seu-usuario/byte-counter.git
   ```
2. **Execute localmente:**
   Abra o arquivo `appByteCalc.html` diretamente em qualquer navegador moderno (Chrome, Firefox, Edge, Safari) ou sirva-o via **GitHub Pages**, **Vercel** ou **Netlify**.

---

## 🛠️ Tecnologias Utilizadas

* **HTML5 & JavaScript (ES6+ Vanilla):** Uso nativo das APIs `TextEncoder`, `TextDecoder`, `FileReader` (`ArrayBuffer`), `Blob` e `Intl.Segmenter`.
* **Tailwind CSS (via CDN):** Estilização responsiva com suporte a temas dinâmicos (`darkMode: 'class'`).

---

## 📊 Capacidade e Desempenho

* **Uso ideal e instantâneo:** Textos e arquivos de até **5 MB** (~5 milhões de caracteres).
* **Limite prático no navegador:** Arquivos de texto entre **10 MB e 50 MB**, limitado apenas pela memória alocada pelo motor JavaScript e renderização do `<textarea>` do navegador.

---

## ⌨️ Atalhos e Utilitários

| Ação | Descrição |
| :--- | :--- |
| `Ctrl / Cmd + Enter` | Força o recálculo imediato das métricas |
| **Colar** | Insere o conteúdo da área de transferência diretamente no editor |
| **Limpar Espaços** | Remove espaços em branco à direita das linhas e linhas vazias excedentes |
| **Copiar Resumo** | Copia um relatório formatado em texto plano para a área de transferência |

---

## 📄 Licença

Este projeto está sob a licença **MIT**. Sinta-se livre para usar, modificar e distribuir.
