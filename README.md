# Introdução à Ciência de Dados 2025.1

**Grupo:** 
- Daniel Henrique Batista Gomes
- José Alexandre Bezerra de Oliveira
- Josinaldo da Silva Sousa
- Luiz Henrique Santos da Graça
**Projeto:** #02 - Coleta de dados

## Objetivo

Esta fase tem como objetivo coletar e disponibilizar os dados coletados para análise futura.

## Conjunto de Dados Coletados

Este projeto contém dois principais conjuntos de dados relacionados a acidentes de trânsito no Brasil:

### 1. Dataset DATATRAN (Polícia Rodoviária Federal)

Os arquivos `datatran*.csv` contêm dados de acidentes nas rodovias federais brasileiras (BRs) catalogados pela Polícia Rodoviária Federal (PRF) e disponibilizados pelo governo federal através do portal de dados abertos.

**Período coberto:** 2007-2025  
**Fonte:** Portal de Dados Abertos do Governo Federal  
**Frequência de atualização:** Anual

### 2. Dataset RENAEST/Impala (Secretaria Nacional de Trânsito)

Os arquivos `Impala_*.csv` foram coletados do Sistema RENAEST (Registro Nacional de Estatísticas de Trânsito) através do portal de dados do Ministério da Infraestrutura.

**Período coberto:** Outubro de 2021 (dados adicionais de outros períodos serão coletados)  
**Fonte:** https://dados.transportes.gov.br/en/dataset/renaest  
**Frequência de atualização:** Mensal

## Processo de Coleta dos Dados

### DATATRAN (PRF)
1. **Fonte:** Portal de Dados Abertos do Governo Federal
2. **Método:** Download direto dos arquivos CSV anuais
3. **Formato:** CSV com separador ponto e vírgula (;)
4. **Cobertura:** Acidentes em rodovias federais de todo o Brasil

### RENAEST/Impala (SENATRAN)
1. **Fonte:** Portal de dados do Ministério da Infraestrutura
2. **Método:** Download de arquivos ZIP mensais contendo múltiplos CSVs
3. **Formato:** CSV com separador ponto e vírgula (;)
4. **Cobertura:** Acidentes em vias federais, estaduais, municipais e distritais
5. **Status atual:** Dados de outubro/2021 coletados, expansão para outros períodos em andamento

## Descrição das Colunas

### Dataset DATATRAN

| Nome da Coluna | Descrição | Exemplo |
|---|---|---|
| **id** | Identificador único do acidente | 571789.0 |
| **data_inversa** | Data do acidente no formato YYYY-MM-DD | 2024-01-01 |
| **dia_semana** | Dia da semana em que ocorreu o acidente | Segunda |
| **horario** | Horário do acidente no formato HH:MM:SS | 03:56:00 |
| **uf** | Unidade Federativa onde ocorreu o acidente | ES |
| **br** | Número da rodovia federal | 101 |
| **km** | Quilômetro da rodovia onde ocorreu o acidente | 38 |
| **municipio** | Município onde ocorreu o acidente | CONCEICAO DA BARRA |
| **causa_acidente** | Causa principal do acidente | Ultrapassagem Indevida |
| **tipo_acidente** | Tipo/natureza do acidente | Colisão lateral sentido oposto |
| **classificacao_acidente** | Classificação quanto à gravidade | Com Vítimas Fatais |
| **fase_dia** | Período do dia em que ocorreu | Plena Noite |
| **sentido_via** | Sentido da via (crescente/decrescente) | Crescente |
| **condicao_metereologica** | Condições meteorológicas no momento | Céu Claro |
| **tipo_pista** | Tipo da pista (simples/dupla) | Simples |
| **tracado_via** | Características do traçado da via | Reta |
| **uso_solo** | Tipo de uso do solo no local | Não |
| **pessoas** | Total de pessoas envolvidas | 3 |
| **mortos** | Número de óbitos | 0 |
| **feridos_leves** | Número de feridos leves | 0 |
| **feridos_graves** | Número de feridos graves | 1 |
| **ilesos** | Número de pessoas ilesas | 1 |
| **ignorados** | Número de pessoas com estado ignorado | 1 |
| **feridos** | Total de feridos (leves + graves) | 1 |
| **veiculos** | Número de veículos envolvidos | 3 |
| **latitude** | Coordenada de latitude do local | -18.48261 |
| **longitude** | Coordenada de longitude do local | -39.92379 |
| **regional** | Regional da PRF responsável | SPRF-ES |
| **delegacia** | Delegacia da PRF responsável | DEL04-ES |
| **uop** | Unidade Operacional da PRF | UOP02-DEL04-ES |

### Dataset RENAEST/Impala

#### Arquivo: Impala_Acidentes

