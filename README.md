
<h2 align="center"> <a href="https://arxiv.org/abs/2405.04286">[COLING 2025] Who Wrote This? The Key to Zero-Shot LLM-Generated Text Detection Is GECScore </a></h2>

<h5 align="center"> 

If you like our project, please give us a star ⭐ on GitHub for the latest update.  </h2>

</h5>

<div align=center>
  
[![arXiv](https://img.shields.io/badge/Arxiv-2410.23746-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2410.23746)
[![License](https://img.shields.io/badge/License-Apache%202.0-yellow)](https://github.com/PKU-YuanGroup/ChronoMagic-Bench/blob/main/LICENSE)

This repository is the official implementation of GECScore, a simple but effective black-box zero-shot detection approach, based on the observation that, from the perspective of LLMs, human-written texts typically contain more grammatical errors than LLM-generated texts.
</div>

---

## 📣 News

* `[2024.11.28]`  ✨ Our paper is accepted by **The 31st International Conference on Computational Linguistics (COLING 2025)**. See you in Abu Dhabi, UAE!

## 🧐 Overview

The efficacy of detectors for texts generated by large language models (LLMs) substantially depends on the availability of large-scale training data. However, white-box zero-shot detectors, which require no such data, are limited by the accessibility of the source model of the LLM-generated text. In this paper, we propose a simple yet effective black-box zero-shot detection approach based on the observation that, from the perspective of LLMs, human-written texts typically contain more grammatical errors than LLM-generated texts. This approach involves calculating the Grammar Error Correction Score (GECScore) for the given text to differentiate between human-written and LLM-generated text. Experimental results show that our method outperforms current state-of-the-art (SOTA) zero-shot and supervised methods, achieving an average AUROC of 98.62\% across XSum and Writing Prompts dataset. Additionally, our approach demonstrates strong reliability in the wild, exhibiting robust generalization and resistance to paraphrasing attacks.

## ⚙️ Data and Experimental Reproduction

### Data

- Raw Data
- Normal Data
- Paraphrase Data
- Perturb Data

### Detector Usage

- detection based on the threshold pre-defined
```bash
# zero-shot-detection in xsum.GPT-4o setting
python detector.py --test_data_path xsum.GPT-4o.normal.test_data.json --threshold True --threshold_value 0.9243697428995128
```
  

- detection based on the threshold trained on the training data
```bash
# zero-shot-detection in xsum.GPT-4o setting
python detector.py --train_data_path xsum.GPT-4o.normal.test_data.json --test_data_path xsum.GPT-4o.normal.test_data.json 

# generalization in from xsum.GPT-4o to writing.GPT-4o setting
python detector.py --train_data_path xsum.GPT-4o.normal.test_data.json --test_data_path writing.GPT-4o.normal.test_data.json
```



## ✏️ Citation

If you find our paper and code useful in your research, please consider giving a star ⭐ and citation 📝.

```BibTeX
@article{wu2024GECScore,
  author       = {Junchao Wu and
                  Runzhe Zhan and
                  Derek F. Wong and
                  Shu Yang and
                  Xuebo Liu and
                  Lidia S. Chao and
                  Min Zhang},
  title        = {Who Wrote This? The Key to Zero-Shot LLM-Generated Text Detection
                  Is GECScore},
  journal      = {CoRR},
  volume       = {abs/2405.04286},
  year         = {2024},
  url          = {https://doi.org/10.48550/arXiv.2405.04286},
  doi          = {10.48550/ARXIV.2405.04286},
  eprinttype    = {arXiv},
  eprint       = {2405.04286},
}
```
