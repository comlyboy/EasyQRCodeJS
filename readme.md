# EasyQRCodeJS

EasyQRCodeJS 是一个功能丰富的跨浏览器的纯 JavaScript QRCode 生成库。

EasyQRCodeJS is a feature-rich cross-browser pure JavaScript QRCode generation library.


## Feature

- **中文**

	- 跨浏览器，支持基于 HTML5 Canvas 和 Table 的二维码生成

    - 支持点形风格的 Required Patterns

    - 支持自定义 Position Pattern 内填充和外边框颜色
	
    - 支持自定义 Alignment Pattern 内填充和外边框颜色

    - 支持自定义 Timing Patterns 垂直，水平颜色

    - 支持 Logo 图片（包括背景透明的 PNG 图片）

    - 支持 Background Image 背景图片

	- 支持标题，副标题设置
	
	- 不依赖任何第三方


- **English**

	- Cross-browser support for QR code generation based on HTML5 Canvas and Table

    - Required Patterns that support dot style

    - Support custom Position Pattern inner fill and outer border color

    - Support custom Alignment Pattern inner fill and outer border color

    - Support custom Timing Patterns vertical, horizontal color

    - Support Logo images (including transparent PNG images)

    - Support Background Image

	- Support for title, subtitle settings

	- Has no dependencies.

## Try It!

