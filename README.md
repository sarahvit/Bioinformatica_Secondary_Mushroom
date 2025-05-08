# 🧬 Classificação de Cogumelos com Aprendizado de Máquina: Uma Abordagem Baseada em Bioinformática

Este repositório apresenta um estudo aplicado de ciência de dados voltado para a classificação de cogumelos com base em atributos morfológicos, realizado por **Sarah Vitória Moreira de Aquino** e **Ana Luíza Gomes Vieira**, como parte de uma iniciativa de pesquisa na área de **bioinformática**.

## 🎯 Objetivo do Projeto

O principal objetivo deste projeto é **investigar e aplicar técnicas de aprendizado de máquina para apoiar e automatizar a classificação de cogumelos com base em seus atributos morfológicos** — uma tarefa historicamente feita de forma manual, complexa e sujeita a erros, especialmente quando realizada apenas por análise visual.

Na prática, queremos responder à seguinte pergunta:  
**Até que ponto é possível treinar modelos computacionais capazes de diferenciar cogumelos comestíveis de venenosos apenas com base em suas descrições físicas?**

Para isso, utilizamos uma abordagem de ciência de dados que envolve:

- **Explorar algoritmos de classificação supervisionada** aplicados ao contexto micológico;
- **Comparar diferentes modelos** quanto à sua capacidade de generalização e robustez frente à diversidade morfológica dos cogumelos;
- **Avaliar o impacto de decisões de pré-processamento** (como tratamento de dados ausentes) na performance dos algoritmos;
- **Refletir sobre as limitações dos modelos e dos dados simulados**, e quais são os desafios reais que ainda precisam ser enfrentados na aplicação dessas soluções a fungos do mundo real.

Além disso, este projeto também tem um caráter **formativo e exploratório**: parte da nossa motivação é aprender na prática os fundamentos de modelagem de dados, engenharia de atributos e avaliação de desempenho, usando um problema do mundo real e cientificamente relevante.

Nosso trabalho também visa pavimentar o caminho para uma **etapa futura de construção de uma base de dados própria**, voltada para fungos do gênero *Funalia*, usando técnicas de curadoria e simulação baseadas em NLP.

## 🔍 Contexto e Motivação

O reino Fungi possui uma biodiversidade impressionante, com estimativas de até 3,8 milhões de espécies, das quais aproximadamente 100 mil foram oficialmente descritas até hoje. Apesar de sua importância ecológica, médica, biotecnológica e alimentar, o estudo e a classificação dos fungos ainda enfrentam grandes desafios — principalmente pela limitação dos métodos tradicionais de identificação morfológica.

Espécies morfologicamente semelhantes, como *Agaricus bisporus* (comestível) e *Agaricus xanthodermus* (tóxico), evidenciam o risco de erros e a necessidade de alternativas automatizadas, especialmente quando se trata da segurança alimentar.

## 🔬 Dataset Utilizado

Para essa parte prática do projeto, a gente precisava de um conjunto de dados que representasse melhor os desafios reais da classificação fúngica.

O Mushroom Dataset original, publicado em 1987 no UCI Machine Learning Repository, foi um dos primeiros que a gente conheceu. Ele traz informações sobre 23 espécies de cogumelos dos gêneros Agaricus e Lepiota, com base em atributos morfológicos simples — como formato do chapéu, cor e presença de anel.

Apesar de ser muito usado até hoje, ele tem uma limitação importante: por ser pequeno e conter espécies bem distintas, ele acaba sendo fácil demais pro modelo aprender — o que não representa a complexidade do problema real.
Optamos pelo **Secondary Mushroom Dataset** (Wagner et al., 2021), que simula mais de 61 mil cogumelos a partir de descrições morfológicas reais de 173 espécies extraídas do livro *Mushrooms and Toadstools* (Kibby, 1994).

Este conjunto oferece diversidade morfológica, maior complexidade e maior representatividade dos desafios reais de classificação.

## 🛠️ Pipeline de Ciência de Dados

O projeto foi estruturado em quatro etapas principais:

1. **Análise Exploratória**  
   - Avaliação de distribuições, padrões e valores ausentes.
   - Avaliação de importância das variáveis
   - Análise da dependência das variáveis.
   - Análise da relação pra identificar o tipo de valor ausente.


2. **Tratamento de Dados**  
   - Remoção e imputação de variáveis com excesso de valores nulos;
   - Codificação de variáveis categóricas;
   - Padronização dos dados;


3. **Modelagem**  
   - Aplicação dos algoritmos: KNN, SVM (RBF kernel) e Random Forest;
   - Ajuste de hiperparâmetros via GridSearchCV com validação cruzada.

4. **Avaliação e Interpretação**  
   - Uso de métricas como Acurácia, Precisão, Recall e F1-score macro;
   - Análise do desempenho geral e por classe;


## 📊 Principais Resultados

- O modelo **SVM** com kernel RBF apresentou o melhor desempenho entre os avaliados, com taxa de acerto praticamente total no conjunto de teste.
- O **KNN** também obteve resultados muito próximos, sendo uma alternativa adequada em contextos que favorecem algoritmos baseados em distância.
- Já o **Random Forest**, embora tenha obtido boas métricas gerais, apresentou a maior quantidade de erros de classificação, incluindo casos em que cogumelos venenosos foram classificados como comestíveis — o que representa um risco relevante em cenários reais.

## 🔎 Próximos Passos

- Explorar **novos algoritmos** como MLP, AdaBoost, QDA e Gaussian Naive Bayes;
- Iniciar a construção de um **dataset simulado próprio**, voltado para espécies do gênero *Funalia*, utilizando curadoria de dados taxonômicos e fenotípicos.

## 📁 Estrutura do Repositório

- `notebook/`: Colab Notebook com o pipeline completo;
- `/`: Conjunto de dados utilizado no projeto
- `README.md`: Documentação e descrição do projeto.

## 📚 Referências

- WAGNER, D.; HEIDER, D.; HATTAB, G. Mushroom data creation, curation, and simulation to support classification tasks. Scientific Reports, v. 11, n. 1, 14 abr. 2021.
- MD. SAMIN MORSHED et al. Predicting Mushroom Edibility with Effective Classification and Efficient Feature Selection Techniques. 7 jan. 2023.
- Kibby, G. (1994). *Mushrooms and Toadstools*.
- UCI Machine Learning Repository. *Mushroom Dataset*.

---

**Sinta-se à vontade para explorar este projeto, enviar sugestões ou contribuir com novas ideias. Feedbacks são sempre bem-vindos!**
