---
title: "JWT"
author: Bill.Lin
date: 2021-07-01T23:39:52+08:00
draft: false
tags: []
Description: ""
Categories: []
DisableComments: false
---

# JWT Dependency Inject

```xml

// 兩種  引入 jjwt ， version 放 properties 內方便控管

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <java.version>1.8</java.version>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
        <jjwt.version>0.9.0</jjwt.version>
    </properties>

    <dependency>
        <groupId>io.jsonwebtoken</groupId>
        <artifactId>jjwt</artifactId>
        <version>${jjwt.version}</version>
    </dependency>

    <dependency>
        <groupId>javax.xml.bind</groupId>
         <artifactId>jaxb-api</artifactId>
    </dependency>

// 第二種

    <dependency>
        <groupId>io.jsonwebtoken</groupId>
        <artifactId>jjwt-api</artifactId>
        <version>0.11.2</version>
    </dependency>

    <dependency>
        <groupId>io.jsonwebtoken</groupId>
        <artifactId>jjwt-impl</artifactId>
        <version>0.11.2</version>
        <scope>runtime</scope>
    </dependency>

    <dependency>
        <groupId>io.jsonwebtoken</groupId>
        <artifactId>jjwt-jackson</artifactId>
        <version>0.11.2</version>
        <scope>runtime</scope>
    </dependency>

```

