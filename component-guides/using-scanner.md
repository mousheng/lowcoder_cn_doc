# 使用扫码组件

扫码组件支持扫描二维码和条形码。成功扫描后，将自动存储解码后的信息。灵活配置扫码组件的属性和事件等，以满足不同的使用场景需求。

![](../../assets/1-20231002211720-48824jq.gif)​

## 扫描并打开二维码链接

插入一个扫码组件 `scanner1`​，如下图。点击按钮并扫描二维码后，解码后的信息可通过 `scanner1.data`​ 访问。关闭**连续扫描**开关，扫描成功后将自动关闭弹窗。此时每次扫描将只产生一项数据，如果多次点击扫描按钮，产生的新数据将会覆盖旧数据。

![](../../assets/2-20231002211720-7ucgflz.png)​

如果扫描的二维码信息是一个链接，可以为扫码组件的**成功**事件设置**打开链接**的动作，URL 设置为 `{{scanner1.data[0]}}`​。还可以设置是否​**在新标签页中打开**​，如果未生效，需要检查弹出的新标签页是否被浏览器拦截。

![](../../assets/3-20231002211720-h0co4cr.png)​

## 连续扫描多个条形码

开启**连续扫描**开关时，扫描弹窗将保持打开状态而不会自动关闭，连续扫描得到的信息将以数组的形式存储在 `data`​ 字段。连续扫描的频率约为每秒一次，建议开启**忽略重复数据**开关，自动过滤冗余信息。

![](../../assets/4-20231002211720-xdgignu.png)​

## 支持的编码格式

目前支持的二维码和条形码的编码格式如下：

|**1D product**|**1D industrial**|**2D**|
| --------| ----------| -------------|
|UPC-A|Code 39|QR Code|
|UPC-E|Code 128|Data Matrix|
|EAN-8|ITF|Aztec|
|EAN-13|RSS-14|PDF 417|