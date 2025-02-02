# everything-recognition
Программа для распознавания объектов через веб-камеру с использованием компьютерного зрения. Позволяет конфигурировать распознаваемые объекты и выделять их в цветную рамку.  

# Установка
Вам понадобится установленный Python 3.4-3.7 и git

Склонируйте репозиторий
```bash
$ git clone https://github.com/valeriy131100/everything-recognition
```

Создайте в этой папке виртуальное окружение
```bash
$ python3 -m venv [полный путь до папки everything-recognition]
```

Активируйте виртуальное окружение и установите зависимости
```bash
$ cd everything-recognition
$ source bin/activate
$ pip install -r requirements.txt
```
# Использование
## Запуск и работа с программой
Находясь в директории everything-recognition исполните
```bash
$ bin/python run.py
```
Программа покажет окно с изображением с вашей веб-камеры, либо сообщит о том, что не смогла её найти. Если программа найдет в изображении с веб-камеры объект, то выделит его в рамку заданного цвета.
 
 Для того, чтобы завершить работу программы, нажмите на клавиатуре клавишу "q".
## Настройка
Все настройки программы находятся в файле config.py

Настройки представляют собой словарь словарей CASCADES
```python
CASCADES = {
    ...
    "Face profile": {
        "path": "haarcascades/faces/haarcascade_profileface.xml",
        "color": (255, 0, 0),
        "draw": True
    },
    ...
}
```
Ключом словаря указывается имя для объекта распознавания, а в значении-словаре перечисляются параметры:
* path - путь до .xml модели
* color - цвет рамки вокруг распознаваемого объекта, задается в виде кортежа RGB
* draw - отрисовывать ли рамку вокруг данного объекта

Предустановленные xml-модели можно найти в папке haarcascades в директории с программой.