[Try It!](http://www.easyproject.cn/easyqrcodejs/tryit.html "EasyQRCodeJS Try It!")

## Demo preview

![Demo preview](doc/images/demo.png)

## QR Code Structure

![QR Code Structure](doc/images/QR_Code_Structure.png)


## Installation

- Download install

	```HTML
	<script src="dist/easy.qrcode.min.js" type="text/javascript" charset="utf-8"></script>
	
	```

- Npm install

	```BASH
	npm install easyqrcodejs
	```


## Basic Usages
```HTML

<div id="qrcode"></div>

<script type="text/javascript">
	// Options
	var options = {
		text: "https://github.com/ushelp/EasyQRCodeJS"
	};
	
	// Create QRCode Object
	new QRCode(document.getElementById("qrcode"), options);
</script>
```

## QRCode API

### Object 

```JS
var qrcode = new QRCode(DOM_object, options_object);
```


### Options

```JS
 var options = {
		// ====== Basic
		text: "https://github.com/ushelp/EasyQRCodeJS",
		width: 256,
		height: 256,
		colorDark : "#000000",
		colorLight : "#ffffff",
		correctLevel : QRCode.CorrectLevel.H, // L, M, Q, H
		dotScale: 1 // Must be greater than 0, less than or equal to 1. default is 1
		
		// ====== Logo
		//	logo:"../demo/logo.png", // Relative address, relative to `easy.qrcode.min.js`
		//	logo:"http://127.0.0.1:8020/easy-qrcodejs/demo/logo.png", 
		//	logoWidth:80, // widht. default is automatic width
		//	logoHeight:80 // height. default is automatic height
		//	logoBackgroundColor:'#fffff', // Logo backgroud color, Invalid when `logBgTransparent` is true; default is '#ffffff'
		//	logoBackgroundTransparent:false, // Whether use transparent image, default is false
	
		// ====== Backgroud Image
		//	backgroundImage: '', // Background Image
		//	backgroundImageAlpha: 1, // Background image transparency, value between 0 and 1. default is 1. 
		//	autoColor: false,
		
		
		// ====== Colorful
		// === Posotion Pattern(Eye) Color
		//	PO: '#e1622f', // Global Posotion Outer color. if not set, the defaut is `colorDark`
		//	PI: '#aa5b71', // Global Posotion Inner color. if not set, the defaut is `colorDark`
		//	PO_TL:'', // Posotion Outer color - Top Left 
		//	PI_TL:'', // Posotion Inner color - Top Left 
		//	PO_TR:'', // Posotion Outer color - Top Right 
		//	PI_TR:'', // Posotion Inner color - Top Right 
		//	PO_BL:'', // Posotion Outer color - Bottom Left 
		//	PI_BL:'', // Posotion Inner color - Bottom Left 
		//	PO_BR:'', // Posotion Outer color - Bottom Right 
		//	PI_BR:'', // Posotion Inner color - Bottom Right 
		// === Alignment Color
		//	AO: '', // Alignment Outer. if not set, the defaut is `colorDark`
		//	AI: '', // Alignment Inner. if not set, the defaut is `colorDark`
		// === Timing Pattern Color
		//	timing: '#e1622f', // Global Timing color. if not set, the defaut is `colorDark`
		//	timing_H: '', // Horizontal timing color
		//	timing_V: '', // Vertical timing color
		
		// ====== Title
		//	title: 'QR Title', // content 
		//	titleFont: "bold 18px Arial", //font. default is "bold 16px Arial"
		//	titleColor: "#004284", // color. default is "#000"
		//	titleBackgroundColor: "#fff", // background color. default is "#fff"
		//	titleHeight: 70, // height, including subTitle. default is 0
		//	titleTop: 25, // draws y coordinates. default is 30
		
		// ====== SubTitle
		//	subTitle: 'QR subTitle', // content
		//	subTitleFont: "14px Arial", // font. default is "14px Arial"
		//	subTitleColor: "#004284", // color. default is "4F4F4F"
		//	subTitleTop: 40, // draws y coordinates. default is 0
}
```

| Option | Required | Type | Defaults | Description | Compatibility |
| --- | --- |--- | --- |--- | --- |
| Basic options| --- | ---|---|---|---|
| **text** | Y | String |`''` |  Text | &nbsp; |
| **width** | N | Number | `256` |  Width |  &nbsp; |
| **height** | N | Number | `256` |  Height |  &nbsp; |
| **colorDark** | N | String | `#000000` | Dark CSS color |  &nbsp; |
| **colorLight** | N | String | `#ffffff` | Light CSS color |  &nbsp; |
| **correctLevel** | N | Enum | `QRCode.CorrectLevel.H` | `QRCode.CorrectLevel.H`<br/>`QRCode.CorrectLevel.Q` <br/> `QRCode.CorrectLevel.M` <br/> `QRCode.CorrectLevel.L`|  &nbsp; |
| **dotScale** | N | Number | `1.0` |Dot style required Patterns. Ranges: `0-1.0` | IE9+ |
| Logo options| --- | ---|---|---|---|
| **logo** | N | String | `undefined` | Logo Image Path. If use relative address, relative to `easy.qrcode.min.js` |  &nbsp; |
| **logoWidth** | N | Number | `undefined` |  Height |  &nbsp; |
| **logoHeight** | N | Number | `undefined` |  Width |  &nbsp; |
| **logoBackgroundTransparent** | N | Boolean | `false` |  Whether the background transparent image shows transparency |  &nbsp; |
| **logoBackgroundColor** | N | String | `#ffffff` |  Set Background CSS Color when image background transparent |  &nbsp; |
| Backgroud Image options|  ---|--- |---|---|---|
| **backgroundImage** | N | String | `undefined` | Background Image Path. If use relative address, relative to `easy.qrcode.min.js` |  IE9+ |
| **backgroundImageAlpha** | N | Number | `1.0` |  Background image transparency. Ranges: `0-1.0`  |  IE9+ |
| **autoColor** | N | Boolean | `false` |  Automatic color adjustment |  IE9+ |
| Posotion Pattern Color options| --- | ---|---|---|---|
| **PO** | N | String | `undefined` | Global Posotion Outer CSS color. if not set, the defaut is `colorDark` |  &nbsp; |
| **PI** | N | String | `undefined` | Global Posotion Inner CSS color. if not set, the defaut is `colorDark` |  &nbsp; |
| **PO_TL** | N | String | `undefined` | Posotion Outer CSS color - Top Left |  &nbsp; |
| **PI_TL** | N | String | `undefined` | Posotion Inner CSS color - Top Left |  &nbsp; |
| **PO_TR** | N | String | `undefined` | Posotion Outer CSS color - Top Right |  &nbsp; |
| **PI_TR** | N | String | `undefined` | Posotion Inner CSS color - Top Right |  &nbsp; |
| **PO_BL** | N | String | `undefined` | Posotion Outer CSS color - Bottom Left |  &nbsp; |
| **PI_BL** | N | String | `undefined` | Posotion Inner CSS color - Bottom Left |  &nbsp; |
| Alignment Color options| --- |--- |---|---|---|
| **AO** | N | String | `undefined` | Alignment Outer CSS color. if not set, the defaut is `colorDark` |  &nbsp; |
| **AI** | N | String | `undefined` | Alignment Inner CSS color. if not set, the defaut is `colorDark` |  &nbsp; |
| Timing Pattern Color options| --- | ---|---|---|---|
| **timing** | N | String | `undefined` | Global Timing CSS color. if not set, the defaut is `colorDark` |  &nbsp; |
| **timing_H** | N | String | `undefined` | Horizontal timing CSS color |  &nbsp; |
| **timing_V** | N | String | `undefined` | Vertical timing CSS color |  &nbsp; |
| Title options| --- | ---|---|---|---|
| **title** | N | String | `''` |  |  &nbsp; |
| **titleFont** | N | String | `bold 16px Arial` | CSS Font |  &nbsp; |
| **titleColor** | N | String | `#000000` | CSS color |  &nbsp; |
| **titleBackgroundColor** | N | String | `#ffffff` | CSS color|  &nbsp; |
| **titleHeight** | N | Number | `0` | Title Height, Include subTitle |  &nbsp; |
| **titleTop** | N | Number | `30` | draws y coordinates.|  &nbsp; |
| SubTitle options| --- | ---|---|---|---|
| **subTitle** | N | String | `''` |  |  &nbsp; |
| **subTitleFont** | N | String | `14px Arial` | CSS Font |  &nbsp; |
| **subTitleColor** | N | String | `#4F4F4F` | CSS color |  &nbsp; |
| **subTitleTop** | N | String | `0` | draws y coordinates. default is 0|  &nbsp; |




### Method

```JS
qrcode.clear(); // remove the code.
qrcode.makeCode("https://github.com/ushelp/EasyQRCodeJS"); // make another code text.
```

## Browser Compatibility
IE6+, Chrome, Firefox, Safari, Opera, Mobile Safari, Android, Windows Mobile, ETC.

## License
MIT License

## End

Email：<inthinkcolor@gmail.com>

[http://www.easyproject.cn](http://www.easyproject.cn "EasyProject Home")


**Donation/捐助:**


<img alt="
支付宝/微信/QQ/云闪付/PayPal 扫码支付" src="http://www.easyproject.cn/thanks/donation.png"  title="支付宝/微信/QQ/云闪付/PayPal 扫码支付"  height="320" width="320"></img>
<div>支付宝/微信/QQ/云闪付/PayPal</div>

<br/>

我们相信，每个人的点滴贡献，都将是推动产生更多、更好免费开源产品的一大步。

**感谢慷慨捐助，以支持服务器运行和鼓励更多社区成员。**

We believe that the contribution of each bit by bit, will be driven to produce more and better free and open source products a big step.

**Thank you donation to support the server running and encourage more community members.**


