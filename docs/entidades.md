### Classe Usuário

#### Atributos:
- `id : int` - Identificador único do usuário.
- `nome : string` - Nome completo do usuário.
- `email : string` - Endereço de e-mail associado ao usuário.
- `senha : string` - Senha para autenticação do usuário.
- `perfil : Perfil` - Referência ao perfil do usuário, que contém informações sobre histórico, preferências, entre outras coisas.
- `data_de_nascimento : data` - Data de nascimento do usuário.
- `telefone : string` - Número de telefone do usuário.
- `endereço : string` - Endereço do usuário.
- `assinatura_ativa : bool` - Indica se o usuário possui uma assinatura ativa.
- `data_criacao_conta : datetime` - Data e hora em que a conta foi criada.

#### Métodos:
- `__init__(id, nome, email, senha, data_de_nascimento, telefone, endereço)` - Construtor que inicializa os atributos do usuário ao ser criado.
- `adicionar_item_ao_historico(item)` - Adiciona um item de conteúdo ao histórico do usuário.
- `atualizar_informacoes_pessoais(novo_nome, novo_email, nova_senha, nova_data_de_nascimento, novo_telefone, novo_endereço)` - Atualiza as informações pessoais do usuário.
- `ativar_assinatura()` - Ativa a assinatura do usuário.
- `desativar_assinatura()` - Desativa a assinatura do usuário.

#### Relacionamentos:
- `1 perfil : 1 Perfil` - Um usuário tem um perfil associado que contém informações detalhadas sobre suas preferências e histórico de visualizações.

#### Comentários:
- Esta versão mais completa da classe Usuário inclui informações adicionais, como data de nascimento, telefone, endereço e status da assinatura. Isso pode ser útil em cenários onde essas informações são relevantes para a funcionalidade do sistema.

### Classe Perfil

#### Atributos:
- `historico : list` - Lista de itens visualizados pelo usuário.
- `preferencias : list` - Lista de gêneros, diretores, artistas, etc., preferidos pelo usuário.

#### Métodos:
- `adicionar_ao_historico(item)` - Adiciona um item ao histórico de visualizações do usuário.
- `adicionar_preferencia(genero)` - Adiciona um gênero (ou outra preferência) à lista de preferências do usuário.
- `remover_preferencia(genero)` - Remove um gênero (ou outra preferência) da lista de preferências do usuário.
- `limpar_historico()` - Limpa o histórico de visualizações do usuário.
- `limpar_preferencias()` - Limpa a lista de preferências do usuário.

#### Relacionamentos:
- N/A

#### Comentários:
- A classe `Perfil` é responsável por armazenar informações relacionadas ao comportamento do usuário, como histórico de visualizações e preferências. Estas informações são essenciais para a geração de recomendações personalizadas e para oferecer uma experiência mais ajustada aos gostos do usuário.

### Classe Genero

#### Atributos:
- `id : int` - Identificador único.
- `descrição : string` - Gênero do conteúdo.

#### Comentários:
- A tabela Genero armazena diferentes gêneros associados aos itens de conteúdo, como séries, filmes e músicas. Cada gênero é identificado por um id único e possui uma descrição que especifica o tipo ou categoria do conteúdo. Esta tabela será referenciada pelos itens de conteúdo para categorizá-los conforme seus respectivos gêneros.

### Classe Música

#### Atributos:
- `id : int` - Identificador único da música.
- `titulo : string` - Título da música.
- `interprete : string` - Nome do intérprete, seja um artista solo, banda ou entidade responsável pela execução da música.
- `duracao : float` - Duração da música em minutos.
- `ano_lancamento : int` - Ano de lançamento da música.
- `album : string` - Nome do álbum em que a música está presente.
- `compositores : list` - Lista de compositores da música.
- `letra : string` - Letra da música.
- `avaliacao_media : float` - Avaliação média atribuída pelos usuários.
- `genero_id : int` - Identificador do gênero associado à música.

#### Relacionamentos:
- `1 genero_id : N Genero` - Uma música está associada a um gênero específico da tabela Genero.

