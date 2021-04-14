# Projeto Impacto da pandemia de Covid-19 sobre o tratamento do câncer de mama no SUS

# Project Impact of the Covid-19 pandemic on the treatment of breast cancer in SUS

# Apresentação

O presente projeto foi originado no contexto das atividades da disciplina de pós-graduação [*Ciência e Visualização de Dados em Saúde*](https://github.com/datasci4health/home), oferecida no primeiro semestre de 2021, na Unicamp.

| Nome   | RA    | Especialização |
| ------ | ----- | -------------- |
| Annemeri Livinalli | 226976 | Saúde |
| Kevin Martins Araújo | 223971 | Computação |
| Luísa Von Zuben Veçoso | 156457 | Saúde |
| Rafael Duarte Paes | 224242 | Saúde |

# Descrição Resumida do Projeto
A COVID-19, doença causada pelo vírus SARS-CoV-2, emergiu na China no final de 2019. Com o número crescente de casos avançando globalmente, em março de 2020 a Organização Mundial de Saúde reconheceu a pandemia [1] e instituiu medidas preventivas contra a disseminação, incluindo distanciamento associado à medidas de higiene [2]. A doença, transmitida por via respiratória [3],  causou até abril de 2021, mais de 2,9 milhões de óbitos em todo o mundo [4] e mais de 340 mil no Brasil [5]. 
Dentre os diversos impactos da pandemia observados globalmente, o medo da COVID-19 resultou em uma redução na demanda por atendimento médico em situações consideradas não urgentes, incluindo exames diagnósticos de câncer e o próprio tratamento, incluindo quimioterapia, radioterapia ou cirurgia [6]. No Brasil, os diagnósticos de câncer reduziram de 24,3% (região Norte) a 42,7% (região Nordeste), com média de 35,5% no país, correspondentes a 15 mil casos não diagnosticados por mês no período de janeiro a agosto de 2020 [7]. O tratamento dos pacientes com câncer também reduziu em alguns países, tornando-se uma preocupação desde o início da pandemia [6]. 

Neste contexto, buscaremos por dados que apontem  o impacto da pandemia no tratamento de mulheres com idade igual ou superior a 60 anos com câncer de mama no Brasil. Faremos uma comparação do número de procedimentos relacionados aos tratamentos (quimioterapia, radioterapia ou cirurgia) realizados durante a pandemia em 2020 com a quantidade realizada no mesmo período em anos anteriores.

Link para vídeo de apresentação da proposta do projeto: https://drive.google.com/file/d/1w6-9AbcpNAfgPTRWBStaWuJMb-mndVEQ/view?usp=sharing 

# Pergunta de Pesquisa
Qual o impacto da pandemia de Covid-19 no tratamento do câncer de mama não metastático, em mulheres acima dos 60 anos, atendidas no Sistema Único de Saúde (SUS).

# Bases de Dados
Para o desenvolvimento do projeto foram utilizadas a base de dados fornecido pelo Departamento de Informática do Sistema Único de Saúde (DATASUS) e a base de dados do Coronavírus Brasil que disponibiliza o número de casos de Covid-19.


| Base de Dados | Localização | Descrição |
|--|--|--|
| SIASUS | [*DATASUS/SIASUS*](http://www2.datasus.gov.br/DATASUS/index.php?area=0901&item=1&acao=22&pad=31655) | Arquivos com informações referente aos atendimentos ambulatoriais. |
| SIH/SUS | [*DATASUS/SIHSUS*](http://www2.datasus.gov.br/DATASUS/index.php?area=0202&id=11633) | Arquivos com informações de cirurgias. |
|COVID-19 | [*CoronavírusBrasil*](https://covid.saude.gov.br/) | Site com painel interativo com dados da Covid-19 informados pelo Ministério da Saúde|


# Metodologia

Com base nas informações de acesso público disponibilizadas pelo Departamento de Informática do Sistema Único de Saúde (DATASUS), analisaremos os dados mensais de produção ambulatorial e hospitalar relacionados aos procedimentos de tratamento do câncer de mama, por região de atendimento, no período de Janeiro de 2015 a Dezembro de 2020. Buscaremos estes dados no sistema TabNet, que é um programa do DATASUS em que os dados são tabulados e disponibilizados em ambiente internet, com auxílio da ferramenta TabWin, que permite o cruzamento destes dados. 

Serão incluídos os dados de mulheres com idade ≥ 60 anos, com diagnóstico de câncer de mama não metastático, atendidas no Sistema Único de Saúde (SUS).

Com base nas diretrizes diagnósticas e terapêuticas do carcinoma de mama, consultamos os códigos dos procedimentos no sistema de gerenciamento da tabela de procedimentos, medicamentos e OPM do SUS (SIGTAP). Serão obtidos os dados dos seguintes procedimentos:
* monoquimioterapia ou poliquimioterapia
* hormonioterapia
* radioterapia de mama
* mastectomia
* ressecção de lesão não palpável de mama
* segmentectomia/quadrantectomia/setorectomia de mama

O número de casos acumulados de Covid-19 por região será obtido na plataforma [*CoronavírusBrasil*](https://covid.saude.gov.br/).

Em relação ao câncer, consideraremos as seguintes variáveis: idade, localização geográfica (região de tratamento), tipo de tratamento. Em relação à Covid-19 consideraremos as mesmas variáveis, exceto o tipo de tratamento.

A frequência de cada conjunto de procedimentos (quimioterapia, hormonioterapia, radioterapia e cirurgia) será apresentada como média e desvio padrão, por ano e região. Se nós observarmos redução na frequência de tratamento em 2020 em relação aos anos anteriores, nós iremos verificar a região com maior redução e a frequência de casos de Covid-19, para estabelecer uma possível relação entre a pandemia e a redução no número de procedimentos.

Este estudo será conduzido com base no modelo de processo *Knowledge Discovery in Databases* (KDD) e suas respectivas etapas descritas por Fayyad e col [8]. Iniciaremos pela seleção das bases de dados que serão utilizadas. Após, as bases de dados serão pré-processadas e tratadas, com o objetivo de entender os dados obtidos, remover dados errados, nulos, irrelevantes ou considerados como outliers. Para a manipulação, cruzamento e análise das bases de dados iremos utilizar a linguagem de programação Python, em alguns momentos será utilizado o programa Jupyter Notebook para auxiliar no desenvolvimento dos códigos que serão criados para o desenvolvimento do projeto. Também será utilizado a ferramenta Orange3 Data Mining e WEKA, que são ferramentas que auxiliam na análise e mineração dos dados.


# Ferramentas
| Ferramenta | Endereço na Web | Descrição
|--|--|--|
| Python |[*Python.org*](https://www.python.org/)| Linguagem de programação.  |
| Google Colab |[*Google Colab*](https://colab.research.google.com)| Ferramenta que permite a criação e edição de notebooks pelo navegador sem necessidade de instalar qualquer programa no computador do usuário exceto o navegador web|
| Tabwin |[*DATASUS/TABWIN*](https://datasus.saude.gov.br/transferencia-de-arquivos/)|Ferramenta para utilizar da base de dados fornecido pelo DATASUS |
| Tabnet |[*DATASUS/TABNET*](https://datasus.saude.gov.br/informacoes-de-saude-tabnet/)| Sistema que permite a extração de base de dados fornecidos pelo DATASUS | 
| Jupyter |[*Projeto Jupyter*](https://jupyter.org/)| Ferramenta que permite a criação e edição de notebooks em navegadores web|
| Orange | [*Orange Data Mining*](https://orangedatamining.com/) | É uma ferramenta open source de visualização de dados, aprendizado de máquina e mineração de dados. | 


# Cronograma

| Atividades | 1ª Semana 05/04 | 2ª Semana 11/04 | 3ª Semana 18/04 | 4ª Semana 25/04 | 5ª Semana 02/05 | 6ª Semana 09/05 | 7ª Semana 16/05 | 8ª Semana 23/05 |
|--|--|--|--|--|--|--|--|--|
Definição do Projeto            |X|X| | | | | | |
Analise da Base de Dados        | |X|X| | | | | | 
Tratamento da Base de Dados     | |X|X|X| | | | |
Definição de Modelos e métricas | | |X|X|X|X| | |
Validação de Modelos            | | | |X|X|X|X| |
Análise dos Resultados          | | | | | |X|X| |
Conclusão                       | | | | | |X|X|X|



# Referências
[1] World Health Organization. Press Conference on 11/03/2020. Acesso em 09/04/2021. Disponível em: https://www.who.int/director-general/speeches/detail/who-director-general-s-opening-remarks-at-the-media-briefing-on-covid-19---11-march-2020

[2] ---. Press Conference on 13/03/2020. Acesso em 09/04/2021. Disponível em: https://www.who.int/director-general/speeches/detail/who-director-general-s-opening-remarks-at-the-mission-briefing-on-covid-19---13-march-2020

[3] Kamps BS, Hoffmann C. Covid reference. Steinhauser Verlag, 2021. 6ed. Acesso em 09/04/2021. Disponível em: www.covidreference.com

[4] World Health Organization. WHO Coronavirus dashboard. Acesso em 09/04/2021. Disponível: https://covid19.who.int/

[5] CoronavirusBrasil. Painel Covid-19. Acesso em 09/04/2021. disponível em: https://covid.saude.gov.br/

[6] Jindal V, Sahu KK, Gaikazian S, Siddiqui AD, Jaiyesimi I. Cancer treatment during Covid-19 pandemic. Medical Onc 2020; 37: 58.

[7] Marques NP et al. Cancer diagnosis in Brazil in the COVID-19 era. Semin Oncol 2020; 10.1053/j.seminoncol.2020.12.002 

[8] Fayyad U, Piatetsky-Shapiro G, Smyth P. Knowledge Discovery and Data Mining: Towards a Unifying Framework. KDD 96, 82-88

