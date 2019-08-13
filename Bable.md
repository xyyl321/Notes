# Babel

> 下一代JavaScript语法编译器

解析：词法分析和语法分析 抽象语法树

转换：转换操作

再建：语法树->代码

## 编译文件

- 输出到标准输出设备  npx babel script.js
-  输出到文件 npx babel input.js --out-file output.js   (-o)
- 监听文件(一直监听) npx babel script.js  --watch 
- 编译并输出源码映射表

## 编译文件夹

- 编译整个文件夹
- 输出合并为一个文件夹

npm install @babel/plugin-transform-arrow-functions



npx babel index1.js -o lx.js --plugin=@babel/plugin-transform-arrow-functions