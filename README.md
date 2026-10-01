# Nanshan Street View — Raw

南山区研究区百度街景原始影像数据集。

## 数据内容

- 1,909 个有效采样点
- 每个采样点包含 0°、90°、180°、270° 四个方向
- 共 7,636 张有效影像
- 512×512，JPEG 编码（历史文件扩展名为 `.png`）
- 文件名包含采样点 ID、WGS84 经度、纬度和方向

数据压缩包位于仓库的 **Releases** 页面；`MANIFEST.csv` 提供每个文件的相对路径、字节数和 SHA-256。

## 目录结构

```text
data/
└── <point_id>/
    └── <point_id>_<longitude>_<latitude>_<heading>.png
```

本仓库仅发布与最终处理数据一一对应的有效原始影像，已排除 134 个孤立、诊断或旧版本文件。

## 下载与校验

```bash
gh release download v1.0.0 --repo Aspartame-yao/nanshan-street-view-raw
shasum -a 256 -c RELEASE_ASSETS.sha256
for file in *part-*.tar; do tar -xf "$file"; done
```

## 使用说明

影像来源于百度地图相关接口。本数据集不授予影像版权或额外许可；使用者需自行遵守百度地图条款、隐私要求及所在地法律。仓库不包含 API 密钥、访问令牌或请求凭据。
