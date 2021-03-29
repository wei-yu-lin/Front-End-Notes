# <a name='toc'>目錄</a>
  1. [一般屬性](#general-property)
  1. [BOX MODEL](#general-MODEL)
  1. [CASCADE、inheritance 級聯和繼承](#CASCADE-inheritance)

# <a name='general-property'>一般屬性</a>
## 1.box-sizing 所有可設定width、height對象
	value有content-box、border-box，
	1. content-box為預設不需要特別宣告，設定width和height可直接更改content area範圍
	2. border-box則需特別宣告box-sizing:border-box，設定width和height可更改包含border以內的範圍
## 2.overflow 
	希望限制在某個範圍內，避免破壞版面配置的時候

## 3.Display
 
# <a name='general-MODEL'>BOX MODEL</a>
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
	
# <a name='CASCADE-inheritance'>CASCADE、inheritance</a>
   ## inheritance
      1.子元素會繼承父元素的屬性
      2.總共有三個概念在控制CSS，cascade, specificity, and inheritance
      3.控制繼承
        1. inherit
	 繼承其父元素所有屬性
        2. initial
	 選定元素的屬性值設置為該屬性的初始值
        3. unset
	 如果該屬性是自然繼承的，則其行為類似於inherit，否則，其行為類似於initial
	EX.搭配ALL使用，會對父元素全部屬性做動
   ## CASCADE 級聯
	  1.級聯有三個因素影響，這裡重要性從高到低的順序列出
		1.貨源順序
		2.專一性
		3.重要性
	  2.當specificity(特異性)越高，代表有重複衝突的屬性就被優先選取。
	    計算specificity的分數，共有分4種不同的值
		1. 千：如果聲明位於style屬性（也稱為內聯樣式）內，則在此列中得分一。這樣的聲明沒有選擇器，因此它們的特異性始終為1000。
		2. 百：選擇器中包含的每個ID選擇器。
		3. 十：選擇器中包含的每個類選擇器，屬性選擇器或偽類。
		4. 個位數：選擇器中包含的元素選擇器或偽元素。



	