| Nome da Coluna | Descrição | Exemplo |
|---|---|---|
| **numacidente** | Número identificador único do acidente | 1883985 |
| **chvlocalidade** | Chave da localidade (código composto) | AC12004012018 |
| **datacidente** | Data e hora do acidente | 2018-01-01 00:00:00 |
| **ufacidente** | Unidade Federativa do acidente | AC |
| **anoacidente** | Ano do acidente | 2018 |
| **codigoibge** | Código IBGE do município | 1200401 |
| **diasemana** | Dia da semana | Segunda-feira |
| **fasedia** | Fase do dia | Tarde |
| **tpacidente** | Tipo do acidente | Colisão |
| **condmeteorologica** | Condição meteorológica | Claro |
| **tprodovia** | Tipo de rodovia | Não Informado |
| **condpista** | Condição da pista | Seca |
| **tpcruzamento** | Tipo de cruzamento | Não Informado |
| **tppavimento** | Tipo de pavimento | Asfalto |
| **tpcurva** | Tipo de curva | Não Informado |
| **limvelocidade** | Limite de velocidade | Não Informado |
| **tppista** | Tipo de pista | Não Informado |
| **indguardrail** | Indicador de guard rail | Não Informado |
| **indcantcentral** | Indicador de canteiro central | Não Informado |
| **indacostamento** | Indicador de acostamento | Não Informado |
| **qtdeacidente** | Quantidade de acidentes | 1 |
| **qtdeferidosilesos** | Quantidade de feridos e ilesos | 2 |
| **qtdeobitos** | Quantidade de óbitos | 0 |
| **qtdeenvolvidos** | Quantidade total de envolvidos | 2 |

#### Arquivo: Impala_Localidade

| Nome da Coluna | Descrição | Exemplo |
|---|---|---|
| **chvlocalidade** | Chave da localidade | MA21004772021 |
| **anoreferencia** | Ano de referência | 2021 |
| **regiao** | Região do Brasil | Nordeste |
| **uf** | Unidade Federativa | MA |
| **codigoibge** | Código IBGE do município | 2100477 |
| **municipio** | Nome do município | Alto Alegre do Pindaré |
| **regiaometropolitana** | Região metropolitana | Não |
| **qtdehabitantes** | Quantidade de habitantes | 32114 |
| **frotatotal** | Frota total de veículos | 3711 |
| **frotacirculante** | Frota circulante de veículos | 2062 |

#### Arquivo: Impala_TipoVeiculo

| Nome da Coluna | Descrição | Exemplo |
|---|---|---|
| **numacidente** | Número do acidente | 2199093 |
| **tipoveiculo** | Tipo do veículo envolvido | Automóvel |
| **indveicestrangeiro** | Indicador se é veículo estrangeiro | Não Informado |
| **qtdeveiculos** | Quantidade de veículos deste tipo | 1 |

#### Arquivo: Impala_Vitimas

| Nome da Coluna | Descrição | Exemplo |
|---|---|---|
| **numacidente** | Número do acidente | 1883985 |
| **chvlocalidade** | Chave da localidade | AC12004012018 |
| **datacidente** | Data do acidente | 2018-01-01 00:00:00 |
| **ufacidente** | UF do acidente | AC |
| **anoacidente** | Ano do acidente | 2018 |
| **faixaidade** | Faixa etária da vítima | Entre 30 e 34 anos |
| **genero** | Gênero da vítima | Masculino |
| **tpoenvolvido** | Tipo de envolvimento | Motorista |
| **gravidadelesao** | Gravidade da lesão | Não Informado |
| **equipseguranca** | Equipamento de segurança | Não Informado |
| **indmotorista** | Indicador se é motorista | Sim |
| **suspalcool** | Suspeita de álcool | Não Informado |
| **qtdeacidente** | Quantidade de acidentes | 1 |
| **qtdeenvolvidos** | Quantidade de envolvidos | 1 |
| **qtdeobitos** | Quantidade de óbitos | 0 |
| **qtdeferidosilesos** | Quantidade de feridos e ilesos | 1 |

## Estatísticas dos Datasets

### DATATRAN
- **Total de arquivos:** 19 (2007-2025)
- **Exemplo de volume:** datatran2024.csv com 73.157 registros
- **Cobertura geográfica:** Rodovias federais de todo o Brasil
- **Granularidade:** Por acidente individual

### RENAEST/Impala
- **Acidentes:** 3.190.831 registros
- **Localidades:** 22.281 registros
- **Tipos de Veículo:** 3.751.358 registros
- **Vítimas:** 4.951.738 registros
- **Cobertura geográfica:** Vias federais, estaduais, municipais e distritais
- **Período atual:** Outubro de 2021

## Próximos Passos

1. **Integração:** Desenvolver scripts para integração e harmonização dos datasets
2. **Análise exploratória:** Realizar análise estatística descritiva dos dados
3. **Visualização:** Criar dashboards e visualizações para análise dos padrões de acidentes
5. **Modelagem:** Identificar fatores de risco e propor soluções baseadas na conclusão da pesquisa

## Observações Técnicas

- Todos os arquivos CSV utilizam ponto e vírgula (;) como separador
- Coordenadas geográficas estão no sistema WGS84
- Alguns campos podem conter valores "Não Informado" ou estar vazios
- Os datasets RENAEST possuem estrutura relacional através do campo `numacidente`
- Recomenda-se validação e limpeza dos dados antes de análises estatísticas

