# Lista de Artigos

***

Approved

Requisitos de Design

1. [Ver design em Figma](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB\[Handoff]-Design-Visual?node-id=6081-41075\&t=d393wPn6Kz5XhKSI-4)

Funcionais

1. **Requisitos Gerais**
   1. Conteúdo
      1. A aplicação deve exibir uma lista de artigos filtrada por diferentes elementos e atributos de classificação.
   2. Acesso ao ecrã
      1. A _Lista de Artigos_ pode ser acedida através de diferentes áreas da app:
         1. Ecrã de Destaques (blocos): Quando o utilizador interage com blocos de destaques que possuem navegação em profundidade;
         2. Página de Artigo: Quando o utilizador interage com os atributos de um artigo no ecrã de detalhe (Temática, Subtemática, Fonte, Autores e Tags)
         3. Feed de Artigos (Para mim): Quando o utilizador interage com blocos que possuem navegação em profundidade, como o _Full Coverage_ (previsto para pós MVP).
   3. Ações e Navegação
      1. Aceder ao detalhe do artigo (Página de Artigo)
         1. Ao interagir com o card do artigo, o utilizador deve ser redirecionado para a página de detalhes do artigo escolhido.
      2. Visualizar resumo de artigo
         1. O utilizador deve poder reproduzir o resumo do artigo diretamente a partir do card do artigo na lista de artigos;
         2. A reprodução do resumo deve seguir os fluxos e regras especificados em Resumo de Artigo Único.
      3. Feedback de Relevância (Like/Dislike)
         1. O utilizador deve poder indicar interesse (**Like**) ou desinteresse (**Dislike**) por um artigo, diretamente a partir do card do artigo na lista de artigos;
         2. Aplicam-se as regras especificadas para a funcionalidade Feedback de Relevância (Like/Dislike).
      4. Seguir conteúdo (Following)
         1. O utilizador deve poder **seguir (following)** ou **deixar de seguir (unfollowing)** um “tipo” de conteúdo, diretamente a partir da lista de artigos;
         2. Aplicam-se as regras especificadas para a funcionalidade Following - Seguir Conteúdo;
         3. O CTA das ações following/unfollowing deve ser exibido apenas para listas filtradas por elementos que podem ser seguidos (ver requisitos em Following - Seguir Conteúdo).
      5. Voltar
         1. O utilizador deve poder voltar para o ecrã anterior.

***

2. **Temática e Sub-temática (**[**ver em Figma**](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11596-141258\&t=UaLRh78IBsyrjneh-4)**)**
   1. Carrossel de Subtemáticas (filtro) ([ver em Figma](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11596-141260\&t=Tf9w9kUBayaOlaa1-4))
      1. **Descrição**: Componente para navegação e filtragem entre Subtemáticas de uma mesma Temática;
      2. **Regra de Exibição**: Deve ser exibido somente quando a lista é filtrada por Temática ou Subtemática.
   2. Destaque Principal ([ver em Figma](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11596-141268\&t=Tf9w9kUBayaOlaa1-4))
      1. **Descrição**: Componente que destaca um artigo específico;
      2. **Regra de Exibição**: É exibido somente se o ecrã _Lista de Artigos_ for acedido através dos blocos temáticos presentes no ecrã de destaques;
      3. **Conteúdo**: Deve exibir o **primeiro** dos artigos obtidos do highlights-group associado ao bloco (temático) pelo qual o utilizador acedeu ao ecrã _Lista de Artigos_.
         1. **Nota**: Os artigos devem ser obtidos conforme as regras especificadas nos requisitos técnicos do ecrã de destaques.
   3. Carrossel de Destaques ([ver em Figma](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11990-12469\&t=PNXkmhe0TBbsvR0k-4))
      1. **Descrição**: Componente que exibe os artigos destacados da temática filtrada;
      2. **Regra de Exibição**:
         1. É exibido somente se o ecrã _Lista de Artigos_ for acedido através dos blocos temáticos presentes no ecrã de destaques;
         2. É exibido somente quando o ecrã estiver filtrado por **temática** (no [carrossel de subtemáticas](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11596-141260\&t=Tf9w9kUBayaOlaa1-4), deve estar selecionada a tab _“Todos”_). Quando filtrado por **subtemática**, este componente não deve ser exibido.
      3. **Conteúdo**: Deve exibir do **segundo** ao **último** dos artigos obtidos do highlights-group associado ao bloco (temático) pelo qual o utilizador acedeu ao ecrã _Lista de Artigos_.
         1. **Nota**: Os artigos devem ser obtidos conforme as regras especificadas nos requisitos técnicos do ecrã de destaques.
   4. Lista de Últimas
      1. **Descrição**: A aplicação deve exibir uma listagem de artigos filtrada por Temática ou Sub-Temática, e ordenada em decrescente por data de publicação (mais recente no topo).
      2. **Conteúdo (filtros)**
         1. Quando a _Lista de Artigos_ é acedida através do **Ecrã de Destaques (blocos),** por default, a lista deve ser filtrada pelas **Temáticas**(categoryIds) e **Tags**(tagIds) associada ao bloco;
         2. Quando a _Lista de Artigos_ é acedida através da **Página de Artigo**, por default, a lista pode ser filtrada pela **Temática** (opção _Todos_ selecionada) ou por **Subtemática**, dependendo do elemento em destaque no detalhe do artigo visualizado e com o qual o utilizador interage;
         3. Para evitar duplicações, a Lista de Últimas não deve apresentar artigos que já estejam visíveis nos componentes de destaque (Destaque Principal e Carrossel de Destaques). Ou seja, ao exibir os destaques, a Lista de Últimas deverá filtrar e omitir esses mesmos artigos.
      3. **Carrossel de Subtemáticas**
         1. Quando houver interação com o **Carrossel de Chips**, a lista deverá ser filtrada pela **Sub-Temática** selecionada;
         2. Deve ser possível selecionar apenas uma Sub-Temática por vez, consequentemente a lista é sempre filtrada apenas por uma uma Sub-Temática por vez;
         3. Ao selecionar a opção _Todos_ no **Carrossel de Chips**, a lista deve ser novamente filtrada por **Temática**;
         4. A lista nunca deve ser filtrada por mais de uma **Temática** por vez.
   5. Título do ecrã
      1. Exibe sempre o nome da temática filtrada. Quando filtrado por subtemática, continua a exibir o nome da temática pai (parentCategory).
   6. Following
      1. Disponível

