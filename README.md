# 八字算法与古籍对照 · Bazi Core

从 [知几排盘](https://github.com/weihaoyang/qimen-llm-chart) 提取的八字 TypeScript 算法与测试，包含四柱、神煞、十神关系和结构分析。共享历法与奇门模块按运行依赖一并保留。采用固定提交的 [3meta 修正版](https://github.com/weihaoyang/3meta-patched)和 [lunar 修正版](https://github.com/weihaoyang/lunar-patched)，无需安装后修改依赖。

```sh
npm install
npm test
npm run typecheck
```

入口 `src/lib/bazi/chart.ts`。发布后可通过 `npm install @singseq/bazi-core` 安装。

发布后可直接调用：

```ts
import { buildBaziChartFromProfile } from "@singseq/bazi-core";
import { normalizeProfileInput } from "@singseq/bazi-core/profile";

const profile = normalizeProfileInput({ calendarMode: "solar", datetime: "2024-02-04T16:28", timeZone: "Asia/Shanghai", gender: "male", timeBasis: "civil" });
const chart = buildBaziChartFromProfile(profile);
console.log(chart.raw.pillars);
```

## 古籍与案例

上海 2024-02-04，依赖库立春约 16:27:07；16:27 年柱癸卯，16:28 年柱甲辰。对照 [香港天文台 2024 年历](https://www.hko.gov.hk/tc/gts/astron2024/files/HKO_almanac_2024.pdf)，测试见 `src/lib/bazi/chart.test.ts`。

神煞的版本、规则及待核问题见[研究论文](https://github.com/weihaoyang/qimen-llm-chart/blob/main/docs/research/calculation-audit-paper.md)。案例验证计算字段，不构成对预测效果的验证。

## 授权

代码 [GPL-3.0-only](LICENSE)，源自知几排盘；3meta 与 lunar-typescript 的 MIT 许可见 `LICENSES/`。不附影像与原始基准数据；[影像权利记录](https://github.com/weihaoyang/qimen-llm-chart/blob/main/docs/research/sources/RIGHTS.md)。
