# ReABTIC2021

Continuação do trabalho do Impacto de Viés nos modelos (Versão estendida).

## Diretórios

### Diretório 0_Datasets_Sources
Contém todos os datasets originais, sem modificação. Apenas o Kronodroid foi a concatenação do dataset benigno com o dataset maligno. O MotoDroid_22K é um conjunto de dados criado pela nossa equipe.

### Diretório 1_Data_Preparation
Contém os códigos referentes à preparação dos dados nos datasets. Na preparação foi realizada uma limpeza nos dados e foram selecionadas apenas as permissões como características relevantes para o estudo. 

Através dos datasets originais, nós geramos 28 novos datasets contendo apenas permissões, onde 12 conjuntos de dados foram utilizados em testes utilizando todas as permissões, 8 conjuntos de dados foram utilizados no 1° experimento de intersecção utilizando as mesmas permissões geradas, e 8 conjuntos de dados foram utilziados no 2° experimento de intersecção utilizando as mesmas permissões geradas: 

   1° 6 datasets contendo todas as permissões filtradas.

   2° 6 datasets contendo todas as permissões filtradas e registros duplicados.

   3° Dois Experimentos:

      * 4 datasets contendo as mesmas 13 permissões + class;

      * 4 datasets contendo as mesmas 55 permissões + class;
   
   4° Dois Experimentos:

      * 4 datasets contendo as mesmas 13 permissões + class e registros duplicados;
      
      * 4 datasets contendo as mesmas 55 permissões + class e registros duplicados;

Os registros duplicados são exemplos de aplicativos que possuem todas as suas características iguais a outro exemplo. Essas duplicatas podem causar viés no modelo na hora de predizer a classe de um aplicativo Android, pois o mesmo saberá predizer corretamente se aquele aplicativo Android é malicioso ou não sem aprender.

### Diretório 2_Only_Permissions_Datasets
Contém os datasets incluindo apenas as permissões Android como características (com e sem duplicatas).

### Diretório 3_Permissions_Datasets_Intersection
Contém os dois experimentos de datasets incluindo as mesmas permissões:

   1° A intersecção de 4 datasets: Drebin215, Androcrawl, AndroidMalwareNormal e DefenseDroid;

   2° A intersecção de 4 datasets: Drebin215, Kronodroid, DefenseDroid e MotoDroid_22K.

### Diretório 4_Datasets_Permissions_After_sigPID
Contém os datasets finais após a aplicação do sigPID nos datasets do diretório 2.

### Diretório 5_Data_Preparation
Contém os códigos referentes a redução de amostras de aplicativos (benignos e malignos) a fim de nivelar a mesma quantidade para todos os datasets. Assim, não havera impacto de um modelo ter aprendido mais do que outro.

### Diretório 6_Leveled_Datasets
Contém os datasets contendo a mesma quantidade de amostras de aplicativos benignos e malignos (com e sem duplicatas).
A quantidade de amostras foram niveladas da seguinte forma para todos os datasets em todos os experimentos:

   **Sem duplicatas**

      * Benignos >> 3.146

      * Malignos >> 1.720

   **Com duplicatas**

      * Benignos >> 5.975

      * Malignos >> 5.560

### Diretório 7_Model_Test
Contém os códigos referentes ao desempenho do modelo RandomForest em detectar aplicativos maliciosos.
Nesse diretório, há três experimentos: um utilizando todas as permissões dos datasets, e dois utilizando datasets com as mesmas permissões, citadas no Diretório 3. Também há um quarto Experimento onde foram realizados testes para analisar o desempenho do modelo em classificar os APKs nos datasets de permissões antes e depois da aplicação do SigPID, sendo que para cada dataset, adequamos o modelo para aquele conjunto de dados testado.

**Permission_tests**

   Contém os códigos referentes ao desempenho do modelo adequado para o Drebin (2012) para classificar APKs em datasets mais recentes utilizando todas as suas permissões.

**Intersection_tests**

   Contém os códigos referentes ao desempenho do modelo, adequado para o Drebin (2012) e validado em datasets mais recentes, utilizando as mesmas permissões. São dois experimentos:

   * 1° Experimento: utiliza 4 datasets com as mesmas 13 permissões + class (Drebin215, Androcrawl, AndroidMalwareNormal e DefenseDroid).

   * 2° Experimento: utiliza 4 datasets com as mesmas 55 permissões + class (Drebin215, KronoDroid, DefenseDroid e MotoDroid_22K).

### Diretório 8_SigPID_Test
Contém o código referente a exploração do número de permissões selecionadas pelo SigPID em cada dataset de intersecção (sem duplicatas), para analisar a ligação que possui com os resultados dos modelos. Os resultados serão exibidos a seguir, junto com o desempenho do modelo antes e depois do SigPID:

