# Gestão Financeira Pessoal

Sistema web de controle financeiro pessoal, criado a partir da planilha "GESTÃO FINANCEIRA 2026 - PESSOAL".
É uma única página (`index.html`), sem servidor nem build: basta abrir no navegador.

## Funcionalidades

- **Painel** – saldo atual, receitas e despesas do mês, contas fixas pagas/pendentes e gráficos.
- **Lançamentos** – cadastro de receitas e despesas com grupo de conta, subcategoria, descrição e repetição mensal; filtros e saldo acumulado.
- **Contas a pagar** – grade anual (jan–dez) de financiamentos, cartões e contas fixas; marcar como pago com um clique; total de dívidas, pago, pendente e em atraso.
- **Relatórios** – despesas por grupo/subcategoria, receitas por grupo, evolução de gastos, contas fixas por mês e painel anual.
- **Diário** – receitas, despesas e saldo dia a dia.
- **Categorias** – grupos de conta e subcategorias editáveis.
- **Importar extrato** – lê extratos OFX, CSV e Excel; PDF e imagens são lidos com o Claude quando a página roda como artefato no claude.ai. Sugere categorias, detecta duplicados e memoriza as escolhas.
- **Configurações** – saldo inicial, importação da planilha original (.xlsx), backup JSON e exportação CSV.

## Armazenamento

- Publicado como artefato no claude.ai, os dados ficam salvos na conta do dono (privados).
- Aberto em qualquer outro lugar, os dados ficam no `localStorage` do navegador. Use **Configurações → Exportar backup** para guardar uma cópia.

## Ferramentas

`ferramentas/converter_planilha.py` converte a planilha original em JSON de backup:

```bash
pip install openpyxl
python ferramentas/converter_planilha.py planilha.xlsx backup.json
```

O JSON gerado pode ser carregado em **Configurações → Restaurar backup**.

## Dependências (CDN)

Chart.js 4.4.1, SheetJS 0.18.5 e pdf.js 3.11.174, carregados de cdnjs.cloudflare.com; fonte Inter do Google Fonts.
