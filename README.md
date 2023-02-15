# TimesNet (ICLR 2023)
**:triangular_flag_on_post: The complete code and scripts of TimesNet have been included in [[Time-Series-Library]](https://github.com/thuml/Time-Series-Library).**

TimesNet: Temporal 2D-Variation Modeling for General Time Series Analysis [[paper]](https://openreview.net/pdf?id=ju_Uqw384Oq)

<p align="center">
<img src=".\pic\overall.png" height = "300" alt="" align=center />
</p>

In this paper, we present TimesNet as a powerful foundation model for general time series analysis, which can

- 🏆 Achieve the consistent state-of-the-art in five main-stream tasks: **Long- and Short-term Forecasting, Imputation, Anomaly Detection and Classification**.
- 🌟 Directly take advantage of booming vision backbones by transforming the 1D time series into 2D space.

## Temporal 1D-Variation vs. 2D-Variation

Temporal variation modeling is the common key problem of extensive analysis tasks. Previous methods attempt to accomplish this directly from the 1D time series, which is extremely challenging due to the intricate temporal patterns. Based on the observation of multi-periodicity in time series, we present the TimesNet to **transform the origianl 1D-timeseries into 2D Space**, which can unfiy the intraperiod- and interperiod-variations.

<p align="center">
<img src=".\pic\timesnet.png" height = "300" alt="" align=center />
</p>

## General Representation Learning Capacity

To demonstrate the model capacity in representation learning, we calculate the [CKA similarity](https://github.com/jayroxis/CKA-similarity) between representations from the bottom and top layer of each model. A smaller CKA similarity means that the representations of bottom and top layer are more distinct, indicating the hierarchical representations. From this representation analysis, We find that:

- **Forecasting and anomaly detection tasks require the low-level representations.**
- **Imputation and classification tasks expect the hierarchical representations.**

Benefiting from 2D kernel design, **TimesNet (marked by red stars) can learn appropriate representations for different tasks**, demonstrating its task generality as a foundation model.

<p align="center">
<img src=".\pic\representation.png" height = "200" alt="" align=center />
</p>

## Leaderboard for Time Series Analysis

In this paper, we also provide a comprehensive benchmark to evaluate different backbones. **More than 15 advanced baselines are compared.** Till February 2023, the top three models for five different tasks are:

| Model<br>Ranking | Long-term<br>Forecasting                                     | Short-term<br>Forecasting                                    | Imputation                                                   | Anomaly<br>Detection                                         | Classification                                     |
| ---------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------------------------------- |
| 🥇 1st            | [TimesNet](https://arxiv.org/abs/2210.02186)                 | [TimesNet](https://arxiv.org/abs/2210.02186)                 | [TimesNet](https://arxiv.org/abs/2210.02186)                 | [TimesNet](https://arxiv.org/abs/2210.02186)                 | [TimesNet](https://arxiv.org/abs/2210.02186)       |
| 🥈 2nd            | [DLinear](https://github.com/cure-lab/LTSF-Linear)           | [Non-stationary<br/>Transformer](https://github.com/thuml/Nonstationary_Transformers) | [Non-stationary<br/>Transformer](https://github.com/thuml/Nonstationary_Transformers) | [Non-stationary<br/>Transformer](https://github.com/thuml/Nonstationary_Transformers) | [FEDformer](https://github.com/MAZiqing/FEDformer) |
| 🥉 3rd            | [Non-stationary<br>Transformer](https://github.com/thuml/Nonstationary_Transformers) | [FEDformer](https://github.com/MAZiqing/FEDformer)           | [Autoformer](https://github.com/thuml/Autoformer)            | [Informer](https://github.com/zhouhaoyi/Informer2020)        | [Autoformer](https://github.com/thuml/Autoformer)  |

See our [paper](https://openreview.net/pdf?id=ju_Uqw384Oq) for the comprehensive benchmark.

## Citation

If you find this repo useful, please cite our paper.

```
@inproceedings{wu2023timesnet,
  title={TimesNet: Temporal 2D-Variation Modeling for General Time Series Analysis},
  author={Haixu Wu and Tengge Hu and Yong Liu and Hang Zhou and Jianmin Wang and Mingsheng Long},
  booktitle={International Conference on Learning Representations},
  year={2023},
}
```

## Contact
If you have any questions, please contact whx20@mails.tsinghua.edu.cn.

## Acknowledgement

We appreciate the following github repos for their valuable codebase:

- Forecasting: https://github.com/thuml/Autoformer

- Anomaly Detection: https://github.com/thuml/Anomaly-Transformer

- Classification: https://github.com/thuml/Flowformer