#### Comentários:
- A classe `Música` representa uma faixa musical na plataforma. Possui atributos como identificador único (`id`), título da música, intérprete (artista responsável pela execução), duração, ano de lançamento, álbum, compositores, letra, avaliações dos usuários e avaliação média. O atributo `genero_id` refere-se ao identificador do gênero associado à música, estabelecendo um relacionamento com a tabela `Genero`, onde cada música está vinculada a um gênero específico.

### Classe Filme

#### Atributos:
- `id : int` - Identificador único do filme.
- `titulo : string` - Título do filme.
- `diretor : string` - Nome do diretor do filme.
- `duracao : float` - Duração do filme em minutos.
- `ano_lancamento : int` - Ano de lançamento do filme.
- `atores : list` - Lista de atores principais do filme.
- `avaliacao_media : float` - Avaliação média atribuída pelos usuários.
- `genero_id : int` - Identificador do gênero associado ao filme.

#### Relacionamento:
- `1 genero_id : N Genero` - Um filme está associado a um gênero específico da tabela `Genero`.

#### Comentários:
- A classe `Filme` representa um filme na plataforma. Possui atributos como identificador único (`id`), título do filme, diretor, duração, ano de lançamento, lista de atores, avaliações dos usuários e avaliação média. O atributo `genero_id` refere-se ao identificador do gênero associado ao filme, estabelecendo um relacionamento com a tabela `Genero`, onde cada filme está vinculado a um gênero específico.

### Classe Série

#### Atributos:
- `id : int` - Identificador único da série.
- `titulo : string` - Título da série.
- `criador : string` - Nome do criador ou showrunner da série.
- `temporadas : int` - Número de temporadas da série.
- `ano_lancamento : int` - Ano de lançamento da série.
- `elenco : list` - Lista de elenco principal da série.
- `avaliacao_media : float` - Avaliação média atribuída pelos usuários.
- `genero_id : int` - Identificador do gênero associado à série.

#### Relacionamento:
- `1 genero_id : N Genero` - Uma série está associada a um gênero específico da tabela `Genero`.

#### Comentários:
- A classe `Série` representa uma série de televisão na plataforma. Possui atributos como identificador único (`id`), título da série, criador/showrunner, número de temporadas, ano de lançamento, elenco principal, avaliações dos usuários e avaliação média. O atributo `genero_id` refere-se ao identificador do gênero associado à série, estabelecendo um relacionamento com a tabela `Genero`, onde cada série está vinculada a um gênero específico.

### Classe Playlist

#### Atributos:
- `id : int` - Identificador único da playlist.
- `titulo : string` - Título ou nome da playlist.
- `descricao : string` - Descrição da playlist.
- `criador : string` - Nome do usuário criador da playlist.
- `publica : bool` - Indica se a playlist é pública (`True`) ou privada (`False`).
- `musicas : list` - Lista de músicas presentes na playlist.
- `filmes : list` - Lista de filmes presentes na playlist.
- `series : list` - Lista de séries presentes na playlist.
- `avaliacao_media : float` - Avaliação média atribuída pelos usuários.
- `usuario_id : int` - Identificador do usuário proprietário da playlist.

#### Relacionamentos:
- `1 usuario_id : N Usuário` - Uma playlist pertence a um único usuário. Um usuário pode ter várias playlists.
- `N musicas : N Música` - Várias músicas podem estar presentes em várias playlists.
- `N filmes : N Filme` - Vários filmes podem estar presentes em várias playlists.
- `N series : N Série` - Várias séries podem estar presentes em várias playlists.

#### Comentários:
- A classe `Playlist` representa uma lista de reprodução na plataforma. Possui atributos como identificador único (`id`), título, descrição, criador da playlist, indicador de privacidade (`publica` ou `privada`), listas de músicas, filmes e séries presentes na playlist, informações sobre as avaliações dos usuários e a avaliação média atribuída à playlist. Estabelece-se relacionamentos com as classes `Usuário`, `Música`, `Filme` e `Série`, indicando que uma playlist pertence a um único usuário e pode conter várias músicas, filmes e séries.

### Classe Avaliação

