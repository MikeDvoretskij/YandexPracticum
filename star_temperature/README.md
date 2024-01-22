<section class="theory-viewer__block theory-viewer__block_type_markdown"><div class="Markdown base-markdown base-markdown_with-gallery markdown markdown_size_normal markdown_type_theory full-markdown"><h2><strong>Прогнозирование температуры звезды</strong></h2><div class="paragraph">Вам пришла задача от обсерватории «Небо на ладони»: придумать, как с помощью нейросети определять температуру на поверхности обнаруженных звёзд. Обычно для расчёта температуры учёные пользуются следующими методами:</div><ul><li>Закон смещения Вина.</li><li>Закон Стефана-Больцмана.</li><li>Спектральный анализ.</li></ul><div class="paragraph">Каждый из них имеет плюсы и минусы. Обсерватория хочет внедрить технологии машинного обучения для предсказания температуры звёзд, надеясь, что этот метод будет наиболее точным и удобным.</div><div class="paragraph">В базе обсерватории есть характеристики уже изученных 240 звёзд.</div><h2><strong>Характеристики</strong></h2><ul><li>Относительная светимость&nbsp;<code class="code-inline code-inline_theme_light">L/Lo</code> — светимость звезды относительно Солнца.</li><li>Относительный радиус&nbsp;<code class="code-inline code-inline_theme_light">R/Ro</code> — радиус звезды относительно радиуса Солнца.</li><li>Абсолютная звёздная величина&nbsp;<code class="code-inline code-inline_theme_light">Mv</code> — физическая&nbsp;величина, характеризующая блеск звезды.</li><li>Звёздный цвет&nbsp;(<code class="code-inline code-inline_theme_light">white</code>, <code class="code-inline code-inline_theme_light">red</code>, <code class="code-inline code-inline_theme_light">blue</code>, <code class="code-inline code-inline_theme_light">yellow</code>, <code class="code-inline code-inline_theme_light">yellow-orange</code> и др.) — цвет звезды, который определяют на основе спектрального анализа.</li><li><div class="paragraph">Тип звезды.</div><div class="table" style="--max-table-height: 400px;"><div class="scrollable-default scrollable scrollable_theme_light table__wrapper"><div></div><div class="scrollable__content-wrapper"><div class="scrollbar-remover scrollable__content-container" tabindex="0" style="--scroll-bar-width: 16px; --scroll-bar-height: 16px;"><div class="scrollable__content"><table cellpadding="0" cellspacing="0"><thead><tr><th scope="col">Тип звезды</th><th scope="col">Номер, соответствующий типу</th></tr></thead><tbody><tr><td>Коричневый карлик</td><td>0</td></tr><tr><td>Красный карлик</td><td>1</td></tr><tr><td>Белый карлик</td><td>2</td></tr><tr><td>Звёзды главной последовательности</td><td>3</td></tr><tr><td>Сверхгигант</td><td>4</td></tr><tr><td>Гипергигант</td><td>5</td></tr></tbody></table><div></div></div></div></div><section class="scrollbar-default scrollbar scrollbar_vertical scrollbar_hidden scrollable__scrollbar scrollable__scrollbar_type_vertical" style="--scrollbar-offset-size: 263px; --scrollbar-control-size: 263px; --scrollbar-control-container-size: 100%; --scrollbar-scale: 1; --scrollbar-control-offset: 0;" size="1"><div class="scrollbar__control-container"><div class="scrollbar__control"><div class="scrollbar__control-line"></div></div></div></section><section class="scrollbar-default scrollbar scrollbar_horizontal scrollbar_hidden scrollable__scrollbar scrollable__scrollbar_type_horizontal" style="--scrollbar-offset-size: 641px; --scrollbar-control-size: 641px; --scrollbar-control-container-size: 100%; --scrollbar-scale: 1; --scrollbar-control-offset: 0;" size="1"><div class="scrollbar__control-container"><div class="scrollbar__control"><div class="scrollbar__control-line"></div></div></div></section></div></div></li><li><div class="paragraph">Абсолютная температура&nbsp;<code class="code-inline code-inline_theme_light">T(K)</code> — температура на поверхности звезды в Кельвинах.</div></li></ul><div class="paragraph">В этом самостоятельном проекте вам необходимо разработать нейронную сеть, которая поможет предсказывать абсолютную температуру на поверхности звезды.</div><div class="quiz-task" style="--quiz-task-background: var(--color-background-alternate); --quiz-task-color: var(--color-content-primary);"><div class="Markdown base-markdown base-markdown_with-gallery base-markdown markdown markdown_size_normal markdown_type_theory quiz-task__content">
<div class="paragraph">💡 Справочная информация:
 Светимость Солнца (англ. <em>Average Luminosity of Sun</em>)
 <span class="markdown-formula-wrapper"><span class="formula"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi>L</mi><mn>0</mn></msub><mo>=</mo><mn>3.828</mn><mo>⋅</mo><mn>1</mn><msup><mn>0</mn><mn>26</mn></msup> <mtext>Вт</mtext></mrow><annotation encoding="application/x-tex">L_0 = 3.828 \cdot 10^{26}\,Вт</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.83333em; vertical-align: -0.15em;"></span><span class="mord"><span class="mord mathdefault">L</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.301108em;"><span class="" style="top: -2.55em; margin-left: 0em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight">0</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.15em;"><span class=""></span></span></span></span></span></span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">=</span><span class="mspace" style="margin-right: 0.277778em;"></span></span><span class="base"><span class="strut" style="height: 0.64444em; vertical-align: 0em;"></span><span class="mord">3</span><span class="mord">.</span><span class="mord">8</span><span class="mord">2</span><span class="mord">8</span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mbin">⋅</span><span class="mspace" style="margin-right: 0.222222em;"></span></span><span class="base"><span class="strut" style="height: 0.814108em; vertical-align: 0em;"></span><span class="mord">1</span><span class="mord"><span class="mord">0</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">2</span><span class="mord mtight">6</span></span></span></span></span></span></span></span></span><span class="mspace" style="margin-right: 0.166667em;"></span><span class="mord cyrillic_fallback">В</span><span class="mord cyrillic_fallback">т</span></span></span></span></span></span>
 Радиус Солнца (англ. <em>Average Radius of Sun</em>) 
 <span class="markdown-formula-wrapper"><span class="formula"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi>R</mi><mn>0</mn></msub><mo>=</mo><mn>6.9551</mn><mo>⋅</mo><mn>1</mn><msup><mn>0</mn><mn>8</mn></msup> <mtext>м</mtext></mrow><annotation encoding="application/x-tex">R_0 = 6.9551\cdot 10^8\,м</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.83333em; vertical-align: -0.15em;"></span><span class="mord"><span class="mord mathdefault" style="margin-right: 0.00773em;">R</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.301108em;"><span class="" style="top: -2.55em; margin-left: -0.00773em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight">0</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.15em;"><span class=""></span></span></span></span></span></span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">=</span><span class="mspace" style="margin-right: 0.277778em;"></span></span><span class="base"><span class="strut" style="height: 0.64444em; vertical-align: 0em;"></span><span class="mord">6</span><span class="mord">.</span><span class="mord">9</span><span class="mord">5</span><span class="mord">5</span><span class="mord">1</span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mbin">⋅</span><span class="mspace" style="margin-right: 0.222222em;"></span></span><span class="base"><span class="strut" style="height: 0.814108em; vertical-align: 0em;"></span><span class="mord">1</span><span class="mord"><span class="mord">0</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight">8</span></span></span></span></span></span></span></span><span class="mspace" style="margin-right: 0.166667em;"></span><span class="mord cyrillic_fallback">м</span></span></span></span></span></span></div></div></div>
