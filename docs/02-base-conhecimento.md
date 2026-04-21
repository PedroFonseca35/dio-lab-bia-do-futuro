# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Para que serve no Lumi? |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores, ou seja, dar continuidade ao atendimento de forma mais eficiente. |
| `perfil_investidor.json` | JSON | Personalizar as explicações sobre as dúvidas e necessidades de aprendizado do cliente. |
| `produtos_financeiros.json` | JSON | Conhecer os produtos disponíveis para que eles possam ser ensinados ao cliente. |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente e usar essas informações de forma didática. |

## Adaptações nos Dados

Foi ampliada a base com novos exemplos de transações financeiras e dúvidas comuns de iniciantes.
Foram adicionados mais produtos financeiros e melhorias na estrutura dos dados para personalização das respostas afim de englobar mais casos.

---

## Estratégia de Integração

### Como os dados são carregados?

```python
import pandas as pd
import json
perfil = json.load(open('./data/perfil_investidor.json'))
produtos = json.load(open('./data/produtos_financeiros.json'))
transacoes = pd.read_csv('./data/transacoes.csv')
historico = pd.read_csv('./data/historico_atendimento.csv')
```

### Como os dados são usados no prompt?

[`data/historico_atendimento`](../data/historico_atendimento.csv)
[`data/perfil_investidor`](../data/perfil_investidor.json)
[`data/produtos_financeiros`](../data/produtos_financeiros.json)
[`data/transacoes`](../data/transacoes.csv)

---

## Exemplo de Contexto Montado

```
{
  "usuario": {
    "idade": null,
    "profissao": null,
    "renda_mensal": null,
    "perfil_investidor": null,
    "objetivo_principal": null,
    "patrimonio_total": null,
    "reserva_emergencia_atual": null,
    "aceita_risco": null,
    "metas": [
      {
        "descricao": null,
        "valor": null,
        "prazo": null
      }
    ]
  }
}
```
