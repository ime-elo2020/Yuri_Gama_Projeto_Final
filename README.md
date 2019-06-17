**RadioDSP-DNR

**Descrição do conceito com função e motivação

Processamento digital de sinal (Digital Signal Processing - DSP) de áudio para receptor de rádio com recursos de redução de ruído digital (Digital Noise Reduction-DNR) baseados em subtração espectral.

O objetivo desse projeto foi utilizar a arquitetura de DSP do microprocessador ARM Cortex M4 presente na placa de desenvolvimento STM32F407. Devido às extensões DSP é possível processar FFT em tempo real (bin) de 256 elementos garantindo uma boa resposta nas funcionalidades de DNR, filtragem e visualização do áudio sinal. 

Para realizar a pré-filtragem do sinal ruidoso, quatro elementos filtrantes do tipo resposta ao impulso finita (FIR) foram implementados, com as seguintes características:
_Filtro 0: passa-alta (> 12kHz)
Filtro 1: passa-baixa para AM (<6kHz)
Filtro 2: passa-baixa para SSB (<3kHz)
Filtro 3: passa-banda para CW (500 Hz)_

Foi implementado também um _Filtro Adaptativo_ (Least Mean Square - LMS). Na filtragem convencional do tipo resposta ao impulso finita (FIR) ou do tipo resposta ao impulso infinita (IIR), geralmente assume-se que os parâmetros do processo estocástico de entrada são conhecidos, tais parâmetros determinam as características do sinal de entrada. No entanto, em nosso problema prático, alguns parâmetros de entrada podem mudar, ou ainda, o sistema pode não conhecer exatamente o comportamento destes parâmetros. Desse modo, é altamente desejável um filtro que possua o atributo de auto-aprendizado, de maneira que este possa ajustar-se automaticamente de acordo com  cada situação. O algoritmo clássico LMS (Least Mean Squares) utilizado constitui uma das técnicas mais conhecidas para a implementação de um filtro adaptativo. O LMS utiliza um algoritmo de gradiente estocástico para adaptar a carga de um filtro. Esta adaptação consiste no ajuste contínuo (e adaptativo) dos valores dos coeficientes do filtro, tendo como métrica a minimização do erro no sentido da média dos quadrados.

Além disso,  foi utilizada a funcionalidade da FFT, pois a partir do valor de módulo (magnitude) do sinal pode-se aplicar a técnica de subtração espectral de potência, antes da informação de fase ser novamente incorporada ao sinal.

Funções finais:

DNR com dois estágios (Filtros espectrais de subtração + filtro adaptativo (Least Mean Square - LMS)
Filtros BPF / LPF (12, 6, 3, 0,5 kHz)
Decodificador Morse CW

![Diagrama_Blocos_DNR](https://user-images.githubusercontent.com/37374766/59629492-581cc080-9119-11e9-888f-9a164f1cd51c.jpg)

**Diagrama de blocos da eletrônica;

**Diagrama/tabela de pinagem;

**Fluxograma do firmware;





