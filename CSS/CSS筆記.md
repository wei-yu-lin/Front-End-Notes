# <a name='toc'>目錄</a>
  * [一般屬性](#general-property)
  * BOX MODEL
  * CASCADE、inheritance 級聯和繼承

# <a name='general-property'>一般屬性</a>
## 1.box-sizing 所有可設定width、height對象
	value有content-box、border-box，
	1. content-box為預設不需要特別宣告，設定width和height可直接更改content area範圍
	2. border-box則需特別宣告box-sizing:border-box，設定width和height可更改包含border以內的範圍
## 2.overflow 
	希望限制在某個範圍內，避免破壞版面配置的時候

# BOX MODEL
## 1.布局流 (Normal flow)
	1. display:inline 用來定義元素在同一行呈現，也就是圖片或文字均不換行的意思
	2. display block 規定元素以區塊方式呈現
## 2.Formatting context 格式化上下文
	決定box怎麼被排列、怎麼影響跟其它box的相對位置
	- BFC(Block formatting context)
	- IFC(Inline formatting context)
	- FFC(Flex formatting context)
	- GFC(Grid formatting context)
## 3.Margin collapse Margin發生合併的現象
	1. 相連元素沒有padding、border、clearfix、和line box隔開。
	2. 垂直排列的margin:
		- 相鄰兄弟元素的margin-bttom跟margin-top。
		- 父元素跟第一個子元素的margin-top。
		- 父元素跟最後一個子元素的margin-bottom。
	3. 重疊後的值會取大的margin值。
	
# CASCADE、inheritance
   ## inheritance
      1.子元素會繼承父元素的屬性
