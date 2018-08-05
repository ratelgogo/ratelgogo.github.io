---
title: gradle版本冲突
date: 2018-02-25 10:22:58
tags: -gradle
---

### Transitive

gradle的依赖管理默认具有传递性，A依赖B，B依赖C，则A依赖C。

也可以将这项配置关闭，这样A所依赖的B和C需要手动添加。

```groovy
//整个项目取消依赖传递
configurations.all {
  transitive = false
}
//单个依赖取消依赖传递
dependencies {
  compile ('group:name:version') {
    transitive = false
  }
}
```

### 依赖冲突

如果D也依赖C，而且B依赖的C的版本为1.0，D依赖的C的版本为2.0

gradle会如何选择？

默认选择最新版本，不会报错。所以在默认配置下，依赖会生产冲突。

依赖冲突的解决方法应该是定制化的。

+ #### Force

  强制设置某个版本

  ```groovy
  //整个项目统一使用某个版本
  configurations.all {
    resolutionStrategy {
      force 'group:c:1.0'
    }
  }
  //特定依赖使用某个版本
  dependencies {
    compile ('group:B:version') {
      force 'group:C:1.0'
    }
  }
  ```

  ​

+ #### exclude

去除某个依赖，其实就会使用没有去处的依赖的版本，也可以使依赖一致。

```groovy
dependencies {
  compile ('group:D:version) {
    exclude 'group:C'
  }
}
```

