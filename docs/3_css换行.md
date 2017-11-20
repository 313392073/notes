css自动换行策略：

word-break				
	normal : 		使用浏览器默认换行策略
	break-all ： 	允许在单词内换行
	keep-all ： 	只能在半角空格或连字符处换行
	
word-wrap
	normal : 		只在允许的断字点换行（浏览器保持默认处理）
	break-word : 	在长单词或者URL地址内部进行换行
	
white-space			设置如何处理元素内的空白	
	normal : 		默认。空白会被浏览器忽略
	pre : 			空白会被浏览器保留。行为方式类似HTML的pre标签
	nowrap : 		文本不会换行，而是在同一行上显示，直到遇到br标签
	pre-wrap : 		保留空白符序列，但是正常的进行换行
	pre-line : 		合并空白符序列，但是保留换行符
	inherit : 		继承父元素的值

text-overflow		当文本溢出包含元素时发生的问题
	clip : 			修剪文本
	ellipsis : 		显示省略符号来代表被修剪了的文本
	string : 		使用给定字符串代表被修剪的文本
	
overflow			当内容溢出元素框时发生的事情
	visible : 		默认值。内容不会被修剪，会呈现在元素框之外
	hidden : 		内容被修剪，并且其余内容不可见
	scroll : 		内容被修剪，但是浏览器出现滚动条，以便查看内容（内容不足以超出容器时也会出现滚动条）
	auto : 			内容被修剪，但是浏览器出现滚动条，以便查看内容
	inherit : 		继承父元素的值
	
	
区别：
word-break:break-all 正如其名字，所有的都换行。毫不留情，一点空隙都不放过。
word-wrap:break-word 则带有怜悯之心，如果这一行文字有可以换行的点，如空格，
	或CJK(Chinese/Japanese/Korean)(中文/日文/韩文)之类的，则就不打英文单词或字符的主意了，
	让这些换行点换行，至于对不对齐，好不好看，则不关心，因此，很容易出现一片一片牛皮癣一样的空白的情况。
---------------------------------	
word-spacing :		单词间的间距

此三个设置会使文本在一行显示，超出容器范围的文字隐藏并用'...'代替。
overflow: hidden;
white-space: nowrap;
text-overflow: ellipsis;



<a href="javascript:;" class="clear-input" style="display: none;"></a>







