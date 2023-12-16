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
*#начало работы
from docx import Document
from docx.shared import Pt
from docx.enum.text import WD_PARAGRAPH_ALIGNMENT*

def update_docx(file_path):
 ```python 
    #открыть документ
    doc = Document(file_path)
  
    #установка шрифта, размера и межстрочного интервала 
    for paragraph in doc.paragraphs:
        for run in paragraph.runs:
            run.font.name = "Times New Roman"
            run.font.size = Pt(14)
        paragraph.paragraph_format.line_spacing = Pt(14)
        paragraph.paragraph_format.alignment = WD_PARAGRAPH_ALIGNMENT.LEFT
      
    #сохранение
    doc.save(file_path)
  
files_to_update = ["1.docx", "2.docx", "3.docx", "4.docx", "5.docx"]

for file_path in files_to_update:
    update_docx(file_path)
  
    print("Файл обновлен: ", file_path)
```
