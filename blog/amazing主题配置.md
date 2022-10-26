# 主题配置过程中的问题记录

### 环境配置

- ```bash
  {
    "name": "hexo-site",
    "version": "0.0.0",
    "private": true,
    "scripts": {
      "build": "hexo generate",
      "clean": "hexo clean",
      "deploy": "hexo deploy",
      "server": "hexo server"
    },
    "hexo": {
      "version": "5.2.0"
    },
    "dependencies": {
      "bulma-stylus": "^0.8.0",
      "hexo": "^5.0.0",
      "hexo-blog-encrypt": "^3.0.13",
      "hexo-component-inferno": "^0.8.2",
      "hexo-deployer-git": "^2.1.0",
      "hexo-generator-archive": "^1.0.0",
      "hexo-generator-category": "^1.0.0",
      "hexo-generator-index": "^2.0.0",
      "hexo-generator-tag": "^1.0.0",
      "hexo-renderer-ejs": "^1.0.0",
      "hexo-renderer-inferno": "^0.1.3",
      "hexo-renderer-marked": "^3.0.0",
      "hexo-renderer-stylus": "^2.0.0",
      "hexo-server": "^2.0.0"
    }
  }
  ```

- 将上面配置代码替换到博客根目录package.json中  (依赖包配置文件)

- 删除博客根目录node_modules文件夹  (依赖包文件夹)

- npm install 安装依赖包即可

- hexo clean

- hexo g

- hexo s

- heox d



### 依赖包过期，需要升级

- ```bash
  INFO  === Checking package dependencies ===
  ERROR Package hexo-component-inferno's version (0.8.2) does not satisfy the required version (^0.10.1).
  ERROR Please install the missing dependencies your Hexo site root directory:
  ERROR npm install --save hexo-component-inferno@^0.10.1
  ERROR or:
  ERROR yarn add hexo-component-inferno@^0.10.1
  
  INFO === 检查包依赖关系 ===
  错误软件包 hexo-component-inferno 的版本 (0.8.2) 不满足所需的版本 (^0.10.1)。
  错误请在您的 Hexo 站点根目录安装缺少的依赖项：
  错误 npm install --save hexo-component-inferno@^0.10.1
  错误或：
  错误纱线添加 hexo-component-inferno@^0.10.1
  ```

- 上面报错是说这个hexo-component-inferno过期了，太老了，需要升级

- 我自己尝试的是把最上面那个环境配置文件中的"hexo-component-inferno": "^0.8.2"版本号更改，更改成需要的版本，比如报错里的0.10.1

- 更改完成之后再次删除原有依赖包文件夹重新安装



### 依赖包过期问题自我解决之后遇到的新问题记录

##### 一

- ```bash
  npm WARN deprecated source-map-url@0.4.1: See https://github.com/lydell/source-map-url#deprecated
  npm WARN deprecated urix@0.1.0: Please see https://github.com/lydell/urix#deprecated
  npm WARN deprecated source-map-resolve@0.5.3: See https://github.com/lydell/source-map-resolve#deprecated
  npm WARN deprecated resolve-url@0.2.1: https://github.com/lydell/resolve-url#deprecated
  npm WARN deprecated highlight.js@9.18.5: Support has ended for 9.x series. Upgrade to @latest
  
  npm WARN 已弃用 source-map-url@0.4.1：请参阅 https://github.com/lydell/source-map-url#deprecated
  npm WARN 已弃用 urix@0.1.0：请参阅 https://github.com/lydell/urix#deprecated
  npm WARN 已弃用 source-map-resolve@0.5.3：请参阅 https://github.com/lydell/source-map-resolve#deprecated
  npm WARN 已弃用 resolve-url@0.2.1：https://github.com/lydell/resolve-url#deprecated
  npm WARN 已弃用 highlight.js@9.18.5：对 9.x 系列的支持已结束。 升级到@latest
  ```

- 这是修改版本号重新安装依赖包后遇到的，目前没啥问题和发现



##### 二

- ```bash
  (node:11536) Warning: Accessing non-existent property 'lineno' of module exports inside circular dependency
  (Use `node --trace-warnings ...` to show where the warning was created)
  (node:11536) Warning: Accessing non-existent property 'column' of module exports inside circular dependency
  (node:11536) Warning: Accessing non-existent property 'filename' of module exports inside circular dependency
  (node:11536) Warning: Accessing non-existent property 'lineno' of module exports inside circular dependency
  (node:11536) Warning: Accessing non-existent property 'column' of module exports inside circular dependency
  (node:11536) Warning: Accessing non-existent property 'filename' of module exports inside circular dependency
  
  （节点：11536）警告：在循环依赖中访问模块导出的不存在属性“lineno”
  （使用 `node --trace-warnings ...` 显示警告的创建位置）
  （节点：11536）警告：在循环依赖中访问模块导出的不存在属性“列”
  （节点：11536）警告：在循环依赖中访问模块导出的不存在的属性“文件名”
  （节点：11536）警告：在循环依赖中访问模块导出的不存在属性“lineno”
  （节点：11536）警告：在循环依赖中访问模块导出的不存在属性“列”
  （节点：11536）警告：在循环依赖中访问模块导出的不存在的属性“文件名”
  ```

- 这个是在hexo s之后发现的问题，目前没啥发现和问题



##### 三

- ```bash
  (node:13432) Warning: Accessing non-existent property 'lineno' of module exports inside circular dependency
  (Use `node --trace-warnings ...` to show where the warning was created)
  (node:13432) Warning: Accessing non-existent property 'column' of module exports inside circular dependency
  (node:13432) Warning: Accessing non-existent property 'filename' of module exports inside circular dependency
  (node:13432) Warning: Accessing non-existent property 'lineno' of module exports inside circular dependency
  (node:13432) Warning: Accessing non-existent property 'column' of module exports inside circular dependency
  (node:13432) Warning: Accessing non-existent property 'filename' of module exports inside circular dependency
  
  （节点：13432）警告：在循环依赖中访问模块导出的不存在属性“lineno”
  （使用 `node --trace-warnings ...` 显示警告的创建位置）
  （节点：13432）警告：在循环依赖中访问模块导出的不存在属性“列”
  （节点：13432）警告：在循环依赖中访问模块导出的不存在的属性“文件名”
  （节点：13432）警告：在循环依赖中访问模块导出的不存在属性“lineno”
  （节点：13432）警告：在循环依赖中访问模块导出的不存在属性“列”
  （节点：13432）警告：在循环依赖中访问模块导出的不存在的属性“文件名”
  ```

- 这个是在hexo g之后发现的问题，目前没啥发现和问题



### 配置参数

- 第一步热门推荐中的两个参数未配置
- 第二步友链
- 第三步影音数据
- 第四步时间轴
- 第六步置顶配置为做修改
- 7
- 8
- 9
- 10
- 11







