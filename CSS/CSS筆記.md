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
## 4.background
1.背景圖片 background-image
 大圖像不會按比例縮小以適合該框，只會看到它的一個小角，而小圖像則被平鋪以填充該框。
>控制背景重複(background-repeat)
* no-repeat -停止完全重複背景。
* repeat-x —水平重複。
* repeat-y —垂直重複。
* repeat—默認值；雙向重複。
>調整背景圖片的大小(background-size)
* cover 完全覆蓋方框區域，同時仍保留其寬高比(部分圖像可能會出現在盒子外面)
* contain 圖像大小合適以適合盒子內的大小(如果圖像的高寬比與盒子的高寬比不同，最終可能會在圖像的兩側或頂部和底部出現間隙)
>定位背景圖片(background-position)

background-position值有兩個單獨的值-水平值，然後是垂直值。

` background-position: 20px 10%;`

也可以使用4值語法來指示距框的某些邊緣的距離-在這種情況下，長度單位是其前一個值的偏移量 

` background-position: top 20px right 10px; `
2.背景漸進色(background:gradient)
3.背景附件(background-attachment)
## 5.border
**border基本用法** 
1.border : 圍住Model box框的線

` border: 5px solid #0b385f; `

等於

` border-width: 1px;
  border-style: solid;
  border-color: black; `
  
2.border-collapse : 用來將表格欄位邊框合併
 
* separate : 預設值，邊框彼此間分開
* collapse : 邊框合併為單一邊框
* inherit : 繼承自父層的 border-collapse 屬性值
  
**border進階>>圓角**

border-radius:左上角、右上角、右下角、左下角 ` border-radius:10px 10px 20px 20px `

border-radius:(左上角、右下角)、(右上角、左下角) `border-radius: 10px 20px`

## 6.圖片調整相關	
1.object-fit
* cover 完全覆蓋方框區域，同時仍保留其寬高比(部分圖像可能會出現在盒子外面)
* contain 圖像大小合適以適合盒子內的大小(如果圖像的高寬比與盒子的高寬比不同，最終可能會在圖像的兩側或頂部和底部出現間隙)

## 7.tables調整相關
1.table-layout 調整table佈局
* auto : 一般table默認的情況，會自動調整table和row的寬度
* fixed : col和table的寬度，由table和col元素的寬度或單元格第一行的寬度設置

## 8.text-decoration 文字底線
#### Value
* none (無效果)
* overline (頂線)
* line-through (中線/刪除線)
* underline (底線)
* inherit (繼承)
#### 相關語法
* text-decoration-line (線段位置)
* text-decoration-color (線段色彩)
* text-decoration-style (線段樣式)

<pre><code>
  text-decoration-color: red ;
  text-decoration-style: dotted;  
  text-decoration-line: underline;
  也可以直接設定
  text-decoration: underline red dotted;
 </code></pre>

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
		2. 百：選擇器中包含的每個ID選擇器(#id)。
		3. 十：選擇器中包含的每個類選擇器(class)，屬性選擇器或偽類。
		4. 個位數：選擇器中包含的元素選擇器(tag)或偽元素。
![Image](https://github.com/wei-yu-lin/HTML/blob/master/CSS/css-spectifity.png)

	   3.打破級聯常規的語法 !Important
		

	
