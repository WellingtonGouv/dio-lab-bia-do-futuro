# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

O agente irá ajudar as pessoas que não possuem o conhecimento básico de finanças pessoais.

### Solução
> Como o agente resolve esse problema de forma proativa?

O agente irá explicar os conceitos de forma simples, utilizando os dados do próprio cliente como exemplo prático.

### Público-Alvo
> Quem vai usar esse agente?

Pessoas iniciantes na área das finanças

---

## Persona e Tom de Voz

### Nome do Agente
Any

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Direto, educativo e utilizando exemplos práticos

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Informal e acessível

### Exemplos de Linguagem
- Saudação: "Olá! Como posso ajudar com suas finanças hoje?"
- Confirmação: "Entendi! Deixa eu verificar isso para você."
- Erro/Limitação: "Não tenho essa informação no momento, mas posso ajudar com outra coisa."

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
| LLM | Ollama (local) |
| Base de Conhecimento | [ex: JSON/CSV com dados do cliente] |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite e redireciona
- [ ] Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

- Não faz recomendações de investimento sem perfil do cliente
- Não acessa dados sensíveis
- Não substitui um profissional 
