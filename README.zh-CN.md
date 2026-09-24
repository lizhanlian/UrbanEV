# UrbanEV

UrbanEV 是一个面向城市电动汽车充电需求预测的开放数据集，数据采集于中国深圳，涵盖电动汽车充电空间可用性和用电情况。本项目依据 [CC0 1.0 通用许可](LICENSE) 贡献至公共领域。更多信息请参阅 [Creative Commons - CC0](https://creativecommons.org/publicdomain/zero/1.0/deed.zh)。

**语言：** 中文 | [English](readme.md)

## 最新 Dryad 数据集版本

[2026-02-04 发布的 Dryad 版本](data/DRYAD_2026-02-04.md) 是当前数据集版本，其中包含官方数据下载链接和 SHA-256 校验值。由于压缩包大小为 320.23 MB，超过 GitHub 普通 Git 文件 100 MB 的限制，仓库不重复存储该压缩包，而是提供 Dryad 官方下载入口。

## 论文引用

如果本项目对您的研究有所帮助，请引用以下论文：

> Li, H., Qu, H., Tan, X. et al. (2025). UrbanEV: An Open Benchmark Dataset for Urban Electric Vehicle Charging Demand Prediction. *Scientific Data*. [Springer Nature 论文](https://doi.org/10.1038/s41597-025-04874-4)

> Qu, H., Kuang, H., Li, J., & You, L. (2023). A physics-informed and attention-based graph learning approach for regional electric vehicle charging demand prediction. *IEEE Transactions on Intelligent Transportation Systems*. [IEEE Explore](https://ieeexplore.ieee.org/document/10539613) | [arXiv](https://arxiv.org/abs/2309.05259)

> Kuang, H., Zhang, X., Qu, H., You, L., Zhu, R., & Li, J. (2024). Unravelling the effect of electricity price on electric vehicle charging behavior: A case study in Shenzhen, China. *Sustainable Cities and Society*. [DOI](https://doi.org/10.1016/j.scs.2024.105836)

> Haohao Qu, Han Li, Linlin You, Rui Zhu, Jinyue Yan, Paolo Santi, Carlo Ratti, & Chau Yuen. (2024). ChatEV: Predicting electric vehicle charging demand as natural language processing. *Transportation Research Part D: Transport and Environment*. [论文](https://doi.org/10.1016/j.trd.2024.104470) | [代码](https://github.com/Quhaoh233/ChatEV)

```bibtex
@article{li2025urbanev,
  author={Li, Han and Qu, Haohao and Tan, Xiaojun and You, Linlin and Zhu, Rui and Fan, Wenqi},
  title={UrbanEV: An Open Benchmark Dataset for Urban Electric Vehicle Charging Demand Prediction},
  journal={Scientific Data},
  volume={12},
  pages={523},
  year={2025},
  issn={2052-4463},
  doi={10.1038/s41597-025-04874-4}
}
```

## 联系方式

如对数据集有任何疑问，欢迎联系：

- Han Li：[lihan76@mail2.sysu.edu.cn](mailto:lihan76@mail2.sysu.edu.cn)
- Haohao Qu：[haohao.qu@connect.polyu.hk](mailto:haohao.qu@connect.polyu.hk)

## 更新记录

- 2025 年 1 月 19 日：上传基于 UrbanEV 的分布式预测代码和数据。
- 2025 年 3 月 17 日：在 [Dryad](https://doi.org/10.5061/dryad.np5hqc04z) 发布数据集。
- 2025 年 3 月 28 日：论文《UrbanEV: An Open Benchmark Dataset for Urban Electric Vehicle Charging Demand Prediction》发表于 *Scientific Data*。[Springer Nature 论文](https://doi.org/10.1038/s41597-025-04874-4)
- 2026 年 2 月 4 日：Dryad 发布数据集更新版本。

## 数据说明

UrbanEV 数据集用于支持城市环境中的电动汽车充电需求理解与预测。数据来自深圳市公共电动汽车充电站，覆盖 **2022 年 9 月 1 日至 2023 年 2 月 28 日** 的六个月时间段，包含季节变化信息。原始记录经过关键字段提取、异常值剔除、前向和后向填充缺失值，以及基于 IQR 方法的异常值处理。数据还按照时间和交通小区进行了聚合与筛选。

数据集主要包括：

- **充电数据**：占用情况、充电时长和充电量；
- **环境因素**：天气条件；
- **空间特征**：邻接矩阵和距离矩阵；
- **静态属性**：兴趣点（POI）、区域面积和道路长度。

## 数据获取

UrbanEV 相关数据已公开发布于 [Dryad](https://doi.org/10.5061/dryad.np5hqc04z)。部分数据也可通过 [Google Drive](https://drive.google.com/drive/folders/1VUgdb8uNgmtvO93BHBK_OrSxjndrF-48?usp=sharing) 和 [百度网盘](https://pan.baidu.com/s/1__-IjG39tz9VIhHVK3XpQw?pwd=1234#list/path=%2F) 获取。

本 GitHub 仓库中的 `data` 目录包含论文使用的预处理交通小区级数据，主要包括：

- 小区级小时和 5 分钟分辨率的预处理数据（1,362 个充电站、17,532 个充电桩）；
- 5 分钟分辨率的原始充电站级数据（1,682 个充电站、24,798 个充电桩）；
- 5 分钟分辨率的预处理充电站级数据。

充电站级数据的经纬度采用 **GCJ-02** 坐标系。新上传的预处理充电站级数据目录中还包含对应的详细说明文件。

### GitHub 分卷压缩包

2026-02-04 版本的 `UrbanEVDataset.zip` 也已放在 [`dataset_parts`](dataset_parts/) 目录中，拆分为 7 个分卷（`.z01`–`.z06` 和最后的 `.zip`），每个文件均小于 50 MB。请将全部 7 个文件下载到同一目录后合并并解压：

```bash
cd dataset_parts
zip -s 0 UrbanEVDataset.zip --out UrbanEVDataset-merged.zip
unzip -t UrbanEVDataset-merged.zip
unzip UrbanEVDataset-merged.zip
```

详细说明请参阅 [`dataset_parts/README.md`](dataset_parts/README.md)。请勿重命名、遗漏或单独解压任何分卷。

## 文件说明

### `code`

用于基于 UrbanEV 数据集进行分布式时间序列预测的传统模型和深度学习模型代码，包括多个模块化函数。代码支持 Last Observation、AR、ARIMA、FCNN、LSTM、GCN、GCN-LSTM 和 ASTGCN 等方法。

### `data`

包含经过异常值检测、零值检查等处理的 1 小时分辨率交通小区级数据，共覆盖 **275 个小区**、**1,362 个充电站** 和 **17,532 个充电桩**。主要文件包括：

- `adj.csv`：邻接矩阵；
- `duration.csv`：每小时充电时长，单位为小时；
- `e_price.csv`：电价，单位为元/千瓦时；
- `inf.csv`：275 个小区的筛选后充电站信息；
- `inf_raw.csv`：275 个小区的完整充电站信息；
- `occupancy.csv`：每小时充电占用率，单位为百分比；
- `s_price.csv`：服务费，单位为元/千瓦时；
- `volume.csv`：每小时充电量，单位为千瓦时；
- `volume-11kW.csv`：使用 11 kW 标准功率估算的替代充电量；
- `weather_airport.csv`：深圳宝安机场气象站数据；
- `weather_central.csv`：深圳市中心福田气象站数据；
- `weather_header.txt`：天气数据字段说明；
- `distance.csv`：275 个小区之间的距离矩阵；
- `poi.csv`：兴趣点数据。

需要注意的是，`occupancy.csv` 从充电桩可用性角度记录占用情况；而充电时长和充电量从实际充电使用角度统计，仅包含正在供电的充电桩。请根据研究目的选择相应数据。

### `code-transformer`

包含基于 Transformer 的分布式时间序列预测代码。预测所需的数据可通过 `../code/preprocess.py` 生成。

## 环境要求

项目的时间序列预测环境使用 Python 3.8 和 PyTorch 2.4.1。Linux 环境下可运行：

```shell
cd code
./init_env.sh
```

Windows 环境下可运行：

```shell
cd code
init_env.bat
```

由于 PyG Temporal 已停止维护，运行 ASTGCN 时可能遇到 `ModuleNotFoundError: No module named 'torch_geometric.utils.to_dense_adj'`。可将：

```python
from torch_geometric.utils.to_dense_adj import to_dense_adj
```

改为：

```python
from torch_geometric.utils import to_dense_adj
```

## 运行分布式预测

所有命令均假定当前工作目录为项目根目录。

### 1. 预处理数据

```shell
cd code
python preprocess.py
```

### 2. 运行统计模型和深度学习模型

```shell
cd code
python main.py --model fcnn --seq_len 12 --pred_len 3 --fold 1 --epoch 20
```

也可以运行批量实验脚本：

```shell
# Linux
cd code
./exp.sh

# Windows
cd code
./exp.bat
```

### 3. 运行 Transformer 模型

```shell
cd code-transformer
python run.py --model TimeXer --seq_len 12 --epoch 1 --pred_len 3 --fold 1
```

请确保 `label_len` 不大于 `seq_len`。批量实验可运行 `code-transformer/exp.sh` 或 `code-transformer/exp.bat`。

## 致谢

本项目参考了以下时间序列预测项目：

- [Time Series Library（TSLib）](https://github.com/thuml/Time-Series-Library)
- [PyG Temporal](https://github.com/benedekrozemberczki/pytorch_geometric_temporal)

感谢您对 UrbanEV 的关注与使用。
