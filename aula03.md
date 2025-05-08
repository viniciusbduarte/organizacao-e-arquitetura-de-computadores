# **Aula 4 – Memórias em Sistemas Digitais ( 24/04 )**

---

## **Dado vs Informação**

### 📌 Dado:

É qualquer valor bruto armazenado ou transmitido.

**Exemplo:** `10010110`, `28`, `A`.

### 📌 Informação:

É quando esse dado é interpretado dentro de um contexto.

**Exemplo:** `28` pode significar idade, temperatura, ou posição em uma lista.

`10010110` pode ser interpretado como um caractere, uma cor, ou um comando.

> Resumo: Dado + contexto = informação.
> 

---

## **Operações básicas da memória**

### 📥 Leitura:

- Processo de buscar um dado armazenado na memória.
- A CPU envia o endereço → a memória retorna o conteúdo desse endereço.

### 📤 Escrita:

- A CPU envia um endereço e um dado → a memória armazena esse dado naquele endereço.

> Memórias podem ser de leitura apenas, de leitura e escrita ou com restrições.
> 

---

## **Tipos de acesso à memória**

### 🔄 Acesso aleatório (Random Access):

- Permite acessar **qualquer posição diretamente** e em **tempo constante**.
- Exemplos: **RAM, ROM, EEPROM, Flash**.
- Muito mais eficiente.

### 🔁 Acesso sequencial:

- O dado só pode ser lido na **ordem em que está armazenado**.
- Exemplo clássico: **fita magnética**.
- Usado em sistemas antigos ou de arquivamento massivo.

---

## **Barramento de endereço**

- É um **conjunto de fios ou trilhas** no sistema que transporta os endereços da CPU até a memória.
- A **largura** do barramento (quantos bits ele tem) define **quantas posições de memória** podem ser acessadas:
    - 8 bits → 2⁸ = 256 posições
    - 16 bits → 2¹⁶ = 65.536 posições
    - 32 bits → 2³² = 4.294.967.296 posições (~4 GB)

> A memória é sempre acessada por endereços binários.
> 

---

## **Tempo de acesso**

- Intervalo entre a solicitação de leitura e a entrega do dado.
- Medido em **nanossegundos (ns)** nas memórias principais e **milissegundos (ms)** nas memórias secundárias.

**Comparação:**

| Tipo de Memória | Tempo Médio |
| --- | --- |
| SRAM (cache) | ~1 ns |
| DRAM (RAM) | ~10–100 ns |
| Flash (SSD) | ~100 µs–1 ms |
| HDD (disco) | ~10 ms |

---

## **Bufferização**

- **Buffer** é uma **área temporária** de memória usada para equilibrar a diferença de velocidade entre dois dispositivos.
- Exemplo: ao assistir um vídeo online, ele **carrega em buffer** antes de tocar para evitar travamentos.
- Em sistemas digitais, buffers são comuns entre a CPU e periféricos.

---

## **Volatilidade**

| Tipo | Explicação |
| --- | --- |
| **Volátil** | Perde os dados ao desligar o sistema. Ex: RAM. |
| **Não-volátil** | Retém os dados mesmo sem energia. Ex: ROM, Flash. |

---

## **Capacidade de memória**

- Medida em **bytes**.
- Escala:
    - 1 KB = 1.024 bytes
    - 1 MB = 1.024 KB
    - 1 GB = 1.024 MB
    - 1 TB = 1.024 GB

> A escolha da capacidade depende da aplicação:
> 
> 
> Um microcontrolador pode ter apenas 4 KB de RAM, enquanto um servidor pode ter 128 GB.
> 

---

## **Tecnologia de fabricação**

As diferentes memórias têm arquiteturas e usos distintos:

### 🔹 **SRAM (RAM Estática)**

- Armazena cada bit usando **6 transistores**.
- Mais rápida, não precisa de refresh.
- Cara, ocupa mais espaço → usada em **cache L1/L2**.

### 🔹 **DRAM (RAM Dinâmica)**

- Armazena cada bit com **1 transistor + 1 capacitor**.
- Precisa de **refresh constante**, pois o capacitor perde carga.
- Mais barata e densa → usada como **memória principal**.

---

## **Tipos de memória (ROM e derivados)**

### 🔸 **ROM (Read-Only Memory)**

- Programada de fábrica, **não pode ser alterada**.
- Armazena dados fixos (firmware).

### 🔸 **PROM (Programmable ROM)**

- Pode ser **programada uma vez** pelo usuário.
- Usa fusíveis internos → obsoleta hoje.

### 🔸 **EPROM (Erasable PROM)**

- Pode ser apagada com **luz ultravioleta** e reprogramada.
- Tem uma "janelinha" de quartzo no chip.

### 🔸 **EEPROM (Electrically Erasable PROM)**

- Pode ser **apagada eletricamente**, **byte a byte**.
- Mais flexível, usada em microcontroladores (ex: ATmega328 do Arduino).

### 🔸 **Flash**

- Variante da EEPROM, mas apaga dados **em blocos** (não byte a byte).
- Mais rápida, barata, com maior densidade.
- Usada em **pendrives, SSDs, cartões SD**.

---

## **Estrutura interna das memórias**

- A maioria das memórias é organizada em **matrizes de bits**:
    - Linhas: **wordlines** (endereçamento)
    - Colunas: **bitlines** (leitura/escrita)

### Exemplo: Memória 4x4 (16 bits)

```
     B0  B1  B2  B3
W0 |  0   1   1   0
W1 |  1   0   0   1
W2 |  0   0   1   1
W3 |  1   1   0   0

```

- Quando ativamos uma **wordline**, os valores de seus bits são lidos ou escritos nas **bitlines**.
- Para leitura, usa-se **amplificadores de sentido (sense amplifiers)**.
- Para escrita, são usados **drivers de escrita**.

---

## **Resumo geral (tabela comparativa)**

| Tipo | Volátil | Regravável | Velocidade | Aplicação comum |
| --- | --- | --- | --- | --- |
| SRAM | Sim | Sim | Muito rápida | Cache |
| DRAM | Sim | Sim | Rápida | Memória principal |
| ROM | Não | Não | Média | Firmware fixo |
| PROM | Não | Não (1x) | Média | Substituída |
| EPROM | Não | Sim (UV) | Lenta | Histórico |
| EEPROM | Não | Sim (eletricamente) | Média | Configurações, microcontroladores |
| Flash | Não | Sim (blocos) | Rápida | SSDs, pendrives, celulares |

---
