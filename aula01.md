# Aula (03/04) – Evolução dos Computadores e Arquiteturas de Processadores 

## Década de 1940 - Primeiros Computadores Digitais

Os primeiros computadores digitais dessa época, como o ENIAC, tinham apenas dois níveis de abstração principais:

- **ISA (Instruction Set Architecture)** – Conjunto de instruções que o processador pode executar.
- **Nível Lógico Digital** – Circuitos eletrônicos que implementam essas instruções diretamente.

Esses computadores eram baseados em válvulas eletrônicas e tinham um desempenho muito limitado. O processamento era feito por meio de lógica combinacional e sequencial.

---

## Década de 1970 - Introdução da Microprogramação

A ideia de interpretar o nível ISA por um microprograma, em vez de executar diretamente por hardware, surgiu nessa época. O microprograma atua como uma camada intermediária entre o software e o hardware, permitindo que um conjunto de microinstruções implemente uma única instrução de alto nível.

**Vantagens da microprogramação:**
- ✔️ Facilidade para adicionar novas instruções.
- ✔️ Menor complexidade no design do hardware.
- ✔️ Maior flexibilidade na evolução da arquitetura.

**Exemplo:** Processadores da família IBM System/360 utilizavam microprogramação para oferecer compatibilidade entre diferentes modelos.

Entretanto, alguns pesquisadores perceberam que, ao eliminar o microprograma, as máquinas poderiam ficar mais rápidas, levando ao desenvolvimento das arquiteturas **RISC (Reduced Instruction Set Computing)**, que executavam instruções diretamente em hardware sem microcódigo.

---

## Pontos Comuns entre Operações Aritméticas

As operações seguem os mesmos passos básicos, com pequenas variações:

### Adição (A + B)
1. Buscar os operandos na memória.
2. Executar a soma.
3. Armazenar o resultado.

### Subtração (A - B)
- Mesmos passos da adição, mas a **ULA (Unidade Lógica e Aritmética)** realiza a operação de subtração.

### Multiplicação e Divisão
- Adicionadas posteriormente para otimizar cálculos mais complexos.
- Antes disso, eram feitas por sucessivas adições ou subtrações.

---

## Arquitetura x86 e a Evolução dos Processadores Intel

A arquitetura **x86** surgiu com o processador **Intel 8086** (lançado em 1978). Alguns dos principais membros da família x86 incluem:

| Processador      | Ano  | Bits | Características                               |
|------------------|------|------|-----------------------------------------------|
| Intel 4004       | 1971 | 4    | Primeiro microprocessador comercial           |
| Intel 8086       | 1978 | 16   | Primeiro processador x86                      |
| Intel 80286      | 1982 | 16   | Introduziu modo protegido                     |
| Intel 80386      | 1985 | 32   | Primeiro x86 de 32 bits                       |
| Pentium          | 1993 | 32   | Introduziu pipeline superescalar              |
| Core i7-3960X    | 2011 | 64   | 6 núcleos e suporte a hyper-threading         |

---

### Intel 4004 - O Primeiro Microprocessador

- Lançado em 1971
- 4 bits, 2.300 transistores
- Usado inicialmente em calculadoras
- Marco na história da computação

---

## Arquitetura ARM

Surgiu nos anos 1980 com a empresa **Acorn Computers**, buscando alternativa ao IBM PC. Destacou-se por sua **eficiência energética**, sendo amplamente adotada em **dispositivos móveis**.

### Apple e ARM

A Apple fez contato com a ARM nos anos 1990 para utilizar a arquitetura no **Apple Newton** (um dos primeiros PDAs). Essa parceria ajudou a popularizar o ARM.

### System-on-Chip (SoC)

A ARM se consolidou no desenvolvimento de **SoCs (System-on-Chip)**, que integram CPU, GPU, memória e controladores em um único chip, reduzindo consumo de energia e espaço físico.

### Por que a ARM domina o mercado?

- **Licenciamento de arquitetura**: ARM licencia sua arquitetura para empresas como Qualcomm, Apple e Samsung.
- **Diversidade de implementações**: Várias empresas criam suas próprias versões de processadores ARM, promovendo inovação.

---

## Cache e Máscaras na Produção de Processadores

### Por que o cache ocupa muito espaço?

- Cache usa **memórias SRAM**, que são muito rápidas, mas ocupam mais espaço que memórias DRAM.
- Isso limita o tamanho do cache nos processadores modernos.

### Máscaras na fabricação de chips

- **Máscaras** são usadas no processo de **litografia** para imprimir circuitos nos chips.
- A complexidade das máscaras afeta o **custo de fabricação**.

### Por que os preços dos processadores caem com novas demandas?

- **Economia de escala**: Produção em massa reduz custo por unidade.
- **Avanços tecnológicos**: Chips mais novos tornam os antigos mais baratos.
- **Concorrência**: Disputa entre Intel, AMD e fabricantes ARM reduz preços.

---

## Eletrônica Digital e Microcontroladores

### Computadores Digitais

- Processam informações usando **0 e 1**, representados por sinais elétricos (tensão ou corrente).

### Funcionamento do Transistor

- Atua como um **interruptor eletrônico**, permitindo ou bloqueando a corrente.
- É o **bloco fundamental** dos circuitos digitais.

### Microcontrolador vs Processador

- **Processador (CPU)**: Executa instruções de software, depende de RAM e outros componentes externos.
- **Microcontrolador**: Integra CPU, memória e periféricos em um único chip (ex: ATmega328P – usado no Arduino).

### Sincronismo em Sistemas Digitais

- Feito por **relógios digitais (clock)**, garantindo ordem nas operações.
- O sinal de clock mantém a **sincronia entre os componentes** do sistema.
