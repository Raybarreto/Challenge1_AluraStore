### 📊 Análise de Dados de Vendas de Lojas
## 🛒 Challenge - Alura Store - Análise de Lojas

Este projeto realiza uma análise exploratória de dados de vendas de quatro lojas, utilizando a biblioteca Pandas para manipulação de dados e Matplotlib para visualização. O objetivo é fornecer insights sobre o faturamento, as vendas por categoria, a média de avaliação dos clientes, os produtos mais e menos vendidos e o frete médio de cada loja.


## 🔍 Visão Geral do Projeto

O script Python (`.ipynb `) realiza as seguintes etapas:

1.  **Importação de Dados:** Carrega os dados de vendas de cada loja a partir de arquivos CSV hospedados no GitHub.
2.  **Análise de Faturamento:** Calcula o faturamento total de cada loja, o faturamento médio e visualiza a distribuição do faturamento entre as lojas através de um gráfico de barras.
3.  **Análise de Vendas por Categoria:** Combina os dados de todas as lojas, calcula o faturamento por categoria em cada loja e apresenta essa informação em um gráfico de barras lado a lado.
4.  **Análise da Média de Avaliação:** Calcula a média das avaliações de compra para cada loja e exibe essa informação em um gráfico de barras.
5.  **Análise de Produtos Mais e Menos Vendidos:** Identifica o produto com a maior e a menor quantidade vendida em cada loja.
6.  **Análise de Frete Médio:** Calcula o custo médio de frete para cada loja.
7.  **Análise Geográfica das Vendas:** Utiliza as coordenadas de latitude e longitude presentes nos dados para visualizar a distribuição geográfica das vendas, o faturamento por localização e a distribuição das avaliações.


## ⬇️ Instalação

Para executar este projeto, você precisará ter o Python instalado em seu ambiente. Além disso, as seguintes bibliotecas são necessárias:

-   **Pandas**: Para manipulação e análise de dados tabulares.
-   **Matplotlib**: Para criação de gráficos e visualizações.
-   **NumPy**: Embora não explicitamente importado no código fornecido, o Matplotlib frequentemente o utiliza internamente para operações numéricas.

Você pode instalar essas bibliotecas utilizando o pip, o gerenciador de pacotes do Python. Abra seu terminal ou prompt de comando e execute o seguinte comando:
```bash
pip install pandas matplotlib
````


## 📌 Dependências
As seguintes bibliotecas Python são dependências deste projeto:

* pandas (>= 1.0.0): Utilizada para leitura e manipulação dos dados das lojas a partir de arquivos CSV hospedados em URLs.
* matplotlib (>= 3.0.0): Empregada para gerar gráficos de barras que visualizam o faturamento por loja, as vendas por categoria e a média de avaliação das lojas.
* numpy (>= 1.18.0): Usada internamente pelo Matplotlib para cálculos numéricos, como o cálculo da média de faturamento para a linha de referência no gráfico.


## ⚙️ Execução no Google Colab
O Google Colab é um ambiente Jupyter Notebook hospedado na nuvem que permite executar código Python sem a necessidade de configuração local. Para executar este projeto no Colab, siga estes passos:
1.	Abra o Google Colab: Acesse https://colab.research.google.com/ no seu navegador.
2.	Crie um novo notebook: Clique em "Novo notebook" no canto inferior direito da tela.
3.	Copie e cole o código: Copie todo o código Python fornecido e cole em uma célula de código no seu notebook do Colab.
4.	Execute as células: Execute as células de código sequencialmente, clicando no botão de "play" (executar) ao lado de cada célula ou pressionando Shift + Enter.
O Colab já possui as bibliotecas Pandas e Matplotlib pré-instaladas, então você não precisará executar o comando !pip install novamente, a menos que necessite de versões específicas ou outras bibliotecas adicionais. A linha !pip install matplotlib no código é redundante no ambiente Colab padrão.


### 💡 Explicação do Código
O código Python realiza as seguintes etapas de análise:

1.  Importação dos Dados:
```bash
import pandas as pd


