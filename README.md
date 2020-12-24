# Puisi & Pantun Generator
Puisi and pantun is an Indonesian poetic form. I scraped some puisi & pantun, fine tune GPT-2, and generated one.

## Dataset
The dataset was collected by scraping various websites. 
* The puisi dataset contains 7223 Indonesian puisi with its title and author.
* The pantun dataset contains 440 Indonesian pantun with 18 theme  
  
more detail on [data dir](/data)

## Fine-tuning
I finetune Indonesian GPT-2 ([pretrained by Cahya Wirawan](https://github.com/cahya-wirawan/indonesian-language-models)) on Indonesian puisi & pantun. Both for `2 epoch` with `5e-5 learning rate`.  

The finetuning was done using HuggingFace's run_language_modeling.py script on Kaggle kernel. Link to the kernel:
* [Finetuning Puisi](https://www.kaggle.com/ilhamfp31/finetune-gpt-2-indonesian-poem-puisi)
  * Final perplexity: 42.3635
* [Finetuning Pantun](https://www.kaggle.com/ilhamfp31/finetune-gpt-2-indonesian-pantun)
  * Final perplexity: 34.3172

## Generation Example
* [Try generating Puisi with your own prompt here!](https://www.kaggle.com/ilhamfp31/pembangkitan-puisi-otomatis)
* [Try generating Pantun with your own prompt here!](https://www.kaggle.com/ilhamfp31/pembangkitan-pantun-otomatis/)

Here's some cherry picked result:

<details>
  <summary>Puisi without prompt</summary>
  
  ```
    HILANG BISA 
    Oleh Azwan 
    
    Aku hanya seorang lelaki 
    Yang selalu hadir dihatimu 
    Yang selalu menemani aku 
    Saat aku masih ada di pelukanmu 
    
    Entah kenapa aku masih merasakannya 
    Seakan aku tak berharap dengan keindahanmu 
    Namun aku tak peduli dengan kesungguhanmu 
    Dan yang membuatku merasa bosan 
    
    Aku terlalu jauh dalam memahamimu 
    Aku terlalu kaku dalam memahamimu 
    Karena dia sangat jarang dapat melupakanmu 
    
    Aku hanya seorang lelaki 
    Yang selalu menyayangimu 
    Seperti dia sendiri 
    
    Aku sangat mencintaimu 
    Meski diriku tidak selalu menghargaimu 
    Tanpa aku tau padamu 
    Aku hanya seorang lelaki 
    Yang selalu menyayangimu 
    
    Dia selalu menyayangiku 
    Dan aku akan selalu mencintaimu 
    
    Aku selalu menyayangimu 
    Karen
  ```
  We can check that the dataset did not contain this poem at all. The model successfully generated an original title with valid Indonesian words. But whether the content itself makes sense is left for your judgement 😄

</details>

<details>
  <summary>Puisi with prompt `SENJA DI PELABUHAN BESAR`</summary>
  
  ```
    SENJA DI PELABUHAN BESAR 
    Oleh Anissa N 
    
    Aku sudah tak berdaya 
    Karena ku tahu 
    Aku akan terus saja berlari 
    Tetapi tidak akan berhenti 
    Saat aku tak ada lagi 
    Kau tak sanggup lagi merasakan 
    Menunggu waktu 
    Aku akan segera berpisah 
    Menunggu waktu 
    Berharap waktu sudah tiba 
    Aku akan segera berpisah 
    Menunggu waktu yang tersisa 
    Menunggu waktu yang tersisa 
    Slalu ada 
    Aku akan tetap bersama 
    Aku akan pergi 
    Aku akan pergi 
    Aku akan menunggu waktu yang tersisa 
    Aku akan terus berjuang 
    Aku akan tetap bersama 
  ```
  🤧🤧🤧🤧🤧

</details>

<details>
  <summary>Pantun without prompt</summary>
  
  ```
    Datang ke hilir hutan jati 
    Hilang ke pinggir hutan jati 
    Buah kedondong pun buahnya 
    Agar hutan jati di tengah kita 
  ```
  ???!!!
  
</details>

<details>
  <summary>Pantun with prompt `Kalau ada ladang di sumur`</summary>
  
  ```
    Kalau ada ladang di sumur 
    Jika ada ladang di sawah 
    Tapi bukan karena tidak suka 
    Yang mana dia yang jahat 
  ```
  
</details>

More on the [generated-puisi.txt](generated-puisi.txt) and [generated-pantun.txt](generated-pantun.txt) files.

## What's next
Some idea to improve this experiment:
* Add restriction to the [generation script](https://www.kaggle.com/ilhamfp31/run-generation-py). The current pantun generation script did not put any restriction on the rhyme of each line. Most of the generated pantun has bad rhymes.
* Try controllable generation (ex: [PPLM](https://arxiv.org/abs/1912.02164))
* Add more data