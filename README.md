![PyThaiNLP Logo](https://avatars0.githubusercontent.com/u/32934255?s=200&v=4)

# PyThaiNLP: Thai Natural Language Processing in Python

[![Python 3.6](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/release/python-360/)
[![pypi](https://img.shields.io/pypi/v/pythainlp.svg)](https://pypi.python.org/pypi/pythainlp)
[![Downloads](https://pepy.tech/badge/pythainlp/month)](https://pepy.tech/project/pythainlp)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FPyThaiNLP%2Fpythainlp.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2FPyThaiNLP%2Fpythainlp?ref=badge_shield)
[![Build status](https://ci.appveyor.com/api/projects/status/9g3mfcwchi8em40x?svg=true)](https://ci.appveyor.com/project/wannaphongcom/pythainlp-9y1ch)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/cb946260c87a4cc5905ca608704406f7)](https://www.codacy.com/app/pythainlp/pythainlp_2?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=PyThaiNLP/pythainlp&amp;utm_campaign=Badge_Grade)
[![Coverage Status](https://coveralls.io/repos/github/PyThaiNLP/pythainlp/badge.svg?branch=dev)](https://coveralls.io/github/PyThaiNLP/pythainlp?branch=dev) [![Google Colab Badge](https://badgen.net/badge/Launch%20Quick%20Start%20Guide/on%20Google%20Colab/blue?icon=terminal)](https://colab.research.google.com/github/PyThaiNLP/tutorials/blob/master/source/notebooks/pythainlp_get_started.ipynb)
[![DOI](https://zenodo.org/badge/61813823.svg)](https://zenodo.org/badge/latestdoi/61813823)

PyThaiNLP is a Python package for text processing and linguistic analysis, similar to `nltk` but with focus on Thai language.

PyThaiNLP เป็นไลบารีภาษาไพทอนสำหรับประมวลผลภาษาธรรมชาติ โดยเน้นภาษาไทย ดูรายละเอียดภาษาไทยเพิ่มเติมด้านล่าง

**News**

>We are conducting a 2-minute survey to know more about your experience using the library and your expectations regarding what the library should be able to do. Take part in this survey: https://forms.gle/aLdSHnvkNuK5CFyt9

- The latest stable release is [2.2.1](https://github.com/PyThaiNLP/pythainlp/releases). See [2.2 change log](https://github.com/PyThaiNLP/pythainlp/issues/330).
- For latest development, see [`dev`](https://github.com/PyThaiNLP/pythainlp/tree/dev) branch. See ongoing [2.3 development change log](https://github.com/PyThaiNLP/pythainlp/issues/445).

Using PyThaiNLP:
- [PyThaiNLP Get Started](https://www.thainlp.org/pythainlp/tutorials/notebooks/pythainlp_get_started.html)
- More tutorials at [https://www.thainlp.org/pythainlp/tutorials/](https://www.thainlp.org/pythainlp/tutorials/)
- See full documentation at [https://thainlp.org/pythainlp/docs/2.2/](https://thainlp.org/pythainlp/docs/2.2/)
- Some additional data (like word lists and language models) may get automatically download during runtime and it will be kept under the directory `~/pythainlp-data` by default. See corpus catalog at [https://github.com/PyThaiNLP/pythainlp-corpus](https://github.com/PyThaiNLP/pythainlp-corpus).
- The data location can be changed, using `PYTHAINLP_DATA_DIR` environment variable.
- For PyThaiNLP tokenization performance and measurement methods, see [tokenization benchmark](tokenization-benchmark.md)
- 📫 follow our [PyThaiNLP](https://www.facebook.com/pythainlp/) Facebook page


## Capabilities

- Convenient character and word classes, like Thai consonants (`pythainlp.thai_consonants`), vowels (`pythainlp.thai_vowels`), digits (`pythainlp.thai_digits`), and stop words (`pythainlp.corpus.thai_stopwords`) -- comparable to constants like `string.letters`, `string.digits`, and `string.punctuation`
- Thai word segmentation (`word_tokenize`), including subword segmentation based on Thai Character Cluster (`subword_tokenize`)
- Thai transliteration (`transliterate`)
- Thai part-of-speech taggers (`pos_tag`)
- Read out number to Thai words (`bahttext`, `num_to_thaiword`)
- Thai collation (sort by dictionoary order) (`collate`)
- Thai-English keyboard misswitched fix (`eng_to_thai`, `thai_to_eng`)
- Thai spelling suggestion and correction (`spell` and `correct`)
- Thai soundex (`soundex`) with three engines (`lk82`, `udom83`, `metasound`)
- Thai datetime formatting (`thai_strftime`)
- and much more - see examples in [tutorials](https://www.thainlp.org/pythainlp/tutorials/).


## Installation

PyThaiNLP uses PyPI as its main distribution channel, see [https://pypi.org/project/pythainlp/](https://pypi.org/project/pythainlp/)

### Stable release

```sh
pip install pythainlp
```

### Development pre-release

```sh
pip install --upgrade --pre pythainlp
```

### Fresh from dev branch

```sh
pip install https://github.com/PyThaiNLP/pythainlp/archive/dev.zip
```

### Install options

For some functionalities, like named-entity recognition, extra packages may be needed. Install them with these install options:

```sh
pip install pythainlp[extra1,extra2,...]
```

where `extras` can be
  - `attacut` (to support attacut, a fast and accurate tokenizer)
  - `benchmarks` (for [word tokenization benchmarking](tokenization-benchmark.md))
  - `icu` (for ICU, International Components for Unicode, support in transliteration and tokenization)
  - `ipa` (for IPA, International Phonetic Alphabet, support in transliteration)
  - `ml` (to support ULMFiT models for classification)
  - `thai2fit` (for Thai word vector)
  - `thai2rom` (for machine-learnt romanization)
  - `wordnet` (for Thai WordNet API)
  - `full` (install everything)

For dependency details, look at `extras` variable in [`setup.py`](https://github.com/PyThaiNLP/pythainlp/blob/dev/setup.py).


## Python 2 Users

- PyThaiNLP 2 supports Python 3.6+. Some functions may work with older version of Python 3, but it is not well-tested and will not be supported. See [1.7 -> 2.0 change log](https://github.com/PyThaiNLP/pythainlp/issues/118).
  - [Upgrading from 1.7](https://thainlp.org/pythainlp/docs/2.0/notes/pythainlp-1_7-2_0.html)
  - [Upgrade ThaiNER from 1.7](https://github.com/PyThaiNLP/pythainlp/wiki/Upgrade-ThaiNER-from-PyThaiNLP-1.7-to-PyThaiNLP-2.0)
- Python 2.7 users can use PyThaiNLP 1.6

## Citations

If you use `PyThaiNLP` in your project or publication, please cite the library as follows

```
Wannaphong Phatthiyaphaibun, Korakot Chaovavanich, Charin Polpanumas, Arthit Suriyawongkul, Lalita Lowphansirikul, & Pattarawat Chormai. (2016, Jun 27). PyThaiNLP: Thai Natural Language Processing in Python. Zenodo. http://doi.org/10.5281/zenodo.3519354
```

or BibTeX entry:

``` bib
@misc{pythainlp,
    author       = {Wannaphong Phatthiyaphaibun, Korakot Chaovavanich, Charin Polpanumas, Arthit Suriyawongkul, Lalita Lowphansirikul, Pattarawat Chormai},
    title        = {{PyThaiNLP: Thai Natural Language Processing in Python}},
    month        = Jun,
    year         = 2016,
    doi          = {10.5281/zenodo.3519354},
    publisher    = {Zenodo},
    url          = {http://doi.org/10.5281/zenodo.3519354}
}
```

## Contribute to PyThaiNLP

- Please do fork and create a pull request :)
- For style guide and other information, including references to algorithms we use, please refer to our [contributing](https://github.com/PyThaiNLP/pythainlp/blob/dev/CONTRIBUTING.md) page.
- PyThaiNLP code uses [Apache Software License 2.0](https://github.com/PyThaiNLP/pythainlp/blob/dev/LICENSE)
- Corpus data created by PyThaiNLP project use [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/)
- For other corpus that may included with PyThaiNLP distribution, please refer to [Corpus License](https://github.com/PyThaiNLP/pythainlp/blob/dev/pythainlp/corpus/corpus_license.md).

Made with ❤️<br />
PyThaiNLP Team<br />
"We build Thai NLP"


# ภาษาไทย

PyThaiNLP เป็นไลบรารีภาษาไพทอนสำหรับประมวลผลภาษาธรรมชาติ โดยเน้นภาษาไทย **แจกจ่ายฟรี (ตลอดไป) เพื่อคนไทยและชาวโลกทุกคน!**

> เพราะโลกขับเคลื่อนต่อไปด้วยการแบ่งปัน

**ข่าวสาร**

>สวัสดีค่ะ ทีมพัฒนา PyThaiNLP ขอสอบถามความคิดเห็นของผู้ใช้งาน PyThaiNLP หรือผู้ที่ทำงานในด้านการประมวลผลภาษาไทย เพื่อนำข้อมูลไปปรับปรุงและพัฒนาฟีเจอร์ใหม่ๆ ให้ตรงกับความต้องการใช้งานมากขึ้น สามารถตอบแบบสอบถามได้ที่ https://forms.gle/aLdSHnvkNuK5CFyt9 (ใช้เวลาประมาณ 2-5 นาที)

- รุ่นเสถียรล่าสุดคือรุ่น [2.2.1](https://github.com/PyThaiNLP/pythainlp/releases)
- PyThaiNLP 2 รองรับ Python 3.6 ขึ้นไป
  - ผู้ใช้ Python 2.7+ ยังสามารถใช้ [PyThaiNLP 1.6](https://github.com/PyThaiNLP/pythainlp/blob/007e644daab4ac8379a13f26065e2d9492af0536/docs/pythainlp-1-6-thai.md) ได้
- 📫 ติดตามข่าวสารได้ที่ Facebook [PyThaiNLP](https://www.facebook.com/pythainlp/)

ใช้งาน PyThaiNLP:
- [เริ่มต้นใช้งาน PyThaiNLP](https://www.thainlp.org/pythainlp/tutorials/notebooks/pythainlp_get_started.html)
- สอนการใช้งานเพิ่มเติม ในรูปแบบ notebook [https://www.thainlp.org/pythainlp/tutorials/](https://www.thainlp.org/pythainlp/tutorials/)
- เอกสารตัวเต็ม [https://thainlp.org/pythainlp/docs/2.2/](https://thainlp.org/pythainlp/docs/2.2/)
- ระหว่างการทำงาน PyThaiNLP อาจดาวน์โหลดข้อมูลเพิ่มเติม เช่น ตัวแบบภาษา และรายการคำ ข้อมูลเหล่านี้จะถูกเก็บไว้ที่ไดเรกทอรี `~/pythainlp-data` เป็นตำแหน่งมาตรฐาน
  - ตำแหน่งเก็บข้อมูลนี้สามารถกำหนดเองได้ โดยการเปลี่ยนแปลงตัวแปรสิ่งแวดล้อม `PYTHAINLP_DATA_DIR` ของระบบปฏิบัติการ


## ความสามารถ

- ชุดค่าคงที่ตัวอักษระและคำไทยที่เรียกใช้ได้สะดวก เช่น พยัญชนะ (`pythainlp.thai_consonants`), สระ (`pythainlp.thai_vowels`), ตัวเลขไทย (`pythainlp.thai_digits`), และ stop word (`pythainlp.corpus.thai_stopwords`) -- เหมือนกับค่าคงที่อย่าง `string.letters`, `string.digits`, และ `string.punctuation`
- ตัดคำภาษาไทย (`word_tokenize`) และรองรับการตัดระดับต่ำกว่าคำโดยใช้ Thai Character Clusters (`subword_tokenize`)
- ถอดเสียงภาษาไทยเป็นอักษรละตินและสัทอักษร (`transliterate`)
- ระบุชนิดคำ (part-of-speech) ภาษาไทย (`pos_tag`)
- อ่านตัวเลขเป็นข้อความภาษาไทย (`bahttext`, `num_to_thaiword`)
- เรียงลำดับคำตามพจนานุกรมไทย (`collate`)
- แก้ไขปัญหาการพิมพ์ลืมเปลี่ยนภาษา (`eng_to_thai`, `thai_to_eng`)
- ตรวจคำสะกดผิดในภาษาไทย (`spell`, `correct`)
- soundex ภาษาไทย (`soundex`) 3 วิธีการ (`lk82`, `udom83`, `metasound`)
- รูปแบบวันที่และเวลาไทย (`thai_strftime`)
- และอื่น ๆ ดูตัวอย่างได้ใน [tutorials สอนวิธีใช้งาน](https://www.thainlp.org/pythainlp/tutorials/)


## ติดตั้ง

### รุ่นเสถียร

```sh
pip install pythainlp
```

### รุ่นก่อนเผยแพร่ (pre-release)

```sh
pip install --upgrade --pre pythainlp
```

### รุ่นกำลังพัฒนา (dev branch)

```sh
pip install https://github.com/PyThaiNLP/pythainlp/archive/dev.zip
```

### การติดตั้งความสามารถเพิ่มเติม

สำหรับความสามารถบางอย่าง เช่น การชื่อเฉพาะ (named-entity) จำเป็นต้องติดตั้งแพคเกจเสริม ด้วยการระบุออปชันตอน pip install:

```sh
pip install pythainlp[extra1,extra2,...]
```

โดยที่ `extras` คือ
  - `attacut` (ตัวตัดคำที่แม่นกว่า `newmm` เมื่อเทียบกับชุดข้อมูล BEST)
  - `benchmarks` (สำหรับเครื่องมือ[วัดความแม่นยำของตัวตัดคำ](tokenization-benchmark.md))
  - `icu` (สำหรับการถอดตัวสะกดเป็นสัทอักษรและการตัดคำด้วย ICU)
  - `ipa` (สำหรับการถอดตัวสะกดเป็นสัทอักษรสากล (IPA))
  - `ml` (สำหรับการรองรับโมเดล ULMFiT)
  - `thai2fit` (สำหรับ word vector)
  - `thai2rom` (สำหรับการถอดตัวสะกดเป็นอักษรละติน)
  - `wordnet` (สำหรับ API WordNet ภาษาไทย)
  - `full` (ติดตั้งทุกอย่าง)

รายละเอียดของแพคเกจเสริมดูได้ในตัวแปรชื่อ `extras` ใน [`setup.py`](https://github.com/PyThaiNLP/pythainlp/blob/dev/setup.py)

## การอ้างอิง

หากคุณใช้ `PyThaiNLP` ในโปรเจคของคุณหรืองานวิจัย คุณสามารถอ้างอิงได้ตามนี้

```
Wannaphong Phatthiyaphaibun, Korakot Chaovavanich, Charin Polpanumas, Arthit Suriyawongkul, Lalita Lowphansirikul, & Pattarawat Chormai. (2016, Jun 27). PyThaiNLP: Thai Natural Language Processing in Python. Zenodo. http://doi.org/10.5281/zenodo.3519354
```

หรือ BibTeX entry:

``` bib
@misc{pythainlp,
    author       = {Wannaphong Phatthiyaphaibun, Korakot Chaovavanich, Charin Polpanumas, Arthit Suriyawongkul, Lalita Lowphansirikul, Pattarawat Chormai},
    title        = {{PyThaiNLP: Thai Natural Language Processing in Python}},
    month        = Jun,
    year         = 2016,
    doi          = {10.5281/zenodo.3519354},
    publisher    = {Zenodo},
    url          = {http://doi.org/10.5281/zenodo.3519354}
}
```

## สนับสนุนและร่วมพัฒนา

- คุณสามารถ[ร่วมพัฒนาโครงการนี้](https://github.com/PyThaiNLP/pythainlp/blob/dev/CONTRIBUTING.md)ได้ โดยการ fork และส่ง pull request กลับมา
- โค้ด PyThaiNLP ใช้สัญญาอนุญาต [Apache Software License 2.0](https://github.com/PyThaiNLP/pythainlp/blob/dev/LICENSE)
- คลังคำและข้อมูลที่สร้างโดยโครงการ PyThaiNLP ใช้สัญญาอนุญาตครีเอทีฟคอมมอนส์แบบแสดงที่มา-อนุญาตแบบเดียวกัน 4.0 [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/)
- คลังคำและข้อมูลอื่นๆ ที่แจกจ่ายไปพร้อมกับแพคเกจ PyThaiNLP อาจใช้สัญญาอนุญาตอื่น โปรดดูเอกสาร [Corpus License](https://github.com/PyThaiNLP/pythainlp/blob/dev/pythainlp/corpus/corpus_license.md)
- ตราสัญลักษณ์ออกแบบโดยคุณ วรุตม์ พสุธาดล จากการประกวดที่ในกลุ่มเฟซบุ๊ก [1](https://www.facebook.com/groups/408004796247683/permalink/475864542795041/) [2](https://www.facebook.com/groups/408004796247683/permalink/474262752955220/)

สร้างด้วย ❤️<br />
ทีม PyThaiNLP<br />
"พวกเราสร้าง Thai NLP"
