# Projeto CR32.MIPS

## Equipe:
- **Camila Vanessa**
- **Antônio Rafael**

Este projeto consiste em dois circuitos de 32 bits cada, baseados na arquitetura MIPS. Os circuitos foram carinhosamente apelidados de "Bicicleta" e "Moto", representando modelos monociclo e pipeline, respectivamente.

## Conceitos Rápidos:

- **Processador Monociclo:** 
    > Um processador monociclo é uma arquitetura de processador na qual cada instrução é executada em um único ciclo de clock. Isso significa que o processador passa por uma série de etapas fixas para executar uma instrução, e cada etapa ocorre em um ciclo de clock. As etapas típicas incluem busca de instrução, decodificação, execução e escrita de resultados. Embora seja simples de implementar e entender, o modelo monociclo pode ser menos eficiente em termos de utilização de recursos, pois o processador deve esperar o término de uma instrução antes de iniciar a próxima.

- **Processador Pipeline:** 
    > Um processador pipeline é uma arquitetura de processador que divide a execução de instruções em uma série de estágios sequenciais independentes. Cada estágio executa uma parte diferente do processamento da instrução, permitindo que várias instruções sejam executadas simultaneamente. Isso resulta em uma utilização mais eficiente dos recursos do processador e, geralmente, em um desempenho melhor em comparação com um processador monociclo. No entanto, o pipeline também introduz desafios, como a possibilidade de conflitos de dados ou dependências entre instruções, que precisam ser gerenciados adequadamente para garantir o correto funcionamento do processador.

## Funcionamento dos Circuitos:

### Bicicleta (Modelo Monociclo):
    [Inserir explicação do funcionamento do modelo monociclo]

### Moto (Modelo Pipeline):
    [Inserir explicação do funcionamento do modelo pipeline]

## Configuração e Uso:
As instruções devem ser configuradas em hexadecimal de acordo com o seguinte formato:

- <font color="#00ffcc">0XYZ0000</font>: **ADD** (Soma os valores dos registradores Y e Z e grava no registrador X)
- <font color="#00ff00">1XYZ0000</font>: **SUB** (Subtrai os valores dos registradores Y e Z e grava no registrador X)
- <font color="#0000ff">2XYZ0000</font>: **MULL** (Multiplica os valores dos registradores Y e Z e grava no registrador X)
- <font color="#ff9900">3X0Y00SS</font>: **ADDI** (Soma o valor do registrador Y com um imediato S (0 a 31) e grava no registrador X)
- <font color="#9900ff">5000AAAA</font>: **JUMP** (Salta para a instrução especificada no endereço A)
- <font color="#ff00ff">60YZAAAA</font>: **BGE** (Compara se o valor de Y é maior ou igual a Z e, se sim, salta para o endereço A)
- <font color="#00ffff">7X0000SS</font>: **LI** (Carrega o valor do imediato S no registrador X)
- <font color="#ffcc00">80YZ0000</font>: **SW** (Salva na memória o valor do registrador Y no endereço de memória do registrador Z)
- <font color="#ff0000">9XYZ0000</font>: **LW** (Carrega da memória o valor no endereço Y+Z e salva no registrador X)

- <font color="gray">7F000000</font>: **Bolha** (O registrador F é usado como $zero e sempre contém o valor 0)

### Detalhes dos Parâmetros:
- `X`: Registrador de destino
- `Y`: Registrador base para operações
- `Z`: Registrador base para operações
- `SS`: Valor do imediato (0 a 31 em hexadecimal)
- `A`: Endereço da instrução

Certifique-se de seguir corretamente as configurações para garantir o funcionamento adequado do processador.

