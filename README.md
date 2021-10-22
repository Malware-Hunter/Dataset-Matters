# Dataset-Matters

Esse trabalho tem como objetivo analisar o impacto no desempenho do algoritmo de classificação RandomForest em datasets de diferentes épocas (2012, 2015, 2018 e 2021), utilizando apenas as permissões de aplicativos Android. O repositório está organizado como detalhado a seguir.

### Diretório 0_Datasets_Sources 
Os 4 datasets que foram utilizados como fontes de dados: Drebin-215 (2012), Androcrawl (2015), AndroidMalwareNormal (2018) e DefenseDroid (2021). 

  Links das fontes originais dos datasets:

  Drebin-215           >> https://figshare.com/articles/dataset/Android_malware_dataset_for_machine_learning_2/5854653
  
  Androcrawl           >> https://github.com/phretor/ransom.mobi/blob/gh-pages/f/filter.7z
  
  AndroidMalwareNormal >> https://figshare.com/articles/dataset/Data_set_of_Android_permissions/5986708/8
  
  DefenseDroid         >> https://www.kaggle.com/defensedroid/android-malware-detection

### Diretório 1_Permissions_Extraction 
Passo a passo do tratamento dos dados e a extração de permissões dos datasets originais. Estão inclusos também o tratamento de exemplos de APKs e permissões duplicadas, e a exclusão de características irrelevantes para o estudo.

### Diretório 2_Permissions_Only_Subsets 
Subsets derivados dos datasets originais. Cada subset contém apenas características relacionadas a permissões em dois subconjuntos, um com e outro sem aplicativos que estão duplicados nos conjuntos de dados.

### Diretório 3_Data_Preparation 
Códigos referentes a redução dos datasets de modo que fiquem todos no mesmo nível de balanceamento entre aplicativos benignos e malignos para não causar nenhum impacto na diferença da quantidade de exemplos treinados em cada dataset.

### Diretório 4_Reduced_Datasets 
Datasets reduzidos. Todos possuem o mesmo número de aplicativos malignos e benignos para serem separados em partições iguais para o conjunto de treino, teste e validação.

### Diretório 5_RandomForest_Metrics
Códigos referentes ao desempenho do modelo de classificação RandomForest em cada dataset.

### Diretório 6_Data_Exploration
Códigos referentes a análise exploratória dos conjuntos de dados.
