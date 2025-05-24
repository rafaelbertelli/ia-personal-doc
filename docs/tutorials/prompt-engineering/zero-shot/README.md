# Zero-Shot

Zero-Shot Prompting é uma técnica de prompt que não requer exemplos de entrada e saída para treinar o modelo.

## Quando utilizar

- Quando a resposta é simples e conhecida pelo modelo (ex: perguntas factuais, traduções, etc)
- Quando o modelo não precisa de contexto prévio e/ou o modelo precisa responder rapidamente
- Quando se deseja testar a capacidade do modelo de interpretar a tarefa
- Quando não há exemplos de entrada e saída disponíveis

## Vantagens

- Baixo custo de preparação do prompt
- Alta escalabilidade
- Rápido para experimentação

## Limitações

- Pode falhar em tarefas mais complexas ou menos frequentes para o modelo.
- Não oferece controle sobre o formato da resposta.
- Dependente da compreensão implícita do modelo sobre a tarefa.
- Alucinação de respostas: o modelo pode gerar conteúdo incorreto com alta confiança.
- Variação com pequenas mudanças na formatação: prompts semanticamente equivalentes podem gerar resultados diferentes.
- Dificuldade em tarefas de raciocínio lógico, análises comparativas ou inferência fora do contexto factual.

## Estratégias de mitigação

Mesmo mantendo a proposta de não fornecer exemplos, algumas práticas ajudam a melhorar os resultados com Zero-Shot Prompting:

### Especificidade

Instruções claras que detalham o que se espera aumentam a precisão.

- **Exemplo ruim:** "Analise esse código"
- **Melhorado:** "Explique o que esse código Go faz e liste possíveis problemas de performance."

### Linguagem declarativa e orientada à Tarefa

Preferência por comandos diretos à perguntas abertas.

- **Exemplo ruim:** "Quais seriam os motivos para erros de memória em Go?"
- **Melhorado:** "Liste os principais motivos para erros de memória em da linguagem Go."

[Diferença de respostas](/tutorials/prompt-engineering/zero-shot/ex-declarative-language.md)

### Sinalização do formato esperado

- **Exemplo:** "Responda em forma de lista"

## Boas práticas

Mesmo sem exemplos, prompts estruturados com clareza (persona, formato, objetivo) ajudam o modelo a responder melhor.
Instruções mais detalhadas melhoram a performance do Zero-Shot.

- Especifique o papel do modelo ("Você é um especialista em...")
- Especifique a saída esperada ("Responda em JSON", "Responda em tópicos")
- Garanta que o modelo compreenda a meta ("Seu objetivo é...")

- **Exemplo ruim:** "Explique o que é uma goroutine"
- **Melhorado:** "Você é um especialista em Go. Escreva 2 parágrafos explicando o que é uma goroutine, como ela é usada e quais são suas limitações. Seja claro, técnico e direto.
