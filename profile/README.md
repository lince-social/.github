# O que é a <a href='https://www.lince.social'>Lince</a>?

A Lince é um serviço para cadastro de necessidades e contribuições de escopo aberto:

### 1. O que se precisa:

Temos necessidades diferentes, podendo ser:

- Básicas e pessoais, como: água, luz, saneamento, saúde, educação, habitação, alimentação, roupas, natureza, etc.
- Serviços, como: transporte, apoio técnico, enfermagem, jardinagem, cultura, entretenimento, turismo, etc.
- Outros bens de consumo, como: eletrodomésticos, ferramentas de trabalho, máquinas e matéria prima, etc.

### 2. O que se pode contribuir:

Indivíduos, coletivos e organizações podem oferecer seus produtos, serviços, assistência social, trabalho comunitário, presença, itens para doação, etc.

# Estrutura

A Lince é uma iniciativa sem fins lucrativos. Utiliza-se de financiamento popular, atualmente o Patreon, para desenvolver a tecnologia base, segurança de dados e um servidor próprio.

# Tecnologia

A Lince estará disponível como um site ou aplicativo, sendo acessível em qualquer rede. Os usuários poderão participar de diversos círculos da Lince: mundiais, nacionais, empresariais, municipais, familiares, entre outros. Além disso, a plataforma permitirá que os usuários divulguem suas necessidades, ajudas e doações de forma anônima ou identificada, para todos ou apenas para aqueles que desejarem.

O projeto é uma iniciativa de software livre, permitindo que qualquer pessoa interessada possa contribuir para sua implementação e melhoria contínua. O cadastro poderá ser feito por digitação, voz, foto ou vídeo, tornando-o acessível e fácil de usar. Para aqueles sem acesso à tecnologia, será possível adicionar suas necessidades e capacidades na Lince por meio de instituições credenciadas, como o SUS (Sistema Único de Saúde).

A plataforma busca unificar as interações econômicas e as trocas de recursos entre pessoas, empresas, governos e ONGs, reduzindo a necessidade de utilizar diversos aplicativos. Empresas podem ter perfis oficiais na Lince, oferecendo seus produtos em vez de criarem um aplicativo próprio. O investimento privado no desenvolvimento será compartilhado, reduzindo custos e impulsionando o projeto.

É importante destacar que a Lince é responsável por facilitar a conexão entre pessoas e recursos, transformando necessidades e contribuições em dados. Os custos relacionados à interação, como transporte, produção e serviços em si, continuam sendo responsabilidade das partes envolvidas.

Ao digitalizar as informações, a Lince possibilita o uso de algoritmos de otimização e aprendizado de máquina para um planejamento mais efetivo das contribuições. No entanto, é necessário considerar os vieses humanos presentes nos algoritmos e garantir transparência, consentimento e democracia ao implementar qualquer inteligência artificial tomadora de decisão. A distribuição dos recursos deve ser avaliada cuidadosamente, levando em consideração critérios como proximidade, necessidade absoluta ou potencial de mudança social ao recebê-los.

# Impacto

A Lince permite a criação de uma tabela para coordenar Necessidades Internas (NIs). Com o aumento do número de pessoas uma rede de apoio é formada através de Contribuições Externas (CEs). Também possibilitando Contribuições Internas (CIs) para atender às Necessidades Externas (NEs).

Com a flexibilidade de permitir qualquer tipo de cadastro, a Lince abre um leque de possibilidades. Desde o fornecimento de apoio após desastres naturais até o planejamento de eventos. Idas ao supermercado são facilitadas com Linces de famílias sendo preenchidos por todos. Sinalizações de manutenção de infraestruturas públicas serão como votos para a solução de tais carências. É possível criar recorrências de NIs para mapear seus hábitos, deixando-os visíveis é possível delegar parte deles a outras pessoas através de CEs. Queremos minimizar necessidades não atendidas, alinhar demandas e distribuições, e entender em que devemos trabalhar.

A troca de informações sobre necessidades em tempo real tem o potencial de diminuir o "efeito chicote" nas redes de suprimentos. Esse efeito ocorre quando uma compra esperada não acontece, acumulando perdas e gerando ineficiências. Com um número significativo de usuários cadastrados, as previsões de demanda podem se tornar desnecessárias; juntamente de uma diminuição de superprodução e falta de atendimento por informações de mercado incompletas.

A criação de uma plataforma para ofertar quaisquer produtos e serviços removerá barreiras para pequenos empreendedores e autônomos. Trabalho de qualquer tipo pode ser ofertado. Uma empresa pode criar NIs de tarefas a serem cumpridas e funcionários de insumos e ferramentas a serem comprados. Fluxos de atividades no trabalho podem ser acompanhados pela Lince. Além disso, pessoas e organizações que buscam trabalho comunitário poderão entrar em contato facilmente com aqueles que desejam impactar. Utilizamos recursos existentes, evitamos desperdícios, recebemos ajuda de outros, contribuímos por um preço e quando possível, gratuitamente.

# Lince Atual

Atualmente, a Lince está em fase de desenvolvimento do seu protótipo de site dinâmico e hosting, foca-se nas funcionalidades básicas. O protótipo permitirá o cadastro por digitação, terá listas de necessidades e contribuições, e funcionará a partir da primeira conexão entre uma necessidade de um usuário com uma contribuição de outro.

