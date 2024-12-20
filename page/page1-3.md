# 模式
<span class="keyInfo">底部栏切换模式: <span class="higText"> 创建 | 导出 | 编辑 | 导航 | 变量 </span></span>
## 创建
### 数据导入
<span class="keyInfo">解析传入的数据，通过API转化为设计元素</span>
导入内容：<span class="higText"> \*name | \*w | \*h | s | type</span>（带<span class="higText"> \*</span>号为必填项）<br>
| name | w | h | s| type |
|:---:|:---:|:---:|:---:|:---:|
| kv | 1920 | 1080 |   |   |
| banner#000000 | 1200 | 300 | 500k | jpg |
+ name：资源的名称；
+ w：资源的宽度，单位默认为px；
+ h：资源的高度,单位默认为px；
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
//按下返回后会将数组处理成制表形式文本，回到输入框编辑
```
+ s：资源的目标大小，目前未开放该数值类型，单位默认为k，导出时设置，或通过修改代码预设;
+ type：资源的目标导出格式，目前未开放该数值类型，默认按[导出](#导出)规则识别<span class="higText">jpg | png</span>:<br>

<span class="keyInfo">导入方式：<span class="higText"> 点击 | 拖拽 | 输入 </span></span><br>
+ 点击：点击图标会拉起本地上传文件；
+ 拖拽：将本地文件拖拽到插件区域；
+ 输入：可直接复制表格文件并粘贴，通常是一个用制表符<span class="higText"> tab </span>隔开每行数据的文本；如手动输入也要遵循这个规则；<br>

### 勾选标签
<span class="keyInfo">筛选根据数据生成的候选数值组</span>
数据符合规范，右上角会出现<span class="higText"> 确认 | 清空 </span>，点击确认后自动去除非法空格，显示候选标签，可再次检查，关闭不需要的标签<br>
### 返回
<span class="keyInfo">返回到输入框修改数据</span>
如需修改，点击<span class="higText">返回</span>即可再次在文本框处修改<br>
### 创建对象
<span class="keyInfo">按输入的数据类型创建对应设计元素</span>
当确认无误后，点击<span class="higText">创建对象</span>即可在画面中心创建画板，画板会根据横竖和大小自动排布<br>
### 特殊功能
<span class="keyInfo">基于导入和创建的概念拓展的其他便捷功能</span>
mg中可通过拖拽大于4096px的图（含从网页拖拽）或复制svg代码（如PS右键复制的代码）粘贴到输入区域，可自动裁切并生成在画面中心<br>
ps中则通过图片创建画板<br>
后续将支持通过上传带图层信息的<span class="higText">json | xml</span>文件生成图层<br>
## 导出
<span class="keyInfo">批量将设计元素导出为目标格式或中间格式</span>
### 图片格式
<span class="keyInfo">批量导出到压缩包</span>
目前仅支持将批量<span class="higText">jpg | png</span>导出为压缩包,可通过所选对象命名中的<span class="higText">/</span>创建路径（文件夹）<br>
+ 所选对象的填充为空，判断为<span class="higText">png</span>
+ 所选对象设置了圆角，判断为<span class="higText">png</span>
+ 除此之外，判断为<span class="higText">jpg</span>

如果背景没透明像素但是想保存成png，需要去掉画板填充，在子层设置背景，改动后需重新选中加载；<br>
后续将支持导出序列到<span class="higText">gif | apng | webp | svga</span>等格式;<br>

### PS/AE/其他软件
后续将基于图层整理和PS插件，通过<span class="higText">json</span>形式完成图层内容数据互传<br>
后续将支持导出图文到<span class="higText">Figma | PPT | PDF </span>等格式;<br>

## 编辑
<span class="keyInfo">对位图/矢量图/快照进行调色、变形等编辑</span>

## 导航
<span class="keyInfo">生成页面预览小地图，可借助小地图移动视角</span>

## 变量
<span class="keyInfo">将本地样式记录成便于管理的本地表格，批量切换样式组、按变量和公式生成/刷新样式</span>
