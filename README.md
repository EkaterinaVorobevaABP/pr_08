# pr_08
## Цель: 
определить наиболее эффективный метод загрузки данных (малых и больших объемов) из CSV-файлов в СУБД PostgreSQL, сравнивая время выполнения для методов: pandas.to_sql(), psycopg2.copy_expert() (с файлом и с io.StringIO), и пакетная вставка (psycopg2.extras.execute_values).

## Ход работы:

1.	Подключимся к необходимым библиотекам:
 
 ![image](https://github.com/user-attachments/assets/c660c61c-f884-4998-8546-9e7f763cc02b)
 ![image](https://github.com/user-attachments/assets/113a3bef-a7c8-4e82-8d36-ca47244874f0)



2.	Укажем путь к файлам csv и подключимся к базе данных
 
  ![image](https://github.com/user-attachments/assets/a78dc08e-63b3-4224-9d5b-5ea6f7984365)

3.	Посмотрим ERD-диаграммы: 
  
  ![image](https://github.com/user-attachments/assets/02742dfe-be1b-4a6d-810e-ff9bd298f894)
  ![image](https://github.com/user-attachments/assets/0d574ddb-6ff2-4cc8-8bd9-20ea475fe24f)


4.	После загрузки данных в таблицу проведем анализ скорости загрузки данных разными способами. Заметим, что pandas оказывается в обоих случаях самым медленным способом
   ![image](https://github.com/user-attachments/assets/a86c7bc9-0f43-4ac7-a20a-fc4289d8c91b)

Это ярко видно и на визуализации данных о скорости загрузки:
   ![image](https://github.com/user-attachments/assets/9ab011f5-1f6b-4848-b3dc-1c8c69bd6a2e)

## Вариант 5
## Индивидуальные задания
Перед началом работы убедимся, что все вспомогательные функции из шаблона определены 

 ![image](https://github.com/user-attachments/assets/1037f67b-5341-46e7-8b3e-b36f2d9a8034)
1.	Создать таблицы sales_small, sales_big.
 ![image](https://github.com/user-attachments/assets/5a994dff-390b-4232-a74c-0f77c001a72c)

 ![image](https://github.com/user-attachments/assets/92c9547e-fbd2-4b46-aa98-27013fafd9a8)

2.	Метод: copy_expert (file) для малых данных:
  
  ![image](https://github.com/user-attachments/assets/08497198-1380-4739-9030-9e47a3703d67)
  ![image](https://github.com/user-attachments/assets/ff915a3c-6d2d-40e6-b0ba-a22860536aec)

3.	Метод: copy_expert (file) для больших данных:
  ![image](https://github.com/user-attachments/assets/a51de0ea-4aab-4a1d-8cdd-d37f53c2a7a5)
  ![image](https://github.com/user-attachments/assets/2c9329d9-6fcc-4440-b2ca-65e71244917b)

 
4.	SQL: Найти минимальную cost в sales_big.
  ![image](https://github.com/user-attachments/assets/be2c3b16-c185-4df4-96b2-765af29255d5)

  ![image](https://github.com/user-attachments/assets/5afdac0b-42b8-42c0-bddd-1dd25e2de04a)

5.	Python: Построить ящик с усами (boxplot) для cost из sales_big (LIMIT 50000).
 

  ![image](https://github.com/user-attachments/assets/acb90b22-3554-4ea4-8f1c-89fdca17fe01)

  ![image](https://github.com/user-attachments/assets/8c3a654b-6723-4b6b-a0b3-a56d8fe4177d)


В конце обязательно закрываем соединение.

## Вывод: 
в ходе работы были изучены и найдены наиболее эффективные методы загрузки данных (малых и больших объемов) из CSV-файлов в СУБД PostgreSQL, также была осуществлена визуализация полученных результатов.
