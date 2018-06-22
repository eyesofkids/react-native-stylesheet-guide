# React-Native 樣式指南

`React-Native` 的樣式基本上是實現了 `CSS` 的一個子集，並且屬性名不完全一致，所以當你開始在編寫 `React-Native` 之前，可以先簡要了解一下。

## 當前對應 RN 版本

0.44

## 目錄

- [Properties 屬性](#user-content-properties)
  - [Text 純文字](#user-content-text)
  - [Dimension 尺寸](#user-content-dimension)
  - [Positioning 定位](#user-content-positioning)
  - [Margin 外部白](#user-content-margin)
  - [Padding 內補白](#user-content-padding)
  - [Border 邊框](#user-content-border)
  - [Background 背景](#user-content-background)
  - [Transform 轉換](#user-content-transform)
  - [Flexbox 彈性盒](#user-content-flexbox)
  - [Other 其他](#user-content-other)
- [Values 取值](#user-content-values)
  - [Color 顏色](#user-content-color)
  - [Number 數值](#user-content-number)
- [Units 單位](#user-content-units)
  - [Pt 點](#user-content-pt)
- [PixelRatio 像素密度](#user-content-pixelratio)

<a name="properties"></a>

## Properties 屬性

<a name="text"></a>

### Text 純文字（18）

| 屬性名                                       | 取值                                                                                                     | 描述                                                                                                                                                                                                                                                             |
| -------------------------------------------- | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| color                                        | [&lt;color&gt;](#user-content-color)                                                                     | 對應 `CSS` [color](http://css.doyoe.com/properties/color/color.htm) 屬性                                                                                                                                                                                         |
| fontFamily                                   | string                                                                                                   | 對應 `CSS` [font-family](http://css.doyoe.com/properties/font/font-family.htm) 屬性                                                                                                                                                                              |
| fontSize                                     | [&lt;number&gt;](#user-content-number)                                                                   | 對應 `CSS` [font-size](http://css.doyoe.com/properties/font/font-size.htm) 屬性                                                                                                                                                                                  |
| fontStyle                                    | `normal`, `italic`                                                                                       | 對應 `CSS` [font-style](http://css.doyoe.com/properties/font/font-style.htm) 屬性，但閹割了 `oblique` 取值                                                                                                                                                       |
| fontWeight                                   | `normal`, `bold` `100~900`                                                                               | 對應 `CSS` [font-weight](http://css.doyoe.com/properties/font/font-weight.htm) 屬性，但閹割了 `bolder, lighter` 取值                                                                                                                                             |
| lineHeight                                   | [&lt;number&gt;](#user-content-number)                                                                   | 對應 `CSS` [line-height](http://css.doyoe.com/properties/text/line-height.htm) 屬性                                                                                                                                                                              |
| textAlign                                    | `auto`, `left`, `right`, `center`, `justify`<sup>`iOS`</sup>                                             | 對應 `CSS` [text-align](http://css.doyoe.com/properties/text/text-align.htm) 屬性，但增加了 `auto` 取值。當取值為 `justify` 時，在 `Android` 上會變為 `left`                                                                                                     |
| textDecorationLine                           | `none`, `underline`, `line-through`, `underline line-through`                                            | 對應 `CSS` [text-decoration-line](http://css.doyoe.com/properties/text-decoration/text-decoration-line.htm) 屬性，但閹割了 `overline`, `blink` 取值                                                                                                              |
| textShadowColor                              | [&lt;color&gt;](#user-content-color)                                                                     | 對應 `CSS` [text-shadow](http://css.doyoe.com/properties/text-decoration/text-shadow.htm) 屬性中的顏色定義                                                                                                                                                       |
| textShadowOffset                             | {<br>width:[&lt;number&gt;](#user-content-number),<br>height:[&lt;number&gt;](#user-content-number)<br>} | 對應 `CSS` [text-shadow](http://css.doyoe.com/properties/text-decoration/text-shadow.htm) 屬性中的陰影偏移定義                                                                                                                                                   |
| textShadowRadius                             | [&lt;number&gt;](#user-content-number)                                                                   | 在 `CSS` 中，陰影的圓角大小取決於元素的圓角定義，不需要額外定義                                                                                                                                                                                                  |
| includeFontPadding<br /><sup>`Android`</sup> | [&lt;bool&gt;](#user-content-bool)                                                                       | Android 在默認情況下會為文字額外保留一些 padding，以便留出空間擺放上標或是下標的文字。對於某些字型來說，這些額外的 padding 可能會導致文字難以垂直居中。如果你把 textAlignVertical 設定為 center 之後，文字看起來依然不在正中間，那麼可以嘗試將本屬性設定為 false |
| textAlignVertical<br /><sup>`Android`</sup>  | `auto`, `top`, `bottom`, `center`                                                                        | 對應 `CSS` [vertical-align](http://css.doyoe.com/properties/text/vertical-align.htm) 屬性，增加了 `auto` 取值，`center` 取代了 `middle`，並閹割了 `baseline, sub` 等值                                                                                           |
| fontVariant<br /><sup>`iOS`</sup>            | `small-caps`, `oldstyle-nums`, `lining-nums`, `tabular-nums`, `proportional-nums`                        | 對應 `CSS` [font-variant](http://css.doyoe.com/properties/font/font-variant.htm) 屬性，但取值更豐富                                                                                                                                                              |
| letterSpacing<br /><sup>`iOS`</sup>          | [&lt;number&gt;](#user-content-number)                                                                   | 對應 `CSS` [letter-spacing](http://css.doyoe.com/properties/text/letter-spacing.htm) 屬性                                                                                                                                                                        |
| textDecorationColor<br /><sup>`iOS`</sup>    | [&lt;color&gt;](#user-content-color)                                                                     | 對應 `CSS` [text-decoration-color](http://css.doyoe.com/properties/text-decoration/text-decoration-color.htm) 屬性                                                                                                                                               |
| textDecorationStyle<br /><sup>`iOS`</sup>    | `solid`, `double`, `dotted`, `dashed`                                                                    | 對應 `CSS` [text-decoration-style](http://css.doyoe.com/properties/text-decoration/text-decoration-style.htm) 屬性，但閹割了 `wavy` 取值                                                                                                                         |
| writingDirection<br /><sup>`iOS`</sup>       | `auto`, `ltr`, `rtl`                                                                                     | 對應 `CSS` [direction](http://css.doyoe.com/properties/writing-modes/direction.htm) 屬性，增加了 `auto` 取值                                                                                                                                                     |

<a name="dimension"></a>

### Dimension 尺寸（6）

| 屬性名    | 取值                                   | 描述                                                                                   |
| --------- | -------------------------------------- | -------------------------------------------------------------------------------------- |
| width     | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [width](http://css.doyoe.com/properties/dimension/width.htm) 屬性           |
| minWidth  | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [min-width](http://css.doyoe.com/properties/dimension/min-width.htm) 屬性   |
| maxWidth  | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [max-width](http://css.doyoe.com/properties/dimension/max-width.htm) 屬性   |
| height    | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [height](http://css.doyoe.com/properties/dimension/height.htm) 屬性         |
| minHeight | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [min-height](http://css.doyoe.com/properties/dimension/min-height.htm) 屬性 |
| maxHeight | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [max-height](http://css.doyoe.com/properties/dimension/max-height.htm) 屬性 |

<a name="positioning"></a>

### Positioning 定位（6）

| 屬性名   | 取值                                   | 描述                                                                                                                |
| -------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| position | `absolute`, `relative`                 | 對應 `CSS` [position](http://css.doyoe.com/properties/positioning/position.htm) 屬性，但閹割了 `static, fixed` 取值 |
| top      | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [top](http://css.doyoe.com/properties/positioning/top.htm) 屬性                                          |
| right    | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [right](http://css.doyoe.com/properties/positioning/right.htm) 屬性                                      |
| bottom   | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [bottom](http://css.doyoe.com/properties/positioning/bottom.htm) 屬性                                    |
| left     | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [left](http://css.doyoe.com/properties/positioning/left.htm) 屬性                                        |
| zIndex   | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [z-index](http://css.doyoe.com/properties/positioning/z-index.htm) 屬性                                  |

<a name="margin"></a>

### Margin 外部白（7）

| 屬性名           | 取值                                   | 描述                                                                                                                                                                                  |
| ---------------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| margin           | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [margin](http://css.doyoe.com/properties/margin/margin.htm) 屬性，不同的是，它只能定義一個參數，如需分別定義`上、右、下、左`4 個方位的外補白，可以通過下面的單向外部白屬性 |
| marginHorizontal | [&lt;number&gt;](#user-content-number) | 無對應的 `CSS` 屬性。其效果相當於同時設定 `marginRight` 和 `marginLeft`                                                                                                               |
| marginVertical   | [&lt;number&gt;](#user-content-number) | 無對應的 `CSS` 屬性。其效果相當於同時設定 `marginTop` 和 `marginBottom`                                                                                                               |
| marginTop        | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [margin-top](http://css.doyoe.com/properties/margin/margin-top.htm) 屬性                                                                                                   |
| marginRight      | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [margin-right](http://css.doyoe.com/properties/margin/margin-right.htm) 屬性                                                                                               |
| marginBottom     | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [margin-bottom](http://css.doyoe.com/properties/margin/margin-bottom.htm) 屬性                                                                                             |
| marginLeft       | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [margin-left](http://css.doyoe.com/properties/margin/margin-left.htm) 屬性                                                                                                 |

<a name="padding"></a>

### Padding 內部白（7）

| 屬性名            | 取值                                   | 描述                                                                                                                                                                                     |
| ----------------- | -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| padding           | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [padding](http://css.doyoe.com/properties/padding/padding.htm) 屬性，不同的是，它只能定義一個參數，如需分別定義`上、右、下、左`4 個方位的內補白，可以通過下面的單向內部白屬性 |
| paddingHorizontal | [&lt;number&gt;](#user-content-number) | 無對應的 `CSS` 屬性。其效果相當於同時設定 `paddingRight` 和 `paddingLeft`                                                                                                                |
| paddingVertical   | [&lt;number&gt;](#user-content-number) | 無對應的 `CSS` 屬性。其效果相當於同時設定 `paddingTop` 和 `paddingBottom`                                                                                                                |
| paddingTop        | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [padding-top](http://css.doyoe.com/properties/padding/padding-top.htm) 屬性                                                                                                   |
| paddingRight      | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [padding-right](http://css.doyoe.com/properties/padding/padding-right.htm) 屬性                                                                                               |
| paddingBottom     | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [padding-bottom](http://css.doyoe.com/properties/padding/padding-bottom.htm) 屬性                                                                                             |
| paddingLeft       | [&lt;number&gt;](#user-content-number) | 對應 `CSS` [padding-left](http://css.doyoe.com/properties/padding/padding-left.htm) 屬性                                                                                                 |

<a name="border"></a>

### Border 邊框（20）

| 屬性名                  | 取值                                                                                                        | 描述                                                                                                                 |
| ----------------------- | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| borderStyle             | `solid`, `dotted`, `dashed`                                                                                 | 對應 `CSS` `border-style` 屬性，但閹割了 `none, hidden, double, groove, ridge, inset, outset` 取值，且無方向分拆屬性 |
| borderWidth             | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-width` 屬性                                                                                       |
| borderTopWidth          | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-top-width` 屬性                                                                                   |
| borderRightWidth        | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-right-width` 屬性                                                                                 |
| borderBottomWidth       | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-bottom-width` 屬性                                                                                |
| borderLeftWidth         | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-left-width` 屬性                                                                                  |
| borderColor             | [&lt;color&gt;](#user-content-color)                                                                        | 對應 `CSS` `border-color` 屬性                                                                                       |
| borderTopColor          | [&lt;color&gt;](#user-content-color)                                                                        | 對應 `CSS` `border-top-color` 屬性                                                                                   |
| borderRightColor        | [&lt;color&gt;](#user-content-color)                                                                        | 對應 `CSS` `border-right-color` 屬性                                                                                 |
| borderBottomColor       | [&lt;color&gt;](#user-content-color)                                                                        | 對應 `CSS` `border-bottom-color` 屬性                                                                                |
| borderLeftColor         | [&lt;color&gt;](#user-content-color)                                                                        | 對應 `CSS` `border-left-color` 屬性                                                                                  |
| borderRadius            | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-radius` 屬性                                                                                      |
| borderTopLeftRadius     | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-top-left-radius` 屬性                                                                             |
| borderTopRightRadius    | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-top-right-radius` 屬性                                                                            |
| borderBottomLeftRadius  | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-bottom-left-radius` 屬性                                                                          |
| borderBottomRightRadius | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` `border-bottom-right-radius` 屬性                                                                         |
| shadowColor             | [&lt;color&gt;](#user-content-color)                                                                        | 對應 `CSS` [box-shadow](http://css.doyoe.com/properties/border/box-shadow.htm) 屬性中的顏色定義                      |
| shadowOffset            | {<br>width: [&lt;number&gt;](#user-content-number), <br>height: [&lt;number&gt;](#user-content-number)<br>} | 對應 `CSS` [box-shadow](http://css.doyoe.com/properties/border/box-shadow.htm) 屬性中的陰影偏移定義                  |
| shadowRadius            | [&lt;number&gt;](#user-content-number)                                                                      | 在 `CSS` 中，陰影的圓角大小取決於元素的圓角定義，不需要額外定義                                                      |
| shadowOpacity           | [&lt;number&gt;](#user-content-number)                                                                      | 對應 `CSS` [box-shadow](http://css.doyoe.com/properties/border/box-shadow.htm) 屬性中的陰影透明度定義                |

<a name="background"></a>

### Background 背景（1）

| 屬性名          | 取值                                 | 描述                               |
| --------------- | ------------------------------------ | ---------------------------------- |
| backgroundColor | [&lt;color&gt;](#user-content-color) | 對應 `CSS` `background-color` 屬性 |

<a name="transform"></a>

### Transform 轉換（3）

| 屬性名             | 取值                                                                                                                                                                                                                                    | 描述                                                                 |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| transform          | `[{perspective: number}, {rotate: string}, {rotateX: string}, {rotateY: string}, {rotateZ: string}, {scale: number}, {scaleX: number}, {scaleY: number}, {translateX: number}, {translateY: number}, {skewX: string}, {skewY: string}]` | 對應 `CSS` `transform` 屬性                                          |
| transformMatrix    | `TransformMatrixPropType`                                                                                                                                                                                                               | 類別似於 `CSS` 中 `transform` 屬性的 `matrix()` 和 `matrix3d()` 函式 |
| backfaceVisibility | `visible`, `hidden`                                                                                                                                                                                                                     | 對應 `CSS` `backface-visibility` 屬性                                |

<a name="flexbox"></a>

### Flexbox 彈性盒（9）

| 屬性名         | 取值                                                                | 描述                                                         |
| -------------- | ------------------------------------------------------------------- | ------------------------------------------------------------ |
| flex           | [&lt;number&gt;](#user-content-number)                              | 對應 `CSS` `flex` 屬性，但只能為整數值                       |
| flexGrow       | [&lt;number&gt;](#user-content-number)                              | 對應 `CSS` `flex-grow` 屬性                                  |
| flexShrink     | [&lt;number&gt;](#user-content-number)                              | 對應 `CSS` `flex-shrink` 屬性                                |
| flexBasis      | [&lt;number&gt;](#user-content-number)                              | 對應 `CSS` `flex-basis` 屬性                                 |
| flexDirection  | `row`, `row-reverse`, `column`, `column-reverse`                    | 對應 `CSS` `flex-direction` 屬性                             |
| flexWrap       | `wrap`, `nowrap`                                                    | 對應 `CSS` `flex-wrap` 屬性，但閹割了 `wrap-reverse` 取值    |
| justifyContent | `flex-start`, `flex-end`, `center`, `space-between`, `space-around` | 對應 `CSS` `justify-content` 屬性，但閹割了 `stretch` 取值。 |
| alignItems     | `flex-start`, `flex-end`, `center`, `stretch`                       | 對應 `CSS` `align-items` 屬性，但閹割了 `baseline` 取值。    |
| alignSelf      | `auto`, `flex-start`, `flex-end`, `center`, `stretch`               | 對應 `CSS` `align-self` 屬性，但閹割了 `baseline` 取值       |

<a name="other"></a>

### Other 其他

| 屬性名                                 | 取值                                   | 描述                                                                |
| -------------------------------------- | -------------------------------------- | ------------------------------------------------------------------- |
| opacity                                | [&lt;number&gt;](#user-content-number) | 對應 `CSS` `opacity` 屬性                                           |
| overflow                               | `visible`, `hidden`, `scroll`          | 對應 `CSS` `overflow` 屬性，但閹割了 `auto` 取值                    |
| elevation<br /><sup>`Android`</sup>    | [&lt;number&gt;](#user-content-number) | `CSS`中沒有對應的屬性，只在 `Android5.0+` 上有效                    |
| resizeMode                             | `cover`, `contain`, `stretch`          | `CSS`中沒有對應的屬性，可以參考 `background-size` 屬性              |
| overlayColor<br /><sup>`Android`</sup> | string                                 | `CSS`中沒有對應的屬性，當圖像有圓角時，將角落都充滿一種顏色         |
| tintColor<br /><sup>`iOS`</sup>        | [&lt;color&gt;](#user-content-color)   | `CSS`中沒有對應的屬性，`iOS` 圖像上特殊的色彩，改變不透明像素的顏色 |

<a name="values"></a>

## Valuse 取值

<a name="color"></a>

### Color 顏色

`React Native` 支援了 `CSS` 中大部分的顏色類別型：

- `#f00` (#rgb)
- `#f00c` (#rgba)：`CSS` 中無對應的值
- `#ff0000` (#rrggbb)
- `#ff0000cc` (#rrggbbaa)：`CSS` 中無對應的值
- `rgb(255, 0, 0)`
- `rgba(255, 0, 0, 0.9)`
- `hsl(360, 100%, 100%)`
- `hsla(360, 100%, 100%, 0.9)`
- `transparent`
- `0xff00ff00` (0xrrggbbaa)：`CSS` 中無對應的值
- `Color Name`：支援了 [基本顏色關鍵字](http://css.doyoe.com/appendix/color-keywords.htm#basic) 和 [擴充顏色關鍵字](http://css.doyoe.com/appendix/color-keywords.htm#extended)，但不支援 [28 個系統顏色](http://css.doyoe.com/appendix/color-keywords.htm#system)；

<a name="number"></a>

### Number 數值

在 `React-Native` 中，目前僅支援 `Number` 這一種長度取值。默認缺省了 `pt` 單位，詳細請看 [Units 單位](#user-content-units) 部分。

<a name="units"></a>

## Units 單位

<a name="pt"></a>

### Pt 點

在 `React-Native` 中，並不支援百分比單位，目前只支援一種單位，即 `pt` 絕對長度單位，同時，你在定義時不需要加單位，例如：

```
<View style={{width: 100, height: 50}}></View>
```

```
var styles = StyleSheet.create({
    box: {
        width: 100,
        height: 50
    }
});
```

<a name="pixelratio"></a>

## PixelRatio 像素密度

在 `React-Native` 中，存取設備像素密度的方法由 `PixelRatio` 類別提供。

我們的應用通常都會執行在不同的設備上，並且這些設備的像素密度很有可能各不相同。這會造成一個現象就是：

- 定義了元素的邊框為 `1像素`，而實際上在不同像素密度的設備上結果不一樣，例如：iPhone6 顯示為 `2像素`，iPhone6 Plus 顯示為 `3像素`；
- 對於一個圖片來講，因為設備的像素密度不同，它也需要對應不同尺寸的規則，以防止圖片過小變得模糊；

### 根據像素密度指定邊框厚度

出於對產品體驗的一致性，我們會要求不論是在哪種設備上，其邊框厚度都應該是相同的。一個取得物理上的相同邊框厚度的好方法就是用邏輯尺寸除以像素密度比：

```
var styles = StyleSheet.create({
    box: {
        borderWidth: 1 / PixelRatio.get(),
        borderStyle: solid
    }
});
```

上述程式碼將保證你的應用在所有的設備上（像素密度），都獲得 `1像素` 的邊框厚度。`PixelRatio` 通過 `get()` 方法來回傳設備的像素密度。

未完待續。。。
