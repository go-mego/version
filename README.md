# Version

Version 套件能讓你更好聲明任何事物的版本號。這套件可能有點奇怪，但有些時候它能協助你維持命名的秩序。

# 索引

* [安裝方式](#安裝方式)
* [使用方式](#使用方式)

# 安裝方式

打開終端機並且透過 `go get` 安裝此套件即可。

```bash
$ go get github.com/go-mego/version
```

# 使用方式

透過 `Define` 來定義一個新的版本號，而 `String` 能將版本建構體轉換為淺顯易懂的純文字字串。

```go
package main

import (
	"github.com/go-mego/mego"
	"github.com/go-mego/version"
)

func main() {
	m := mego.New()
	m.Get("/", func() string {
		// 結果：「此伺服器版本是：1.0.0+stable」。
		return "此伺服器版本是：" + version.Define(1, 0, 0, "stable").String()
	})
	m.Run()
}
```