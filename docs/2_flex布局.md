
### 任何容器都可以设定为flex布局：
	.box{display:flex;}
	行内元素：
	.box{display:inline-flex;}
### 容器的属性：
	flex-direction		控制主轴的方向
	flex-wrap			控制主轴的换行策略
	flex-flow			flex-direction和flex-wrap的缩写
	justify-content		控制主轴的对其方式
	align-items			控制项目在交叉轴的对其方式
	align-content		控制多根轴线的对齐方式
### 项目的属性：
    order		 		定义项目的排列顺序
	flex-grow			定义项目的放大比例
	flex-shrink			定义项目的缩小比例
	flex-basis			定义了在分配多于空间之前，项目占据的主轴空间
	flex				前三个属性的缩写。快捷值：auto(1 1 auto : 自适应) none(0 0 auto:固定大小)
	align-self			控制单个项目的对齐方式
### 在将一个盒模型布局的界面改为flex布局时发现的一点：不利于扩展的代码坚决不能留，不能图一时简便导致后期难以维护。切记！