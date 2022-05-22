# Wav2vec
This repo aims to provide a comparison among the ASR performance of wav2vec models finetuned in monolingual, multilingual and cross-lingual settings. For this purpose, we pretrain the wav2vec model on 6 languages: English, Bulgarian, Mandarin Chinese, Russian, Arabic and Japanese and finetuned on different languages according to the settings.
- Monolingual: Pretraining and finetuning on the same language.
- Cross-lingual: Pretraining on multiple languages and finetuning on one language.
- Multilingual: Pretraining on one language and finetuning on a different language.

## Dataset
We match the total length of the train, valid, test split of the corpus of each language to that of the English: 960 hours of train, 5 hours of valid and 10 hours of test.
- English: [LibriSpeech](https://www.openslr.org/12)
- Bulgarian: 
  - [VoxPopuli](https://github.com/facebookresearch/voxpopuli)
  - GlobalPhone
- Mandarin Chinese: 
  - Pretraining: [United Nations Proceedings Speech](https://catalog.ldc.upenn.edu/LDC2014S08)
  - Fintuning: GlobalPhone
- Russian:
  - Pretraining: [United Nations Proceedings Speech](https://catalog.ldc.upenn.edu/LDC2014S08)
  - Fintuning: [LibriSpeech](https://www.openslr.org/96)
- Arabic: 
  - Pretraining: [United Nations Proceedings Speech](https://catalog.ldc.upenn.edu/LDC2014S08)
  - Finetuning: [GALE Phase 3 Arabic Broadcast News Speech Part 2](https://catalog.ldc.upenn.edu/LDC2017S02)
- Japanese
  - Pretraining: [LaboroTVSpeech](https://github.com/laboroai/LaboroTVSpeech)
  - Finetuning: [Corpus of Spontaneous Japanese](https://clrd.ninjal.ac.jp/csj/en)
## Models
- [English](https://drive.google.com/drive/folders/1yo7Nolgf-Tg4Sj0FWHD_oAOAHiEE7adL?usp=sharing)
- [Bulgarian](https://drive.google.com/drive/folders/1yo7Nolgf-Tg4Sj0FWHD_oAOAHiEE7adL?usp=sharing)
- [Mandarin Chinese](https://drive.google.com/drive/folders/1yo7Nolgf-Tg4Sj0FWHD_oAOAHiEE7adL?usp=sharing)
- [Russian](https://drive.google.com/drive/folders/1yo7Nolgf-Tg4Sj0FWHD_oAOAHiEE7adL?usp=sharing)
- [Arabic](https://drive.google.com/drive/folders/1yo7Nolgf-Tg4Sj0FWHD_oAOAHiEE7adL?usp=sharing)
- [Japanese](https://drive.google.com/drive/folders/1yo7Nolgf-Tg4Sj0FWHD_oAOAHiEE7adL?usp=sharing)
- [Multilingual XLSR](https://dl.fbaipublicfiles.com/fairseq/wav2vec/xlsr_53_56k.pt)

## Performance
### Monolingual
| Mono | Valid UER | Valid WER | Test UER |
|--|--|--|--|
| en-ft-en | 3.51 | 9.87 | 2.97 |
| bg-ft-bg | 1.85 | 8.78 | 1.89 |
| zh-ft-zh | 10.43 | - | 10.60 |
| zh-ft-zh-pinyin | 2.90 |-| 2.96
| ru-ft-ru | 5.57 | 23.06 | 6.98 | 
| ar-ft-ar | 3.62 | 12.32 | 3.45 |
| jp-ft-jp | 10.38 | - | 9.91 |
| jp-ft-jp-kana | 4.52 | - | 5.08 |

### Cross-lingual
| Cross | Valid UER | Valid WER | Test UER | 
|--|--|--|--|
| en-ft-en | 3.51 | 9.87 | 2.97 | 
| en-ft-bg | 3.48 | 17.68 | 3.47 | 
| en-ft-zh | 15.20 | - | 15.41 | 
| en-ft-zh-pinyin | 3.65 | - | 3.80 | 
| en-ft-ru | 5.57 | 27.92 | 5.59 |
| en-ft-ar | 6.49 | 20.41 | 5.47 | 
| en-ft-jp | 16.08 | - | 16.33 | 
| en-ft-jp-kana | 7.28 | - | 8.18 | 

### Multilingual

| Multi | Valid UER | Valid WER | Test UER | 
| -- | -- | -- | -- |
| xlsr-ft-en | 1.91 | 6.58 | 1.91 | 
| xlsr-ft-bg | 2.67 | 13.79 | 2.70 | 
| xlsr-ft-zh | 14.15 | - | 14.56 | 
| xlsr-ft-zh-pinyin |3.92 |-|	4.02
| xlsr-ft-ru | 5.84 | 28.21 | 4.84 | 
| xlsr-ft-ar | 4.67 | 17.56 | 4.58 | 
| xlsr-ft-jp | 14.67 | - | 14.35 | 
| xlsr-ft-jp-kana | 6.36 | - | 7.16 | 
