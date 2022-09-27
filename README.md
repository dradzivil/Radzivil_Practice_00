![Python](https://i2ds.org/wp-content/uploads/2020/03/python-faq-670x335-1.jpg)

# Занятие #00. Введение

Цель данного задания &ndash; познакомить вас с форматом, в котором будут проходить семинары и проверяться домашние
задания, а также дать вам возможность поразбираться с Git и GitHub.

# Основные правила

1. Задание для каждого семинара/домашнего задания будет описано в [`README`](README.md)
   соответствующего репозитория и частично продублировано в файлах `tasks/*/*.py`
2. Можно и нужно редактировать файлы, расположенные в папке [`tasks`](tasks), имена которых не содержат слово `test`
   &ndash; это шаблоны для решения заданий
3. Не обращайте внимание на файлы `__init__.py` &ndash; они вам не понадобятся
4. :grey_exclamation: Нельзя редактировать файлы, содержащие в названии слово `test`, *если в явном виде не указано
   обратное*. На данный момент это проверяется преподавателями вручную, однако в будущем этим будет заниматься отдельный
   скрипт
5. :grey_exclamation: Нельзя редактировать файлы, расположенные в папке [`.github`](.github), аналогично предыдущему
   пункту

# Задание

## 1. Настройка Git и GitHub

1. Установите систему контроля версий [Git](https://git-scm.com/downloads)
    * Вам *не понадобятся* графические оболочки для гита
2. ~~Зарегистрируйтесь (если еще нет) на [GitHub](https://github.com)~~
3. Создайте SSH-ключ для доступа к своим репозиториям
    * Воспользуйтесь Git Bash, который должен был установиться вместе с Git, если вы используете Windows
    * Вам может
      помочь [эта страница](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/about-ssh)
    * Никогда не давайте никому свой приватный ключ!

Вместо доступа по SSH *раньше можно использовать доступ по HTTPS*, однако авторизация через пароль больше не
поддерживается. Альтернативный вариант, чтобы не генерировать ключ &ndash; подключить PyCharm (см. далее) напрямую к
GitHub через access token.

## 2. Установка языка и среды

1. Установите [Python 3.8](https://www.python.org/downloads/)
    * Убедитесь, что `python` или `python3` можно вызвать из командной строки
    * На всякий случай обновите пакетный менеджер `pip` (для этого придется запустить скрипт от имени администратора) с
      помощью команды `python -m pip install --upgrade pip`
2. Установите среду программирования [PyCharm](https://www.jetbrains.com/pycharm/)
    * Если вы уже получили университетские почты, выбирайте Professional Edition
    * Получить доступ к университетской почте можно в ИСУ: Главная страница -> Быстрые сервисы (раздел справа):
        * "Настроить MS Office 365 и почту @niuitmo.ru"
        * "Открыть почту niuitmo.ru"

## 3. Работа с этим репозиторием

Два пути работы с Git, выберите тот, который вам наиболее удобен:

### Консольный путь

1. Скопируйте SSH-адрес этого репозитория, ниже видно как его можно найти
   ![SSH address](https://i.ibb.co/Zf9cfWy/download.png)
2. Склонируйте этот репозиторий, создайте новую ветку `practice` и перейдите на нее:

```shell
git clone [repo-address]
cd [repo-name]
git checkout -b practice
```

3. В PyCharm создайте откройте склонированный репозиторий как проект
4. В папке [`tasks/helloworld`](tasks/helloworld) создайте новый файл `helloworld.py`, на предложение добавить его в
   систему контроля версий *
   откажитесь*
5. Заполните файл содержимым

```python
print('Hello World!')
```

6. Добавьте новый файл в систему контроля версий и сделайте коммит:

```shell
git add tasks/helloworld/helloworld.py
git commit -m "Hello World!"
```

7. Запишите сделанные вами изменения в репозиторий на GitHub (для всех последующих обновлений репозитория можно
   использовать просто `git push`):

```shell
git push -u origin practice
```

### Путь IDE

1. Склонируйте этот репозиторий через меню "Git &rightarrow; Clone..." в Pycharm
    * Если планируете использовать этот же способ и дальше, имеет смысл подключить PyCharm к аккаунту на GitHub через
      access tokens, подробнее &ndash; [здесь](https://www.jetbrains.com/help/pycharm/github.html)
    * Или же можно воспользоваться пунктом 1 из консольного пути и скопировать ssh-адрес
2. Создайте новую ветку `practice` через меню "Git &rightarrow; New Branch"
    * Через "Git &rightarrow; Branches" убедитесь, что вы находитесь на новой ветке
3. В папке [`tasks/helloworld`](tasks/helloworld) создайте новый файл `helloworld.py`, на предложение добавить его в
   систему контроля версий *согласитесь*
4. Заполните файл содержимым

```python
print('Hello World!')
```

5. Сделайте коммит через то же меню Git или `Ctrl + K`, укажите сообщение к коммиту "Hello World!"
    * Если вы не подвержали добавление файла в систему контроля версий, отметьте его добавление в левом меню
6. Запишите сделанные вами изменения в репозиторий на GitHub (`Ctrl + Shift + K`)
    * Убедитесь, что вы записываете из локальной ветки `practice` в `origin:practice`

## 3.5. Убедитесь, что все работает

1. Не возникло никаких ошибок по мере выполнения задания
2. Автоматическая проверка в GitHub Classroom показала, что первый тест (`Test 00. Hello World!`) пройден

Если что-то пошло не так &ndash; спрашивайте преподавателя.

## 4. Выполните оставшиеся задания

### 4.1. Fix me!

Откройте файл [`tasks/fixme/fixme.py`](tasks/fixme/fixme.py). Сейчас код, написанный в нем, не работает по множеству
причин. Ваша задача &ndash; исправить все ошибки в коде, чтобы получить программу, считывающую три целых числа и
печатающее среднее из них по значению.

После выполнения задания сделайте коммит *с осмысленным сообщением в `-m`* и сделайте `git push` в репозиторий. Если
все верно, тесты с `Test 01` по `Test 10` должны стать отмечены как пройденные.

### 4.2. Сложение дробей

Откройте файл [`tasks/fractions/fractions.py`](tasks/fractions/fractions.py). В нем находится шаблон функции,
принимающей 4 целых аргумента и возвращающей пару из двух целых чисел. Допишите тело функции так, чтобы `f(a, b, c, d)`
возвращала такую пару `(x, y)`
, что

1. a/b + c/d = x/y
2. x/y &ndash; несократимая дробь
3. y > 0

После выполнения задания сделайте коммит *с осмысленным сообщением в `-m`* и сделайте `git push` в репозиторий. Если
все верно, `Test 11. Fractions` должен стать отмечен как пройденный.

## 5. Pull Request

После того, как вы выполните все задания, сделайте Pull Request на объединение веток `practice` и `main`. В комментарии
к PR можете оставить ваши идеи по поводу того, что можно улучшить в этом задании или любые другие впечатления.

В общем случае обсуждение, привязанное к PR, будет использоваться для получения вами фидбека от преподавателей по вашему
решению.
