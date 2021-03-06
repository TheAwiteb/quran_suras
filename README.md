<h1 align="center">
  <br>
  <a><img src="https://onepathnetwork.com/wp-content/uploads/2020/09/photo-1542816417-0983c9c9ad53-610x380.jpg" alt="quran_suras - img"></a>
  <br>
  quran_suras
  <br>
</h1>


<p align="center">A python <a href=https://codeberg.org/Awiteb/quran_suras/src/branch/master/quran_suras/quran_suras.py>method</a> based on the API of the <a href=https://www.mp3quran.net>mp3quran</a>, which helps you to fetch the surahs of the Qur’an via the surah number or name and more

<p align="center">
  <a href="https://pypi.org/project/quran-suras/">
    <img src="https://img.shields.io/pypi/pyversions/quran-suras?color=9cf" alt="python - Version">
  </a>
  <a href="https://pypi.org/project/quran-suras/">
    <img src="https://img.shields.io/pypi/v/quran-suras?color=9cf" alt="pypi - Version">
  </a>
  <a href="https://www.gnu.org/licenses/gpl-3.0.html">
    <img src="https://img.shields.io/pypi/l/quran-suras?color=9cf&label=License" alt="License">
  </a>
</p>


<p align="center">
  <a href="#installation">Installation</a>
  •
  <a href="#features">Features</a>
  •
  <a href="#usage">Usage</a>
  •
  <a href="#history">History</a>
  •
  <a href="#license">License</a>
</p>


## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install quran_suras.

```bash
pip3 install quran_suras
```

## Features
* get surah by number
* get surah by name
* get surah name by number
* get surah number by name
* get quran page url by number
* get islamic radio url by language

## Usage

**you can find examples [here](https://codeberg.org/Awiteb/quran_suras.py/src/branch/master/examples)**


**get surah by number:**
```python
from quran_suras import QuranSuras

quran_suras = QuranSuras()

suras = quran_suras.get_sura_by_number(sura_number=15, amount=1)
print(suras)
```
<details>
<summary> Example Result</summary>

```json
{
    'sura_name': 'يوسف', 
        'result': [
            {'reader': 'أحمد الحذيفي', 
                'url': 'https://server8.mp3quran.net/ahmad_huth/015.mp3'
            }
            ]
}
```
</details>
<br><br>

**get surah by name:**
```python
from quran_suras import QuranSuras

quran_suras = QuranSuras()

suras = quran_suras.get_sura_by_name(sura_name="النحل", amount=1)
print(suras)
```
<details>
<summary> Example Result</summary>

```json
{
    'sura_name': 'النحل', 
        'result': [
            {'reader': 'أحمد الحواشي', 
                'url': 'https://server11.mp3quran.net/hawashi/016.mp3'
                }
            ]
}
```

</details>
<br><br>

**get surah name by number:**
```python
from quran_suras import QuranSuras

quran_suras = QuranSuras()

sura_name = quran_suras.get_sura_name(sura_number=88)
print(sura_name)
```

<details>
<summary> Example Result</summary>

```bash
الغاشية
```

</details>
<br><br>

**get surah number by name:**
```python
from quran_suras import QuranSuras

quran_suras = QuranSuras()

sura_number = quran_suras.get_sura_number(sura_name="النمل")
print(sura_number)
```

<details>
<summary> Example Result</summary>

```bash
27
```

</details>
<br><br>

**get page from quran by page number:**
```python
from quran_suras import QuranSuras

quran_suras = QuranSuras()
page = quran_suras.get_page(page_number=601)
print(page)
```

<details>
<summary> Example Result</summary>

```bash
https://www.mp3quran.net/api/quran_pages_arabic/601.png
```

</details>
<br><br>

**get radios by language:**
```python
from quran_suras import QuranSuras

quran_suras = QuranSuras()

radios = quran_suras.get_radios('en', 3)
print(radios) 
```

<details>
<summary> Example Result</summary>

```json
{
  'language': 'en', 
  'result': [
    {'name': '---Amazing short Recitations---', 
      'url': 'http://live.mp3quran.net:9702/'}, 
    {'name': '--Quran Tafseer--', 
      'url': 'http://live.mp3quran.net:9718/'}, 
    {'name': '-Beautiful Recitations-', 
      'url': 'http://live.mp3quran.net:9992/'}
  ]
}
```

</details>
<br><br>


## History
* **1.0.0**: added [get_sura_by_number, get_sura_by_name, get_sura_name, get_sura_number, get_page]

* **1.1.0**: add get_radios function, is help you to get islamic radios.

* **1.1.1**: add islamic radios future.

* **1.1.2**: edit README.md

* **1.1.3**: Fixed [#1](https://codeberg.org/Awiteb/quran_suras/issues/1) - conditional sentence bug

* **1.1.4**: edit README.md

## LICENSE
[GPLv3](https://www.gnu.org/licenses/gpl-3.0.html)