# Dataset-Matters

Esse trabalho tem como objetivo analisar o impacto no desempenho do modelo de classificação RandomForest em datasets de diferentes datas (2012, 2015, 2018 e 2021), a cada 3 anos. Os diretórios desse repositório serão explicados a seguir:

### Diretório 0_Originals_Datasets => Contém todos os 4 datasets originais utilizados nesse estudo, são eles: Drebin-215, Androcrawl, AndroidMalwareNormal e DefenseDroid, em ordem do mais antigo para o mais atual, respetivamente. Como o dataset Androcrawl possui um tamanho grande, ele está zipado.

  Links dos Datasets originais disponíveis para download:

  *Drebin-215           >> https://figshare.com/articles/dataset/Android_malware_dataset_for_machine_learning_2/5854653
  
  *Androcrawl           >> https://github.com/phretor/ransom.mobi/blob/gh-pages/f/filter.7z
  
  *AndroidMalwareNormal >> https://figshare.com/articles/dataset/Data_set_of_Android_permissions/5986708/8
  
  *DefenseDroid         >> https://www.kaggle.com/defensedroid/android-malware-detection

### Diretório 1_Permissions_Extraction 
=> Contém todo o passo a passo do tratamento dos dados e extração de permissões dos datasets originais. Estão inclusos também o tratamento dos dados e permissões duplicadas, e features irrelevantes para o estudo.

### Diretório 2_Only_Permissions_Datasets 
=> Contém subsets de apenas permissões extraídas dos datasets originais. Há subsets com e sem duplicatas (exemplos de aplicativos que estão duplicados nos conjuntos de dados).

### Diretório 3_Data_Preparation 
=> Contém os códigos referentes a redução dos datasets (com e sem duplicatas) de modo que fiquem todos no mesmo nível de balanceamento entre benignos e malignos para não causar nenhum impacto sobre a diferença da quantidade de exemplos treinados em cada dataset.

### Diretório 4_Reduced_Datasets 
=> Contém os datasets (com e sem duplicatas) com os exemplos de apks reduzidos. Todos possuem o mesmo número de aplicativos malignos e benignos para serem separados em partições iguais para o conjunto de treino, teste e validação.

### Diretório 5_Tests 
=> Contém os códigos referentes ao desempenho do modelo de classificação RandomForest em cada dataset (com e se duplicatas).
