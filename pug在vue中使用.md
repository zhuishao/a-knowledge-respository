#在vue中使用pug
##声明pug语言
在 .vue 文件中，使用 `<template lang="pug"> ... </template>` 声明pug模板
##书写属性及文本
1. 在 .vue 文件中,使用`tagname.className·(attributeName="attributeValue") textContent`格式书写。
举例：  `div.test(:data="data-var") {{ data.text}}`
2. *注意：圆括号前没有空格，圆括号后面有空格*
3. 如果有多个attribute，可以分行写或者用逗号隔开。
举例：

    // 分行
    `slot(:msg="msg"
      class="hahah")`

或者
    // 一行
   ` slot(:msg="msg" class="hahah")`

或者
    // 使用逗号
   ` slot(:msg="msg", class="hahah")`  


