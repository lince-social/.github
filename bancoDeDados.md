Versão Básica Lince:

Tabela conta:
- id | CP (chave primária)
- nomeUsuário
- senha

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


Fiz uma normalização do banco de dados que eu acho que funcionaria pra primeira versão da lince, só com criação de contas, cadastro de necessidades e contribuições, chat pra conversar e realizar a interação lince e com frontend a gente bota um botão que quando as duas contas envolvidas clicam nele, o status da contribuição e necessidade é atualizado, ou só a quantidade. Exemplo: preciso de 10 maçãs, alguem doou 4, nós dois apertamos o botão, o status da contribuição fica como inexistente, pq a maçã foi doada, e o status da necessidade fica ainda como existente, mas agora da quantidade da necessidade como 6

Para fazer um banco de dados da lince é preciso ter a criação de uma conta com poderes administrativos, e uma de usuários, com nome de usuário e senha, podendo criar diferentes perfis para uma conta de usuário. Acho. Dependendo do protocolo utilizado pra troca de informações entre círculos lince/servidores lince e formas de ter contas com usuários e perfis várias formas de modelar o banco de dados vão existir, essa é a versão que eu acho que funcionaria.

O outro banco de dados deve ser para os cadastros que esses usuários fizeram, seja em nececidades (N) ou contribuições (C) . Qualquer cadastro lince deverá ter diversas propriedades, não necessariamente preenchidas sempre, que permitem usuários criar qualquer N ou C.

Uma sugestão de features desses cadastro é: id, idConta, Título, Descrição, Tipo de Cadastro, Status, Tags, Ordem, Periodicidade, Tipo Periodicidade, Dia Semana, Horário para Criação, Dia Início, Período Desde Criação.

Explicando a lógica do banco de dados de cadastros: a idéia era fazer um modelo que não precisasse deixar a pessoa criar quantas propriedades ela quiser, que nem no notion, e sim entender o que elas precisariam em cadastros e fazer isso como base do aplicativo, posso estar errado. Então com tipo de cadastro seria se é uma necessidade ou contribuição, tags é uma hashtag. Status é se algo está tipo ativo ou não, se é necessário ou não, se pode ser oferecido ou não, isso existe para manter o cadastro mas sem excluí-lo quando ele é resolvido temporariamente. Ordem seria um número pra pesssoa ordenar como ela quiser os cards arrastando eles por exemplo, quando estiver vendo num frontend com eles no formato de kanban, os cards ficam mais em cima ou mais embaixo segundo seu número da Ordem. Essa é a parte que torna os cadastros uma criação única.

O resto das propriedades deles garantem uma automatização de re-criação/re-ativação de uma N ou C. A pessoa cria uma necessidade de transporte pro trabalho, e deixa aquilo ser criado todos os dias em um horário. A forma que eu pensei que isso vai ter é com tais propriedades de cadastros: Periodicidade seria um número, o Tipo Periodicidade seria 'dia', 'semana' ou 'mês'. Juntos tu tem '1, Dia' ou '3, Semanas', o Dia Semana para dizer se o cadastro deve ser criado nas terças e sextas por exemplo. Horário criação para dizer se é pra ser criado a cada dois dias às 16:57. Dia início é o que marca a data inicial daquela necessidade, o cálculo feito pela Periodicidade, Tipo Periodicidade e outros é com base no Dia Início, se eu falei que é pra começar a criar uma Necessidade Interna de tomar banho todos os dias, começando uma semana antes do natal, algo no backend vai checar isso todo segundo, minuto, sei lá e se for uma semana antes do natal, no horário especificado, a Necessidade Interna "Tomar Banho" será colocada como Existente/Ativo no Status (daí a pessoa pode clicar numa caixinha do frontend e modificar o Status pra Inativo; tomara que la tenha tomado o banho). E por último o Período Desde Criação, que é um contador, se pedi que a cada seis dias o Status de algo deve ficar como Ativo, todo dia o contador deve saber que um dia se passou e aumentar um.


Contas criadas em um servidor ou através de selfhost devem ter um id, idContasSeguindo, idContasSeguidores, foto de capa, foto de perfil
