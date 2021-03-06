# Como um tester deve lidar com bugs em produção?

Acredito que a frase que um testador, no seu início de carreira, mais teme é: “quebrou em produção”, de fato não é nada bom! Porem, ao passar do tempo aprendemos a lidar com a frase e, além disso, aprendemos que isso é inevitável, cedo ou tarde irá quebrar em produção, por isso existimos, para minimizar os impactos dos bugs e diminuir os riscos de lançamentos. *A inevitabilidade de ocorrer bugs em produção é um dos fundamentos de teste de software.*

> Ninguém na breve história da computação jamais escreveu um software perfeito. É improvável que você seja o primeiro. - Andy Hunt

#### Mas como devemos reagir a bugs em produção?

Quando encontramos um bug em produção muitas dúvidas podem surgir:

* Quem devo comunicar?
* Devo adicionar o bug report na sprint backlog como prioridade máxima?
* Devo adicionar o bug report no product backlog para ser priorizado pelo Product Owner?
* Esperamos os clientes abrirem um chamado?
* Devemos fazer rollback do código?

Essas e muitas outras dúvidas podem surgir, mas, devemos manter a calma e pensar de maneira sistemática.

#### Erros são bem-vindos, desde que possamos aprender com eles.

Encarre os bugs que ocorrem em produção como uma oportunidade de fazer melhor! É maravilhoso quando encontramos os bugs no ambiente de sandbox e podemos reportar-lós no backlog e avisar os stakeholders, no entanto, já sabemos que exceções ocorrem e devemos estar preparados para solucionar com agilidade e destreza.

É compreensível que seja difícil pensar que bugs são oportunidades quando você ocupa um cargo de importância na organização, como, por exemplo, Project Manager ou Product Owner, pois sabemos que há custos para realizar correções, além de gerar insatisfação de clientes, podendo até ter o seu desfecho em disputas judiciais gerando multas contratuais e até o cancelamento do desenvolvimento do projeto, mas, não há outra forma de pensar a não ser essa sem deixar o ambiente tóxico.

Quando bugs ocorrem em produção, algumas vezes o peso cai nas costas do time de testes, mas devemos lembrar que a responsabilidade da qualidade do produto não é de responsabilidade inteira dos testadores e sim do time em sua totalidade e inclusive da alta direção (ISO 9001 de 2015); antes de chegar em produção temos algumas fases, como, por exemplo: levantamento de requisitos, análise de requisitos, prototipação, design da arquitetura, desenvolvimento, testes, implantação e treinamento. É completamente injusto, para não falar covarde, que a responsabilidade caia por completo sobre as costas do time de teste, afinal, somos um time, não? 

#### O objetivo de encontrar bugs não é culpar ninguém, mas melhorar a qualidade do produto.

Quando é apontado o dedo ao time de teste e dito: é culpa de vocês. Esta situação, além de deixar o ambiente tóxico, é sem dúvida prejudicial à saúde mental, desanimando e fazendo com que os testadores duvidem de sua própria capacidade. É simplesmente contraproducente, devemos focar no que deve ser realizado para solucionar o problema e evitar que se repita no futuro e não quem é responsável pelo que aconteceu.

Quando estamos trabalhando em uma empresa com uma cultura que não dê o devido valor aos testes, devemos jogar com os números ao nosso favor, podemos criar uma apresentação para a equipe de desenvolvimento mostrando alguns números de como a implementação de teste diminui a quantidade de bugs reportados em produção em empresas do mesmo porte e/ou segmento, desta forma comprovamos por A + B que as coisas tendem a melhorar no médio/longo prazo se adicionarmos um fluxo de testes robusto com pipelines de CI/CD, análise estática de código, build, etc. Isto não irá somente diminuir o número de bugs críticos que poderiam ser evitados antes mesmo da funcionalidade chegar até as mãos de um testador como também vai diminuir a dor de cabeça da equipe e o time não irá precisar fazer horas extras para apagar incêndio. Se você já trabalha algum tempo na organização elabore um relatório de quantos bugs já foram reportados e qual seria o impacto desses bugs caso acontecesse em produção.

