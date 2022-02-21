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


### Subtask e  

Построим гистограммы всех образцов с помощью bedgraph и питона (код в colab-ноутбуке):


<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/8_cell_hist.PNG width=500/>  
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/epiblast_hist.PNG width=500/>  
<img src=https://github.com/TheMostKnown/hse_hw1_meth/blob/main/images/icm_hist.PNG width=500/>  


