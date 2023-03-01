---
title: "S2CD: Self-heuristic Speaker Content Disentanglement for Any-to-Any Voice Conversion"
---

## Abstract

In this paper, we propose a **S**elf-heuristic **S**peaker **C**ontent **D**isentanglement (S2CD) model for *any_to_any* voice conversion without using any external resources, e.g., speaker labels or vectors, linguistic models, and transcriptions. S2CD is built on the disentanglement sequential variational autoencoder (DSVAE), but improves DSVAE structure at the model architecture level from three perspectives. Specifically, we develop different structures for speaker and content encoders based on their underlying static/dynamic property. We further propose a generative graph, modelled by S2CD, so as to make S2CD well mimic the multi-speaker speech generation process. Finally, we propose a self-heuristic way to introduce bias to the prior modelling. Extensive empirical evaluations show the effectiveness of S2CD for *any_to_any* voice conversion.

![](2.png)

## Key Points of S2CD

Compared with DSVAE, S2CD makes the following improvements:

- Different structures for speaker and content encoders
- Positive pair-wise training based on a multi-speaker speech generation graph
- self-heuristic prior modelling

## Voice Conversion Demon samples

### Unseen2unseen

**Female2Male**:

| Models | Example 1 | Example 2 |
|  ----  | ----  | ----  |
| Source | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample1/src_001.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample2/src_003.wav"></audio> |
| Target | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample1/tgt_001.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample2/tgt_003.wav"></audio> |
| DSVAE | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample1/ds_001.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample2/ds_003.wav"></audio> |
| S2CD_woT&P | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample1/tswoTwoP_001.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample2/tswoTwoP_003.wav"></audio> |
| S2CD_woT | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample1/tswoTwP_001.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample2/tswoTwP_003.wav"></audio> |
| S2CD | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample1/ts_001.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2male/sample2/ts_003.wav"></audio> |

**Male2female**:

| Models | Example 1 | Example 2 |
|  ----  | ----  | ----  |
| Source | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample1/src_026.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample2/src_029.wav"></audio> |
| Target | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample1/tgt_026.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample2/tgt_029.wav"></audio> |
| DSVAE | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample1/ds_026.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample2/ds_029.wav"></audio> |
| S2CD_woT&P | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample1/tswoTwoP_026.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample2/tswoTwoP_029.wav"></audio> |
| S2CD_woT | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample1/tswoTwP_026.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample2/tswoTwP_029.wav"></audio> |
| S2CD | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample1/ts_026.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2female/sample2/ts_029.wav"></audio> |

**Male2Male**:

| Models | Example 1 | Example 2 |
|  ----  | ----  | ----  |
| Source | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample1/src_009.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample2/src_010.wav"></audio> |
| Target | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample1/tgt_009.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample2/tgt_010.wav"></audio> |
| DSVAE | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample1/ds_009.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample2/ds_010.wav"></audio> |
| S2CD_woT&P | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample1/tswoTwoP_009.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample2/tswoTwoP_010.wav"></audio> |
| S2CD_woT | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample1/tswoTwP_009.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample2/tswoTwP_010.wav"></audio> |
| S2CD | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample1/ts_009.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/male2male/sample2/ts_010.wav"></audio> |

**Female2Female**:

| Models | Example 1 | Example 2 |
|  ----  | ----  | ----  |
| Source | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample1/src_016.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample2/src_023.wav"></audio> |
| Target | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample1/tgt_016.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample2/tgt_023.wav"></audio> |
| DSVAE | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample1/ds_016.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample2/ds_023.wav"></audio> |
| S2CD_woT&P | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample1/tswoTwoP_016.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample2/tswoTwoP_023.wav"></audio> |
| S2CD_woT | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample1/tswoTwP_016.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample2/tswoTwP_023.wav"></audio> |
| S2CD | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample1/ts_016.wav"></audio> | <audio id="audio" controls="" preload="none" style="height: 40px"> <source id="wav" src="demo_samples/u2u/female2female/sample2/ts_023.wav"></audio> |
