# Исследование функций активации и гиперпараметров в архитектуре сетей долгой краткосрочной памяти для прогнозирования финансовых временных рядов

## **_Кумсков Михаил Иванович, Арсланова Алина Рустямовна,  Махова Анастасия Геннадьевна_**

В данной работе рассматриваются варианты архитектуры LSTM сетей в задаче прогнозирования финансовых временных рядов на примере цен BTC-USD и ETH-USD на минутных, часовых и дневных тиках. Целью работы является исследование влияния функции активации и гиперпараметров LSTM-сети на качество прогноза. Рассмотрены как классические функции активации, такие как сигмоидальная, гиперболический тангенс, линейная, ReLU, так и неклассические функции активации cloglog, loglog. Гиперпараметры задают архитектурные решения нейросети и влияют на качество прогноза и скорость обучения. 
	В работе показано, что правильный выбор функции активации и гиперпараметров сетей долгой краткосрочной памяти, является важным фактором, влияющим на качество прогноза и что неклассические функции активации cloglog и loglog, стоит использовать в архитектурах сетей долгой краткосрочной памяти для задач прогнозирования временных рядов наравне с классическими функциями активации.
 
_Ключевые слова: рекуррентные нейронные сети, RNN, Long short-term memory, LSTM, функция активации, units, lookback, TensorFlow, гиперпараметры, финансовые временные ряды._

------
В архиве все полученные данные, если получится, загружу в скором времени файлы отдельно, так как их много, с этим сейчас есть проблемы.

-------------


