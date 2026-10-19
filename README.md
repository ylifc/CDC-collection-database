# CDC集合数据库

本仓库保存两份公共生物信息学参考数据库的本地蛋白质 FASTA 快照，方便疾控相关科研中的资料管理、版本留存和研究引用。两份文件均按原始本地字节上传，未筛选、去重、重新注释或修改序列。

这是个人整理的资料仓库，不代表任何疾控机构、NCBI 或 VFDB 的官方发布。

## 文件内容

| 文件 | 内容说明 | FASTA 记录数 | 大小 |
| --- | --- | ---: | ---: |
| [AMRProt.fa](AMRProt.fa) | 根据文件名和记录头格式，对应 NCBI AMRFinderPlus 蛋白质参考数据；该数据库覆盖耐药及部分应激反应、毒力等相关注释，并非仅含耐药条目。 | 9,998 | 4,658,980 字节（4.44 MiB） |
| [VFDB_complete_pro.fas](VFDB_complete_pro.fas) | 根据记录标识和注释格式，对应 VFDB 细菌毒力因子相关蛋白质参考数据。 | 34,970 | 22,206,967 字节（21.18 MiB） |

记录数按 FASTA 中以 `>` 开头的记录头统计，不代表独立基因、功能或物种数量。两份文件共 26,865,947 字节（25.62 MiB）。本仓库仅包含这两份序列文件，不包含上游软件、全部配套注释表或运行所需索引。

## 下载与完整性校验

- [下载 AMRProt.fa](https://raw.githubusercontent.com/ylifc/CDC-collection-database/main/AMRProt.fa)
- [下载 VFDB_complete_pro.fas](https://raw.githubusercontent.com/ylifc/CDC-collection-database/main/VFDB_complete_pro.fas)
- [下载 SHA256SUMS](https://raw.githubusercontent.com/ylifc/CDC-collection-database/main/SHA256SUMS)

也可使用仓库页面的 **Code → Download ZIP** 获取全部文件，或克隆仓库：

```bash
git clone https://github.com/ylifc/CDC-collection-database.git
cd CDC-collection-database
sha256sum -c SHA256SUMS
```

校验成功时，两份数据均显示 `OK`。如果分别下载文件，请把数据文件和 `SHA256SUMS` 放在同一目录，再运行校验命令。

| 文件 | SHA-256 |
| --- | --- |
| AMRProt.fa | `dc21f47094024efb9bd46a7e239933323fe0eb24190185847e1f426f1696fe56` |
| VFDB_complete_pro.fas | `599b8ece2b8aab982168f035f9faada6443434c048a2efbd9908db4613f6a619` |

## 来源与版本记录

本次入库日期为 **2026-10-19**，仅表示本仓库保存快照的日期。原始下载日期、确切上游版本和发布编号尚未核实；文件修改时间不能替代这些信息。机器可读清单见 [snapshot.json](snapshot.json)。

- **NCBI AMRFinderPlus**：[官方介绍](https://www.ncbi.nlm.nih.gov/pathogens/antimicrobial-resistance/AMRFinder/)、[数据库文档](https://github.com/ncbi/amr/wiki/AMRFinderPlus-database)、[官方版本目录](https://ftp.ncbi.nlm.nih.gov/pathogen/Antimicrobial_resistance/AMRFinderPlus/database/)。官方文档列有 `AMRProt.fa`；本地文件名和记录头与其格式一致，尚未与特定官方版本逐字节比对。
- **VFDB**：[官方主页](https://www.mgc.ac.cn/VFs/main.htm)、[官方下载页](https://www.mgc.ac.cn/VFs/download.htm)。官方区分核心集和完整集，当前完整蛋白集下载名为 `VFDB_setB_pro.fas.gz`。本地 `VFDB_complete_pro.fas` 的命名来源尚未确认，不能据此断言其等同于当前官方完整集。

当前仓库是静态快照，不自动同步上游更新。正式引用时，建议同时记录本仓库提交号和文件校验值。后续如有可验证的原始下载记录，可据此补充版本信息。

## 文件格式与解释范围

两份文件均为蛋白质 FASTA。原始记录头、序列字符及换行均予以保留；`VFDB_complete_pro.fas` 的少量记录头含非 UTF-8 字节，读取工具需要妥善处理原始注释编码，序列行均为 ASCII 字符。

数据库中的注释或序列匹配不能单独证明临床耐药表型、致病性或个体感染情况，应结合原数据库文档、研究设计和其他证据解读。

## 许可与署名

两份数据分别遵循原始来源的条款，**不存在覆盖全部数据的统一 MIT 或 CC0 许可**。完整说明见 [DATA_LICENSES.md](DATA_LICENSES.md)。

- NCBI AMRFinderPlus 官方声明其软件和数据库属于美国政府作品、公共领域；使用时请保留来源并按官方要求适当引用。
- VFDB 官方声明其数据（包括序列）适用 **[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)**。使用和再分发须遵守署名、非商业用途等条件；商业使用请联系原维护方。

## 参考文献

1. Feldgarden M, et al. *AMRFinderPlus and the Reference Gene Catalog facilitate examination of the genomic links among antimicrobial resistance, stress response, and virulence.* Scientific Reports. 2021;11:12728. [doi:10.1038/s41598-021-91456-0](https://doi.org/10.1038/s41598-021-91456-0).
2. Zhou SY, Liu B, Zheng DD, Chen LH, Yang J. *VFDB 2025: an integrated resource for exploring anti-virulence compounds.* Nucleic Acids Research. 2025;53(D1):D871–D877. [doi:10.1093/nar/gkae968](https://doi.org/10.1093/nar/gkae968).

引用上述论文不表示本地快照具有对应年份的版本身份；具体引用方式以原数据库官方说明为准。
