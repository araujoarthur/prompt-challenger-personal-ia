# O que é PromptDML

PromptDML é uma linguagem de marcação usada para estruturar prompts, similar ao XML e HTML, que define o comportamento de interações baseadas em variáveis, regras e contexto.

# Principais Tags do PromptDML

- <prompt>: Delimita o início e fim do prompt.
- <system>: Define como a interação deve se comportar.
- <context>: Define o cenário ou situação a ser considerado na resposta.
- <variables>: Contém uma lista de variáveis a serem usadas no prompt.
   - <variable name="x" description="y">: Define o nome e a descrição de uma variável.
- <rules>: Lista regras a serem seguidas na elaboração da resposta.
   - <rule name="x">: Define uma regra com base no nome.
- <constraints>: Define fatores limitantes na resposta. Caso o modelo suporte, podem ser usadas as seguintes tags:
   - <temperature>, <top-p>, <terminating-sequence>, <max-tokens>.
   - Caso não suportadas, devem ser ignoradas sem afetar outros constraints.
- <instructions>: Contém as instruções claras sobre como utilizar contexto, variáveis, regras e constraints.

# Regras Adicionais

Tags genéricas podem ser usadas para estruturar listas e outras informações e devem ser inferidas durante a interpretação do prompt.
O atributo relation pode ser usado para associar uma tag a uma variável, vinculando-a com o valor do nome da variável.