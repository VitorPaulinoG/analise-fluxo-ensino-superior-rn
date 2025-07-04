## DataFrame
### Selecionar Colunas
```py
colunas_selecionadas = [
    'Grau Acadêmico', 
    'Modalidade de Ensino', 
    'Nome da Grande Área do Curso segundo a classificação CINE BRASIL', 
    'Ano de Ingresso', 
    'Quantidade de Ingressantes no Curso', 
    'Quantidade de Concluintes no Curso no ano de referência', 
    'Quantidade de Desistência no Curso no ano de referência'
]
df = df[colunas_selecionadas]
```

### Parsing de Valores de uma Coluna
```py
pd.to_numeric(df['Quantidade de Ingressantes no Curso'], errors='coerce').astype('Int64')
```
>[!obs] `errors='coerce'` faz com que um valor que não pode ser convertido seja tranformado em null

### Métodos Utilitários
#### Tamanho 
`size()`
#### Soma
`sum()`
#### Máximo
`max()`
### Média
`mean()`
#### Mínimo
`min()`
#### Mediana
`median()`
#### Moda
`mode()`
#### Quartil
`quantile()`
#### Variância
`var()`
#### Desvio Padrão
`std()`
#### Covariância
`cov()`
[LINK](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.cov.html)
#### Correlação
`corr()`
[LINK](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.corr.html)
#### Quantidade de Distintos
`nunique()`
#### Descrição Resumida dos Dados
`describe()`
### Agrupamento
```py
df.groupby('Nome da Grande Área do Curso segundo a classificação CINE BRASIL')['Quantidade de Concluintes no Curso no ano de referência'].agg(lambda x: x.mode())
```