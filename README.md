# ${\ {\color{cyan}C}}\{\color{red}R}\ 32.MIPS$

## Equipe:
- $\color{cyan}{Camila\ Vanessa\ de\ Matos\ Sousa}$
- $\color{red}{Antônio\ Rafael\ Oliveira\ da\ Cunha}$

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

- $\color{blue}{0XYZ0000}$: **ADD** (Soma os valores dos registradores Y e Z e grava no registrador X)
- $\color{green}{1XYZ0000}$: **SUB** (Subtrai os valores dos registradores Y e Z e grava no registrador X)
- $\color{orange}{2XYZ0000}$: **MULL** (Multiplica os valores dos registradores Y e Z e grava no registrador X)
- $\color{purple}{3X0Y00SS}$: **ADDI** (Soma o valor do registrador Y com um imediato S (0 a 31) e grava no registrador X)
- $\color{teal}{5000AAAA}$: **JUMP** (Salta para a instrução especificada no endereço A)
- $\color{magenta}{60YZ00AA}$: **BGE** (Compara se o valor de Y é maior ou igual a Z e, se sim, salta para o endereço A)
- $\color{red}{7X0000SS}$: **LI** (Carrega o valor do imediato S no registrador X)
- $\color{brown}{80YZ0000}$: **SW** (Salva na memória o valor do registrador Y no endereço de memória do registrador Z)
- $\color{lime}{9XYZ0000}$: **LW** (Carrega da memória o valor no endereço Y+Z e salva no registrador X)

- $\color{gray}{7F000000}$: **Bolha** (O registrador F é usado como $zero$ e sempre contém o valor 0)

### Detalhes dos Parâmetros:
- $X$: $\color{Thistle}{Registrador\ de\ destino}$
- $Y$: $\color{Plum}{Registrador\ base\ para\ operações}$
- $Z$: $\color{Periwinkle}{Registrador\ base\ para\ operações}$
- $SS$: $\color{SeaGreen}{Valor\ do\ imediato\ (0\ a\ 31)}$
- $A$: $\color{SkyBlue}{Endereço\ da\ instrução}$

Certifique-se de seguir corretamente as configurações para garantir o funcionamento adequado do processador.

## Erro no Pipeline
Todas as funções e instruções foram testadas e estão funcionando corretamente e as informações estão chegando corretamente no tempo de clock previsto, mas foi detectado um erro quando aplicado para realizar o cálculo de duas matrizes 2x2 em que existem 3 loops e o somatório (addi) para o correto funcionamento de um deles não estava acontecendo. Era realizado o cálculo correto daquela posição na matriz resultante da mas devido a este erro no somatório não era possível calcular as outras posições da matriz. 

Dentro do circuito acompanhamos como essa instrução estava se comportando dentro do processador e no momento em que os dados estão entrando no banco de registradores o bit relativo ao salvamento de dados no registrador estão em 0, chegando atrasado em relação à esses dados, possivelmente afetado pelas instruções anteriores que não há salvamento de dados no banco de registradores.  