<h2><strong>Алгоритм решения задачи</strong></h2><h3><strong>Шаг 1.</strong> Загрузка исходных данных из файла</h3><div class="python code-block code-block_theme_light"><div class="code-block__tools"><button class="code-block__clipboard" type="button">Скопировать код</button><span class="code-block__lang">PYTHON</span></div><div class="scrollable-default scrollable scrollable_theme_light code-block__scrollable"><div></div><div class="scrollable__content-wrapper"><div class="scrollbar-remover scrollable__content-container" tabindex="0" style="--scroll-bar-width: 16px; --scroll-bar-height: 16px;"><div class="scrollable__content"><pre class="code-block__code-wrapper"><code class="code-block__code python">/datasets/<span class="hljs-number">6</span>_class.csv </code></pre><div></div></div></div></div><section class="scrollbar-default scrollbar scrollbar_vertical scrollbar_hidden scrollable__scrollbar scrollable__scrollbar_type_vertical" style="--scrollbar-offset-size: 36px; --scrollbar-control-size: 36px; --scrollbar-control-container-size: 100%; --scrollbar-scale: 1; --scrollbar-control-offset: 0;" size="1"><div class="scrollbar__control-container"><div class="scrollbar__control"><div class="scrollbar__control-line"></div></div></div></section><section class="scrollbar-default scrollbar scrollbar_horizontal scrollbar_hidden scrollable__scrollbar scrollable__scrollbar_type_horizontal" style="--scrollbar-offset-size: 689px; --scrollbar-control-size: 689px; --scrollbar-control-container-size: 100%; --scrollbar-scale: 1; --scrollbar-control-offset: 0;" size="1"><div class="scrollbar__control-container"><div class="scrollbar__control"><div class="scrollbar__control-line"></div></div></div></section></div></div><h3><strong>Шаг 2.</strong> Исследовательский анализ</h3><div class="paragraph">Проведите исследовательский анализ:</div><ul><li>количественных данных,</li><li>категориальных данных.</li></ul><div class="paragraph">Обязательно используйте графический анализ и сделайте вывод.</div><h3><strong>Шаг 3.</strong> Подготовка данных к построению модели</h3><ol start="1"><li>По результату исследовательского анализа внесите корректировки, если они нужны. Сделайте вывод.</li><li>Если необходимо, категоризируйте исходные данные.</li><li>Подготовьте обучающую и тестовую выборки.</li><li>Проведите масштабирование количественных данных.</li></ol><h3><strong>Шаг 4.</strong> Построение простой модели нейронной сети — baseline</h3><ol start="1"><li>Создайте класс для задания архитектуры нейронной сети.</li><li>Самостоятельно выберите количество скрытых слоёв, количество нейронов на них, функции активации на скрытых и выходном слоях. Попробуйте и сравните несколько подобных комбинаций.</li><li>Проведите обучение нейронной сети:
 <ul><li>Создайте функцию для обучения нейронной сети.</li><li>Проведите обучение модели.</li><li>Постройте график «Факт — Прогноз», где по горизонтальной оси будут отложены условные номера звёзд, а по вертикальной — температура в Кельвинах.</li></ul></li></ol><div class="paragraph"><div class="downloadable-image"><a class="downloadable-image__button" download="Image.png"><svg class="icon icon-arrows-24-download downloadable-image__icon" width="24" height="24" viewBox="0 0 24 24" fill="none"><path fill-rule="evenodd" clip-rule="evenodd" d="M12 3C11.45 3 11 3.45 11 4V10.9219C11 11.6763 11.0854 12.4276 11.254 13.1613L11.0483 13.3684L10.8331 13.0242C10.4323 12.3835 9.96022 11.7902 9.42583 11.2558L8.46 10.29C8.07 9.89999 7.44 9.89999 7.05 10.29C6.66 10.68 6.66 11.32 7.05 11.71L10.9404 15.5926C11.526 16.1769 12.474 16.1769 13.0596 15.5926L16.95 11.71C17.34 11.32 17.34 10.68 16.95 10.29C16.56 9.89999 15.93 9.89999 15.54 10.29L14.5742 11.2558C14.0398 11.7902 13.5677 12.3835 13.1669 13.0242L12.9517 13.3684L12.746 13.1613C12.9146 12.4276 13 11.6763 13 10.9219V4C13 3.45 12.55 3 12 3ZM7 19C6.44772 19 6 19.4477 6 20C6 20.5523 6.44772 21 7 21H17C17.5523 21 18 20.5523 18 20C18 19.4477 17.5523 19 17 19H7Z" fill="currentColor" fill-opacity="0.85"></path></svg></a><img src="https://pictures.s3.yandex.net:443/resources/Untitled_79_1651780526.png" alt="image" crossorigin="anonymous" class="image image_expandable"></div></div><ul><li>Сделайте вывод.</li></ul><h3><strong>Шаг 5.</strong> Улучшение сети</h3><ul><li>Создайте решение с перебором параметров нейросети. Список параметров для перебора должен включать как минимум «dropout» и «размер батча». Архитектуру нейронной сети: количество слоёв, нейронов, вид функции активации — оставьте как в <em>Baseline</em>, чтобы сравнить результат.</li><li>Проведите обучение нейронной сети. Выведите метрику RMSE и график «Факт — прогноз». Метрика RMSE не должна превышать 4500.</li><li><div class="paragraph">Сделайте вывод. Желательно оформить его в виде таблицы или графика.</div></li></ul><h3>Шаг 6. Выводы по проекту</h3><ul><li>Кратко опишите результаты каждого типа модели.</li><li>Напишите выводы сравнения двух моделей.</li></ul></div></section>