#### Atributos:
- `id : int` - Identificador único da avaliação.
- `usuario_id : int` - Identificador do usuário que realizou a avaliação.
- `playlist_id : int` - Identificador da playlist avaliada (opcional).
- `musica_id : int` - Identificador da música avaliada (opcional).
- `filme_id : int` - Identificador do filme avaliado (opcional).
- `serie_id : int` - Identificador da série avaliada (opcional).
- `nota : int` - Nota atribuída pelo usuário.
- `comentario : string` - Comentário ou observação do usuário sobre o item avaliado.

#### Relacionamentos:
- `1 usuario_id : N Usuário` - Uma avaliação é realizada por um único usuário. Um usuário pode fazer várias avaliações.
- `1 playlist_id : 1 Playlist` - Uma avaliação está associada a uma única playlist (se aplicável).
- `1 musica_id : 1 Música` - Uma avaliação está associada a uma única música (se aplicável).
- `1 filme_id : 1 Filme` - Uma avaliação está associada a um único filme (se aplicável).
- `1 serie_id : 1 Série` - Uma avaliação está associada a uma única série (se aplicável).

#### Comentários:
- A classe `Avaliação` permite avaliações de playlists, músicas, filmes e séries. Possui atributos como identificador único (`id`), identificador do usuário que fez a avaliação (`usuario_id`), identificadores dos itens avaliados (`playlist_id`, `musica_id`, `filme_id`, `serie_id`), nota atribuída pelo usuário e um comentário opcional sobre o item avaliado.


### Classe Comentário

#### Atributos:
- `id : int` - Identificador único do comentário.
- `usuario_id : int` - Identificador do usuário que fez o comentário.
- `playlist_id : int` - Identificador da playlist relacionada ao comentário (opcional).
- `musica_id : int` - Identificador da música relacionada ao comentário (opcional).
- `filme_id : int` - Identificador do filme relacionado ao comentário (opcional).
- `serie_id : int` - Identificador da série relacionada ao comentário (opcional).
- `texto : string` - Texto do comentário.

#### Relacionamentos:
- `1 usuario_id : N Usuário` - Um comentário é feito por um único usuário. Um usuário pode fazer vários comentários.
- `1 playlist_id : 1 Playlist` - Um comentário está associado a uma única playlist (se aplicável).
- `1 musica_id : 1 Música` - Um comentário está associado a uma única música (se aplicável).
- `1 filme_id : 1 Filme` - Um comentário está associado a um único filme (se aplicável).
- `1 serie_id : 1 Série` - Um comentário está associado a uma única série (se aplicável).

#### Comentários:
- A classe `Comentário` permite aos usuários deixarem comentários em playlists, músicas, filmes e séries. Possui atributos como identificador único (`id`), identificador do usuário que fez o comentário (`usuario_id`), identificadores dos itens relacionados (`playlist_id`, `musica_id`, `filme_id`, `serie_id`) e o texto do comentário em si.

### Classe Recomendação

#### Atributos:
- `id : int` - Identificador único da recomendação.
- `usuario_id : int` - Identificador do usuário para quem a recomendação é feita.
- `playlists : list` - Identificadores da playlist recomendada (opcional).
- `musicas : list` - Identificadores da música recomendada (opcional).
- `filmes : list` - Identificadores do filme recomendado (opcional).
- `series : list` - Identificadores da série recomendada (opcional).
- `texto : string` - Texto da recomendação.
- `dados_utilizados : list` - Lista de tipos de dados dos usuários utilizados para essa recomendação (avaliações, histórico de navegação, preferências, localização, etc.).

#### Relacionamentos:
- `1 usuario_id : N Usuário` - Uma recomendação é direcionada a um único usuário. Vários itens podem ser recomendados a um usuário.

#### Comentários:
- A classe `Recomendação` representa itens recomendados pela plataforma para usuários específicos, utilizando dados variados dos usuários para a geração dessas recomendações. Possui atributos como identificador único (`id`), identificador do usuário para quem a recomendação é feita (`usuario_id`), identificadores dos itens recomendados (`playlist_id`, `musica_id`, `filme_id`, `serie_id`), além do texto descritivo da recomendação, o nome do algoritmo utilizado para a recomendação e uma lista dos tipos de dados dos usuários que foram utilizados para gerar essa recomendação.
