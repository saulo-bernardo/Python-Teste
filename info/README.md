
# SAULO | **TRATAMENTO DE DADOS**

Uma breve descrição sobre o que esse projeto faz e para quem ele é

## 🔎Passo 1: Entender os Dados:

Conhecer a Fonte dos Dados:
Identifique de onde os dados vieram.
Compreenda o propósito dos dados e como foram coletados.
Links de referências para as bibliotecas
Pandas
Numpy
Seaborn
Matplotlib
Plotly

**Carregar as bibliotecas:**

* import pandas as pd
* import numpy as np
* import seaborn as sns
* import matplotlib.pyplot as plt
* import plotly.express as px

**Carregar os dados:**

Carregar arquivo CSV

     df = pd.read_csv(‘caminho do arquivo.csv, delimiter=';')


**Carregar arquivo EXCEL**

     df_excel = pd.read_excel("caminho/para/arquivo.xlsx", sheet_name="Planilha1")


**Carregar dados de uma URL**

     url = "https://exemplo.com/dados.csv" 
     df_url = pd.read_csv(url)
     print(df_url.head())
	
**Carregar arquivos do computador local**

	     from google.colab import files
	     uploaded = files.upload()


## 💹Passo 2: Visualização de Dados
**Informações gerais sobre o DataFrame**

     df.info()

**Exibir o shape (número de linhas e colunas)**

     df.shape()

**Exiba as primeiras linhas do dataset para ter uma visão geral**

    df.head()

**Obtenha um resumo estatístico dos dados**

     df.describe()

**Localizar um ou mais colunas**

     df['Cidade'] 
     df['Cidade', ‘Nome’] 
     df.loc[df['Cidade'] == 'Recife'] #Localizar dados dentro da coluna

## 📊Passo 3: Analisar a Qualidade dos Dados
**Identificar Dados Faltantes:**

Verifique se há valores ausentes:

     df.isnull()

**Determine a proporção de dados faltantes em cada coluna.**

     df.isnull().sum()

**Identificar Dados Duplicados:**

     df.duplicated()
## 🧹Passo 4: Limpar os Dados
**Tratar Dados Faltantes:**

**Remova linhas ou colunas com muitos dados faltantes **

     df.dropna(inplace=True)

**Impute valores faltantes com a média, mediana ou moda**

     df[‘Idade’].fillna(df[‘Idade’].mean(), inplace=True

     df[‘Salário’].fillna(df[‘Salário’].median(), inplace=True

     df[‘Departamento’].fillna(df[‘Departamento’].mode(), inplace=True

**Substitua os valores nulos por "não informado"**

     df['Nome'].fillna('não informado', inplace=True) 
     df['Departamento'].fillna('não informado', inplace=True)
**Remover Dados Duplicados:**

**Drope as colunas que não são necessárias**

     df.drop(columns=['Nome_da_Coluna'], inplace=True)

**Drope as linhas com valores nulos**

     df.drop_duplicates(inplace=True)

**Deletando linhas com dados nulos na coluna 'Idade'**

     df = df.dropna(subset=['Idade'])
**Corrigir Tipos de Dados:**

**Verifique e converta os tipos de dados conforme necessário**

     df['Salário'] = df['Salário'].astype('float', '{:2f}.formato()')
**Certifique-se de que as datas estão no formato de data, números estão no formato numérico, etc.**

     df['data'] = pd.to_datetime(df['data'])

**Tratar Outliers:**

Dependendo do contexto, você pode remover outliers ou transformá-los (por
exemplo, usando log transformação).

     df = df[df['coluna_numerica'] < df['coluna_numerica'].quantile(0.99)]
## 📟Passo 5: Padronizar e Normalizar os Dados
**Padronizar Formatos:**

**Padronize formatos de texto (conversão para minúsculas/maiúsculas).**

df['nome'] = df['nome'].str.lower()

df['nome'] = df['nome'].str.strip()

**Padronize formatos de data e hora.**

df['data'] = pd.to_datetime(df['data'], format='%d/%m/%Y')
## ✍️Passo 6: Documentar o Processo
**Documentar as Alterações:**

Mantenha um registro de todas as alterações feitas nos dados.
Documente as razões para cada passo de limpeza e transformação.
Salvando o DataFrame Limpo:

df.to_csv('caminho/para/arquivo_limpo.csv', index=False)