E-mail para contato: <a href="xaviduds@gmail.com">xaviduds@gmail.com</a>

### <a href="https://github.com/lince-social/lince/blob/main/fotos/Lince%20Wireframe%20website%20desktop%20v0.0.1.png">Wireframe</a>:

<img src="https://github.com/lince-social/lince/blob/main/fotos/Lince%20Wireframe%20website%20desktop%20v0.0.1.png">

Versão Básica Lince:

Tabela conta:
- id | CP (chave primária)
- nomeUsuário
- senha

Tabela perfil:
- id | CP
- nome_perfil


Tabela cadastro:
- id | CP
- título
- descrição
- tags
- idConta | CE (chave estrangeira)

Tabela conexãoLince:
- id | CP
- idCadastro1 | CE
- idCadastro2

(por enquanto fazer só uma conexão entre dois cadastros)

Tabela chat:
- id | CP
- idConta1 | CE
- idConta2 | CE

(toda vez que uma conexão lince ocorre, entre uma Necessidade e Contribuição por exemplo, um chat deverá ser iniciado, se já não existir, entre as contas envolvidas)

Tabela mensagem:
- id | CP
- conteúdo
- horárioCriação
- idConta | CE
- idChat | CE


Fiz uma normalização do banco de dados que eu acho que funcionaria pra primeira versão da lince, só com criação de contas, cadastro de necessidades e contribuições, chat pra conversar e realizar a interação lince e com frontend a gente bota um botão que quando as duas contas envolvidas clicam nele, o status da contribuição e necessidade é atualizado, ou só a quantidade. Exemplo: preciso de 10 maçãs, alguem doou 4, nós dois apertamos o botão, o status da contribuição fica como inexistente, pq a maçã foi doada, e o status da necessidade fica ainda como existente, mas agora da quantidade da necessidade como 6.

---

Informações sobre versões futuras da Lince, n precisa desenvolver pra ter essas features fazer agora, deixo aqui só pra dar mais contexto:

Para fazer um banco de dados da lince é preciso ter a criação de uma conta com poderes administrativos, e uma de usuários, com nome de usuário e senha, podendo criar diferentes perfis para uma conta de usuário. Acho. Dependendo do protocolo utilizado pra troca de informações entre círculos lince/servidores lince e formas de ter contas com usuários e perfis várias formas de modelar o banco de dados vão existir, essa é a versão que eu acho que funcionaria.

O outro banco de dados deve ser para os cadastros que esses usuários fizeram, seja em nececidades (N) ou contribuições (C) . Qualquer cadastro lince deverá ter diversas propriedades, não necessariamente preenchidas sempre, que permitem usuários criar qualquer N ou C.

Uma sugestão de features desses cadastro é: id, idConta, Título, Descrição, Tipo de Cadastro, Status, Tags, Ordem, Periodicidade, Tipo Periodicidade, Dia Semana, Horário para Criação, Dia Início, Período Desde Criação.

Explicando a lógica do banco de dados de cadastros: a idéia era fazer um modelo que não precisasse deixar a pessoa criar quantas propriedades ela quiser, que nem no notion, e sim entender o que elas precisariam em cadastros e fazer isso como base do aplicativo, posso estar errado. Então com tipo de cadastro seria se é uma necessidade ou contribuição, tags é uma hashtag. Status é se algo está tipo ativo ou não, se é necessário ou não, se pode ser oferecido ou não, isso existe para manter o cadastro mas sem excluí-lo quando ele é resolvido temporariamente. Ordem seria um número pra pesssoa ordenar como ela quiser os cards arrastando eles por exemplo, quando estiver vendo num frontend com eles no formato de kanban, os cards ficam mais em cima ou mais embaixo segundo seu número da Ordem. Essa é a parte que torna os cadastros uma criação única.

O resto das propriedades deles garantem uma automatização de re-criação/re-ativação de uma N ou C. A pessoa cria uma necessidade de transporte pro trabalho, e deixa aquilo ser criado todos os dias em um horário. A forma que eu pensei que isso vai ter é com tais propriedades de cadastros: Periodicidade seria um número, o Tipo Periodicidade seria 'dia', 'semana' ou 'mês'. Juntos tu tem '1, Dia' ou '3, Semanas', o Dia Semana para dizer se o cadastro deve ser criado nas terças e sextas por exemplo. Horário criação para dizer se é pra ser criado a cada dois dias às 16:57. Dia início é o que marca a data inicial daquela necessidade, o cálculo feito pela Periodicidade, Tipo Periodicidade e outros é com base no Dia Início, se eu falei que é pra começar a criar uma Necessidade Interna de tomar banho todos os dias, começando uma semana antes do natal, algo no backend vai checar isso todo segundo, minuto, sei lá e se for uma semana antes do natal, no horário especificado, a Necessidade Interna "Tomar Banho" será colocada como Existente/Ativo no Status (daí a pessoa pode clicar numa caixinha do frontend e modificar o Status pra Inativo; tomara que la tenha tomado o banho). E por último o Período Desde Criação, que é um contador, se pedi que a cada seis dias o Status de algo deve ficar como Ativo, todo dia o contador deve saber que um dia se passou e aumentar um.


Contas criadas em um servidor ou através de selfhost devem ter um id, idContasSeguindo, idContasSeguidores, foto de capa, foto de perfil
