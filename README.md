# MÓDULO 14 - Pré-processamento de Dados para Análise de Churn

Este projeto é focado no pré-processamento de dados como parte de um exercício de análise de churn. Estamos trabalhando com um conjunto de dados de telecomunicações que inclui informações de clientes para serviços de internet, telefone e TV. O principal objetivo é limpar e preparar o dataset para análises futuras, com foco na previsão de churn (rotatividade de clientes).

## Objetivo

- Realizar a limpeza e o pré-processamento dos dados como a etapa inicial antes da modelagem.
- Entender a estrutura dos dados e lidar com valores ausentes.
- Preparar o dataset para a análise futura de churn.

## Conjunto de Dados

O dataset contém várias informações sobre os clientes, como uso de serviços de internet, telefone e TV, tipos de contrato, métodos de pagamento e se o cliente cancelou os serviços.

### Colunas dos Dados:
- **customerID**: ID único para cada cliente.
- **Genero**: Gênero do cliente.
- **Idoso**: Se o cliente é idoso (Sim = 1 | Não = 0).
- **Casado**: Se o cliente é casado ou não.
- **Dependents**: Se o cliente tem dependentes.
- **Tempo_como_Cliente**: Duração do relacionamento do cliente com a empresa (em meses).
- **PhoneService**: Se o cliente contratou o serviço de telefone.
- **Servico_Internet**: Tipo de serviço de internet contratado pelo cliente.
- **Servico_Seguranca**: Se o cliente contratou o serviço de segurança.
- **Suporte_Tecnico**: Se o cliente utilizou o suporte técnico.
- **StreamingTV**: Se o cliente possui um serviço de streaming de TV.
- **Tipo_Contrato**: Tipo de contrato (mensal, anual, etc.).
- **PaymentMethod**: Método de pagamento usado pelo cliente.
- **Pagamento_Mensal**: Valor pago mensalmente pelo cliente.
- **Total_Pago**: Valor total pago pelo cliente à empresa.
- **Churn**: Coluna mais importante, indicando se o cliente cancelou os serviços (Sim ou Não).

## Etapas

### 1. Carregamento dos Dados e Verificação dos Tipos
A primeira etapa foi carregar o conjunto de dados e verificar se os tipos de dados estavam corretos para cada coluna. Utilizei a função `pd.info()` para inspecionar os tipos e verificar se era necessário algum ajuste.

```python
df = pd.read_csv("CHURN_TELECON_MOD08_TAREFA.csv", delimiter=';')
df.info()
```

### 2. Tratamento de Dados Faltantes
Identifiquei os valores faltantes no conjunto de dados e calculei a porcentagem de dados ausentes para cada coluna.

```python
(df.isnull().sum()/len(df))*100
```

#### Resultado:
| Coluna              | Dados Faltantes (%) |
|---------------------|---------------------|
| customerID          | 0.00                |
| Genero              | 0.48                |
| Idoso               | 0.00                |
| Casado              | 0.00                |
| Dependents          | 0.00                |
| Tempo_como_Cliente  | 0.00                |
| PhoneService        | 59.28               |
| Servico_Internet    | 0.00                |
| Servico_Seguranca   | 0.00                |
| Suporte_Tecnico     | 0.00                |
| StreamingTV         | 0.00                |
| Tipo_Contrato       | 0.00                |
| PaymentMethod       | 0.00                |
| Pagamento_Mensal    | 13.00               |
| Total_Pago          | 0.00                |
| Churn               | 0.20                |

### 3. Limpeza dos Dados
Com base na análise dos dados faltantes, realizei diversas operações de limpeza:
- Linhas com grande porcentagem de dados ausentes foram tratadas, sendo excluídas ou preenchidas com a media.
- A justificativa para a remoção ou retenção de certos dados foi baseada no contexto e importância das variáveis.

### 4. Visualização dos Dados
Utilizei o **Seaborn** para visualizar o dataset limpo e extrair insights de diferentes características.

```python
import seaborn as sns
import matplotlib.pyplot as plt

## Conclusão

Este projeto foi um exercício de pré-processamento e limpeza de dados. Eu:
- Carreguei e inspecionei o conjunto de dados.
- Identifiquei e tratei valores ausentes.
- Preparei o dataset para análises futuras de churn.

