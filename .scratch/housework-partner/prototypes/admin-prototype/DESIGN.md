---
name: 平台后台交互粗原型
description: 当前模拟页面的事实快照，非正式产品设计系统
colors:
  ink: "#282d2b"
  muted: "#626b66"
  line: "#d8dfda"
  paper: "#ffffff"
  ground: "#f3f5f2"
  accent: "#226b60"
  soft: "#e1efe9"
  danger: "#a43530"
  danger-bg: "#fff1ed"
  warn: "#805311"
  warn-bg: "#fff5df"
typography:
  body:
    fontFamily: '-apple-system, BlinkMacSystemFont, "PingFang SC", "Microsoft YaHei", sans-serif'
    fontSize: "14px"
    lineHeight: 1.65
  heading:
    fontSize: "26px"
    fontWeight: 650
    lineHeight: 1.3
    letterSpacing: "-.02em"
rounded:
  section: "12px"
  button: "7px"
  input: "6px"
spacing:
  comparison-gap: "22px"
  section-padding: "24px"
components:
  button-primary:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.paper}"
    rounded: "{rounded.button}"
    padding: "8px 15px"
---

# 平台后台粗原型设计记录

## Overview

本文件只记录 [index.html](index.html) 已实现的样式和结构；不是产品级品牌规范。用户已确认固定左侧导航、独立家庭详情页、编辑并排对照，用户随后确认 Q4～Q6 的当前页面与交互提示；该确认不扩大为产品级品牌规范。没有增加创意隐喻、品牌承诺或正式技术选型。

操作型电脑后台使用系统中文字体、浅色背景和细分隔线，沿用已有粗原型的基础呈现方式。模拟开关置于独立的紫色折叠区，不构成后台正式功能。

## Colors

绿色用于当前导航、主操作和成功结果；棕色用于停用、下架及影响说明；红色用于风险操作与失败。所有状态同时提供文字，不能仅依靠颜色理解。白色内容区与浅灰背景区分模块，不使用装饰图片或渐变。

## Typography

正文 14px，辅助说明 12～13px，页面标题 26px，分组标题 18px。金额和计数使用等宽数字；不使用衬线或装饰展示字体。手机标题减至 23px。

## Layout

桌面左栏宽 212px，内容区左右内边距 36px，最大宽 1450px。模板对照为等宽两栏，家庭处理为独立详情页。运行概况按家庭组建、家务协作、兑换与兑现三个有意义的分组组织七项指标，不展示排名或下钻图表。

宽度不超过 1100px 时左栏减为 186px、主内边距减为 24px，概况分组纵向堆叠；不超过 760px 时导航收进顶部按钮，对照改为上下布局，主内边距减为 16px。数据表允许在自身容器中横向滚动，页面整体不应横向溢出。

## Elevation & Depth

内容区靠边框与底色分层，无卡片阴影。影响确认使用原生 dialog 与遮罩，只有 dialog 使用柔和投影。全部操作状态以文案和页面结果表达，没有装饰动画。

## Shapes

内容区圆角 12px，表格容器 9px，按钮 7px，输入框 6px。模板当前发布内容使用浅底，编辑区域使用白底；状态使用小面积色块与明确文字。

## Components

- 导航按角色提供入口，当前项通过深绿底与 aria-current 同时标记。
- 主按钮最小高 40px，输入最小高 42px；键盘焦点为 3px 紫色外圈，偏移 3px。
- 模板周期使用下拉、星期复选框、数值与日期字段；允许不完整草稿保存，发布才进行完整性校验。
- 原生 dialog 用于影响确认或放弃编辑，提交中禁用确认，明确失败保留可重试输入。
- 家庭原因按当前家庭保存在内存，失败保留，成功清空填写区并显示已生效原因。
- 明确区分空数据、筛选无匹配、读取失败与加载中。

## Do's and Don'ts

- 保持模拟标识，业务权限和字段范围引用工单最终 Answer。
- 样式事实与用户确认分开记录；不能将绿色主色或圆角参数当作用户已批准的品牌规则。
- 不将原型演示台、模拟账号开通或异常注入能力作为正式后台模块。
- 不将此 HTML 直接认定为正式业务实现；真实鉴权、持久化和并发需另行实现与验收。
