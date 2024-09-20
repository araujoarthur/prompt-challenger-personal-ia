Esse chat será executado em PromptDML.

# O que é PromptDML
PromptDML é uma linguagem de marcação para Prompts semelhante a XML e HTML.

# Principais tags do PromptDML

- A totalidade do prompt é definida entre as tags "<prompt>" e "</prompt>".
- O System Prompt, aquele que define como a interação deve se comportar, é difinido no interior das tags "<system>" e "</system>".
- O contexto do prompt, que deverá ser considerado como situação referente a qual a resposta deve ser elaborada, é definido dentro das tags "<context>" e "</context>" 
- Um Prompt escrito em PromptML pode ter variáveis que são declaradas em lista dentro do corpo da tag "<variables>" e "</variables>". Cada variável é declarada dentro do corpo de uma tag "<variable>" que possui um atributo chamado "name", que é o nome da variável. A tag de variável também pode conter um atributo "description" que auxiliará na identificação da finalidade da informação daquela variável.
- Uma variável pode ser utilizada no exemplo de resposta e será representada pelo placeholder "{{Nome da Variável}}"
- O prompt também pode possuir regras que estão específicadas dentro do corpo da tag "<rules>" "</rules>". Essas regras devem ser levadas em consideração durante a elaboração da saída. Cada regra é definida no interior do corpo de uma tag "<rule>" que possui um atributo "name", que é o nome da regra.
- O prompt pode possuir uma tag "<constraints>", onde são inseridos fatores limitantes da resposta. Se o modelo suportar, podem ser inseridas nessa seção, além dos constraints do usuário, as tags <temperature>, <top-p>, <terminating-sequence> e <max-tokens> que definem respectivamente a temperatura da resposta, o top-p, a sequência de finalização da saída e a quantidade máxima de tokens da saida. O modelo deve informar se suporta as tags de temperatura, top-p, temrinating-sequence e max-tokens. Caso não suporte, deverá ignorar somente estas tags e considerar os constraints do usuário em relação ao conteúdo. 
- O prompt deve possuir a tag "<instructions>". No corpo dessa tag são encontradas as instruções de forma clara e direta de como utilizar  o conteudo das tags de contexto, variáveis, regras e constraints. 

# Regras adicionais do PromptDML

- O prompt também pode possuir tags genéricas para estruturar listas e outras informações. Estas tags devem ser inferidas durante a interpretação do prompt. O usuário pode opcionalmente fornecer um atributo chamado "metatag" que descreverá a intenção daquela tag.
- As vezes, uma tag pode estar relacionada a uma variável. Isso é definido pelo atributo "relation", que terá o valor do "name" da variável relacionada.
