**Interconexão, Memória e Entrada/Saída( 08/05 )**

## 🔰 1. Estrutura Básica de um Computador

Para entender a interconexão de memórias e dispositivos, partimos da **estrutura básica** do computador:

- **Unidade de Processamento (CPU)**
- **Memória (RAM, ROM, Cache)**
- **Dispositivos de Entrada/Saída (E/S)**
- **Barramentos**: canal físico para comunicação entre os componentes.

---

## 🧠 2. Interconexão de Memórias

### 2.1 Seleção de Chips com MSB

Quando se utiliza **mais de um chip de memória**, é preciso definir **qual deles responde** a determinado intervalo de endereços. Isso é feito com:

- **MSB (Most Significant Bits)** do endereço, que vão para um decodificador.
- A saída do decodificador ativa o sinal **CS (Chip Select)** do chip correspondente.
- **OE (Output Enable)** e **WE (Write Enable)** controlam leitura e escrita.

📌 *Exemplo:* Dois chips de 32 KB podem ser endereçados como um bloco contínuo de 64 KB usando 1 bit extra de seleção (2⁶ = 64).

---

### 2.2 Expansão da Largura de Palavra

Para formar **palavras maiores** (ex: 16 bits em vez de 8), combina-se chips **em paralelo**:

- Ex: Dois chips de 8 bits → um para os 8 bits mais baixos, outro para os mais altos.
- Compartilham os mesmos sinais de controle e endereçamento.

---

### 2.3 Expansão da Capacidade Total

A **placa-mãe** suporta **múltimos slots ou bancos de memória** para aumentar a capacidade:

- Ex: 4 slots de DDR4 → até 64 GB.
- A CPU ou o controlador de memória gerencia a leitura de cada módulo.

---

## 🏁 3. Representação de Dados em Memória

### 3.1 Big Endian vs Little Endian

As arquiteturas diferem na forma como armazenam os **bytes** de uma palavra multibyte:

| Ordem | Exemplo (0x12345678) | Arquit. comum |
| --- | --- | --- |
| Big Endian | `12 34 56 78` | SPARC, PowerPC |
| Little Endian | `78 56 34 12` | Intel x86, ARM (default) |

Esses detalhes importam para **interpretação correta de dados binários**, comunicação e sistemas embarcados.

---

## 🔌 4. Entrada e Saída (E/S)

Os dispositivos E/S não se conectam diretamente à CPU. Eles usam **barramentos** e mecanismos de controle.

---

### 4.1 Barramentos

Barramentos são caminhos compartilhados entre componentes. Tipos:

- **Dados**: leva dados.
- **Endereço**: especifica a localização da memória ou dispositivo.
- **Controle**: envia sinais de leitura, escrita, interrupção, etc.

### 4.1.1 Internos vs Externos

| Tipo | Exemplos | Onde atuam |
| --- | --- | --- |
| Internos | Barramento entre ALU e registradores | Dentro da CPU |
| Externos | PCIe, USB, SATA | CPU ↔ periféricos |

---

### 4.2 Estrutura PCI e PCI Express

- **PCI** (antigo): barramento paralelo, largura de banda limitada.
- **PCIe** (moderno): barramento serial ponto a ponto, alta velocidade, lanes escaláveis.

📌 Exemplo: GPUs modernas usam PCIe x16 para transferências massivas de dados.

---

### 4.3 Componentes de Comunicação

### a) **Pontes (Bridges)**

Antigamente, a comunicação era dividida em:

- **Northbridge**: memória e GPU.
- **Southbridge**: E/S, USB, disco.

Hoje, muitas funções dessas pontes estão **integradas ao processador ou chipset**.

### b) **Interrupções**

Permitem que o dispositivo **chame a atenção da CPU** sem polling (espera ativa):

- CPU pausa o que estava fazendo.
- Executa a **rotina de tratamento de interrupção (ISR)**.
- Retorna à tarefa anterior.

### c) **Arbitragem**

Quando múltiplos dispositivos querem usar o barramento, um mecanismo de **arbitragem** decide a ordem.

- Pode ser por prioridade (hierarquia) ou round-robin (rodízio).

### d) **Estados do barramento**

O barramento pode estar em diferentes estados:

- **Idle** – ocioso
- **Read** – leitura ativa
- **Write** – escrita ativa
- **Acknowledge** – reconhecimento

---

## 📈 5. Evolução dos Barramentos

Com o tempo, os barramentos evoluíram em **velocidade**, **eficiência energética** e **modo de operação**:

| Barramento | Tipo | Velocidade |
| --- | --- | --- |
| ISA | Paralelo | ~8 MB/s |
| PCI | Paralelo | ~133 MB/s |
| PCIe 4.0 | Serial | ~32 GB/s |
| USB 1.1 | Serial | 12 Mbps |
| USB 3.2 | Serial | até 20 Gbps |

---
