---
layout: page
title: PyTorch Models
order: 3
---

## Pretrained


Available models trained using OpenNMT.

* [German to English](http://lstm.seas.harvard.edu/latex/opennmt-py-models/translate/de-en/baseline-brnn2.s131_acc_62.71_ppl_7.74_e20.pt)
* [English Summarization](http://lstm.seas.harvard.edu/latex/opennmt-py-models/summary/model-copy_acc_51.78_ppl_11.71_e20.pt)
* [Chinese Summarization](http://lstm.seas.harvard.edu/latex/opennmt-py-models/summary/LCSTS/model_acc_56.86_ppl_10.97_e11.pt)
* [Dialog System](http://lstm.seas.harvard.edu/latex/opennmt-py-models/dialog/model_acc_39.74_ppl_26.63_e13.pt)

## Benchmarks

This page benchmarks training results of open-source NMT systems with generated models of OpenNMT and other systems.

### German->English

| Who/When      | Corpus Prep     | Training Tool | Training Parameters | Server Details | Training Time/Memory | Translation Parameters | Scores | Model |
|:------------- |:--------------- |:-------------|:-------------------|:---------------|:-------------|:------------|:------|:-----|
| 2018/02/11<br>Baseline | [IWSLT '14 DE-EN](https://github.com/facebookresearch/fairseq-py/blob/master/data/prepare-iwslt14.sh) | OpenNMT `d4ab35a` | 2 layers, LSTM 500, WE 500, encoder_type brnn input feed<br>20 epochs | <small>Trained on 1 GPU TITAN X  |  | | BLEU Score: 30.33 | 203MB [here](http://lstm.seas.harvard.edu/latex/opennmt-py-models/translate/de-en/baseline-brnn2.s131_acc_62.71_ppl_7.74_e20.pt) |

### English Summarization

| Who/When      | Corpus Prep     | Training Tool | Training Parameters | Server Details | Training Time/Memory | Translation Parameters | Scores | Model |
|:------------- |:--------------- |:-------------|:-------------------|:---------------|:-------------|:------------|:------|:-----|
| 2018/02/11<br>Baseline | [Gigaword Standard](https://github.com/harvardnlp/sent-summary) | OpenNMT `d4ab35a` | 2 layers, LSTM 500, WE 500, input feed<br>20 epochs | <small>Trained on 1 GPU TITAN X  |  | | Gigaword F-Score R1: 33.60 R2: 16.29 RL: 31.45  | 331MB [here](http://lstm.seas.harvard.edu/latex/opennmt-py-models/summary/model_acc_51.33_ppl_12.74_e20.pt) |
| 2018/02/22<br>Baseline | [Gigaword Standard](https://github.com/harvardnlp/sent-summary) | OpenNMT `338b3b1` | 2 layers, LSTM 500, WE 500, input feed, copy_attn, reuse_copy_attn<br>20 epochs | <small>Trained on 1 GPU TITAN X  |  | replace_unk | Gigaword F-Score R1: 35.51 R2: 17.35 RL: 33.17  | 331MB [here](http://lstm.seas.harvard.edu/latex/opennmt-py-models/summary/model-copy_acc_51.78_ppl_11.71_e20.pt) |

### Chinese Summarization

| Who/When      | Corpus Prep     | Training Tool | Training Parameters | Server Details | Training Time/Memory | Translation Parameters | Scores | Model |
|:------------- |:--------------- |:-------------|:-------------------|:---------------|:-------------|:------------|:------|:-----|
|[playma](https://github.com/playma) 2018/02/25 | [LCSTS](http://icrc.hitsz.edu.cn/Article/show/139.html)<br/>src_vocab_size 8000, tgt_vocab_size 8000, src_seq_length 400, tgt_seq_length 30, src_seq_length_trunc 400, tgt_seq_length_trunc 100 | OpenNMT `338b3b1` | 1 layer, LSTM 300, WE 500, encoder_type brnn, input feed<br>AdaGrad, adagrad_accumulator_init 0.1, learning_rate 0.15<br/>30 epochs |  | | | Gigaword F-Score R1: 35.67 R2: 23.06 RL: 33.14  | 99MB [here](http://lstm.seas.harvard.edu/latex/opennmt-py-models/summary/LCSTS/model_acc_56.86_ppl_10.97_e11.pt) |

### Dialog System

| Who/When      | Corpus Prep     | Training Tool | Training Parameters | Server Details | Training Time/Memory | Translation Parameters | Scores | Model |
|:------------- |:--------------- |:-------------|:-------------------|:---------------|:-------------|:------------|:------|:-----|
| 2018/02/22<br>Baseline | [Opensubtitles](http://opus.lingfil.uu.se/download.php?f=OpenSubtitles/en.tar.gz) | OpenNMT `338b3b1` | 2 layers, LSTM 500, WE 500, input feed, dropout 0.2, global_attention mlp, start_decay_at 7<br>13 epochs | <small>Trained on 1 GPU TITAN X  |  | | TBD  | 355MB [here](http://lstm.seas.harvard.edu/latex/opennmt-py-models/dialog/model_acc_39.74_ppl_26.63_e13.pt) |

