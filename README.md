# Classificador-de-Placas

## 1. Montagem do Dataset  

Inicialmente, para a montagem do dataset foram utilizadas imagens de **5 placas distintas**:  
- Placa de pare (**R-1**)  
- Placa de trânsito de pedestres (**A-32**)  
- Placa de lombada (**A-18**)  
- Placa de proibido virar (**R-3**)  
- Placa de proibido estacionar (**R-6a**)  

O dataset foi construído a partir de imagens obtidas **da internet** e **tiradas manualmente**.  
As placas, classes e número de imagens utilizadas podem ser verificadas na tabela a seguir:  

| Placa | Classe | Quantidade de Imagens |
|:------|:--------|:---------------------|
| Pare | R-1 | 60 |
| Proibido Estacionar | R-6a | 60 |
| Proibido Virar | R-3 | 60 |
| Trânsito de Pedestres | A-32 | 60 |
| Lombada | A-18 | 60 |
| **Total** |  | **300** |

O dataset foi dividido em **60% para treino**, **20% para teste** e **20% para validação**.

## 2. Obtenção do Modelo  

Durante o treino foi utilizada como função de **loss** a `CrossEntropyLoss`,  
o **otimizador** `AdamW` e o **scheduler** `OneCycleLR`.  

Como **métrica de validação** para obtenção do melhor modelo, foi utilizada a **F1-Score**.  

A **Figura 1** mostra as curvas de *loss* durante o treino e validação do modelo.  
O modelo final utilizado foi o salvo na **Época 10**, antes das oscilações da *loss* de validação.  

A tabela a seguir mostra as métricas obtidas no teste com o melhor modelo:

| Métrica | Valor |
|:---------|:------|
| F1-Score | 0.83 |
| Acurácia | 0.85 |
| Precisão | 0.85 |

### Referências utilizadas para criação do dataset:  
- [Road Signs](https://universe.roboflow.com/paulolab/road-signs-tn96c/browse?queryText=&pageSize=50&startingIndex=50&browseQuery=true)  
- [TCC Caroline Paula Kolassa](https://universe.roboflow.com/uri-erechim/tcc-caroline-paula-kolassa-final/dataset/4)  
- [Traffic Signs ikeuk](https://universe.roboflow.com/my-workspace-wyfmd/traffic-signs-ikeuk/dataset/2)  
- [Assets BR](https://universe.roboflow.com/assetsai/assetsbr/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true)

