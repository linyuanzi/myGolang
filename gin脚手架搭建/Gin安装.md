# Gin安装

## 前置条件
1. 安装Golang
2. 配置Golang环境(GOPATH、GOBIN)

## 创建项目
创建项目目录，初始化mod
```
cd [newProject]
go mod init [newProject]
```

## 初始Gin框架
```main.go
package main

import "github.com/gin-gonic/gin"

func main() {
	r := gin.Default()
	r.GET("/ping", func(c *gin.Context) {
		c.JSON(200, gin.H{
			"message": "pong",
		})
	})
	r.Run() // listen and serve on 0.0.0.0:8080
}
```

下载依赖
```
go mod tidy
```

## go mod 命令
```
go mod tidy
拉取缺少的模块，移除不用的模块。

go mod download
下载依赖包。

go mod verify
检验依赖。

go mod graph
打印模块依赖图。
```

## go modules
GO111MODULE 设置为 on