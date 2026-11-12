# 八字算法与古籍对照 · Bazi Core

从 [知几排盘](https://github.com/weihaoyang/qimen-llm-chart) 提取的八字 TypeScript 算法与测试，包含四柱、神煞、十神关系和结构分析。共享历法与奇门模块按运行依赖一并保留。运行前执行 `npm run patch:3meta`，其中也包含 lunar-typescript 的节气与起运修正。

```sh
npm install
npm run patch:3meta
npm test
npm run typecheck
```

入口 `src/lib/bazi/chart.ts`。目前提供 TypeScript 源码，尚未发布 npm 包。

## 古籍与案例

上海 2024-02-04，依赖库立春约 16:27:07；16:27 年柱癸卯，16:28 年柱甲辰。对照 [香港天文台 2024 年历](https://www.hko.gov.hk/tc/gts/astron2024/files/HKO_almanac_2024.pdf)，测试见 `src/lib/bazi/chart.test.ts`。

神煞的版本、规则及待核问题见[研究论文](https://github.com/weihaoyang/qimen-llm-chart/blob/main/docs/research/calculation-audit-paper.md)。案例验证计算字段，不构成对预测效果的验证。

## 授权

代码 [GPL-3.0-only](LICENSE)，源自知几排盘；3meta 与 lunar-typescript 的 MIT 许可见 `LICENSES/`。不附影像与原始基准数据；[影像权利记录](https://github.com/weihaoyang/qimen-llm-chart/blob/main/docs/research/sources/RIGHTS.md)。
