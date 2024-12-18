<h1 align="center"> NLP With HuggingFace Transformers </h1>
<p align="center"> Berisi tentang pipeline dari HuggingFace Transformers untuk keperluan NLP (Natural Language Processing)</p>

<div align="center">

<img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54">
<img src="https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white">

</div>

<h2 align="center"> Analisis </h2> 
Ada beberapa yang sudah saya coba seperti:
1. zero-shot-classification

```
-> untuk klasifikasi kalimat
model: facebook/bart-large-mnli
karena katanya bisa pakai bahasa indonesia tapi tidak seakurat model indobert tetapi pas di coba lumayan bisa dipakai
```
2. text-generation


```
-> untuk generate text agar lebih panjang
model: gpt2
Model utama yang kuat dan sering digunakan untuk text generation
```


3. fill-mask

```
->mengisi kata yang kosong dalam sebuah kalimat
model: distilbert-base-uncased
trust_remote_code=True
setelah saya nanya chatgpt, sebelum saya pakai ini ada sebuah error dan error itu karena BertForMaskedLM tidak secara langsung mewarisi GenerationMixin.
Beberapa bobot model mungkin tidak cocok jika digunakan di luar arsitektur aslinya (misalnya, dari model bert yang dirancang untuk tugas lain seperti sequence classification) dan fungsi parameter ini untuk mengabaikan error tersebut dan sudah bisa dijalankan
```


4. ner

```
-> untuk mengidentifikasi dan mengekstraksi entitas yang diberi nama dalam teks, seperti nama orang, tempat, organisasi, tanggal, jumlah, dll. (chatgpt)
model: distilbert-base-uncased
model ini memang sudah terlatih untuk ner
```

5. question-answering

```
-> untuk menjawab sesuai dengan statement yang sudah diberikan
model: bert-large-cased-whole-word-masking-finetuned-squad
awalnya mau pake bert-base-cased tetapi yang diambil kalimatnya hanya pertengahan bukan seluruh pengertian, setelah cari-cari luntang-lantung begitu nemu model ini dan berhasil
```

6. sentiment-analysis

```
-> menentukan apakah ini kalimat positif atau negatif atau netral
model: w11wo/indonesian-roberta-base-sentiment-classifier
model ini dilatih untuk sentiment analysis versi bahasa indonesia jadi lebih masuk akal dibandingkan dengan yang umum kayak distilbert
```

7. summarization

```
-> seperti namanya adalah untuk menyimpulkan teks
model: cahya/t5-base-indonesian-summarization-cased
model ini sengaja saya pakai biar bisa dipakai untuk teks berbahasa indonesia
```

8. translation

```
-> untuk menerjemahkan teks atau kata
model: Helsinki-NLP/opus-mt-id-en
model: Helsinki-NLP/opus-mt-en-jap
disini saya memakai 2 model karena tujuan awalnya untuk mengubah dari bahasa indonesia ke bahasa jepang dan ternyata tidak ada model yang langsung seperti itu. Jadi saya pakai dari bahasa indonesia diterjemahin ke bahasa inggris dulu, nanti bahasa inggris ini yang akan diterjemahkan ke bahasa jepang. walaupun yang dari bahasa inggris ke jepang masih belum berhasil karena agak lari terjemahannya, setidaknya sudah bisa ke bahasa jepang dulu.
```

Dan dari semua ini, saya masih penasaran dengan translation karena unik dan masih penasaran kenapa bahasa jepang nya masih lari terjemahannya, mungkin kedepannya saya akan mencoba explore lebih jauh lagi tentang ini.


