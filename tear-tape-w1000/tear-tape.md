## Controle de presença fitilho W1000 digital

Melhoria no sistema de monitoramento de presença de fitilho na carteira.

Para quem não conhece o fitilho é aquele facilitador para abrir embalagem seladas por meio de plásticos e filmes, uma boa referência é o famoso pacote de biscoito aquela fitinha que você puxa para abrir a embalagem do seu produto, então já da pra imaginar que é algo importante e critico em qualquer processo de fabricação.


<img src="/tear-tape-w1000/Assets/tearTapeexamplle.png" width="50%"/> 

A máquina W1000 é uma máquina do grupo COESIA - GD ela possui um sistema para monitorar o fitilho porém é de difícil regulagem e muito passível a erros de medição já que seu sistema é por contato físico, o sistema é baseado em um relógio comparador, conforme o sensor encosta no filme e no fitilho ele vária seu sinal analógico e então através de um range de min. e máx. o técnico configura o valor aceitável.

<img src="/tear-tape-w1000/Assets/original-system.png" width="80%"/> 

O grande problema desse sistema é que o fitilho tem menos de 1mm de espessura e essa leitura é feita apoiada em um rolo cilíndrico numa máquina que é capaz de produzir 1000 produtos por minuto o que torna o sistema menos eficiente ainda.

### 🧩 O desafio

Desenvolver um outro sistema de controle onde não há contato direto com o material, integrar a lógica e mensagens de erro ou parâmetros nativamente na interface original da máquina que foi desenvolvida pelo próprio fabricante.

### 💡 A solução

Aplicando técnicas de design thinking onde geralmente o simples é o que resolve, decidimos utilizar um sensor do tipo ótico através de fibra ótica, onde a largura da fibra possibilita exatamente focar no fitilho impedindo erros de leitura.

<img src="/tear-tape-w1000/Assets/new-system.png" width="80%"/> 

Criamos uma lógica onde temos parâmetros para desativar o sistema e um filtro de leitura on delay e off delay, como a máquina trabalha com altas velocidades, de fato por breves instantes menos de 1s o material tende a oscilar axialmente sobre seu percurso.

<img src="/tear-tape-w1000/Assets/par-sensor.png" width="80%"/>

Por fim criei a parte gráfica já que o sensor não faz parte do portifólio da GD, editei uma imagem existente inserindo nosso sensor novo nela mantendo o mesmo padrão da interface original.

Imagem da seção de parâmetros                                               |  Imagem quando a mensagem de erro surge na interface
:----------:                                                        |  :--------------:
<img src="/tear-tape-w1000/Assets/sensor.jpg" width="80%"/>   |  <img src="/tear-tape-w1000/Assets/sensor-msg.jpg" width="80%"/> 

Como boa prática, documentar todo o processo da alteração e atualizar diagramas elétricos devem ser realizados após a validação do projeto, abaixo você confere o novo diagrama de instalação elétrica seguindo os padrões do fabricante.

<img src="/tear-tape-w1000/Assets/diagram.png" width="80%"/>  

### 🤔 Dificuldades do projeto

A fabricante possui um framework para trabalhar com os CLPs da Beckhoff chamada AFL, esse framework possui comunicação direta com a interface chamada de aHMI, normalmente quando se programa em CLP utiliza-se linguagens como ladder, FBD e ST, Nesse caso toda a programação é do tipo OOP linguagem baseada em programação orientada a objeto, o que
dificulta modificações devido a necessidade de conhecer e saber utilizar o framework.

Programação lado CLP                                                |  Programação lado da IHM
:----------:                                                        |  :--------------:
<img src="/tear-tape-w1000/Assets/afl-example.png" width="80%"/>   |  <img src="/tear-tape-w1000/Assets/xml-example.png" width="80%"/> 

Outro ponto critico é sobre criar novas mensagens e parâmetros na IHM já que a mesma é toda baseada em XML e existe pontos específicos de atenção para que as coisas trabalhem corretamente.

### 🎯 Resultado final

Com o novo sistema conseguimos eliminar reclamações de SAC ou inibições de produto pelo setor de qualidade da empresa já que o fitilho é um ponto crítico do produto, no equipamento aumentamos o MTBF (tempo médio entre paradas) nesse ponto da máquina e por fim quando há alguma intervenção no grupo ela é feita rapidamente se comparada ao tempo de ajuste do antigo sistema melhorando também o tempo de MTTR (tempo médio de parada).

<img src="/tear-tape-w1000/Assets/par-menu.png" width="80%"/>  

## 🔥 Próximos passos
- [ ] Expandir para outras unidades a modificação;

## 🙏🏻 Agradecimentos

A parceria no projeto entre meu colega e técnico Thiago Ambrosio onde o mesmo ficou responsável pela lógica e debug no CLP, e eu fiquei responsável pela instalação física e alteração do software da IHM para comunicar com a lógica que ele fez.

[Thiago Ambrosio](https://www.linkedin.com/in/thiago-gomides-ambr%C3%B3sio-3b42a532/)

<br>
<br>

>* [Voltar para página inicial](../README.md)