url = "[https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science/refs/heads/main/base-de-dados-challenge-1/loja_1.csv](https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science/refs/heads/main/base-de-dados-challenge-1/loja_1.csv)"
url2 = "[https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science/refs/heads/main/base-de-dados-challenge-1/loja_2.csv](https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science/refs/heads/main/base-de-dados-challenge-1/loja_2.csv)"
url3 = "[https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science/refs/heads/main/base-de-dados-challenge-1/loja_3.csv](https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science/refs/heads/main/base-de-dados-challenge-1/loja_3.csv)"
url4 = "[https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science/refs/heads/main/base-de-dados-challenge-1/loja_4.csv](https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science/refs/heads/main/base-de-dados-challenge-1/loja_4.csv)"

loja = pd.read_csv(url)
loja2 = pd.read_csv(url2)
loja3 = pd.read_csv(url3)
loja4 = pd.read_csv(url4)

loja.head()

````

* Importa a biblioteca Pandas, essencial para trabalhar com DataFrames (estruturas de dados tabulares).
* Define URLs para os arquivos CSV contendo os dados de cada loja.
* Utiliza a função pd.read_csv() para ler os dados de cada URL e armazená-los em DataFrames separados (loja, loja2, loja3, loja4).
* loja.head() exibe as primeiras linhas do DataFrame da loja_1, fornecendo uma visão inicial dos dados.


2. 💲 Análise do Faturamento:
```bash
faturamento_loja1 = loja['Preço'].sum()
faturamento_loja2 = loja2['Preço'].sum()
faturamento_loja3 = loja3['Preço'].sum()
faturamento_loja4 = loja4['Preço'].sum()

print(f"Faturamento Loja 1: R${faturamento_loja1:,.2f}")
print(f"Faturamento Loja 2: R${faturamento_loja2:,.2f}")
print(f"Faturamento Loja 3: R${faturamento_loja3:,.2f}")
print(f"Faturamento Loja 4: R${faturamento_loja4:,.2f}")

faturamento_total = faturamento_loja1 + faturamento_loja2 + faturamento_loja3 + faturamento_loja4
faturamento_medio = faturamento_total / 4

print(f"Faturamento médio das lojas: R${faturamento_medio:,.2f}")

!pip install matplotlib
import matplotlib.pyplot as plt
import numpy as np

faturamento = {
    'Loja 1': faturamento_loja1,
    'Loja 2': faturamento_loja2,
    'Loja 3': faturamento_loja3,
    'Loja 4': faturamento_loja4
}

lojas_nomes = list(faturamento.keys())
valores = list(faturamento.values())
faturamento_medio = np.mean(valores)

plt.figure(figsize=(5, 10))
plt.bar(lojas_nomes, valores, color=['#003785', '#1465bb', '#2196f3', '#81c9fa'], width=0.4)
plt.xlabel("Loja")
plt.ylabel("Faturamento (R$)")
plt.title("Faturamento Total por Loja com Média de Faturamento")
plt.grid(axis='y', linestyle='--')
plt.ticklabel_format(style='plain', axis='y')

plt.axhline(faturamento_medio, color='red', linestyle='--', linewidth=1, label=f'Média: R${faturamento_medio:,.2f}')
plt.legend()

plt.show()
```

* Calcula o faturamento total de cada loja somando os valores da coluna 'Preço' em seus respectivos DataFrames.
* Imprime o faturamento de cada loja formatado como moeda brasileira.
* Calcula o faturamento total de todas as lojas e o faturamento médio.
* Importa as bibliotecas Matplotlib para plotagem e NumPy para cálculos numéricos (especificamente para calcular a média no gráfico).
* Cria um dicionário faturamento para armazenar o faturamento de cada loja.
* Extrai os nomes das lojas e os valores de faturamento para serem usados no gráfico.
* Cria um gráfico de barras utilizando plt.bar() para visualizar o faturamento de cada loja.
* Define rótulos para os eixos, título do gráfico e adiciona uma grade para melhor visualização.
* Formata o eixo y para exibir os valores em formato plano (sem notação científica).
* Adiciona uma linha horizontal representando o faturamento médio utilizando plt.axhline().
* Inclui uma legenda para identificar a linha média.
* Exibe o gráfico com plt.show().


