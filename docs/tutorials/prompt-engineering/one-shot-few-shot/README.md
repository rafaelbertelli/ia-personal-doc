# One-Shot / Few-Shot

Few-Shot Prompting é uma técnica onde fornecemos **um pequeno número de exemplos** (normalmente entre **1 e 5**) para que o modelo entenda o padrão de entrada e saída antes de gerar uma nova resposta. O modelo "aprende" apenas com base nesses exemplos, dentro do próprio prompt, sem qualquer re-treinamento.

## Quando utilizar

- A tarefa **tem múltiplas formas de execução válidas**, e você deseja orientar o estilo da resposta.
- O modelo **comete erros ou se comporta de forma inconsistente** em Zero-Shot.
- A tarefa é **relativamente complexa ou específica** e pode se beneficiar de demonstrações diretas.
- É necessário **replicar padrões linguísticos, técnicos ou formais** específicos.

## Vantagens

- **Precisão aumentada:** exemplos ajudam o modelo a compreender nuances da tarefa.
- **Consistência de estilo:** útil para gerar código/documentação com padronização.
- **Pouco custo de engenharia:** mais simples do que treinar modelos.

## Limitações

- **Custo em tokens:** exemplos ocupam espaço no prompt, reduzindo espaço para contexto.
- **Dependência da qualidade dos exemplos:** exemplos ambíguos ou mal formulados comprometem a resposta.
- **Fragilidade à ordem:** mudar a ordem dos exemplos pode afetar o desempenho.

## Estrutura e exemplos

**Exemplo 1:**

- Entrada: `<texto de entrada>`
- Saída: `<resposta esperada>`

**Exemplo 2:**

- Entrada: `<texto de entrada>`
- Saída: `<resposta esperada>`

**Prompt:**

```bash
"Gere testes unitários para a função fornecida"

Exemplo:

  Função:
  func Soma(a, b int) int { return a + b }

  Teste:
  func TestSoma(t *testing.T) { r := Soma(2, 3) if r != 5 { t.Errorf("esperado 5, obteve %d", r) } }

  Função:
  func Multiplica(a, b int) int { return a * b }

  Teste:
  ... Resultado esperado de acordo com o exemplo ...
```

## Comparativo

| Tipo de Prompt | Exemplos | Precisão | Controle de Saída | Custo |
| -------------- | -------- | -------- | ----------------- | ----- |
| Zero-Shot      | Nenhum   | Média    | Baixo             | Baixo |
| One-Shot       | 1        | Média+   | Médio             | Médio |
| Few-Shot       | 2-5      | Alta     | Alto              | Alto  |
