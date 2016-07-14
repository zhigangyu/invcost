spring-boot默认提供内嵌的tomcat，所以打包直接生成jar包，用java -jar命令就可以启动。但是，有时候我们更希望一个tomcat来管理多个项目，这种情况下就需要项目是war格式的包而不是jar格式的包。spring-boot同样提供了解决方案，只需要简单的几步更改就可以了，这里提供maven项目的解决方法：

###将项目的启动类Application.java继承SpringBootServletInitializer并重写configure方法

```
@SpringBootApplication
public class Application extends SpringBootServletInitializer {

    @Override
    protected SpringApplicationBuilder configure(SpringApplicationBuilder application) {
        return application.sources(Application.class);
    }

    public static void main(String[] args) throws Exception {
        SpringApplication.run(Application.class, args);
    }

}
```

###在pom.xml文件中，project下面增加package标签

```
<packaging>war</packaging>
```

###在pom.xml文件中，dependencies下面添加

```
<dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-tomcat</artifactId>
        <scope>provided</scope>
</dependency>
```

这样，只需要以上3步就可以打包成war包，并且部署到tomcat中了。需要注意的是这样部署的request url需要在端口后加上项目的名字才能正常访问。spring-boot更加强大的一点就是：即便项目是以上配置，依然可以用内嵌的tomcat来调试，启动命令和以前没变，还是：mvn spring-boot:run。
如果需要在springboot中加上request前缀，需要在application.properties中添加server.contextPath=/prefix/即可。其中prefix为前缀名。这个前缀会在war包中失效，取而代之的是war包名称，如果war包名称和prefix相同的话，那么调试环境和正式部署环境就是一个request地址了。

###create a new repository on the command line
```
echo "# invcost" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/zhigangyu/invcost.git
git push -u origin master
```

###git upload file
```
git add .
git commit -m "update"
git push -u origin master
```

office 2013 KMS 批处理
@echo off
cd %ProgramFiles%\Microsoft Office\Office15
cscript ospp.vbs /sethst:177.18.80.150
cscript ospp.vbs /act
cscript ospp.vbs /dstatus
cscript ospp.vbs /remhst
pause