Uma boa estratégia de teste é fundamental para o sucesso de um produto, além da estratégia é vital que os testadores e desenvolvedores tenham uma boa noção em técnicas de testes de software, óbvio que o testador deve ter um conhecimento técnico mais aprofundado que o desenvolvedor. Há uma lenda que diz que desenvolvedores não sabem e/ou não devem testar, que os testes devem ficar apenas na mão dos testadores, isso é pura balela, desenvolvedor é, querendo ou não, um prestador de serviço e é fundamental que este prestador de serviço saiba garantir a integridade daquilo que entrega. Óbvio que por mais que o desenvolvedor teste, quem deve dar o aval sobre a qualidade da tarefa desenvolvida deve ser um testador.

Por mais que pareça que seja um retrabalho, isso ajuda a fortalecer a empatia entre as equipes, além disso, quando o time fica maduro o suficiente e temos testes automatizados validando as entradas possíveis os testadores não precisa alocar a grande parte do seu tempo testando entrada com múltiplos 9 para avaliar se a aplicação quebrará por coisa que poderia ter sido prevenida antes que a tarefa chegasse até a fila de teste e a detecção de bugs de maneira antecipada por meio de uma pipeline facilitará correção, pois o código ainda está fresco na mente do desenvolvedor. Quando temos o cenário em que o testador não precise alocar muito tempo em smoke testing, este pode estar implementando testes mais complexo e robusto na aplicação, de modo a realmente avaliar como a aplicação se comporta com um cenário desenhado especificamente para quebrar a aplicação.

Alguns testadores, incluindo o meu início como testador, ficam frustrados quando seus colegas, ou ele próprio vai testar uma parte do sistema que já havia sido validada anteriormente e acabam achando novos bugs que não surgiram por novas implementações, elas estavam simplesmente mascaradas até então. Achar bugs em uma segunda bateria de teste ou no teste de regressão é melhor que em produção! Penso que nem precisaria falar isso, mas infelizmente isso ocorre e devemos tratar do assunto. Ninguém é perfeito, incluindo o software. 

#### Cabeças diferentes, já passaram por situações diferentes por consequência pensam diferente, consequentemente testam diferente e acham bugs diferentes.

Quando identificar um bug nunca fique omisso para passar uma falsa ideia do produto está seguro, essa atitude demostra imaturidade, reporte-o e o adicione ao seu conjunto de testes para que não volte a aparecer. Se, por algum motivo, você não se sente confortável em comunicar o seu time que há um bug em produção por conta da reação dos integrantes você deveria repensar sobre a empresa que você trabalha, talvez, a cultura não seja das melhores.

Além de solucionar o problema, procure a causa raiz, o que originou o bug, para chegarmos a causa raiz podemos trabalhar com algumas ferramentas da qualidade, como, por exemplo, os 5 porquês. Investigue até ter uma resposta sobre o que ocasionou o bug.

Provável que para testadores sênior já seja comum, mas para nós meros mortais devemos além de testar somente feature, devemos nós certificarmos que seja possível realizar um rollback no banco de dados sem causar estragos as informações que já estavam lá anteriormente. 

É essencial que quando a aplicação for para produção podemos rastrear as falhas ocorridas antes mesmo dos usuários reportar, para isso temos [ferramentas de monitoramento e rastreamento de erros](https://flatlogic.com/blog/10-best-error-monitoring-and-error-tracking-tools/) que nos auxiliam no processo.

#### Então, resumidamente o que devemos fazer para lidar com bugs em produção é:
1. Saber que cedo ou tarde irá ocorrer bugs em produção.
2. Conscientizar o time a respeito da importância dos testes.
3. Caso não haja, implementar a cultura de teste.
4. Mostre os resultados obtidos através dos testes.
5. Erros são bem-vindos, desde que possamos aprender com eles.
6. Certifique-se que o rollback irá funcionar quando necessário.

É da essência niilista do ser humano maximizar as coisas ruins que acontecem, não se deixe abater, continue se profissionalizando e acredite no seu trabalho.
