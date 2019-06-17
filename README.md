**RadioDSP-DNR

**Descrição do conceito com função e motivação

Processamento digital de sinal (Digital Signal Processing - DSP) de áudio para receptor de rádio com recursos de redução de ruído digital (Digital Noise Reduction-DNR) baseados em subtração espectral.

O objetivo desse projeto foi utilizar a arquitetura de DSP do microprocessador ARM Cortex M4 presente na placa de desenvolvimento STM32F407. Devido às extensões DSP é possível processar FFT em tempo real (bin) de 256 elementos garantindo uma boa resposta nas funcionalidades de DNR, filtragem e visualização do áudio sinal. Quatro elementos filtrantes (FIR) foram implementados, com as seguintes características:

Filtro 0: passa-alta (> 12kHz)
Filtro 1: passa-baixa para AM (<6kHz)
Filtro 2: passa-baixa para SSB (<3kHz)
Filtro 3: passa-banda para CW (500 Hz)

Funções finais:

DNR com dois estágios (Filtros espectrais de subtração + adaptativos LMS)
Filtros BPF / LPF (12, 6, 3, 0,5 kHz)
Decodificador Morse CW

![Diagrama_Blocos_DNR](https://user-images.githubusercontent.com/37374766/59629492-581cc080-9119-11e9-888f-9a164f1cd51c.jpg)

**Diagrama de blocos da eletrônica;

**Diagrama/tabela de pinagem;

**Fluxograma do firmware;





