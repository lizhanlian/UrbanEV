# UrbanEVDataset 分卷

这是 Dryad **2026-02-04** 版本 `UrbanEVDataset.zip` 的分卷 ZIP 文件。分卷文件用于绕过 GitHub 单文件大小限制；所有分卷必须放在同一目录中。

## 文件组成

- `UrbanEVDataset.z01`
- `UrbanEVDataset.z02`
- `UrbanEVDataset.z03`
- `UrbanEVDataset.z04`
- `UrbanEVDataset.z05`
- `UrbanEVDataset.z06`
- `UrbanEVDataset.zip`（最后一卷，必须保留 `.zip` 扩展名）

## 使用方法

下载本目录中的全部 7 个文件后，在该目录执行：

```bash
zip -s 0 UrbanEVDataset.zip --out UrbanEVDataset-merged.zip
unzip -t UrbanEVDataset-merged.zip
unzip UrbanEVDataset-merged.zip
```

上述 `zip -s 0` 命令会将 `.z01` 至 `.z06` 与最后的 `.zip` 卷合并为一个普通 ZIP，然后即可使用 `unzip` 解压。也可以使用支持 split ZIP 的 7-Zip 等工具直接打开最后的 `.zip` 文件。不要单独解压 `.z01` 文件，也不要重命名或遗漏任何分卷。

原始 Dryad 数据集页面：<https://datadryad.org/dataset/doi:10.5061/dryad.np5hqc04z>

原始 ZIP 的 SHA-256：

```text
a041322ed75eab8c49095fe5d0501b05f8d56dae16209586f8e4d7333ad1051f  UrbanEVDataset.zip
```
