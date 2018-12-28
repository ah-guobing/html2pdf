# html2pdf
HTML文件转换为PDF文件


### 环境要求
* JDK：>=1.8
* OS：Windows / Linux / MacOS

### 服务端搭建（以Linux环境为例）
&#35; nohup java -jar html2pdf-0.0.1-SNAPSHOT.jar --server.port=端口号（默认8080） --font.path=PDF需要使用的字体路径  >>./serv.log &<br />
如：<br />
&#35; nohup java -jar html2pdf-0.0.1-SNAPSHOT.jar --font.path=/home/tmpl2pdf/font/simsun.ttc >>./serv.log & 
<br />
执行后，访问 http://ip:port/about 若出现版本等信息，说明服务端搭建成功。

### 客户端调用
API：http://ip:port/html2pdf?htmlFile=HTML文件模板完整路径名&pdfFile=生成后的PDF文件完整路径名
<br />
如：<br />
http://localhost:8080/html2pdf?htmlFile=/Users/guobingbing/Work/MyProject/tmpl2pdf/font/a.html&pdfFile=/Users/guobingbing/Work/MyProject/tmpl2pdf/font/a.pdf

### HTML模板文件的要求
* 所有标签必须是闭合的，如 &lt;br&gt; 应该写为 &lt;br /&gt;
* HTML中要用CSS定义此页面使用的字体，如定义为：body{font-family:SimSun;}
* HTML DTD声明要规范，不能省略不写，如定义为：&lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"&gt;&lt;html xmlns="http://www.w3.org/1999/xhtml"&gt;
