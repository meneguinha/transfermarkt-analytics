# Transfermarkt Analytics - Painel de Transferências de Futebol

Um dashboard moderno, rápido e responsivo construído com **HTML5, CSS3 e JavaScript puro (Vanilla)** para analisar o histórico de transferências de mercado de futebol com base no dataset do Transfermarkt.

O painel é alimentado diretamente a partir de um arquivo `transfers.csv` e processado de forma eficiente diretamente no navegador do cliente usando a biblioteca **PapaParse**.

---

## 🚀 Funcionalidades Principais

* **Busca Inteligente de Clubes (Autocomplete)**: Campo de busca interativo com listagem rápida de clubes recorrentes (mais populares do dataset) e autocomplementação inteligente com suporte a navegação por teclado e busca tolerante a acentos.
* **Filtro de Período Bidirecional (Anos)**:
  * Slider de intervalo duplo (min/max anos) limitado a 2026.
  * Caixas de texto numéricas editáveis que sincronizam bidirecionalmente com o slider.
  * Validação robusta que impede erros de consistência (como ano inicial maior que o final) e ajusta limites automaticamente.
* **Mapeamento Visual por Cores**:
  * **Azul**: Associado a tudo relacionado a **Chegadas** (investimentos, gastos, KPIs de compras, abas e badges na tabela).
  * **Verde**: Associado a tudo relacionado a **Vendas** (faturamento, saídas, KPIs de vendas, abas e badges na tabela).
* **Painel de KPIs Financeiros**:
  * Total de Gastos (Chegadas).
  * Total de Vendas (Saídas).
  * Saldo Líquido (Net Spend) com indicador de tendência (lucro/prejuízo) e uma barra visual de proporção (Investimento vs. Venda).
* **Internacionalização Dinâmica (Multi-idioma PT/EN)**:
  * Alternador elegante no cabeçalho permitindo alternar instantaneamente entre **Português (PT)** e **Inglês (EN)**.
  * Tradução instantânea de toda a interface, cabeçalhos, mensagens de erro, formatação de moedas regionais (€) e formatação de datas (`DD/MM/YYYY` vs. `MM/DD/YYYY`).
* **Tabela de Atletas Detalhada**: Listagem paginada (15 registros por página) contendo iniciais automáticas em badges, valor de mercado, taxa de transferência (com badges dinâmicos para "Gratuito" ou "Não informado") e links interativos para navegar rapidamente entre os clubes.

---

## 🛠️ Tecnologias Utilizadas

* **HTML5**: Estruturação semântica e acessível.
* **CSS3**: Estilização moderna (tema claro premium, gradientes suaves, efeitos glassmorphism e micro-animações de hover).
* **Vanilla JavaScript**: Lógica do dashboard, cruzamento de filtros, manipulação do DOM e internacionalização (sem frameworks pesados).
* **[PapaParse](https://www.papaparse.com/)**: Processamento e parse ultrarrápido do arquivo CSV de grande escala (+170 mil registros) diretamente no client-side.
* **[FontAwesome Icons](https://fontawesome.com/)**: Biblioteca de ícones modernos para a interface.
* **Google Fonts**: Tipografias *Plus Jakarta Sans* e *Outfit*.

---

## 📥 Como Rodar o Projeto Localmente

### Pré-requisitos
Para o carregamento automático dos dados, a página precisa de um ambiente de servidor web simples para evitar restrições de segurança locais de arquivos (CORS).

1. Clone ou baixe este repositório.
2. Certifique-se de ter o arquivo `transfers.csv` na mesma pasta do arquivo `index.html`.
3. Inicie um servidor estático local de sua preferência:

#### Usando Python:
Abra o terminal na pasta do projeto e digite:
```bash
python -m http.server 8000
```
Depois acesse `http://localhost:8000` no seu navegador.

#### Usando Node.js (via npx):
```bash
npx http-server -p 8000
```
Depois acesse `http://localhost:8000` no seu navegador.

#### Método Fallback (Sem Servidor):
Se você abrir o arquivo `index.html` diretamente no navegador dando um duplo clique, o dashboard detectará a restrição de CORS e exibirá um botão elegante para você **selecionar o arquivo `transfers.csv` localmente** no seu computador. Após selecioná-lo, o processamento iniciará imediatamente!

---

> [!TIP]
> Embora o arquivo `transfers.csv` possua cerca de 14.7 MB em disco, servidores modernos como o GitHub Pages o transmitem utilizando compressão (Gzip/Brotli), o que reduz o download inicial para menos de 3.5 MB, tornando o carregamento do painel extremamente rápido.

---

## 📊 Fonte dos Dados

Os dados de transferências utilizados neste projeto foram obtidos a partir do dataset público do Kaggle:  
👉 [Kaggle - Football Data from Transfermarkt](https://www.kaggle.com/datasets/davidcariboo/player-scores)
