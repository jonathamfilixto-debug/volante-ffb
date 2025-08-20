
-----

# **Open FFB Wheel BR - Um Volante Force Feedback Acessível**

`[ PROJETO EM DESENVOLVIMENTO ]`

E aí, beleza? Se você, assim como eu, é maluco por simuladores mas acha um absurdo o preço de um volante com Force Feedback decente, este projeto é pra você.

A ideia aqui é construir um kit completo (volante, pedais e câmbio) com um FFB forte de verdade, gastando o mínimo possível e usando peças fáceis de achar no Brasil. A base toda é controlada por um único Arduino, e a construção pode ser feita tanto em **madeira**, pra quem curte marcenaria, quanto em **impressão 3D**.

Bora montar? 🏎️

## **Índice (pra você não se perder)**

  * [O Que é o Projeto?](https://www.google.com/search?q=%23o-que-%C3%A9-o-projeto)
  * [Opções de Construção](https://www.google.com/search?q=%23op%C3%A7%C3%B5es-de-constru%C3%A7%C3%A3o)
  * [Lista de Peças (O que você vai precisar 🔧)](https://www.google.com/search?q=%23lista-de-pe%C3%A7as-o-que-voc%C3%AA-vai-precisar-)
  * [O Cérebro do Volante: Software e Firmware 🧠](https://www.google.com/search?q=%23o-c%C3%A9rebro-do-volante-software-e-firmware-)
  * [Como Ligar Tudo (Fiação) 🔌](https://www.google.com/search?q=%23como-ligar-tudo-fia%C3%A7%C3%A3o-)
  * [Modelos 3D e Planos de Corte](https://www.google.com/search?q=%23modelos-3d-e-planos-de-corte)
  * [⚠️ LEIA ISSO ANTES DE COMEÇAR (SEGURANÇA) ⚠️](https://www.google.com/search?q=%23-leia-isso-antes-de-come%C3%A7ar-seguran%C3%A7a--)
  * [Licença e Agradecimentos](https://www.google.com/search?q=%23licen%C3%A7a-e-agradecimentos)

## **O Que é o Projeto?**

Resumindo, a gente vai montar um kit completo que inclui:

  * **Volante com Force Feedback:** O coração do projeto. Usa um motor de 24V com polias pra dar aquele coice no braço e sentir a pista de verdade.
  * **Pedais Analógicos:** Um conjunto com 3 pedais (acelerador, freio e embreagem) que usam potenciômetros pra ter precisão.
  * **Câmbio H-Shifter:** Um câmbio de 6 marchas + ré e um botão extra pra mapear o que você quiser.

## **Opções de Construção**

Você pode escolher o caminho que for melhor pra você:

1.  **Na Madeira (Estilo Raiz):** Usando MDF ou Pinus. Fica super robusto e é ideal pra quem já tem umas ferramentas em casa.
2.  **Na Impressora 3D (Estilo Moderno):** Se você tem uma impressora 3D, pode imprimir tudo. O visual fica mais profissional e o encaixe das peças é perfeito.

## **Lista de Peças (O que você vai precisar 🔧)**

### **1. Eletrônica (a alma do negócio)**

| Peça | Qtd | Dicas e Preço Médio (R$) |
| :--- | :-: | :--- |
| Arduino Leonardo | 1 | Tem que ser o Leonardo ou Pro Micro (com chip ATmega32u4)\! Outro não serve. (R$ 50 - R$ 90) |
| Encoder 600 P/R | 1 | Recomendo o de 600 pulsos, é o que o software usa como padrão. (R$ 30 - R$ 60) |
| Driver BTS7960 | 1 | Esse "módulo azul" é o que vai dar força pro motor. É barato e aguenta o tranco. (R$ 40 - R$ 70) |
| Fonte 24V 10A | 1 | **Não economize aqui\!** Uma fonte fraca vai deixar seu FFB mole. (R$ 80 - R$ 150) |
| Potenciômetros B10K | 3 | Pros pedais. Tem que ser o linear (tipo "B"). (R$ 15 - R$ 30) |
| Micro Switches | 8 | Pro câmbio. Pega aquele com uma haste de metal. (R$ 20 - R$ 40) |
| Cabos e Conectores | - | Fios, conectores pra facilitar a desmontagem, etc. (R$ 50 - R$ 80) |

### **2. Mecânica (a parte bruta)**

| Peça | Qtd | Dicas e Preço Médio (R$) |
| :--- | :-: | :--- |
| Motor de Vidro Elétrico 24V | 1 | Um de caminhão é uma boa\! Tem bom torque. Procure em desmanches pra economizar. (R$ 60 - R$ 120) |
| Polias e Correia HTD5M | 1 | Um kit com polia pequena (15-20 dentes) e grande (60 dentes) é o ideal pra multiplicar a força. (R$ 80 - R$ 150) |
| Aro do Volante | 1 | O céu é o limite. Pega um de carro de verdade em um desmanche, fica muito mais legal. (R$ 70 - R$ 200) |
| Eixo, Rolamentos, Molas, Parafusos | - | Itens de ferragem. Nada muito caro. (R$ 70 - R$ 135) |

### **3. Estrutura (a carcaça)**

| Opção | Material | Preço Médio (R$) |
| :--- | :--- | :--- |
| **Madeira** | Chapa de MDF ou tábua de Pinus | R$ 50 - R$ 90 |
| **Impressão 3D**| \~2kg de Filamento PETG (recomendado) | R$ 160 - R$ 280 |

-----

### **Custo Final da Brincadeira?**

  * **Na Madeira:** Fica entre **R$ 615 e R$ 1.215**, dependendo do quanto você garimpar as peças.
  * **Na Impressora 3D:** Sobe um pouco, entre **R$ 725 e R$ 1.405**.

-----

## **O Cérebro do Volante: Software e Firmware 🧠**

Pra fazer o volante "ganhar vida", a gente vai usar um firmware já pronto e um programa de configuração. Sem complicação com código\!

1.  **Firmware:** A gente vai usar o `FFB Wheel 0.16.1 Leonardo.hex` (ou um mais novo). É ele que transforma o Arduino em um volante.
2.  **Programa para gravar:** O **xLoader** joga o firmware pra dentro do Arduino. É só apertar um botão.
3.  **Programa para configurar:** O **WillConfig** é onde a mágica acontece. Nele você calibra os pedais, ajusta os graus do volante e configura a força do FFB.

## **Como Ligar Tudo (Fiação) 🔌**

A pinagem no Arduino Leonardo é essa aqui. Pode parecer complicado, mas se seguir a ordem, não tem erro:

  * **Encoder:** Pinos `D10`, `D11`.
  * **Pedais:** `A0` (Embreagem), `A1` (Freio), `A2` (Acelerador). Todos ligados no `5V` e `GND` do Arduino.
  * **Câmbio:** Pinos `D2`, `D3`, `D4`, `D5`, `D7`, `D8`, `D9`, `D12`. Todos com um fio comum ligado no `GND`.
  * **Driver FFB (BTS7960):** Os pinos `RPWM` e `LPWM` do driver vão em pinos PWM do Arduino (como `D5` e `D6`). A fonte de 24V alimenta o driver, e o motor é ligado na saída dele.

*(Vou adicionar um desenho disso na pasta `/docs` pra facilitar).*

## **Modelos 3D e Planos de Corte**

  * **Versão em Madeira:** Vou deixar os planos de corte e medidas na pasta `/planos_madeira`.
  * **Versão Impressa em 3D:** Todos os arquivos `.STL` estarão na pasta `/STL`. A dica é imprimir as peças que precisam de força em **PETG** ou **ABS**, com umas 4 paredes e 30% de preenchimento pra não quebrar.

## **⚠️ LEIA ISSO ANTES DE COMEÇAR (SEGURANÇA) ⚠️**

Galera, falando sério agora. **Isso aqui não é um brinquedo.** Um motor de 24V com redução por polia tem força pra **machucar de verdade**.

  * **TORQUE ALTO:** O volante pode girar com uma violência inesperada. **Mantenha as mãos longe** durante os testes e a configuração. Cuidado com dedos, fios e a gola da sua camisa.
  * **ELETRICIDADE:** Use um **FUSÍVEL** entre a fonte e o driver. Isso pode salvar seus componentes (e sua casa) de um curto-circuito.
  * **BOTÃO DE EMERGÊNCIA:** É altamente recomendado instalar um botão grande e vermelho que corte a energia do motor na hora. Se algo der errado, é só bater nele.

Montem com cuidado e por sua conta e risco. A responsabilidade é toda sua.

## **Licença e Agradecimentos**

Este projeto é de código aberto (Licença MIT). Pode usar, modificar e compartilhar à vontade. Só peço que mantenha os créditos.

E um agradecimento especial à galera do canal **G-Tec** e a toda a comunidade de Sim Racing DIY que compartilha conhecimento e torna projetos como este possíveis. Tamo junto\!
