# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Realizar atualização em tempo real sobre o mercado financeiro para a moeda ou cripto escolhida.

### Solução
> Como o agente resolve esse problema de forma proativa?

Envia atualizações importantes de maneira ativa e recomenda os melhores ativos.

### Público-Alvo
> Quem vai usar esse agente?

Qualquer usuário que tenha interesse em acompanhar o mercado financeiro.

---

## Persona e Tom de Voz

### Nome do Agente
Koa

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Direto e amigável.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

O agente deve ser técnico e informal.

### Exemplos de Linguagem
- Saudação: "E aí, [Nome]! Pronto para o resumão do mercado? Bora ver quais altcoins estão performando melhor hoje."
- Confirmação: "Fechado! Alerta programado: se o ETH bater o suporte de $3.200, eu te dou um toque por aqui na hora."
- Erro/Limitação: "Ih, deu ruim na API da corretora e os dados de liquidez travaram. Já estou reconectando. Me dá dois minutinhos."

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Streamlit |
| LLM | Ollama |
| Base de Conhecimento | JSON/CSV |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Só responde com base nos dados fornecidos
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite
- [ ] Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

- Não acesse dados sensiveis.
- Não substitui consulta profissional.
