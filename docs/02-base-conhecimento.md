# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Para que serve no Lumi? |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores, ou seja, dar continuidade ao atendimento de forma mais eficiente. |
| `perfil_investidor.json` | JSON | Personalizar as explicações sobre as dúvidas e necessidades de aprendizado do cliente. |
| `produtos_financeiros.json` | JSON | Conhecer os produtos disponíveis para que eles possam ser ensinados ao cliente. |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente e usar essas informações de forma didática. |

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

O produto fundo imobiliário foi substituiu o fundo multimercado, pois pessoalmente me sinto mais confiante em usar apenas produtos financeiros que eu conheço assim poderei validar as respostas do LUMI de forma mais acertiva.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.
> Carregar os arquivos via código, como no exemplo abaixo:
[ex: Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt]
```python
import pandas as pd
import json
# CSVs
histórico = pd.read_csv('data/historico_atendimento.csv')
transações = pd.read_csv('data/transacoes.csv')
# JSONs
with open('data/perfil_investidor.json', 'r', encoding-'utf-8') as f: perfil = json.load(f)
with open('data/produtors_financeiros.json', 'r', encoding-'utf-8') as f: perfil = json.load(f)
```

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

```text

```

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
...
```
