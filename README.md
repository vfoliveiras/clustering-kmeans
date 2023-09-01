# Clusterização Utilizando K-Means (Calinski-Harabasz Index)

![screen](https://uploaddeimagens.com.br/images/004/593/490/full/K-Means.jpg?1693433070)

Este projeto aborda a aplicação do algoritmo de clusterização **K-Means** a um conjunto de dados específico, que se refere a "[Facebook Live Sellers in Thailand](https://archive.ics.uci.edu/dataset/488/facebook+live+sellers+in+thailand)", disponibilizado pela UCI. A análise visa descobrir padrões e insights nos dados de páginas do Facebook de 10 vendedores varejistas de moda e cosméticos tailandeses, considerando diferentes tipos de postagens e métricas de engajamento, como comentários, compartilhamentos e reações.

## Objetivo Principal

O foco central é identificar padrões e agrupamentos naturais nos dados, permitindo determinar o número ideal de clusters que mais se adequa à proposta de análise.

## Etapas do Projeto

#### • Carregamento e Pré-processamento dos Dados

O conjunto de dados foi carregado e pré-processado para remover valores vazios e algumas colunas irrelevantes para prepará-lo para a clusterização. Isso incluiu a aplicação do **LabelEncoder** para transformar valores categóricos em numéricos, garantindo que o **K-Means** possa operar corretamente. Além disso, os dados foram normalizados para que todas as colunas tivessem o mesmo peso no cálculo da distância.

#### • Aplicação do K-Means

Foram testados vários números de clusters para encontrar a melhor configuração que gerasse clusters significativos.

#### • Avaliação dos Clusters

A métrica **Calinski-Harabasz** foi utilizada para avaliar a qualidade dos clusters gerados pelo **K-Means**. Essa métrica mede a relação entre a dispersão dentro dos clusters e a dispersão entre os clusters. Quanto maior o valor do índice **Calinski-Harabasz**, melhor é a separação entre os clusters.

![screen](https://uploaddeimagens.com.br/images/004/594/721/full/Captura_de_tela_2023-08-31_222819.png?1693531741)

A lógica por trás dessa fórmula é comparar a variação média entre os clusters (dispersão entre clusters) com a variação média dentro dos clusters (dispersão dentro dos clusters). Quando os clusters estão bem separados, a dispersão **entre** eles é maior em relação à dispersão **dentro** deles, resultando em um índice mais alto.

Portanto, ao calcular o índice **Calinski-Harabasz** para diferentes números de clusters, podemos identificar o número de clusters que maximiza essa relação, indicando uma clusterização mais robusta e distinta. Isso ajuda a escolher o número de clusters que melhor se ajusta aos padrões dos dados.

#### • Identificação do Melhor Número de Clusters

Através da avaliação do índice **Calinski-Harabasz** para diferentes números de clusters, foi possível identificar o número de clusters que resultou em uma melhor separação dos dados. A seleção do melhor número de clusters foi baseada na observação dos resultados do índice e na análise das características dos dados.

#### • Abaixo estão os resultados do índice Calinski-Harabasz para os diferentes números de clusters testados:

| Número de Clusters | Índice Calinski-Harabasz |
|-------------------|--------------------------|
| 2                 | 3681.78                  |
| 3                 | 4205.44                  |
| 4                 | 4543.92                  |
| 5                 | 4128.26                  |
| 6                 | 4167.36                  |
| 7                 | 4121.85                  |
| 8                 | 4066.57                  |
| 9                 | 3945.47                  |
| 10                | 3974.33                  |

![screen](https://uploaddeimagens.com.br/images/004/593/485/full/Captura_de_tela_2023-08-30_162950.png?1693432815)

Com base na análise desses resultados, o número de clusters que proporcionou a melhor separação foi identificado como **4 clusters**. Essa escolha foi justificada pela observação do ponto em que o índice **Calinski-Harabasz** começou a estabilizar e também pela interpretação dos padrões e características dos dados. *(Testei até 20 clusters e do 16º ao 20º, houve a estabilização dos resultados)*.

## Gráfico de Dispersão dos Clusters

A figura abaixo mostra o gráfico de dispersão que exibe os clusters gerados pelo **K-Means** com **4 clusters**. Os pontos dos clusters estão coloridos de acordo com suas atribuições, e os centroides de cada cluster estão marcados em vermelho.

![screen](https://uploaddeimagens.com.br/images/004/593/489/full/Captura_de_tela_2023-08-30_165335.png?1693432918)

## Conclusão

Ao considerar diferentes números de clusters, a métrica **Calinski-Harabasz** foi fundamental para determinar o número ideal de clusters que melhor separa os dados. A análise dos resultados revelou que o número ideal de clusters é **4**.

Essa seleção é justificada pela observação do índice **Calinski-Harabasz**, que atingiu seu ponto de inflexão quando o número de clusters era **4**. Isso sugere que a separação entre os clusters é maximizada nesse ponto, indicando uma clara distinção entre os grupos.

O uso do **LabelEncoder** para codificar variáveis categóricas e a normalização dos dados foram passos cruciais para garantir que o **K-Means** pudesse operar de maneira eficaz. A visualização dos resultados através do gráfico de dispersão confirmou a validade da clusterização, com os centroides dos clusters e os pontos de dados claramente delineados.

Em resumo, a escolha do número de clusters foi cuidadosamente fundamentada, combinando análise quantitativa **(Calinski-Harabasz)** e interpretação contextual. 
