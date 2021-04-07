# @kkyjh Fork Version

# react-native-drag-sort

Drag and drop sort control for react-native

![GitHub license](https://img.shields.io/badge/license-MIT-green.svg)
[![npm](https://img.shields.io/npm/v/react-native-drag-sort.svg?style=flat)](https://npmjs.com/package/react-native-drag-sort)

### Language

- [English](https://github.com/mochixuan/react-native-drag-sort/blob/master/README.md)
- [中文](https://github.com/mochixuan/react-native-drag-sort/blob/master/README_ZH.md)

### Installation

```bash
yarn add react-native-drag-sort
or
npm i react-native-drag-sort --save

export { DragSortableView, AutoDragSortableView }
```

### 重要提示

1. [Android 版演示地址](https://fir.im/dragsort)
2. 必须要写属性 keyExtractor={(item,index)=> item.id} id 为你数据的唯一识别，没有可用 index 代替 item.id。
3. Android Debug 模式比较卡的话。请打包再安装测试，release 是不会卡的。或者 iOS 下测试动画是很流畅。

#### 2020.2 新增演示固定添加按钮 Demo

[ScrollFixedAddPage](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/ScrollFixedAddPage.js)

![](https://user-gold-cdn.xitu.io/2020/2/10/1702ea81299f097d?w=240&h=400&f=gif&s=863218)

#### 2020.2 去除了 componentWillReceiveProps/componentWillMount 方法。

> React16.3 后使用 Fiber, React 渲染变成了异步渲染，具体请 Google React Fiber.

- React < 16.3 请引用 react-native-drag-sort@2.0.1
- React > 16.3 请引用 react-native-drag-sort@latest

#### 2020.1 新增自动滑动功能

##### 如果你不需要自动滑动功能可以使用或者对 Android 效果不满意可以暂时使用 DragSortableView(稳定、可靠、较长时间没人提 issus Bug 了)，如果你想要使用自动滑动请使用 AutoDragSortableView。

##### 自动滑动功能完成。iOS 实现平滑的自动滑动功能。Android 实现固定时间滑动 1 个 Item。由于 Android 调用 scrollTo 后刷新比较缓慢，造成抖动，所以使用固定时间滑动 1 个 Item,这个折中的方法。也可以通过参数: autoThrottle(单位时间滑动距离)、autoThrottleDuration(定时滑动一个距离的时间)。

1. 建议使用 Demo 设置: Android 自动滑动时每 400ms 滑动一个 Item 高度, iOS 自动滑动时每 10ms 滑动 2。
2. 如果想实现 Android 和 iOS 一样的效果可以配置 autoThrottle={2}、autoThrottleDuration={10}
3. 后期有时间会优化: 触发滑动条件优化、Android 滑动时抖动优化。

[AutomaticSlidingOnePage](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/AutomaticSlidingOnePage.js)

![](https://user-gold-cdn.xitu.io/2020/1/31/16ff953e160a4a8c?w=240&h=514&f=gif&s=3394945)

[AutomaticSlidingThreePage](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/AutomaticSlidingThreePage.js)

![](https://user-gold-cdn.xitu.io/2020/1/31/16ff9538f47c623a?w=240&h=514&f=gif&s=4241359)

#### 2019.10

> 根据网友需求添加一个新的场景。

- 添加属性(isDragFreely): 是否限制拖动空间。
- 添加属性移动时回调函数(onDragging)
- 添加演示 Demo: DragDeletePage

[DragDeletePage](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/DragDeletePage.js)

![dragdelete.gif](https://upload-images.jianshu.io/upload_images/2646598-4d22ddb8f92a6563.gif?imageMogr2/auto-orient/strip)

#### 2019.7

> 1.x 版本结束，该优化的都优化，而且出现的问题都已经解决。接下来将编写 2.x 版本，预计添加自动兼容 ScrollView 滑动、滑动删除功能等。

- 修复一个小问题。
- 添加一个熟悉 keyExtractor:(item,index) => key 实现性能优化，类似 FlatList 的 keyExtractor，当删除 Item 时不会再闪烁(重绘)。
- 添加 delayLongPress 属性:按下到触发的时间，自定义长按多久出发

#### 2019.6

> 新增顶部固定功能，可以设置开始连续几个为不可拖动功能，类似今日头条一样，该功能和今日头条拖拽一样，可以去对比一下。

[SortAndFixedPage](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/SortAndFixedPage.js)

![ezgif.com-resize.gif](https://upload-images.jianshu.io/upload_images/2646598-405b01d61547c972.gif?imageMogr2/auto-orient/strip)

#### 2019.3:

> 新增单行拖拽演示，其实这个功能一致，这个拖拽插件本来就是自适应行,有时间会整体优化下 ScrollView 问题，使控件自带 ScrollView 功能。

[OneRowsPage](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/OneRowsPage.js)

![one-line.gif](https://upload-images.jianshu.io/upload_images/2646598-dd17c76291514316.gif?imageMogr2/auto-orient/strip)

#### 2019.2:

> 优化拖拽不移动时自动恢复，现在这个插件应该没有任何问题。新加一个实战演示例子，后面有时间会对这个例子进行加动画，删除时 item 向下到待选的 item 动画，和待选到 item。还有滑动时自动向下滑动动画。

[CommonSortPage](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/CommonSortPage.js)

![ezgif.com-video-to-gif.gif](https://upload-images.jianshu.io/upload_images/2646598-bd118152420cc0a9.gif?imageMogr2/auto-orient/strip)

---

### Performance

[ScrollPage](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/ScrollPage.js)

![Demonstration.gif](https://upload-images.jianshu.io/upload_images/2646598-f3ece6209cb07e43.gif?imageMogr2/auto-orient/strip)

### Example

- [ScrollView](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/ScrollPage.js)
- [View](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/NonScrollPage.js)
- [Fixed Rows](https://github.com/mochixuan/react-native-drag-sort/blob/master/Example/app/container/FixedRowsPage.js)

```jsx
<DragSortableView
  dataSource={this.state.data}
  parentWidth={parentWidth}
  childrenWidth={childrenWidth}
  childrenHeight={childrenHeight}
  marginChildrenTop={marginChildrenTop}
  onDataChange={(data) => {
    // delete or add data to refresh
    if (data.length != this.state.data.length) {
      this.setState({
        data: data,
      });
    }
  }}
  keyExtractor={(item, index) => item.id}
  onClickItem={(data, item, index) => {}}
  renderItem={(item, index) => {
    return this.renderItem(item, index);
  }}
/>
```

### API

isRequired if there is a \* in the name field

| name                     | Proptypes | Description                                                             |
| ------------------------ | --------- | ----------------------------------------------------------------------- |
| **dataSource** \*        | array     |
| **parentWidth**          | number    | parent width                                                            |
| **childrenHeight** \*    | number    | Each item height                                                        |
| **childrenWidth** \*     | number    | Each item width                                                         |
| **marginChildrenTop**    | number    | So the item's outermost view adds margin, you can only use this method. |
| **marginChildrenBottom** | number    |
| **marginChildrenLeft**   | number    |
| **marginChildrenRight**  | number    |
| **sortable**             | bool      | Do not allow dragging                                                   |
| **onClickItem**          | func      | click                                                                   |
| **onDragStart**          | func      |
| **onDragEnd**            | func      |
| **onDataChange**         | func      | This method is called every time the data changes.                      |
| **renderItem** \*        | func      | render item view                                                        |
| **fixedItems**           | array     | no remove                                                               |
| **keyExtractor**         | func      | (item,index) => key                                                     |
| **delayLongPress**       | number    |
| **isDragFreely**         | bool      | Whether to limit the drag space                                         |
| **onDragging**           | func      |
| **maxScale**             | number    |
| **minOpacity**           | number    |
| **scaleDuration**        | number    |
| **slideDuration**        | number    |
| **autoThrottle**         | number    |
| **autoThrottleDuration** | number    |
