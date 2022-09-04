## Sistema de aquecimento para rolo alumínio EW

Instalação elétrica do sistema de aquecimento e pneumático para rolo aquecido do alumínio de uma máquina de Packaging do grupo COESIA - GD.

A EW é uma máquina de desenvolvimento, que basicamente desenrola uma bobina de alumínio até a entrega para uma outra máquina, afim de formar a embalagem interna do produto a ser fabricado.


<img src="/EW-roller-heater/Assets/machine.jpg"/> 

Essas bobinas vem com um defeito de fabricação onde sua extremidade vem ondulada e devido a sensores na máquina essa ondulação impacta numa alta rejeição de produtos considerados conforme para o mercado. 

<img src="/EW-roller-heater/Assets/defect.jpg" width="45%"/> 

### 🧩 O desafio

Desenvolver um circuito off-board da máquina para controle de temperatura das resistências, outro ponto é o acionamento de um pistão somente no momento que a máquina girar, pois o rolo aquecido não pode ficar em contato direto com a matéria prima.

### 💡 A solução

Para o sistema de aquecimento foi escolhido um módulo de controle de temperatura da NOVUS ligado a um termopar para a medição da temperatura, de acordo com o set-point configurado no controlador ele aciona uma saída para um relé de estado sólido este por sua vez libera tensão para a resistência.


Em relação ao pistão pneumático, a melhor solução foi alterar o software do CLP Step7 onde lincamos o seu movimento a um bit da leitura do encoder, ou seja quando a máquina entra em funcionamento uma saída digital atrelada a leitura do encoder aciona a válvula que libera o ar para o pistão fazendo o rolo aquecido entrar em contato com o alumínio somente nesse caso.

<img src="/EW-roller-heater/Assets/componentes.png" width="80%"/> 

Diagrama de instalação elétrica seguindo os padrões do fabricante.


Diagrama de potência                                            |  Diagrama de contole
:----------:                                           |  :--------------:
<img src="/EW-roller-heater/Assets/diagrama-potencia.jpg" width="90%"/>   |  <img src="/EW-roller-heater/Assets/diagrama-valvula.jpg" width="90%"/>

### 🤔 Dificuldades do projeto

Nesse projeto a maior dificuldade foi a implementação do código direto no CLP, devido a linguagem utilizada pelo fabricante da máquina ser complexa e pouco intuitiva chamada de STL uma especie de lista de instruções parecida com a antiga assembly.


<img src="/EW-roller-heater/Assets/stl.png" width="60%"/>

A montagem também foi complexa já que há pouco espaço sobressalente no equipamento para a inserção de novos dispositivos como disjuntores, relés e cabos elétricos.


### 🎯 Resultado final
Graças ao sistema foi possível trabalhar com bobinas que antes iriam para refugo, tornado a máquina mais eficiente contribuindo para um aumento de OEE do equipamento.

<img src="/EW-roller-heater/Assets/roller.jpg" width="50%"/>

## 🔥 Próximos passos
- [ ] Incorporar o sistema de medição diretamente ao CLP da máquina;

## 🙏🏻 Agradecimentos

A parceria no projeto entre meu colega e técnico mecânico Michael foi imprescindível para a eficácia do projeto, já que ele desenvolveu todo o sistema mecânico como rolos, suportes, acionamentos e demais ajustes pertinentes.

[Michael Silva](https://www.linkedin.com/in/michael-silva-37370520b/)

<br>
<br>

>* [Voltar para página inicial](../README.md)
