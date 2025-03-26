# poc_quickchart

# 📊 Tutorial QuickChart.io

[QuickChart.io](https://quickchart.io/) é uma API poderosa que permite gerar gráficos dinâmicos usando apenas uma URL. Com ela, você pode criar gráficos de barras, linhas, pizza e muito mais, integrando-os facilmente em dashboards, relatórios, bots ou READMEs de projetos no GitHub.

---

## 🚀 Como Funciona

A ideia central é construir uma URL que contenha uma configuração baseada no [Chart.js](https://www.chartjs.org/docs/latest/), definida em **JSON**. QuickChart interpreta essa configuração, gera o gráfico e retorna uma **imagem PNG**.

**Formato da URL:**

https://quickchart.io/chart?c=<configuração-em-JSON-codificada>

> **Dica:** Após criar seu JSON de configuração, utilize uma ferramenta de codificação de URL (como [urlencoder.io](https://www.urlencoder.org/)) para transformar o JSON em uma string adequada para a URL.

---

## 📈 Representação dos Dados em JSON

Antes de gerar a URL, é importante saber como estruturar seus dados no formato JSON. A seguir, veja alguns exemplos:

### 1. Gráfico de Barras

**JSON:**

```json
{
  "type": "bar",
  "data": {
    "labels": ["Janeiro", "Fevereiro", "Março"],
    "datasets": [
      {
        "label": "Vendas",
        "data": [10, 20, 30]
      }
    ]
  }
}
```

**Resultado:**

![Gráfico de Barras](https://quickchart.io/chart?c=%7B%22type%22%3A%22bar%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Janeiro%22%2C%22Fevereiro%22%2C%22Mar%C3%A7o%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Vendas%22%2C%22data%22%3A%5B10%2C20%2C30%5D%7D%5D%7D%7D)

---

### 2. Gráfico de Linhas

**JSON:**

```json
{
  "type": "line",
  "data": {
    "labels": ["Segunda", "Terça", "Quarta", "Quinta", "Sexta"],
    "datasets": [
      {
        "label": "Temperatura",
        "data": [22, 21, 23, 24, 22]
      }
    ]
  }
}
```

**Resultado:**

![Gráfico de Linhas](https://quickchart.io/chart?c=%7B%22type%22%3A%22line%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Segunda%22%2C%22Ter%C3%A7a%22%2C%22Quarta%22%2C%22Quinta%22%2C%22Sexta%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Temperatura%22%2C%22data%22%3A%5B22%2C21%2C23%2C24%2C22%5D%7D%5D%7D%7D)

---

### 3. Gráfico de Pizza

**JSON:**

```json
{
  "type": "pie",
  "data": {
    "labels": ["Azul", "Vermelho", "Amarelo"],
    "datasets": [
      {
        "data": [300, 50, 100]
      }
    ]
  }
}
```

**Resultado:**

![Gráfico de Pizza](https://quickchart.io/chart?c=%7B%22type%22%3A%22pie%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Azul%22%2C%22Vermelho%22%2C%22Amarelo%22%5D%2C%22datasets%22%3A%5B%7B%22data%22%3A%5B300%2C50%2C100%5D%7D%5D%7D%7D)

---

### 4. Gráfico Radar

**JSON:**

```json
{
  "type": "radar",
  "data": {
    "labels": ["Força", "Velocidade", "Resistência", "Inteligência", "Magia"],
    "datasets": [
      {
        "label": "Jogador A",
        "data": [65, 59, 90, 81, 56]
      },
      {
        "label": "Jogador B",
        "data": [28, 48, 40, 19, 96]
      }
    ]
  }
}
```

**Resultado:**

![Gráfico Radar](https://quickchart.io/chart?c=%7B%22type%22%3A%22radar%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22For%C3%A7a%22%2C%22Velocidade%22%2C%22Resist%C3%AAncia%22%2C%22Intelig%C3%AAncia%22%2C%22Magia%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Jogador%20A%22%2C%22data%22%3A%5B65%2C59%2C90%2C81%2C56%5D%7D%2C%7B%22label%22%3A%22Jogador%20B%22%2C%22data%22%3A%5B28%2C48%2C40%2C19%2C96%5D%7D%5D%7D%7D)

---

### 5. Gráfico de Linha com Título e Legenda

**JSON:**

```json
{
  "type": "line",
  "data": {
    "labels": ["Jan", "Fev", "Mar", "Abr", "Mai"],
    "datasets": [
      {
        "label": "Lucro",
        "data": [100, 200, 150, 300, 250]
      }
    ]
  },
  "options": {
    "title": {
      "display": true,
      "text": "Lucro Mensal"
    },
    "legend": {
      "position": "bottom"
    }
  }
}
```

**Resultado:**

![Gráfico com Título e Legenda](https://quickchart.io/chart?c=%7B%22type%22%3A%22line%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Jan%22%2C%22Fev%22%2C%22Mar%22%2C%22Abr%22%2C%22Mai%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Lucro%22%2C%22data%22%3A%5B100%2C200%2C150%2C300%2C250%5D%7D%5D%7D%2C%22options%22%3A%7B%22title%22%3A%7B%22display%22%3Atrue%2C%22text%22%3A%22Lucro%20Mensal%22%7D%2C%22legend%22%3A%7B%22position%22%3A%22bottom%22%7D%7D%7D)

---

### 6. Gauge Chart (Velocímetro)

**Resultado:**

![Gauge Chart](https://quickchart.io/chart?c=%7B%22type%22%3A%22doughnut%22%2C%22data%22%3A%7B%22datasets%22%3A%5B%7B%22data%22%3A%5B60%2C40%5D%2C%22backgroundColor%22%3A%5B%22green%22%2C%22lightgray%22%5D%2C%22borderWidth%22%3A0%7D%5D%7D%2C%22options%22%3A%7B%22rotation%22%3A1*Math.PI%2C%22circumference%22%3AMath.PI%2C%22cutoutPercentage%22%3A80%2C%22plugins%22%3A%7B%22datalabels%22%3A%7B%22display%22%3Afalse%7D%7D%7D%7D)

---

### 7. Gráfico Horizontal

**Resultado:**

![Gráfico Horizontal](https://quickchart.io/chart?c=%7B%22type%22%3A%22horizontalBar%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Produto%20A%22%2C%22Produto%20B%22%2C%22Produto%20C%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Vendas%22%2C%22data%22%3A%5B30%2C60%2C90%5D%7D%5D%7D%7D)

---

[...] 

---

### 8. Gráfico de Funil (Funnel Chart)

**Fonte de dados:** `./funnel_data.json`

**funnel_data.json:**

```json
{
  "labels": ["Visitantes", "Interessados", "Propostas", "Conversões"],
  "data": [1000, 800, 300, 80]
}
```

**JSON para QuickChart:**

```json
{
  "type": "funnel",
  "data": {
    "labels": ["Visitantes", "Interessados", "Propostas", "Conversões"],
    "datasets": [
      {
        "label": "Pipeline de Vendas",
        "data": [1000, 800, 300, 80]
      }
    ]
  }
}
```

**Resultado:**

![Gráfico de Funil](https://quickchart.io/chart?c=%7B%22type%22%3A%22funnel%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Visitantes%22%2C%22Interessados%22%2C%22Propostas%22%2C%22Convers%C3%B5es%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Pipeline%20de%20Vendas%22%2C%22data%22%3A%5B1000%2C800%2C300%2C80%5D%7D%5D%7D%7D)


## 🧰 Dicas Úteis

- **QuickChart Editor:** Utilize o [QuickChart Editor](https://quickchart.io/chart-maker/) para construir e testar seus gráficos de forma interativa.
- **Codificação da URL:** Lembre-se de sempre codificar sua configuração JSON antes de inserir na URL.
- **Customização:** Explore as opções de personalização do Chart.js para ajustar cores, títulos, legendas, eixos e outros elementos.
- **Testes:** Experimente diferentes configurações no [QuickChart Playground](https://quickchart.io/chart-maker/) para ver os resultados em tempo real.

---

## ✅ Conclusão

QuickChart é uma solução leve, prática e totalmente gratuita para gerar gráficos dinâmicos a partir de simples URLs. Trabalhando com dados estruturados em JSON, você pode integrar visualizações em diversos contextos, como READMEs, relatórios automatizados, dashboards e bots de chat. Explore as possibilidades e transforme seus dados em visualizações impactantes!

---

📎 **Documentação Completa:** [https://quickchart.io/documentation/](https://quickchart.io/documentation/)

---

https://github.com/govinda777/poc_quickchart

https://quickchart.io/gallery/

---

[... conteúdo anterior ...]

---

## 🔜 Próximos Passos

Se você gostou do poder do QuickChart, aqui estão algumas sugestões para expandir este projeto:

### 1. ✅ Automatizar a Geração de Gráficos
- Criar um script em **Python** ou **Node.js** para:
  - Ler dados de arquivos `.json`
  - Gerar URLs do QuickChart automaticamente
  - Salvar as imagens localmente (`/images/*.png`)
  - Atualizar automaticamente o `README.md` com os gráficos

### 2. 🌐 Criar uma API de suporte (chart-from-json)
- API que:
  - Recebe o caminho de um JSON como query param
  - Lê os dados do repositório ou uma URL
  - Gera dinamicamente a imagem ou redireciona para a URL do QuickChart
- Exemplo de rota: `/chart?type=funnel&file=data/funnel_data.json`
- Pode ser hospedado em [Render](https://render.com/), [Vercel](https://vercel.com/), [Replit](https://replit.com/)

### 3. 🧪 Adicionar testes para URLs geradas
- Validar se as URLs são válidas e se os gráficos são gerados corretamente.
- Usar ferramentas como `requests` (Python) ou `axios` (JS) + `jest`/`pytest`.

### 4. 🧱 Integrar com GitHub Actions
- Automatizar a geração de gráficos sempre que houver alteração nos dados.
- Exemplo:
  - Push em `data/*.json` → Roda script → Atualiza imagens + README

### 5. 📊 Explorar outros tipos de gráficos
- Gráfico de dispersão (scatter)
- Gráficos combinados (linha + barra)
- Mapas de calor (heatmaps com plugins)
- Gráficos com tooltips customizados

### 6. 📝 Criar uma Wiki ou GitHub Pages
- Publicar os gráficos em um site navegável
- Documentar cada tipo de gráfico com seu JSON correspondente


