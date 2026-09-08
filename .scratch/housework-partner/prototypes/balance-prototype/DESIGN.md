---
name: 协作天平粗原型 A/B/C
description: 本轮确认 B 的粗原型事实快照，非正式产品设计系统
colors:
  ink: "#282532"
  muted: "#666172"
  line: "#dddce5"
  paper: "#fff"
  ground: "#eeedf3"
  a: "#654496"
  a-soft: "#eee7f7"
  b: "#226b60"
  b-soft: "#e0f0eb"
  focus: "#654496"
typography:
  body:
    fontFamily: '-apple-system, BlinkMacSystemFont, "PingFang SC", "Microsoft YaHei", sans-serif'
  title:
    fontSize: "25px"
    letterSpacing: "-.025em"
  points:
    fontSize: "29px"
    fontWeight: 650
    lineHeight: 1.2
    letterSpacing: "-.03em"
rounded:
  panel: "14px"
  button: "10px"
  select: "9px"
  preview: "24px"
spacing:
  action-gap: "8px"
  record-gap: "10px"
  people-gap: "20px"
components:
  button-default:
    backgroundColor: "{colors.paper}"
    textColor: "{colors.ink}"
    rounded: "{rounded.button}"
    padding: "10px 14px"
  button-primary:
    backgroundColor: "{colors.a}"
    textColor: "{colors.paper}"
    rounded: "{rounded.button}"
    width: "100%"
---

# 协作天平粗原型设计记录

## Overview

**仅记录当前粗原型事实，不是正式产品设计系统或完整小程序验收。** 用户已在本轮确认 B「双方对照」，A/C 仅保留对照；当前最大 13 度倾斜、整数占比与提示语也已获本轮粗原型确认。frontmatter 仅在本目录内描述当前实现，不构成产品级规范。创意北极星与最终品牌语言未确认，本文件不代选。

来源为 [index.html](index.html) 与 [README.md](README.md)。业务决定仅引用[协作天平工单](../../issues/06-balance-prototype.md)，不在这里复制。当前为 code-first 静态 HTML/CSS/JavaScript，无图片资产；主要图形是源码中的天平几何 SVG，另有简单的方向及房屋线条图标。没有外部字体或图像素材。

**Key Characteristics:**
- 紫色与绿色区分双方，同时保留姓名与数字标签。
- 白色预览页面、浅灰工作台、细分隔线。
- B 为本轮确认布局，A/C 在同一模拟状态下保留对照。

## Colors

本人分值与入口使用 a，伴侣分值使用 b；a-soft / b-soft 分别用于浅底。中性色 ink、muted、line、paper、ground 承担文字、说明、分隔、页面与工作台背景。颜色记录当前实现，不是胜负或评价标签；没有提炼新的色阶。

## Typography

使用系统中文字体栈。页面标题对应 title；贡献分对应 points，使用等宽数字。B 将贡献分放大到 36px，C 缩小到 23px，月度总计为 24px。记录正文为 13px，说明多为 11–12px。这里记录具体角色，不推导通用字体比例。

## Layout

| 候选 | 当前信息顺序与差异 |
| --- | --- |
| A · 天平居中 | 月份 → 大天平浅底区 → 双方分值 → 提示 → 记录 |
| B · 双方对照 | 月份 → 紫绿并排分值卡 → 较小天平 → 提示 → 记录 |
| C · 月度记录 | 月份 → 月度总计与小天平 → 双方分值 → 记录 → 提示 |

桌面工作台最大宽 1090px，左侧控制区与 430px 预览并列；页面内边距为 24px。视口不超过 820px 时改为单列，预览宽度随容器，页面左右内边距为 20px，规则演示操作收进折叠区。C 总计右侧图形列从 146px 调整为 132px。底部固定切换器属于原型控制台，不是正式产品导航。

## Elevation & Depth

页面通过浅底与细线分区，没有卡片投影；唯一投影用于悬浮布局切换器。阴影与动效的源码值见 [.impeccable/design.json](.impeccable/design.json)。

## Shapes

预览外框大圆角，按钮与选择器较小圆角；B 的两块贡献卡只保留外侧圆角，形成并列整体。天平由直线、圆与托盘轮廓组成。移动预览外框圆角收至 18px。

## Components

- 按钮：最小高度 44px；默认白底细边框，选中方案为深底白字；禁用态透明度 .43。
- 月份导航：两侧方向按钮加原生选择器；焦点采用 3px 紫色外轮廓、3px 偏移。
- 贡献展示：姓名色点、贡献分、占比、完成次数；三方案共用内容，排版不同。
- 天平：当前几何部件变换过渡为 .48s；减少动态效果偏好下关闭过渡。最大 13 度倾斜与整数占比已获本轮粗原型确认；业务决定见工单。
- 家务记录：日期、可换行标题和右侧分值，细线分隔；C 更侧重记录阅读。
- 积分区域：点击入口展开说明和模拟收支；不构成完整积分页面设计。

## Do's and Don'ts

- **Do** 保留模拟数据与粗原型标识，让 A/B/C 在相同状态下比较。
- **Do** 使用源码和已有截图核对本目录文档，正式产品设计确定后再更新适用范围。
- **Don't** 将本轮粗原型确认扩展为正式产品设计系统、完整小程序验收或未确认的记录条数规则。
- **Don't** 将本目录的控制台、预览外框和切换器推广为正式产品组件。
