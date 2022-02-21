# hse_hw1_meth
Bioinformatics 4 semester 1 homework


[Ссылка на google colab ноутбук](https://colab.research.google.com/drive/1IY5RFtGvdPKsypkePDJMeYafhdq1vzHt?usp=sharing)  
Сам блокнот также можно найти во вкладке data  

## Task 1  

Сравним секвенирование ДНК и РНК. Для этого посмотрим на некоторые места отчетов FastQC для этого задания и прошлого (оба файла есть в папке data):  

#### Base statistics

<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/prev_fastQC_1.PNG width=500/>  
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/new_fastQC_1.PNG width=500/>  

Как мы можем заметить, %GC стал меньше более чем в два раза  

#### Per base sequence content  

<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/prev_fastQC_2.PNG width=500/>  
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/new_fastQC_2.PNG width=500/>  

Как мы можем заметить, сейчас почти отсутствуют Цитозины, cодержание Гуанина выше, а Тимина наоборот, ниже.  

#### Per sequence GC content  


<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/prev_fastQC_3.PNG width=500/>  
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/new_fastQC_3.PNG width=500/>   

Как мы можем заметить, нормальное распределение довольно значительно сместилось влево.  

## Task 2  
### Subtask a  

Составим таблицу для числа ридов закартированных на участки 11347700-11367700 и 40185800-40195800:  

Образец\Участок | 11347700-11367700 | 40185800-40195800
--------------- | ----------------- | ------------------
8 cell          | 1090              | 464
Epiblast        | 2328              | 1062
ICM             | 1456              | 630

### Subtask b  

Провели дедупликацию одним bash-скриптом (на +1 балл), скрипт можно увидеть в colab-ноубуке  
Таблица дуплицированных процентов:  

Образец    | Процент дуплицирования 
---------- | ---------------------- 
8 cell     | 81.69%
Epiblast   | 97.08%
ICM        | 90.92%

### Subtask с  

Провели коллинг метилирования цитозинов. Код в colab-ноубуке  

### Subtask d  

Сделаем отчеты M-bias по каждому из образцов и опишем их:  

#### 8 cell
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/8_cell_mbias.PNG width=500/>  

#### Epiblast
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/epiblast_mbias.PNG width=500/>  
Можем заметить, что здесь мы имеем самый большой уровень CpG метилирования.  

#### ICM
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/icm_mbias.PNG width=500/>  


В целом, мы можем заметить, что уровень метилирования не линейный. В начале он снижаетсся, после чего, ближе к поздним стадиям снова увеличивается.  

Также, во всех трех образцах уровни CHH и  ChG метилирования Изначально не равны 0, но вскоре сильно падают (в 0 или почти в 0)

### Subtask e  

Построим гистограммы всех образцов с помощью bedgraph и питона (код в colab-ноутбуке):

#### 8 cell
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/8_cell_hist.PNG width=500/>  
Можем заметить, что здесь мы имеем довольно высокую частоту 0% метилирования среди всех образцов, однако, меньше, чем у icm. Также данное распределение ближе всего к нормальному средо образцов. 

#### Epiblast
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/epiblast_hist.PNG width=500/>  
Можем заметить, что здесь мы имеем самую высокую частоту 100% метилирования среди всех образцов. Также, данное распредение похоже на смещенное нормальное.  

#### ICM
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/icm_hist.PNG width=500/>  
Можем заметить, что здесь мы имеем самую высокую частоту 0% метилирования среди всех образцов. Данное распределение наверное будет даже ближе к равномерному, чем к нормальному.  


В целом, можно заметить, что самая большая частота у 0% метилирования цитозинов. А также совершенно ясно, что нет никакой зависимости между уровнем метилирования цитозина и тем, на какой ступени развития сейчас находится зародыш.