3.	🛒 Vendas por Categoria:
```bash
vendas_por_categoria_loja1 = loja.groupby('Categoria do Produto')['Preço'].count()
vendas_por_categoria_loja2 = loja2.groupby('Categoria do Produto')['Preço'].count()
vendas_por_categoria_loja3 = loja3.groupby('Categoria do Produto')['Preço'].count()
vendas_por_categoria_loja4 = loja4.groupby('Categoria do Produto')['Preço'].count()

print("Vendas por categoria (Loja 1):\n", vendas_por_categoria_loja1)
print("\nVendas por categoria (Loja 2):\n", vendas_por_categoria_loja2)
print("\nVendas por categoria (Loja 3):\n", vendas_por_categoria_loja3)
print("\nVendas por categoria (Loja 4):\n", vendas_por_categoria_loja4)

categorias = vendas_por_categoria_loja1.index
largura = 0.2

x = range(len(categorias))

fig, ax = plt.subplots(figsize=(12, 6))
rects1 = ax.bar([i - 1.5*largura for i in x], vendas_por_categoria_loja1.values, largura, label='Loja 1', color='#003785')
rects2 = ax.bar([i - 0.5*largura for i in x], vendas_por_categoria_loja2.values, largura, label='Loja 2', color='#1465bb')
rects3 = ax.bar([i + 0.5*largura for i in x], vendas_por_categoria_loja3.values, largura, label='Loja 3', color='#2196f3')
rects4 = ax.bar([i + 1.5*largura for i in x], vendas_por_categoria_loja4.values, largura, label='Loja 4', color='#81c9fa')

ax.set_ylabel('Número de Vendas')
ax.set_xlabel('Categoria do Produto')
ax.set_title('Número de Vendas por Categoria em Cada Loja')
ax.set_xticks(x)
ax.set_xticklabels(categorias, rotation=45, ha='right')
ax.legend()
fig.tight_layout()
plt.grid(axis='y', linestyle='--')
plt.show()
```

* Utiliza o método groupby() para agrupar os dados de cada loja pela 'Categoria do Produto' e, em seguida, count() para contar o número de ocorrências (vendas) em cada categoria.
* Imprime o número de vendas por categoria para cada loja.
* Extrai os nomes das categorias de produtos.
* Define a largura das barras para o gráfico de barras agrupadas.
* Cria um array de posições para as barras no eixo x.
* Cria um gráfico de barras agrupadas para comparar as vendas por categoria entre as quatro lojas. Ajusta as posições de cada grupo de barras para evitar sobreposição.
* Define rótulos para os eixos, título do gráfico e ajusta os rótulos do eixo x para melhor legibilidade (rotação de 45 graus).
* Adiciona uma legenda para identificar cada loja.
* Utiliza fig.tight_layout() para ajustar o espaçamento do gráfico e evitar cortes nos rótulos.
* Adiciona uma grade no eixo y.
* Exibe o gráfico.
* Média de Avaliação das Lojas:

```bash
media_avaliacoes = lojas.groupby('Loja')['Avaliação da compra'].mean()

print("\nMédia de avaliações por loja:")
media_avaliacoes

plt.figure(figsize=(8, 5))
media_avaliacoes.plot(kind='bar', color=['#003785', '#1465bb', '#2196f3', '#81c9fa'])
plt.title('Média de Avaliação por Loja')
plt.xlabel('Loja')
plt.ylabel('Média de Avaliação')
plt.xticks(rotation=0)
plt.grid(axis='y', linestyle='--')
plt.ylim(0, 5)
plt.show()
````

* Agrupa o DataFrame lojas (que deveria ser a concatenação de todas as lojas, mas não está definido no código fornecido. Assume-se que em um contexto completo haveria uma etapa para combinar os DataFrames) pela coluna 'Loja' e calcula a média da coluna 'Avaliação da compra' para cada loja.
* Imprime a média de avaliação por loja.
* Cria um gráfico de barras utilizando o método .plot(kind='bar') diretamente do objeto Series resultante do groupby().
* Define o título e os rótulos dos eixos.
* Garante que os rótulos do eixo x não sejam rotacionados.
* Adiciona uma grade no eixo y e define os limites do eixo y de 0 a 5 (assumindo que a escala de avaliação seja de 0 a 5).
* Exibe o gráfico.


5.	📦 Produtos Mais e Menos Vendidos:

```bash
produtos_vendidos = lojas.groupby(['Loja', 'Produto'])['Produto'].count().reset_index(name='Quantidade Vendida')