***

3. **Opinião (**[**ver em Figma**](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11990-13811\&t=PNXkmhe0TBbsvR0k-4)**)**
   1. Destaque Principal
      1. **Descrição**: Componente que destaca um artigo específico;
      2. **Regra de Exibição**: É exibido somente se o ecrã _Lista de Artigos_ for acedido através do bloco de opinião presente no ecrã de destaques;
      3. **Conteúdo**: Deve exibir o **primeiro** dos artigos obtidos do highlights-group associado ao bloco (opinião) pelo qual o utilizador acedeu ao ecrã _Lista de Artigos_.
         1. **Nota**: Os artigos devem ser obtidos conforme as regras especificadas nos requisitos técnicos do ecrã de destaques.
   2. Carrossel de Destaques
      1. **Descrição**: Componente que exibe os artigos de opinião destacados;
      2. **Regra de Exibição**: É exibido somente se o ecrã _Lista de Artigos_ for acedido através do bloco de opinião presente no ecrã de destaques;
      3. **Conteúdo**: Deve exibir do **segundo** ao **último** dos artigos obtidos do highlights-group associado ao bloco (opinião) pelo qual o utilizador acedeu ao ecrã _Lista de Artigos_.
         1. **Nota**: Os artigos devem ser obtidos conforme as regras especificadas nos requisitos técnicos do ecrã de destaques.
   3. Lista de Última
      1. Exibe uma lista de todos os artigos de opinião (subtemática = _‘opinião’_) disponíveis na app, ordenada em decrescente por data de publicação (mais recente no topo);
   4. Título do ecrã
      1. Exibe o texto fixo “Opinião”;
   5. Following
      1. Disponível (o utilizador passa a seguir a subtemática _Opinião_)

***

4. **Fontes (**[**ver em Figma**](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11596-141292\&t=UaLRh78IBsyrjneh-4)**)**
   1. Conteúdo: Exibe uma lista de artigos filtrada por uma **Fonte/Parceiro** (partners) específica;
   2. Título do ecrã: Exibe o nome da fonte filtrada (partners.title);
   3. Following: Disponível

***

5. **Autores (**[**ver em Figma**](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11596-141320\&t=UaLRh78IBsyrjneh-4)**)**
   1. Conteúdo: Exibe uma lista de artigos filtrada por um **Autor** (authors) específico;
   2. Título do ecrã: Exibe o nome do autor filtrado (authors.name);
   3. Following: Disponível

***

6. **Tag (**[**ver em Figma**](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11596-141304\&t=UaLRh78IBsyrjneh-4)**)**
   1. Conteúdo: Exibe uma lista de artigos filtrada por uma **Tag** específica.
   2. Título do ecrã: Exibe o nome da tag filtrada;
   3. Following: Disponível

***

7. **Últimas** [**(ver em Figma**](https://www.figma.com/design/jWFlJEYGhbSeCSDxLjKHTp/Sapo%E3%83%BB-Handoff--Design-Visual?node-id=11596-141234\&t=UaLRh78IBsyrjneh-4)**)**
   1. Conteúdo: Exibe uma lista de todos os artigos disponíveis na app, não filtrada e ordenada em decrescente por data de publicação (mais recente no topo).
   2. Título do ecrã: Exibe o texto fixo “Últimas”;
   3. Following: Indisponível

***
