# WeUI for mpvue

> WeUI-mpvue 是一套基于 WeUI 开发的 mpvue 组件库，增加了一些新的特性和组件。
> 我的目标是源于 WeUI，更胜 WeUI。

[![npm version](https://img.shields.io/npm/v/weui-mpvue.svg?style=flat)](https://www.npmjs.com/package/weui-mpvue) [![npm download](https://img.shields.io/npm/dt/weui-mpvue.svg?style=flat)](https://www.npmjs.com/package/weui-mpvue) [![license](https://img.shields.io/npm/l/weui-mpvue.svg?style=flat)](https://github.com/kankungyip/weui-mpvue/blob/master/LICENSE)

## 说明

组件库尽量以 Vue 组件形式实现，部分组件因 mpvue 尚不支持的语法而无法实现，详细见[不支持列表](http://mpvue.com/mpvue/#_14)。

## 安装

```bash
$ yarn add weui-mpvue
```

## 预览

```bash
$ git clone https://github.com/kankungyip/weui-mpvue
$ cd weui-mpvue
$ yarn run example
```

用[微信web开发者工具](https://mp.weixin.qq.com/debug/wxadoc/dev/devtools/download.html)打开`weui-mpvue`项目目录。

## 使用
### 引入全局样式

```vue
<style lang="less">
@import "<project_dir>/node_modules/weui-mpvue/theme/weui";
</style>
```

并非全部组件样式，仅全局（字体、颜色等）样式和未被 Vue 组件化的 WeUI 样式。

### 使用组件

```vue
<template>
  <ui-article :content="content" />
</template>

<script>
import uiArticle from 'weui-mpvue/components/article'

export default {
  components: {
    uiArticle,
  },

  data () {
    return {
      content: `# 大标题

## 章标题

### 1.1 节标题

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

![](https://avatars1.githubusercontent.com/u/1096425?s=460&v=4)

### 1.2 节标题

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
`,
    }
  },
}
</script>
```

需要 Slot 支持暂未实现的组件，请使用全局样式。

## 组件状态
### 新组件

- [ ] `Avatar`
- [ ] `Countdown`
- [ ] `Counter`
- [ ] `Ellipsis`
- [x] `LoadingBar`
- [ ] `NoticeBar`
- [ ] `Price`
- [ ] `Steps`
- [ ] `Tag`

_部分组件样式源自 [zanui](https://github.com/youzan/zanui-weapp) 和 [minui](https://github.com/meili/minui) 项目，并对其进行了必要重构以符合 WeUI 样式。_

### 表单

- [x] `Agree`
- [x] `Button`
- [ ] `ButtonArea`（需要 Slot 支持）
- [ ] `Counter`
- [ ] `List`（需要 Slot 支持）
- [x] `Cell`（需配合 `List` 一起使用）
- [x] `Input`（需配合 `List` 一起使用）
- [x] `CheckboxGroup`
- [x] `RadioGroup`
- [x] `Select`
- [x] `Switch`
- [x] `Uploader`

### 基础组件

- [x] `Article`
- [ ] `Avatar`
- [x] `Badge`
- [ ] `BadgeBox`（需要 Slot 支持）
- [ ] `Countdown`
- [ ] `Ellipsis`
- [ ] `Flex`（需要 Slot 支持）
- [ ] `Row`
- [ ] `Col`
- [x] `Footer`
- [x] `Grid`
- [x] `Icons`
- [x] `Loadmore`
- [ ] `Panel`（需要 Slot 支持）
- [x] `MediaBox`
- [x] `Preview`
- [ ] `Price`
- [x] `Progress`
- [ ] `Tag`

### 操作反馈

- [x] `LoadingBar`
- [x] `Msg`
- [ ] `NoticeBar`
- [x] `Toptips`

### 导航相关

- [ ] `Tabs`（需要 Slot 支持）
- [ ] `Steps`

### 搜索相关

- [x] `SearchBar`

## 新特性

- WeUI 样式按需引用
- `Article` 组件自动解析 markdown 格式内容，支持自定义样式：.weui-article__<TAG>
- `Badge` 支持自定义显示最大值，超过最大值显示 max+
- `Grid` 自持自定义列数
- `Icons` 支持自定义图标，推荐使用 [iconfont.cn](http://iconfont.cn)
- `LoadingBar` 引入独立 API `vm.$loading`，整合 `wx.showNavigationBarLoading`
- `SearchBar` 实时查询结果反馈
- `Toptips` 引入独立 API `vm.$toptips`
- `Uploader` 整合 `wx.uploadFile`，支持中断操作和进度提示

## 计划

- 为表单引入独立 API `vm.$form`，方便表单数据的获取和校验

## 开发文档

有点懒，暂时没有编写，请参考 `example` 目录下的示例源码。

## License

[The MIT License](http://opensource.org/licenses/MIT)

请自由地享受和参与开源
