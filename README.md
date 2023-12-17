:heart: **Проект "CHANGE_MY_DOC"
Маркеева Анастасия и Маньков Александр
РАНХиГС | ИОМ | ФИМ | УФТ | 1 курс**
***
**:star:Данный скрипт позволяет изменить в пяти документах**:
- [x] *шрифт - "Times New Roman"*
- [x] *размер шрифта 14*
- [x] *межстрочный интервал 1,5*
- [x] *при использовании библиотеки python-docx*
***
**:boom:Для того, чтобы использовать данный скрипт, необходимо скачать 5 файлов doxc, а также пакеты функцтй Pt, WD_PARAGRAPH_ALIGNMENT**
***
Начало работы - импорт пакетов функций, которые будут необохдимы в процессе создания скрипта, создание функции, а также открытие файла.
***
 ```python
from docx import Document
from docx.shared import Pt
from docx.enum.text import WD_PARAGRAPH_ALIGNMENT*

def update_docx(file_path):

    #открыть документ
    doc = Document(file_path)
```
***
Далее с помощью цикла с применением функций меняем шрифт на "Times New Roman", размер шрифта на 14, а также создаем выравнивание.
***
 ```python
    for paragraph in doc.paragraphs:
        for run in paragraph.runs:
            run.font.name = "Times New Roman"
            run.font.size = Pt(14)
        paragraph.paragraph_format.line_spacing = Pt(14)
        paragraph.paragraph_format.alignment = WD_PARAGRAPH_ALIGNMENT.LEFT

    #сохранение
    doc.save(file_path)
  ```
***
Далее мы создаем список из пяти файлов и создаем цикл, с помощью которого к каждому файлу в списке будет применяться функция.
***
```python
files_to_update = ["1.docx", "2.docx", "3.docx", "4.docx", "5.docx"]

for file_path in files_to_update:
    update_docx(file_path)
```
***
И после действия нашей функции, для обозначения исправного функционирования, выводим на экран информацию об успешном обновлении каждого файла.
***
```python
    print("Файл обновлен: ", file_path)
```
***
И на этом - все. Спасибо за внимание, дорогой Никита Игоревич! Для вас старались Анастасия и Александр.
