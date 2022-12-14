# JBR_test_2022_oct

#### Почему выбрана именно эта тема? 

Сама задача классификации звучит для меня очень интересно с точки зрения реализации и выявления признаков у данных. Также в курсе "Цифровой обработки сигнала" мы учимся по сигналу получать различные данные диктора, в том числе решали задачи классификации и мне стало очень интересно решать задачи такого вида. 

#### Про выполненную работу 

Код в большей своей степени реализован с помощью PyTorch с применением оберток для моделей. 
Реализован классификатор на основе модели BERT 'bert-base-uncased'. Смотря на результаты классификации, можно сказать, что результаты достигнуты чуть хуже, чем в статье  "Multi-label Classification of Commit Messages using Transfer Learning", но не значительно хуже.

Также рассматривал реализацию на основе модели 'distilbert-base-uncased', которая показала результаты получше, чем обычный 'bert'.

##### distilBert
![](img/distil_bert_1.png)
![](img/distil_bert_2.png)

##### Bert
![](img/bert_1.png)
![](img/bert_2.png)
### Выводы-полувыводы 

На мой взгляд требования, приписанные к каждому классу в статье, довольно жесткие, к ним либо можно добавить какие-либо условия, либо ослабить. 

Я также не успел поиграть с параметрами -- batch_size, n_epochs, и выявить для них закономерности, также не все метрики проверил. 

Также проверил работу классификатора на коммитах из своего репозитория (не могу сказать, что все сообщения супер содержательные), и в целом с большей части распределения по классам я согласен, хотя, на мой в взгляд, для некоторых явных случаев точности недостаточно (вполне скорее всего из-за того, что мы обучались на довольно малом количестве данных):
> "adding first AS with some basic screens"
>
>Corrective: 0.02807340957224369
Adaptive: 0.6855127215385437
Perfective: 0.24234390258789062



Однако все эти нюансы в той или иной степени были также указаны в статье. 
