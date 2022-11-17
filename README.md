# informatica-industrial
Trabalho prático da disciplina de Informática Industrial do curso de Engenharia de Controle e Automação da UFMG desenvolvendo um sistema de controle e automação de uma planta de manufatura
O trabalho deverá ser desenvolvido em grupos de até 3 alunos e aborda o desenvolvimento de um sistema de controle e automação de uma planta de manufatura contendo uma estante (ET) para armazenamento de tarugos, um braço mecânico (BM) para transporte, uma mesa (MT) para trabalho de tarugos (transformação em peça) e um transportador (TP) tipo esteira para transporte de peças dentro
de um forno (têmpera). Ao final, deve-se ter o controle lógico de cada equipamento, bem como o controle lógico e sequencial de todo o processo de manufatura, envolvendo todos os equipamentos, conforme mostram a Figura 1 e Figura 2.
![image](https://user-images.githubusercontent.com/62022318/202323601-014b7029-28d9-4d5d-9096-83c2a7917354.png)
![image](https://user-images.githubusercontent.com/62022318/202323631-03dfb9d1-a086-4753-93a3-85ce0e445793.png)

Uma indústria metalúrgica está modernizando sua linha de produção de peças e uma das unidades modernizadas é representada pela Figura 1. O processo de manufatura consiste em retirar um tarugo da estante (ET) e transportá-lo, por meio do braço mecânico (BM), até a mesa de trabalho (MT), onde um funcionário o retira da mesa e executa determinado trabalho (furação, usinagem, etc.), transformando o tarugo em uma peça. Após, um operador local devolve a peça para a MT e solicita que essa seja enviada para a têmpera, i.e., a peça deve ser transportada, por meio do BM, para o início do transportador (TP). Ao detectar a presença de uma peça em seu início, o TP é acionado, transportando a peça através de um forno. Quando a peça chegar ao final do TP, ele deve parar. Dessa forma, tem-se a seguinte sequência operacional para o processo:

I. O BM retira um tarugo da ET e transporta para a MT. Ao liberar o tarugo na MT, uma sinalização deve indicar a um operador de área que retire o tarugo para realizar trabalho;

II. Ao retornar com a peça tralhada para a MT, o mesmo operador solicita o seu envio para o forno de têmpera. Logo, o BM deve transportar a peça para o início do TP, onde se encontra instalado um sensor discreto capacitivo (ZXS-201).

III. Ao detectar a presença da peça por ZXS-201, o motor do TP (M4) deve ser acionado transportando a peça através do forno até o final do TP, onde se encontra instalado outro sensor discreto capacitivo (ZXS-202);

IV. Após o acionamento do TP, a peça deve ser transportada por um tempo de 5s, sendo posicionada no centro do forno de têmpera. Ela deve permanecer na mesma posição até que o processo de têmpera seja concluído;

V. Com a peça posicionada, o processo de têmpera consiste em manter a peça no forno por 25s e o requisitos de funcionamento para o acionamento são descritos no item 4;

VI. Após a etapa têmpera, o TP deve ser acionado novamente, para retirar a peça do forno e, ao detectar a presença da dessa pelo sensor ZXS-202, o TP deve ser desligado e uma sinalização deve indicar a um operador de área que retire a peça temperada da linha. Esse, por sua vez, deve sinalizar ao sistema, “peça foi retirada da linha”, de forma que o TP esteja
apto a receber uma nova peça.

Não existem sensores instalados na ET, portanto, assume-se que sempre haverá um tarugo disponível para uso, na mesma posição. Logo, para correta simulação do problema, deve ser possível ativar o status de presença de um tarugo na ET, manualmente, por meio da IHM;
