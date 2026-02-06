## 前言

本项目是基于Java语言和Spring Boot框架，结合Vue前端技术，开发的阿坝州旅游实战项目。该项目适用于计算机毕业设计，不仅包含完整的源码、文档报告，还有详细的代码讲解。在此，我们将其开源分享给大家，希望能为正在做或准备做相关项目的同学提供一些参考和帮助。

## 内容介绍

本项目主要分为前后端两部分，前端采用Vue技术实现旅游信息的展示，后端采用Spring Boot技术处理业务逻辑和数据库操作。通过此项目，用户可以了解阿坝州的旅游景点、旅游攻略等信息，同时提供用户注册、登录等功能，使游客能够更好地体验阿坝州的风光。

## 技术介绍

- 语言：Java
- 使用框架：Spring Boot
- 前端技术：JS、Vue、css3
- 开发工具：IDEA/Eclipse
- 数据库：MySQL 5.7/8.0
- 数据库管理工具：phpstudy/Navicat
- JDK版本：jdk1.8
- Maven: apache-maven 3.8.1-bin
- 前端环境：Node.Js 12\14\16

## 核心代码

以下是一段后端处理用户登录请求的核心代码：

```java
@PostMapping("/login")
public ResponseEntity<String> login(@RequestBody User user) {
    String username = user.getUsername();
    String password = user.getPassword();
    
    if (StringUtils.isEmpty(username) || StringUtils.isEmpty(password)) {
        return ResponseEntity.badRequest().body("用户名或密码不能为空");
    }
    
    User loginUser = userService.findByUsername(username);
    if (loginUser == null) {
        return ResponseEntity.status(HttpStatus.UNAUTHORIZED).body("用户名或密码错误");
    }
    
    if (!passwordEncoder.matches(password, loginUser.getPassword())) {
        return ResponseEntity.status(HttpStatus.UNAUTHORIZED).body("用户名或密码错误");
    }
    
    // 登录成功，生成token
    String token = jwtTokenUtil.generateToken(loginUser);
    return ResponseEntity.ok("登录成功").header("Authorization", token);
}
```

## 免费源码获取

```
5000套系统成品在线演示视频，复制到流浪器： 
```
```
https://www.yuque.com/yuqueyonghux32e1j/kxdc9g/ad8oz3bamkxmay0e#Cxun
``` 
![下载](https://img12.360buyimg.com/ddimg/jfs/t1/339687/11/1349/28408/68ad865fF412d7877/adaa650483a100f2.jpg)

## 项目截图

（由于篇幅原因，这里不展示项目截图，您可以在获取源码后自行运行查看）
## 万字文档
![文档介绍](https://img14.360buyimg.com/ddimg/jfs/t1/338393/1/3576/156947/68b1ad0cF74dc525c/ff9cd6c574295685.jpg)
