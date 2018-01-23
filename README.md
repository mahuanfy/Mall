# Mall
工程：SSM电商平台工程搭建模板

># 一 工程介绍
该工程是一个基于Spring+SpringMVC+Mybatis的电商项目，项目采用多模块化来实现，具体实现如下图所示

![多模块Maven项目搭建](http://upload-images.jianshu.io/upload_images/1616232-6e42af9269d811a6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

># 二 创建工程步骤
- #### 1.首先创建一个普通的项目文件夹`Mall`,里面存放该项目的所有工程
- #### 2.创建`mall-parent`父类工程，后面所有的工程全部继承该工程
  - 创建maven项目：file-->New-->Project-->Maven
![image.png](http://upload-images.jianshu.io/upload_images/1616232-d915089528e195a3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/1616232-41bb56b03c81b1a8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/1616232-b640fd6bd2aaa751.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- mall-parent:pom.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <!--功能：父工程 打包方式为pom 管理jar包的版本号。项目中的所有工程都应该继承父工程。-->
    <groupId>com.mall</groupId>
    <artifactId>mall-parent</artifactId>
    <version>1.0-SNAPSHOT</version>
    <modules>
        <module>../mall-common</module>
        <module>../mall-manager</module>
        <module>../mall-web</module>
    </modules>
    <packaging>pom</packaging>
    <!--版本号-->
    <properties>
        <junit.version>4.12</junit.version>
        <spring.version>4.2.4.RELEASE</spring.version>
        <mybatis.version>3.2.8</mybatis.version>
        <mybatis.spring.version>1.2.2</mybatis.spring.version>
        <mybatis.paginator.version>1.2.15</mybatis.paginator.version>
        <mysql.version>5.1.32</mysql.version>
        <slf4j.version>1.6.4</slf4j.version>
        <jackson.version>2.4.2</jackson.version>
        <druid.version>1.0.9</druid.version>
        <httpclient.version>4.3.5</httpclient.version>
        <jstl.version>1.2</jstl.version>
        <servlet-api.version>2.5</servlet-api.version>
        <jsp-api.version>2.0</jsp-api.version>
        <joda-time.version>2.5</joda-time.version>
        <commons-lang3.version>3.3.2</commons-lang3.version>
        <commons-io.version>1.3.2</commons-io.version>
        <commons-net.version>3.3</commons-net.version>
        <pagehelper.version>3.4.2</pagehelper.version>
        <jsqlparser.version>0.9.1</jsqlparser.version>
        <commons-fileupload.version>1.3.1</commons-fileupload.version>
        <jedis.version>2.7.2</jedis.version>
        <solrj.version>4.10.3</solrj.version>
        <dubbo.version>2.5.3</dubbo.version>
        <zookeeper.version>3.4.7</zookeeper.version>
        <zkclient.version>0.1</zkclient.version>
        <activemq.version>5.11.2</activemq.version>
        <freemarker.version>2.3.23</freemarker.version>
        <quartz.version>2.2.2</quartz.version>
    </properties>
    <dependencyManagement>
        <dependencies>
            <!-- 时间操作组件 -->
            <dependency>
                <groupId>joda-time</groupId>
                <artifactId>joda-time</artifactId>
                <version>${joda-time.version}</version>
            </dependency>
            <!-- Apache工具组件 -->
            <dependency>
                <groupId>org.apache.commons</groupId>
                <artifactId>commons-lang3</artifactId>
                <version>${commons-lang3.version}</version>
            </dependency>
            <dependency>
                <groupId>org.apache.commons</groupId>
                <artifactId>commons-io</artifactId>
                <version>${commons-io.version}</version>
            </dependency>
            <dependency>
                <groupId>commons-net</groupId>
                <artifactId>commons-net</artifactId>
                <version>${commons-net.version}</version>
            </dependency>
            <!-- Jackson Json处理工具包 -->
            <dependency>
                <groupId>com.fasterxml.jackson.core</groupId>
                <artifactId>jackson-databind</artifactId>
                <version>${jackson.version}</version>
            </dependency>
            <!-- httpclient -->
            <dependency>
                <groupId>org.apache.httpcomponents</groupId>
                <artifactId>httpclient</artifactId>
                <version>${httpclient.version}</version>
            </dependency>
            <!-- quartz任务调度框架 -->
            <dependency>
                <groupId>org.quartz-scheduler</groupId>
                <artifactId>quartz</artifactId>
                <version>${quartz.version}</version>
            </dependency>
            <!-- 单元测试 -->
            <dependency>
                <groupId>junit</groupId>
                <artifactId>junit</artifactId>
                <version>${junit.version}</version>
                <scope>test</scope>
            </dependency>
            <!-- 日志处理 -->
            <dependency>
                <groupId>org.slf4j</groupId>
                <artifactId>slf4j-log4j12</artifactId>
                <version>${slf4j.version}</version>
            </dependency>
            <!-- Mybatis -->
            <dependency>
                <groupId>org.mybatis</groupId>
                <artifactId>mybatis</artifactId>
                <version>${mybatis.version}</version>
            </dependency>
            <dependency>
                <groupId>org.mybatis</groupId>
                <artifactId>mybatis-spring</artifactId>
                <version>${mybatis.spring.version}</version>
            </dependency>
            <dependency>
                <groupId>com.github.miemiedev</groupId>
                <artifactId>mybatis-paginator</artifactId>
                <version>${mybatis.paginator.version}</version>
            </dependency>
            <dependency>
                <groupId>com.github.pagehelper</groupId>
                <artifactId>pagehelper</artifactId>
                <version>${pagehelper.version}</version>
            </dependency>
            <!-- MySql -->
            <dependency>
                <groupId>mysql</groupId>
                <artifactId>mysql-connector-java</artifactId>
                <version>${mysql.version}</version>
            </dependency>
            <!-- 连接池 -->
            <dependency>
                <groupId>com.alibaba</groupId>
                <artifactId>druid</artifactId>
                <version>${druid.version}</version>
            </dependency>
            <!-- Spring -->
            <dependency>
                <groupId>org.springframework</groupId>
                <artifactId>spring-context</artifactId>
                <version>${spring.version}</version>
            </dependency>
            <dependency>
                <groupId>org.springframework</groupId>
                <artifactId>spring-beans</artifactId>
                <version>${spring.version}</version>
            </dependency>
            <dependency>
                <groupId>org.springframework</groupId>
                <artifactId>spring-webmvc</artifactId>
                <version>${spring.version}</version>
            </dependency>
            <dependency>
                <groupId>org.springframework</groupId>
                <artifactId>spring-jdbc</artifactId>
                <version>${spring.version}</version>
            </dependency>
            <dependency>
                <groupId>org.springframework</groupId>
                <artifactId>spring-aspects</artifactId>
                <version>${spring.version}</version>
            </dependency>
            <dependency>
                <groupId>org.springframework</groupId>
                <artifactId>spring-jms</artifactId>
                <version>${spring.version}</version>
            </dependency>
            <dependency>
                <groupId>org.springframework</groupId>
                <artifactId>spring-context-support</artifactId>
                <version>${spring.version}</version>
            </dependency>
            <!-- JSP相关 -->
            <dependency>
                <groupId>jstl</groupId>
                <artifactId>jstl</artifactId>
                <version>${jstl.version}</version>
            </dependency>
            <dependency>
                <groupId>javax.servlet</groupId>
                <artifactId>servlet-api</artifactId>
                <version>${servlet-api.version}</version>
                <scope>provided</scope>
            </dependency>
            <dependency>
                <groupId>javax.servlet</groupId>
                <artifactId>jsp-api</artifactId>
                <version>${jsp-api.version}</version>
                <scope>provided</scope>
            </dependency>
            <!-- 文件上传组件 -->
            <dependency>
                <groupId>commons-fileupload</groupId>
                <artifactId>commons-fileupload</artifactId>
                <version>${commons-fileupload.version}</version>
            </dependency>
            <!-- Redis客户端 -->
            <dependency>
                <groupId>redis.clients</groupId>
                <artifactId>jedis</artifactId>
                <version>${jedis.version}</version>
            </dependency>
            <!-- solr客户端 -->
            <dependency>
                <groupId>org.apache.solr</groupId>
                <artifactId>solr-solrj</artifactId>
                <version>${solrj.version}</version>
            </dependency>
            <!-- dubbo相关 -->
            <dependency>
                <groupId>com.alibaba</groupId>
                <artifactId>dubbo</artifactId>
                <version>${dubbo.version}</version>
            </dependency>
            <dependency>
                <groupId>org.apache.zookeeper</groupId>
                <artifactId>zookeeper</artifactId>
                <version>${zookeeper.version}</version>
            </dependency>
            <dependency>
                <groupId>com.github.sgroschupf</groupId>
                <artifactId>zkclient</artifactId>
                <version>${zkclient.version}</version>
            </dependency>
            <dependency>
                <groupId>org.apache.activemq</groupId>
                <artifactId>activemq-all</artifactId>
                <version>${activemq.version}</version>
            </dependency>
            <dependency>
                <groupId>org.freemarker</groupId>
                <artifactId>freemarker</artifactId>
                <version>${freemarker.version}</version>
            </dependency>

        </dependencies>
    </dependencyManagement>
    <build>
        <finalName>${project.artifactId}</finalName>
        <plugins>
            <!-- 资源文件拷贝插件 -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-resources-plugin</artifactId>
                <version>2.7</version>
                <configuration>
                    <encoding>UTF-8</encoding>
                </configuration>
            </plugin>
            <!-- java编译插件 -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.7.0</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                    <encoding>UTF-8</encoding>
                </configuration>
            </plugin>
        </plugins>
        <pluginManagement>
            <plugins>
                <!-- 配置Tomcat插件 -->
                <plugin>
                    <groupId>org.apache.tomcat.maven</groupId>
                    <artifactId>tomcat7-maven-plugin</artifactId>
                    <version>2.2</version>
                </plugin>
            </plugins>
        </pluginManagement>
    </build>
</project>
```
- #### 3.创建`mall-common` 通用的工程, 打包方式jar
  - 在`mall-parent`文件上右击创建新的model,和创建maven类似不需要勾选信息,然后会出现如下如下界面
![子类](http://upload-images.jianshu.io/upload_images/1616232-80f22eec089bf45a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/1616232-911cd4af71845c25.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- mall-common:pom.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <!--功能：通用的工具类，通用的pojo 打包方式jar-->
    <!--继承parent工程-->
    <parent>
        <artifactId>mall-parent</artifactId>
        <groupId>com.mall</groupId>
        <version>1.0-SNAPSHOT</version>
        <relativePath>../mall-parent/pom.xml</relativePath>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>mall-common</artifactId>
    <dependencies>
        <!--====================添加工具类包的依赖=======================-->
        <!-- 时间操作组件 -->
        <dependency>
            <groupId>joda-time</groupId>
            <artifactId>joda-time</artifactId>
        </dependency>
        <!-- Apache工具组件 -->
        <dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-lang3</artifactId>
        </dependency>
        <dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-io</artifactId>
        </dependency>
        <dependency>
            <groupId>commons-net</groupId>
            <artifactId>commons-net</artifactId>
        </dependency>
        <!-- Jackson Json处理工具包 -->
        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
        </dependency>
        <!-- httpclient -->
        <dependency>
            <groupId>org.apache.httpcomponents</groupId>
            <artifactId>httpclient</artifactId>
        </dependency>
        <!-- quartz任务调度框架 -->
        <dependency>
            <groupId>org.quartz-scheduler</groupId>
            <artifactId>quartz</artifactId>
        </dependency>
        <!-- 单元测试 -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <scope>test</scope>
        </dependency>
        <!-- 日志处理 -->
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-log4j12</artifactId>
        </dependency>
    </dependencies>

</project>
```
- #####4.创建`mall-manager`服务层工程、聚合工程、pom工程
  - 创建工程类似`mall-common`的过程不在演示
  - mall-manager:pom.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <!--功能：服务层工程、聚合工程、pom工程-->
    <!--继承parent工程-->
    <parent>
        <artifactId>mall-parent</artifactId>
        <groupId>com.mall</groupId>
        <version>1.0-SNAPSHOT</version>
        <relativePath>../mall-parent/pom.xml</relativePath>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>mall-manager</artifactId>
    <packaging>pom</packaging>
    <modules>
        <module>mall-manager-dao</module>
        <module>mall-manager-entity</module>
        <module>mall-manager-interface</module>
        <module>mall-manager-service</module>
    </modules>
    <dependencies>
        <!--工程之间的依赖 manager依赖common-->
        <dependency>
            <artifactId>mall-common</artifactId>
            <groupId>com.mall</groupId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
    </dependencies>
</project>
```
- #### 5.创建`mall-manager-dao`、
  - 在`mall-manager`上右键创建，过程类似`mall-common`的创建但是路径选择需要重写填写，如下图
![](http://upload-images.jianshu.io/upload_images/1616232-6f7d935553de6a4e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  - mall-manager-dao:pom.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>mall-manager</artifactId>
        <groupId>com.mall</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>mall-manager-dao</artifactId>
    <dependencies>
        <!--依赖entity 实体类-->
        <dependency>
            <artifactId>mall-manager-entity</artifactId>
            <groupId>com.mall</groupId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
        <!--====================添加mybatis等数据库相关依赖===========================-->
        <!-- Mybatis -->
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis</artifactId>
        </dependency>
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis-spring</artifactId>
        </dependency>
        <dependency>
            <groupId>com.github.miemiedev</groupId>
            <artifactId>mybatis-paginator</artifactId>
        </dependency>
        <dependency>
            <groupId>com.github.pagehelper</groupId>
            <artifactId>pagehelper</artifactId>
        </dependency>
        <!-- MySql -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
        </dependency>
        <!-- 连接池 -->
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid</artifactId>
        </dependency>
    </dependencies>
</project>
```
  - mall-manager-entity：pom.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>mall-manager</artifactId>
        <groupId>com.mall</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>mall-manager-entity</artifactId>
</project>
```
  - mall-manager-interface:pom.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>mall-manager</artifactId>
        <groupId>com.mall</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>mall-manager-interface</artifactId>
    <dependencies>
        <!--依赖entity 实体类-->
        <dependency>
            <artifactId>mall-manager-entity</artifactId>
            <groupId>com.mall</groupId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
    </dependencies>
</project>
```
  - mall-manager-service 创建时要创建webapp/WEB-INF/web.xml
![image.png](http://upload-images.jianshu.io/upload_images/1616232-15b30ff60d5cdeb8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xmlns="http://java.sun.com/xml/ns/javaee"
         xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd"
         id="WebApp_ID" version="2.5">
    <display-name>mall-manager</display-name>
    <welcome-file-list>
        <welcome-file>index.jsp</welcome-file>
    </welcome-file-list>

</web-app>
```
  - mall-manager-service:pom.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>mall-manager</artifactId>
        <groupId>com.mall</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>mall-manager-service</artifactId>
    <packaging>war</packaging>
    <dependencies>
       <!--依赖dao-->
        <dependency>
            <artifactId>mall-manager-dao</artifactId>
            <groupId>com.mall</groupId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
        <!--加载spring-->
        <!-- Spring -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-beans</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jdbc</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-aspects</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jms</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context-support</artifactId>
        </dependency>
    </dependencies>
</project>
```
- #### 6.创建mall-web 表现层

![创建项目](http://upload-images.jianshu.io/upload_images/1616232-78db007c184f755f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/1616232-0a82c7e2f2ed790b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/1616232-ac76ba61cc880435.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  - mall-web：pom.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>mall-parent</artifactId>
        <groupId>com.mall</groupId>
        <version>1.0-SNAPSHOT</version>
        <relativePath>../mall-parent/pom.xml</relativePath>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>mall-web</artifactId>
    <packaging>war</packaging>
    <dependencies>
        <!--依赖 mall-common-->
        <dependency>
            <groupId>com.mall</groupId>
            <artifactId>mall-common</artifactId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
        <!--依赖 mall-manager-interface-->
        <dependency>
            <groupId>com.mall</groupId>
            <artifactId>mall-manager-interface</artifactId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
        <!-- Spring -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-beans</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jdbc</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-aspects</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jms</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context-support</artifactId>
        </dependency>
        <!-- JSP相关 -->
        <dependency>
            <groupId>jstl</groupId>
            <artifactId>jstl</artifactId>
        </dependency>
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>servlet-api</artifactId>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>jsp-api</artifactId>
            <scope>provided</scope>
        </dependency>
        <!-- dubbo相关的jar包 -->
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>dubbo</artifactId>
            <exclusions>
                <exclusion>
                    <artifactId>spring</artifactId>
                    <groupId>org.springframework</groupId>
                </exclusion>
                <exclusion>
                    <artifactId>netty</artifactId>
                    <groupId>org.jboss.netty</groupId>
                </exclusion>
            </exclusions>
        </dependency>
        <dependency>
            <groupId>org.apache.zookeeper</groupId>
            <artifactId>zookeeper</artifactId>
        </dependency>
        <dependency>
            <groupId>com.github.sgroschupf</groupId>
            <artifactId>zkclient</artifactId>
        </dependency>
    </dependencies>
    <build>
        <plugins>
            <plugin>
               <groupId>org.apache.tomcat.maven</groupId>
                <artifactId>tomcat8-maven-plugin</artifactId>
                <configuration>
                    <path>/</path>
                    <port>8090</port>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
```
到此为止已经创建好了项目结构，创建的目录结构如下所示
![目录结构](http://upload-images.jianshu.io/upload_images/1616232-b2b7990852c8ba84.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
># 三 通过tomcat插件启动项目
- 这个配置已经在mall-web：pom.xml中配置，无需再配置
```
 <build>
        <plugins>
            <plugin>
               <groupId>org.apache.tomcat.maven</groupId>
                <artifactId>tomcat8-maven-plugin</artifactId>
                <configuration>
                    <path>/</path>
                    <port>8090</port>
                </configuration>
            </plugin>
        </plugins>
    </build>
```
- 首先运行mall-parent-->install
![](http://upload-images.jianshu.io/upload_images/1616232-352b24b4125423e8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 然后运行mall-web -->
![](http://upload-images.jianshu.io/upload_images/1616232-7addd926d757cdd3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 项目启动成功
![](http://upload-images.jianshu.io/upload_images/1616232-8a8e9f80205a8f0b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 在地址栏输入：localhost:8090(默认是8080)
![成功访问](http://upload-images.jianshu.io/upload_images/1616232-29adb68305f03af2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>### 代码GitHub地址：[project-Mall](https://github.com/821453366/Mall)
>## 所属文集：[技术栈](https://www.jianshu.com/nb/11370298)
