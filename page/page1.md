# 模式
<span class="keyInfo">底部栏右侧有用以切换模式的tab: <span class="higText"> 创建 | 导出 | 编辑 | 帮助 </span>,帮助即本文档</span>
## 创建
### 数据导入
<span class="keyInfo">导入内容：<span class="higText"> \*name | \*w | \*h | s | type</span>（带<span class="higText"> \*</span>号为必填项）</span><br>
| name | w | h | s| type |
|:---:|:---:|:---:|:---:|:---:|
| kv | 1920 | 1080 |   |   |
| banner#000000 | 1200 | 300 | 500k | jpg |
+ name：资源的名称；
+ w：资源的宽度，单位默认为px；
+ h：资源的高度,单位默认为px；
+ s：资源的目标大小，单位默认为k;<br>

```javascript
//插件中可双击输入框填充示例
/*-----------------------
name    w    h   
kv  1920    1080
banner#000000  1200    300
---------------------------*/
//按下确认后插件中会转化为数组，如格式不对会显示[数据错误]

allFrame = [
{name:"kv",w:1920,h:1080},
{name:"banner#000000",w:1200,h:300},
...
]
```
+ type：资源的目标导出格式，目前未开放该数值类型，默认按[导出](#导出)规则识别<span class="higText">jpg | png</span>:<br>

<span class="keyInfo">导入方式：<span class="higText"> 点击 | 拖拽 | 输入 </span></span><br>
+ 点击：点击图标会拉起本地上传文件；
+ 拖拽：将本地文件拖拽到插件区域；
+ 输入：可直接复制表格文件并粘贴，通常是一个用制表符<span class="higText"> tab </span>隔开每行数据的文本；如手动输入也要遵循这个规则；<br>

### 三级标题
内容内容这是内容内容这是内容内容这是内容内容这是内容内容这是内容内容这是内容内容这是内容内容这是内容内容
内容内容这是内容内容这是内容内容这是内容内容这是内容内容这是内容内容这是内容内容这是内容内容这是内容内容
## 导出
### 图片格式
目前仅支持将批量<span class="higText">jpg | png</span>导出为压缩包,可通过所选对象命名中的<span class="higText">/</span>创建路径（文件夹）<br>
+ 所选对象的填充为空，判断为<span class="higText">png</span>
+ 所选对象设置了圆角，判断为<span class="higText">png</span>
+ 除此之外，判断为<span class="higText">jpg</span><br>

如果背景没透明像素但是想保存成png，需要去掉画板填充，在子层设置背景，改动后需重新选中加载；<br>
后续将支持导出序列到<span class="higText">gif | apng | webp | svga</span>等格式;

### PSD/AE
后续将基于图层整理和PS插件，通过<span class="higText">json</span>形式完成图层内容数据互传
