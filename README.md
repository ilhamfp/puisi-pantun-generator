# Puisi & Pantun Generator
Puisi and pantun is both a type

This repository contains my experiment


## Dataset
The dataset was collected by scraping various website. 
* The puisi dataset contains 7223 Indonesian puisi (poem) with its title and author.
* The pantun dataset contains 440 Indonesian pantun with 18 theme

## Finetuning
I finetune Indonesian GPT-2 ([pretrained by Cahya Wirawan](https://github.com/cahya-wirawan/indonesian-language-models)) on Indonesian puisi & pantun. The finetuning was done using HuggingFace's run_language_modeling.py script on Kaggle kernel. Link to the kernel:
* [Finetuning Puisi](https://www.kaggle.com/ilhamfp31/finetune-gpt-2-indonesian-poem-puisi)
* [Finetuning Pantun](https://www.kaggle.com/ilhamfp31/finetune-gpt-2-indonesian-pantun)

## Generation Example
* [Try generating Puisi with your custom prompt here!](https://www.kaggle.com/ilhamfp31/pembangkitan-puisi-otomatis)
* [Try generating Pantun with your custom prompt here!](https://www.kaggle.com/ilhamfp31/pembangkitan-pantun-otomatis/)

Here's some cherry picked result:

* Pantun without prompt
```
hehe
```

* Puisi with prompt `bagaimana`
```
hehe
```

* Pantun without prompt
```
hehe
```

* Puisi without prompt
```
hehe
```