![image](https://github.com/user-attachments/assets/ed8123a5-f10c-4de8-8835-2277292a98b5)

Синяя линия - сходимость на тренировочных данных, оранжевая - сходимость на тестовых, для функции активации 𝑡𝑎𝑛ℎ, тики дневные


![image](https://github.com/user-attachments/assets/9a1e5995-7cd9-4dff-aa32-5d1317377124)

Синяя линия - сходимость на тренировочных данных, оранжевая - сходимость на тестовых, для функции активации 𝑠𝑖𝑔𝑚𝑜𝑖𝑑, тики дневные.


![image](https://github.com/user-attachments/assets/8b8df979-0537-432d-99e1-100a9be86097)

Синяя линия - сходимость на тренировочных данных, оранжевая - сходимость на тестовых, для функции активации 𝑐𝑙𝑜𝑔𝑙𝑜𝑔, тики дневные


![image](https://github.com/user-attachments/assets/6218f7a3-a98c-41af-882a-7080ec8e0a86)

Синяя линия - сходимость на тренировочных данных, оранжевая - сходимость на тестовых, для функции активации 𝑙𝑜𝑔𝑙𝑜𝑔, тики дневные.


![image](https://github.com/user-attachments/assets/e2e0cb44-a714-465d-8d17-defd8ad31a12)

График цен BTC-USD. Синим обозначены все настоящие значения, оранжевым – тренировочная часть, зеленым – тестовая. Видно, что прогноз с использованием 𝑅𝑒𝐿𝑈 при маленьком значении параметра 𝑢𝑛𝑖𝑡𝑠 крайне неточен.


![image](https://github.com/user-attachments/assets/382d8f14-a05d-4426-8328-416c8a23ec90)

Минутные тики. График метрик регрессии на тренировочном датасете в зависимости от параметра 𝑢𝑛𝑖𝑡𝑠. Здесь и далее часть значений для 𝑅𝑒𝐿𝑈 не отображается, чтобы не нарушать масштаб.


![image](https://github.com/user-attachments/assets/02a19b4e-54ee-4355-85ea-c5f654d9f55c)

Минутные тики. График метрик регрессии на тестовом датасете в зависимости от параметра 𝑢𝑛𝑖𝑡𝑠. Здесь и далее часть значений для 𝑅𝑒𝐿𝑈 не отображается, чтобы не нарушать масштаб.


![image](https://github.com/user-attachments/assets/3e7a08f7-8ee9-47d5-a9c3-ab0263e26fce)

Часовые тики. График метрик регрессии на тренировочном датасете в зависимости от параметра 𝑢𝑛𝑖𝑡𝑠. Часть «плохих» значений для 𝑅𝑒𝐿𝑈 не отображается, чтобы не нарушать масштаб.


![image](https://github.com/user-attachments/assets/4b0c35b0-482c-474b-b727-346c470624a8)

Часовые тики. График метрик регрессии на тестовом датасете в зависимости от параметра 𝑢𝑛𝑖𝑡𝑠. Часть «плохих» значений для 𝑅𝑒𝐿𝑈 не отображается, чтобы не нарушать масштаб.


![image](https://github.com/user-attachments/assets/fe4a3fe4-b7d3-4b64-969f-2c1e24b361d2)

Дневные тики. График метрик регрессии на тренировочном датасете в зависимости от параметра 𝑢𝑛𝑖𝑡𝑠. Часть «плохих» значений для 𝑅𝑒𝐿𝑈 не отображается, чтобы не нарушать масштаб.


![image](https://github.com/user-attachments/assets/f5137afa-a8d5-4612-bb5c-03986ce13fb0)

Дневные тики. График метрик регрессии на тестовом датасете в зависимости от параметра 𝑢𝑛𝑖𝑡𝑠. Часть «плохих» значений для 𝑅𝑒𝐿𝑈 не отображается, чтобы не нарушать масштаб.


![image](https://github.com/user-attachments/assets/72ec04f6-87b7-47ff-a071-39616b552a1c)

Минутные тики. Время обучения нейросети.


![image](https://github.com/user-attachments/assets/9b8c916a-6d40-4400-9613-74eceee185c5)

Часовые тики. Время обучения нейросети.


![image](https://github.com/user-attachments/assets/04d7d108-09e5-4670-9262-2391a09c994f)

Дневные тики. Время обучения нейросети.

![image](https://github.com/user-attachments/assets/025d1df4-729c-47a9-b4da-f3059ae1030a)

Минутные тики. График метрик регрессии на тренировочном датасете в зависимости от параметра 𝑙𝑜𝑜𝑘𝑏𝑎𝑐𝑘


![image](https://github.com/user-attachments/assets/a3318cd8-17d1-448f-9cb0-c0f58e05fa82)

Минутные тики. График метрик регрессии на тестовом датасете в зависимости от параметра 𝑙𝑜𝑜𝑘𝑏𝑎𝑐𝑘


![image](https://github.com/user-attachments/assets/1d8d51cc-31c6-44e5-9964-acc5957b3b93)

Часовые тики. График метрик регрессии на тренировочном датасете в зависимости от параметра 𝑙𝑜𝑜𝑘𝑏𝑎𝑐𝑘


![image](https://github.com/user-attachments/assets/54f5f7a0-a8be-4f41-b5a9-03cd0a7c9ad0)

Часовые тики. График метрик регрессии на тестовом датасете в зависимости от параметра 𝑙𝑜𝑜𝑘𝑏𝑎𝑐𝑘


![image](https://github.com/user-attachments/assets/c14ddb80-ccdf-41af-94f4-2313c013e742)

Дневные тики. График метрик регрессии на тренировочном датасете в зависимости от параметра 𝑙𝑜𝑜𝑘𝑏𝑎𝑐𝑘


![image](https://github.com/user-attachments/assets/7d8f9e13-571e-4b01-ab98-b18f4bec2a19)

Дневные тики. График метрик регрессии на тестовом датасете в зависимости от параметра 𝑙𝑜𝑜𝑘𝑏𝑎𝑐𝑘


![image](https://github.com/user-attachments/assets/8dfe6425-9829-46a0-9ad1-3d4db308b028)

Минутные тики. Время обучения нейросети.


![image](https://github.com/user-attachments/assets/2752853d-b73c-4862-9c7d-694261f4c5d7)

Часовые тики. Время обучения нейросети.


![image](https://github.com/user-attachments/assets/1d33fa44-7cdb-4897-9be2-316251977c8f)

Дневные тики. Время обучения нейросети.
