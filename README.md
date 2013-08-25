world_city_names_russian
========================
<h1>Описание</h1>

<h2>Что это?</h2>

<p>Файлы формата seeds.rb для Ruby on Rails, содержащие связанные между собой крупнейшие страны и города мира на русском языке. 105 стран, 10306 городов. Используется, например, на веб-анализаторе мнений <a href="http://brainlook.org/">Brainlook</a>.</p>

<h2>Зачем это?</h2>

<p>Позволяет посредством ввода пары простых команд наполнить базу любой структуры странами и городами. </p>

<h2>Кому это надо?</h2>

<p>Любому Ruby on Rails разработчику, который собирается добавить на свой проект выбор стран и городов для пользователей на русском языке.</p>

<h2>В чем преимущества?</h2>

<p>Очень простая структура - нет ничего лишнего. У каждого города есть страна. Отсутствуют повторы. Благодаря формату seed, эти данные могут быть одинаково легко интегрированы в любой тип БД.</p>

<h2>Так какая же структура?</h2>

<pre><code>table "cities"
  t.string   "name"
  t.integer  "country_id"
end
</code></pre>

<pre><code>table "countries"
  t.string   "name"
end
</code></pre>

<h2>Пример записей:</h2>

<p><code>&lt;City id: 173, name: "Санкт-Петербург", country_id: 1, created_at: "2013-08-25 10:13:39", updated_at: "2013-08-25 10:13:39"&gt;</code></p>

<p><code>&lt;Country id: 105, name: "Япония", created_at: "2013-08-25 10:13:37", updated_at: "2013-08-25 10:13:37"&gt;</code></p>

<h1>Использование</h1>

<p>Предположим, у вас в проекте еще отсутствуют таблицы Cities и Countries.</p>

<ol>
<li>
<p>Создаем файлы для таблиц командой в терминале:</p>

<p><code>rails g scaffold Country name:string</code></p>

<p><code>rails g scaffold City name:string country_id:integer</code></p>
</li>
<li>
<p>Прогоняем миграции для добавления таблиц к базе</p>

<p><code>rake db:migrate</code></p>
</li>
<li>
<p>Скачиваем файл seeds.rb и меняем на свой. Либо скачиваем cities.seeds.rb и countries.seeds.rb , копируем их содержимое в файл seeds.rb своего проекта и в первую строчку вставляем </p>

<p><code># encoding: utf-8</code></p>
</li>
<li>
<p>Прогоняем сид</p>

<p><code>rake db:seed</code></p>
</li>
</ol><p>Готово, вы восхитительны!</p>
<p>Оставьте свое впечатление на <a href="http://brainlook.org/">Brainlook</a></p>
