# pdf2image

将PDF文档转换为图片，图片格式可以是PNG或者JPG，需要用C语言。 在mac上实现
ImageMagick

##### 1.安装brew

	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" 

##### 2.安装ghostscript

	brew install ghostscript
用 gs -v 查看是否成功安装

##### 3.link文件

	brew link libpng

##### 4.source bash 或者 zsh

	source .zshrc 
	
	source .bashrc

##### 4.5安装pkg-config

	brew install pkg-config

##### 5.编译程序

	cc -o transfer pdfTransferImage.c `pkg-config --cflags --libs MagickWand` 

pdfTransferImage.c 是需要编译的c文件名  

transfer 是将要生成的文件名  

--cflags 给出在编译时需要的选项  

–-libs 参数可以给出连接时的选项

##### 6.执行程序
实例：
		
		./transfer pdfsample.pdf a.png 

#### P.s.
如需转换其中某些页数，则添加相应参数，例如

	./transfer pdfsample.pdf'[0-1]' a.png
页码编号从零开始

#### PP.s：

./transfer 完全等价与convert指令
可以直接使用

	convert pdfsample.pdf 1.png
