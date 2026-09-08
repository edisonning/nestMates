# Issue tracker: Local Markdown

本项目的需求规格和工单保存在 `.scratch/`。

## 文件约定

- 每个功能一个目录：`.scratch/<feature-slug>/`。
- 需求规格：`.scratch/<feature-slug>/spec.md`。
- 实施工单：`.scratch/<feature-slug>/issues/<NN>-<slug>.md`，
  从 `01` 开始编号，每张工单独立成文件。
- 分诊状态记录在工单顶部附近的 `Status:` 行；
  状态名称见 `triage-labels.md`。
- 评论和讨论追加在文件底部的 `## Comments` 下。

## 发布和读取

当技能要求“发布到 issue tracker”时，按上述路径创建对应文件，
并按需创建目录。

当技能要求“获取相关工单”时，读取用户指定路径的文件。
如果只提供编号，先在相关功能目录定位；存在多个匹配时确认目标。

## Wayfinder 操作

以下约定用于 `/wayfinder` 的探索工单。

- 地图：`.scratch/<effort>/map.md`，包含
  Notes、Decisions-so-far、Fog。
- 子工单：`.scratch/<effort>/issues/<NN>-<slug>.md`，
  从 `01` 编号，正文记录待回答的问题。
- `Type:` 取值为 `research`、`prototype`、`grilling` 或 `task`。
- 依赖记录在顶部附近的 `Blocked by: NN, NN`；
  所列工单全部为 `resolved` 时解除阻塞。
- 按编号选择尚未解决、无阻塞且未被领取的工单。
- 开始工作前设置 `Status: claimed` 并保存。
- 完成后在 `## Answer` 下追加答案，设置 `Status: resolved`，
  并将结论摘要及工单链接追加到地图的 Decisions-so-far。

Wayfinder 的 `claimed`、`resolved` 表示探索执行状态；
普通工单的分诊状态使用 `triage-labels.md` 中的五个名称。
