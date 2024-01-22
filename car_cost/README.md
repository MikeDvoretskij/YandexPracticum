<section class="theory-viewer__blocking-layout-block theory-viewer__block theory-viewer__block_type_vertical-layout theory-viewer__block_layout"><section class="theory-viewer__block theory-viewer__block_type_markdown"><div class="Markdown base-markdown base-markdown_with-gallery markdown markdown_size_normal markdown_type_theory full-markdown"><h1>Определение стоимости автомобилей</h1><div class="paragraph">Поздравляем! Вы прошли курс в тренажёре. Самое время проверить знания и решить новую задачу машинного обучения. Выполнять работу будете самостоятельно.  </div><div class="paragraph">Когда закончите, отправьте её на проверку ревьюеру: он пришлёт комментарии в течение суток. После этого нужно доработать проект и пройти повторную проверку. </div><div class="paragraph">Скорее всего, вы будете дорабатывать кейс по комментариям ещё несколько раз. Это нормально. </div><div class="paragraph">Проект завершён, когда ревьюер одобрит все доработки. </div><h2>Описание проекта</h2><div class="paragraph">Сервис по продаже автомобилей с пробегом «Не бит, не крашен» разрабатывает приложение, чтобы привлечь новых клиентов. В нём можно будет узнать рыночную стоимость своего автомобиля. </div><div class="paragraph">Постройте модель, которая умеет её определять. В вашем распоряжении данные о технических характеристиках, комплектации и ценах других автомобилей.</div><div class="paragraph">Критерии, которые важны заказчику:</div><ul><li>качество предсказания;</li><li>время обучения модели;</li><li>время предсказания модели.</li></ul><h3>Инструкция по выполнению проекта</h3><div class="paragraph">Чтобы усилить исследование, не ограничивайтесь градиентным бустингом. Попробуйте более простые модели — иногда они работают лучше. Эти редкие случаи легко пропустить, если всегда применять только бустинг. </div><div class="paragraph">Поэкспериментируйте и сравните характеристики моделей: время обучения, время предсказания, точность результата.</div><h3>Основные шаги:</h3><ol start="1"><li>Загрузите данные, путь к файлу:  <code class="code-inline code-inline_theme_light">/datasets/autos.csv</code>.</li><li>Изучите данные. Заполните пропущенные значения и обработайте аномалии в столбцах. Если среди признаков имеются неинформативные, удалите их.</li><li>Подготовьте выборки для обучения моделей.</li><li>Обучите разные модели, одна из которых — LightGBM, как минимум одна — не бустинг. Для каждой модели попробуйте разные гиперпараметры.</li><li>Проанализируйте время обучения, время предсказания и качество моделей.</li><li>Опираясь на критерии заказчика, выберете лучшую модель, проверьте её качество на тестовой выборке.</li></ol><div class="paragraph">Примечания:</div><ul><li>Для оценки качества моделей применяйте метрику&nbsp;RMSE.</li><li>Значение метрики&nbsp;RMSE&nbsp;должно быть меньше 2500.</li><li>Самостоятельно освойте библиотеку&nbsp;LightGBM&nbsp;и её средствами постройте модели градиентного бустинга.</li><li>Время выполнения ячейки кода&nbsp;Jupyter Notebook&nbsp;можно получить специальной командой. Найдите её.</li><li>Модель градиентного бустинга может долго обучаться, поэтому измените у неё только два-три параметра.</li><li><div class="paragraph">Если перестанет работать&nbsp;Jupyter Notebook, удалите лишние переменные оператором&nbsp;<code class="code-inline code-inline_theme_light">del</code>.</div><div class="python code-block code-block_theme_light"><div class="code-block__tools"><button class="code-block__clipboard" type="button">Скопировать код</button><span class="code-block__lang">PYTHON</span></div><div class="scrollable-default scrollable scrollable_theme_light code-block__scrollable"><div></div><div class="scrollable__content-wrapper"><div class="scrollbar-remover scrollable__content-container" tabindex="0" style="--scroll-bar-width: 18px; --scroll-bar-height: 18px;"><div class="scrollable__content"><pre class="code-block__code-wrapper"><code class="code-block__code python"><span class="hljs-keyword">del</span> features_train </code></pre><div></div></div></div></div><section class="scrollbar-default scrollbar scrollbar_vertical scrollbar_hidden scrollable__scrollbar scrollable__scrollbar_type_vertical" style="--scrollbar-offset-size: 36px; --scrollbar-control-size: 36px; --scrollbar-control-container-size: 100%; --scrollbar-scale: 1; --scrollbar-control-offset: 0;" size="1"><div class="scrollbar__control-container"><div class="scrollbar__control"><div class="scrollbar__control-line"></div></div></div></section><section class="scrollbar-default scrollbar scrollbar_horizontal scrollbar_hidden scrollable__scrollbar scrollable__scrollbar_type_horizontal" style="--scrollbar-offset-size: 641px; --scrollbar-control-size: 641px; --scrollbar-control-container-size: 100%; --scrollbar-scale: 1; --scrollbar-control-offset: 0;" size="1"><div class="scrollbar__control-container"><div class="scrollbar__control"><div class="scrollbar__control-line"></div></div></div></section></div></div></li></ul><h3>Описание данных</h3><div class="paragraph">Данные находятся в файле <code class="code-inline code-inline_theme_light">/datasets/autos.csv</code>. <a href="https://code.s3.yandex.net/datasets/autos.csv" target="_blank">Скачать датасет</a>. </div><div class="paragraph"><strong>Признаки</strong></div><ul><li><em>DateCrawled</em> — дата скачивания анкеты из базы</li><li><em>VehicleType</em> — тип автомобильного кузова</li><li><em>RegistrationYear</em> — год регистрации автомобиля</li><li><em>Gearbox</em> — тип коробки передач</li><li><em>Power</em> — мощность (л. с.)</li><li><em>Model</em> — модель автомобиля</li><li><em>Kilometer</em> — пробег (км)</li><li><em>RegistrationMonth</em> — месяц регистрации автомобиля</li><li><em>FuelType</em> — тип топлива</li><li><em>Brand</em> — марка автомобиля</li><li><em>Repaired</em> — была машина в ремонте или нет</li><li><em>DateCreated</em> — дата создания анкеты</li><li><em>NumberOfPictures</em> — количество фотографий автомобиля</li><li><em>PostalCode</em> — почтовый индекс владельца анкеты (пользователя)</li><li><em>LastSeen</em> — дата последней активности пользователя</li></ul><div class="paragraph"><strong>Целевой признак</strong></div><div class="paragraph"><em>Price</em> — цена (евро)</h2></section></section>