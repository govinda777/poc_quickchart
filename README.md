# poc_quickchart

# 📊 Tutorial QuickChart.io

[QuickChart.io](https://quickchart.io/) é uma API poderosa que permite gerar gráficos dinâmicos usando apenas uma URL. Com ela, você pode criar gráficos de barras, linhas, pizza e muito mais, integrando-os facilmente em dashboards, relatórios, bots ou READMEs de projetos no GitHub.

---

## 🚀 Como Funciona

A ideia central é construir uma URL que contenha uma configuração baseada no [Chart.js](https://www.chartjs.org/docs/latest/), definida em **JSON**. QuickChart interpreta essa configuração, gera o gráfico e retorna uma **imagem PNG**.

**Formato da URL:**

```
https://quickchart.io/chart?c=<configuração-em-JSON-codificada>
```

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

**URL Codificada:**

```
https://quickchart.io/chart?c=%7B%22type%22%3A%22bar%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Janeiro%22%2C%22Fevereiro%22%2C%22Mar%C3%A7o%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Vendas%22%2C%22data%22%3A%5B10%2C20%2C30%5D%7D%5D%7D%7D
```

**Markdown para Exibição:**

```markdown
![Gráfico de Barras](https://quickchart.io/chart?c=%7B%22type%22%3A%22bar%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Janeiro%22%2C%22Fevereiro%22%2C%22Mar%C3%A7o%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Vendas%22%2C%22data%22%3A%5B10%2C20%2C30%5D%7D%5D%7D%7D)
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

**URL Codificada:**

```
https://quickchart.io/chart?c=%7B%22type%22%3A%22line%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Segunda%22%2C%22Ter%C3%A7a%22%2C%22Quarta%22%2C%22Quinta%22%2C%22Sexta%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Temperatura%22%2C%22data%22%3A%5B22%2C21%2C23%2C24%2C22%5D%7D%5D%7D%7D
```

**Markdown para Exibição:**

```markdown
![Gráfico de Linhas](https://quickchart.io/chart?c=%7B%22type%22%3A%22line%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Segunda%22%2C%22Ter%C3%A7a%22%2C%22Quarta%22%2C%22Quinta%22%2C%22Sexta%22%5D%2C%22datasets%22%3A%5B%7B%22label%22%3A%22Temperatura%22%2C%22data%22%3A%5B22%2C21%2C23%2C24%2C22%5D%7D%5D%7D%7D)
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

**URL Codificada:**

```
https://quickchart.io/chart?c=%7B%22type%22%3A%22pie%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Azul%22%2C%22Vermelho%22%2C%22Amarelo%22%5D%2C%22datasets%22%3A%5B%7B%22data%22%3A%5B300%2C50%2C100%5D%7D%5D%7D%7D
```

**Markdown para Exibição:**

```markdown
![Gráfico de Pizza](https://quickchart.io/chart?c=%7B%22type%22%3A%22pie%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Azul%22%2C%22Vermelho%22%2C%22Amarelo%22%5D%2C%22datasets%22%3A%5B%7B%22data%22%3A%5B300%2C50%2C100%5D%7D%5D%7D%7D)
```

**Resultado:**

![Gráfico de Pizza](https://quickchart.io/chart?c=%7B%22type%22%3A%22pie%22%2C%22data%22%3A%7B%22labels%22%3A%5B%22Azul%22%2C%22Vermelho%22%2C%22Amarelo%22%5D%2C%22datasets%22%3A%5B%7B%22data%22%3A%5B300%2C50%2C100%5D%7D%5D%7D%7D)

---

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
