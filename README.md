# `nure_tools python library`

> **Warning**
> The library is still under development. I will be happy to receive any feedback, and you can feel free to improve my code

> Simple pyton library for nure-dev API
> (Python 3.10+)

****************************************************************

## Installation

### for linux
```shell
git clone https://github.com/SoappGuy/nure_tools.git && cd ./nure_tools && python -m pip install -e .
```

### for windows
```shell
git clone https://github.com/SoappGuy/nure_tools.git ; cd ./nure_tools ; python -m pip install -e .
```
****************************************************************

# Examples
> for more examples see [examples.py file](https://github.com/SoappGuy/nure_tools/blob/master/examples.py)


# Functions

### Get auditoriums

> [Reference](https://nure-dev.pp.ua/#%D0%B7%D0%B0%D0%BF%D0%B8%D1%82-%D0%BD%D0%B0-%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D1%96%D1%97)

**Example:**

```python
import nure_tools
from pprint import pprint

auditories = nure_tools.get_auditories()
pprint(auditories)    
```

**Output:**

```ts
[{'id': '172', 'name': '___0'},
 {'id': '3931027', 'name': '285'},
 {'id': '97', 'name': '287'},
 ...
 ...
  {'id': '169', 'name': '165-6'},
 {'id': '1675427', 'name': '166вц'},
 {'id': '170', 'name': '167вц'}]
```

****************************************************************

### Get groups

> [Reference](https://nure-dev.pp.ua/#%D0%B7%D0%B0%D0%BF%D0%B8%D1%82-%D0%BD%D0%B0-%D0%B3%D1%80%D1%83%D0%BF%D0%B8)

**Example:**

```python
import nure_tools
from pprint import pprint

groups = nure_tools.get_groups()
pprint(groups)
```

**Output:**

```ts
[{'id': '6949796', 'name': 'ЕЕК-18-1'},
 {'id': '7310687', 'name': 'ЕЕКи-18-1'},
 ...
 ...
 {'id': '10486626', 'name': 'ЕЕКі-22-1'},
 {'id': '11106524', 'name': 'ЕЕКі-23-1'}]
```

****************************************************************

### Find a group

**Example:**

```python
import nure_tools

print(nure_tools.find_group("пзпі-23-2"))
```

**Output:**

```ts
{'id': '10887378', 'name': 'ПЗПІ-23-2'}
```

****************************************************************

### Get teachers

> [Reference](https://nure-dev.pp.ua/#%D0%B7%D0%B0%D0%BF%D0%B8%D1%82-%D0%BD%D0%B0-%D0%B2%D0%B8%D0%BA%D0%BB%D0%B0%D0%B4%D0%B0%D1%87%D1%96%D0%B2)

**Example:**

```python
import nure_tools
from pprint import pprint

teachers = nure_tools.get_teachers()
pprint(teachers)

```

**Output:**

```ts
[{'full_name': 'Боцюра Олеся Анатоліївна', 'id': '5343992', 'short_name': 'Боцюра О. А.'},
 {'full_name': 'Бутенко Ніна Семенівна', 'id': '1810189', 'short_name': 'Бутенко Н. С.'},
 ...
 ...
 {'full_name': 'Бабкова Н І', 'id': '7605119', 'short_name': 'Бабкова Н. І.'},
 {'full_name': 'Карпенко К І', 'id': '8769045', 'short_name': 'Карпенко К. І.'}]
```

****************************************************************

### Find a teacher

**Example:**

```python
import nure_tools
from pprint import pprint

pprint(nure_tools.find_teacher("Новіков"))
```

**Output:**

```ts
[{'full_name': 'Новіков Олексій Валентинович',
  'id': '7278549',
  'short_name': 'Новіков О. В.'},
 {'full_name': 'Новіков Юрій Сергійович',
  'id': '2145721',
  'short_name': 'Новіков Ю. С.'}]
```

****************************************************************

### Get schedule

> [Reference](https://nure-dev.pp.ua/#%D0%B7%D0%B0%D0%BF%D0%B8%D1%82-%D0%BD%D0%B0-%D1%80%D0%BE%D0%B7%D0%BA%D0%BB%D0%B0%D0%B4)

**Example:**

```python
import nure_tools
from pprint import pprint

schedule = nure_tools.get_schedule('group',
                                    nure_tools.get_group_id("пзпі-23-2"),
                                    "2023-09-13",
                                    "2023-09-14"
                                    )


pprint(schedule)


```

**Output:**

```ts
[{'auditory': '424',
  'end_time': '1694592300',
  'groups': [{'id': '10887378', 'name': 'ПЗПІ-23-2'}],
  'id': '20596',
  'number_pair': 2,
  'start_time': '1694586600',
  'subject': {'brief': 'Фіз', 'id': '1021372', 'title': 'Фізика'},
  'teachers': [{'full_name': 'Стороженко Володимир Олександрович',
                'id': '584',
                'short_name': 'Стороженко В. О.'}],
  'type': 'Лк',
  'updatedAt': '2023-09-04T23:35:05.222Z'},
 {'auditory': '103і',
  'end_time': '1694586000',
  'groups': [{'id': '10887378', 'name': 'ПЗПІ-23-2'}],
  'id': '20595',
  'number_pair': 1,
  'start_time': '1694580300',
  'subject': {'brief': 'ВМ', 'id': '1021413', 'title': 'Вища математика'},
  'teachers': [{'full_name': 'Литвин Олександра Григорівна',
                'id': '950',
                'short_name': 'Литвин О. Г.'}],
  'type': 'Лк',
  'updatedAt': '2023-09-04T23:35:05.218Z'}]
```


## Licence

nure_tools is [GNU GPLv3.0 licenced](https://github.com/SoappGuy/nure_tools/blob/master/LICENSE)