produtos_mais_vendidos = produtos_vendidos.loc[produtos_vendidos.groupby('Loja')['Quantidade Vendida'].idxmax()]
produtos_menos_vendidos = produtos_vendidos.loc[produtos_vendidos.groupby('Loja')['Quantidade Vendida'].idxmin()]

print("\nProdutos Mais Vendidos por Loja:")
print(produtos_mais_vendidos[['Loja', 'Produto', 'Quantidade Vendida']])

print("\nProdutos Menos Vendidos por Loja:")
print(produtos_menos_vendidos[['Loja', 'Produto', 'Quantidade Vendida']])
```

* Agrupa o DataFrame lojas pelas colunas 'Loja' e 'Produto', conta o número de ocorrências de cada produto em cada loja e renomeia a coluna resultante para 'Quantidade Vendida'.
* Para encontrar o produto mais vendido em cada loja, agrupa produtos_vendidos pela 'Loja' e utiliza idxmax() para obter o índice da linha com a maior 'Quantidade Vendida' em cada grupo. Em seguida, utiliza .loc para selecionar essas linhas.
* Similarmente, para encontrar o produto menos vendido, utiliza idxmin() para obter o índice da linha com a menor 'Quantidade Vendida' em cada grupo.
* Imprime os produtos mais e menos vendidos por loja, mostrando as colunas 'Loja', 'Produto' e 'Quantidade Vendida'.


6. 🚚 Frete Médio por Loja:
```bash
frete_medio = lojas.groupby('Loja')['Frete'].mean()

print("\nFrete Médio por Loja:")
frete_medio
```

* Agrupa o DataFrame lojas pela coluna 'Loja' e calcula a média da coluna 'Frete' para cada loja.
* Imprime o frete médio por loja.


## ⚠️ Possíveis Problemas e Soluções
Durante a execução do projeto, alguns problemas podem surgir:
1.	Erro ao acessar as URLs dos arquivos CSV:
* Problema: Se as URLs dos arquivos CSV estiverem incorretas, o Pandas não conseguirá ler os dados, resultando em um erro urllib.error.URLError ou FileNotFoundError.
* Solução: Verifique se as URLs estão corretas e se os arquivos estão acessíveis publicamente nos respectivos endereços.

2.	Erro de importação de bibliotecas:
   
* Problema: Se as bibliotecas Pandas ou Matplotlib não estiverem instaladas corretamente no seu ambiente local (fora do Colab), você poderá encontrar erros de ImportError.
* Solução: Certifique-se de que as bibliotecas estão instaladas utilizando o pip install pandas matplotlib no seu terminal. No Colab, isso geralmente não é um problema, mas se ocorrer, tente executar !pip install pandas matplotlib em uma célula.

3.	Problemas com a exibição de gráficos:

* Problema: Em alguns ambientes, os gráficos gerados pelo Matplotlib podem não ser exibidos corretamente.
* Solução: No Google Colab, os gráficos são geralmente exibidos inline automaticamente. Se estiver executando em um ambiente local, certifique-se de ter um backend gráfico configurado para o Matplotlib. Você pode tentar adicionar %matplotlib inline no início do seu script em notebooks Jupyter locais.

4.	Incompatibilidade de versões das bibliotecas.


## ✨ Observações
Os dados foram disponibilizados como parte de um desafio de ciências de dados da [Alura](https://www.alura.com.br/)


## 🤝 Contribuições
Contribuições para este projeto são bem-vindas. Sinta-se à vontade para propor melhorias, ou enviar pull requests com suas modificações.


## 💾 Licença
Este projeto não possui uma licença específica definida. O uso e distribuição devem seguir as políticas dos dados originais e as diretrizes de uso do GitHub.


## 👩‍💻 Sobre a Autora

<img src="https://avatars.githubusercontent.com/u/180755020?v=4" height="100"/>

Desenvolvido por **Raylaine Barreto** 

- [LinkedIn](https://www.linkedin.com/in/raylaine-barreto)



