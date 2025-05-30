# Feed de Capas

***

{#feed-de-capas}

Approved

### **Feed - Carrossel de Capas Favoritas**

Funcional

1. Ver em [Capas Favoritas](broken-reference)

***

### **Feed - Carrossel de Capas por Temática**

O utilizador deve poder visualizar capas agrupadas por temática

Design

1. [Link Figma](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB\[Handoff]-Design-Visual?node-id=5171-15506\&t=wAieDihblOGN662Q-0)

Funcional

1. **Regras de exibição do componente**
   1. Deve ser exibido um carrossel de capas para cada temática existente que possua ao menos uma Capa-Fonte associada;
2. **Regras de exibição das capas**
   1. Exibe **apenas** capas-fonte correspondentes a **temática** do carrossel;
   2. Para cada **capa-fonte**, deve ser exibida apenas 1 **capa-publicação**;
   3. Deve ser exibido sempre a capa-publicação com data de publicação **mais recente** (independente do valor da data ou da periodicidade de publicação);
   4. Limite de capas: Cada carrossel deve exibir no máximo 10 capas-fonte:
   5. Tempo de cache: O tempo de expiração de cache previsto para o ecrã Feed de Capas deve ser de 10 min. Enquanto a cache estiver válida, a app não deve fazer novos pedidos para carregamento de novos conteúdos.
3. **Regras de Ordenação (carrossel no Feed):**
   1. A aplicação deve ordenar os carrosséis no Feed com base na seguinte hierarquia:
      1. 1º posição: exibe sempre o carrossel de capas favoritas;
      2. 2º posição em diante: ordenar **ascendente** por **nome da temática**.
4. **Regras de Ordenação (capas dentro do carrossel):**
   1. A aplicação deve ordenar as capas com base na seguinte hierarquia:
      1. 1º: Ordenar **ascendente** por _**posição**_;
      2. 2º: Ordenar **descendente** por _**data de publicação**_;
      3. 3º: Ordenar **ascendente** por _**nome da capa-fonte**_;
   2. Para este componente (_Carrossel de Capas por Temática_) deve ser aplicado o valor de posição associada a sub-temática _“todos”_.
   3. **Nota técnicas**:
      1. Todos os atributos fazem parte do objeto capa, retornado pelo RabbitMQ-SAPO:
         1. _posição =_ position;
         2. _data de publicação =_ DateTime;
         3. _nome da capa-fonte =_ Producer.Name.
      2. As capas possuem um valor de posição para cada sub-temática a qual fazem parte, podendo ter diferentes valores de posição entre as sub-temáticas.
5. **Ações:**
   1. Aceder à **lista completa** de capas da temática:
      1. Ao interagir com o carrossel, a aplicação deve ser capaz de redirecionar o utilizador para o layout [_Lista de Capas_](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB\[Handoff]-Design-Visual?node-id=5171-15499\&t=wAieDihblOGN662Q-0);
      2. Após o redirecionamento:
         1. A _Lista de Capas_ deve ser automaticamente filtrada pela temática correspondente ao carrossel selecionado;
         2. A _Lista de Capas_ deve ser automaticamente filtrada pela sub-temática _todos_.
   2. Aceder ao **detalhe de um capa-fonte** específica:
      1. Ao interagir com uma capa específica, a aplicação deve ser capaz de redirecionar o utilizador para o layout [_Detalhe de Capa_](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB\[Handoff]-Design-Visual?node-id=5171-15482\&t=wAieDihblOGN662Q-0);
      2. Após o redirecionamento, deve ser exibido o detalhe da capa selecionada.
   3. Adicionar / Remover dos Favoritos
      1. Ver em [Capas Favoritas](broken-reference)
   4. Partilhar Capa
      1. A partilha de capas deve seguir os requisitos a serem definidos na funcionalidade [Partilhar conteúdos](https://dev.azure.com/blissapps/SAPO%20App/_workitems/edit/29429).

### ---

### **Bottom Bar**

Comportamento da Bottom App Bar no ecrã Feed de Capas

Funcional

1. **Regras de exibição:**
   1. Default: Por default, a Bottom App Bar é **sempre exibida** na renderização do ecrã Feed de Capas;
   2. Hide: A Bottom App Bar deve ser **escondida** quando o utilizador fizer scroll down;
   3. Unhide: A Bottom App Bar deve ser **exibida** novamente quando o utilizador fizer scroll up;

### ---