**DREBIN-215**

   * Sofreu uma redução de 23.68%

   * Características - 114 >> 87

   * Benignos >> 5.539

   * Malignos >> 1.720

   * Desempenho do modelo antes do SigPID  >> 91.95%

   * Desempenho do modelo depois do SigPID >> 88.57%

**ANDROCRAWL**

   * Sofreu uma redução de 88.13%

   * Características - 59 >> 7

   * Benignos >> 138.867

   * Malignos >> 23.247

   * Desempenho do modelo antes do SigPID  >> 55.93%

   * Desempenho do modelo depois do SigPID >> 50.01%

**ANDROID MALWARE NORMAL**

   * Sofreu uma redução de 95.97%

   * Características - 174 >> 7

   * Benignos >> 16.698

   * Malignos >> 7.026

   * Desempenho do modelo antes do SigPID  >> 55.54%

   * Desempenho do modelo depois do SigPID >> 50.07%

**KRONODROID**

   * Sofreu uma redução de 25.74%

   * Características - 167 >> 124

   * Benignos >> 6.747

   * Malignos >> 6.533

   * Desempenho do modelo antes do SigPID  >> 87.42%

   * Desempenho do modelo depois do SigPID >> 85.19%

**DEFENSEDROID**

   * Sofreu uma redução de 37.77%

   * Características - 135 >> 84

   * Benignos >> 3.146

   * Malignos >> 4.579

   * Desempenho do modelo antes do SigPID  >> 84.37%

   * Desempenho do modelo depois do SigPID >> 81.12%

**MOTODROID_22K**

   * Sofreu uma redução de 24.30%

   * Características - 144 >> 109

   * Benignos >> 11.032

   * Malignos >> 11.144

   * Desempenho do modelo antes do SigPID  >> 82.71%

   * Desempenho do modelo depois do SigPID >> 73.62%

A seguir, serão mostradas quantas permissões relevantes selecionadas pelo SigPID cada dataset dos três experimentos possuem, assim como o respectivo desempenho do modelo RandomForest para cada dataset sem duplicatas (caso ideal), utilizando a métrica ROC_AUC:

**Experimento utilizando todas as permissões:**

   *Drebin-215*               >> 86/113 Permissões + class.

   * Modelo                   >> 89.23 %

   *Androcrawl*           >> 6/58 Permissões + class.

   * Modelo                   >> 52.44 %

   *AndroidMalwareNormal* >> 6/173 Permissões + class.

   * Modelo                   >> 51.50 %

   *KronoDroid*           >> 123/166 Permissões + class.

   * Modelo                   >> 84.17 %

   *DefenseDroid*         >> 83/134 Permissões + class.

   * Modelo                   >> 82.42 %

   *MotoDroid_22K*             >> 109/144 Permissões + class.

   * Modelo                   >> 78.51 %

**1° Experimento de intersecção:**

   *Drebin-215*               >> 10/13 Permissões + class.

   * Modelo                   >> 61.93 %

   *Androcrawl*           >> 2/13 Permissões + class.

   * Modelo                   >> 52.90 %

   *AndroidMalwareNormal* >> 0/13 Permissões + class.

   * Modelo                   >> 49.63 %

   *DefenseDroid*         >> 13/13 Permissões + class.

   * Modelo                   >> 50.12 %

**2° Experimento de intersecção:**

   *Drebin-215*              >> 43/55 Permissões + class.

   * Modelo                   >> 77.49 %

   *KronoDroid*           >> 50/55 Permissões + class.

   * Modelo                   >> 59.25 %

   *DefenseDroid*         >> 36/55 Permissões + class.

   * Modelo                   >> 56.19 %

   *MotoDroid_22K*         >> 44/55 Permissões + class.

   * Modelo                   >> 52.71 %


## Data de Coleta das amostras dos datasets

### Drebin-215 (2012)

A data das amostras coletadas variam entre 2010 até 2012.

### Androcrawl (2014-2015)

Não é específicado em nenhum lugar a data de coleta das amostras desse dataset, porém ele é do ano de 2014-2015. Provavelmente contém amostras mais antigas que o seu ano.

### AndroidMalwareNormal (2018)

Não é específicado em nenhum lugar a data de coleta das amostras desse dataset, porém ele é do ano de 2018. Provavelmente contém amostras mais antigas que o seu ano.

### KronoDroid (2021)

A data das amostras coletadas variam entre 2008 até 2021.

### DefenseDroid (2021)

Não é específicado em nenhum lugar a data de coleta das amostras desse dataset, porém ele é do ano de 2021. Provavelmente contém amostras mais antigas que o seu ano.

### MotoDroid_22K (2021)

A data das amostras coletadas variam entre 2018 até 2021. Os exemplos de aplicativos Android foram coletados do AndroZoo.
