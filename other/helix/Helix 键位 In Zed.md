## Helix 原生

> h,j,k,l---左、下、上、右移动

[参考文档](https://helix-editor.vercel.app/start-here/basics)

| 按键           | 含义                        |
| ------------ | ------------------------- |
| x<br>        | 选中1行                      |
| y            | yank复制                    |
| p            | paste粘贴                   |
| b            | 上一个word                   |
| e            | word的末尾                   |
| w            | 下一个word                   |
| c            | 移除选择内容，进入Insert mode      |
| d            | delete删除                  |
| u            | 撤销                        |
| U            | 撤销u的撤销                    |
| gw           | 给word做索引，快速移动到某word       |
| gg           | 回到全文开始或给定行号开始             |
| gl           | 移动到当前行末                   |
| gs           | 移动到当前行首                   |
| gh           | 移动到当前行首字母                 |
| R            | replace替换                 |
| s            | 搜索指定范围                    |
| %            | 选择全文                      |
| C            | 向下一行添加多游标                 |
| ctl+`        | 打开终端                      |
| space + k    | 打开rust doc,相当于鼠标悬停        |
| gd           | goto define跳转定义           |
| gr           | goto reference跳转引用        |
| space + f    | 切换文件                      |
| :            | 打开Zed命令面板(ctl shift p)    |
| ;            | 取消选中                      |
| >            | 将选中向右移动tab                |
| <            | 将选中向左移动tab                |
| Q            | 开始记录宏,先需要指定一个寄存器；再次点击停止记录 |
| q            | 复用宏                       |
| v            | 启用选择模式，可搭配任意移动游标键位进行选择    |
| ma+ f/c/a    | 选中整个函数/注释/arg             |
| mi + f/c/a   | 选择函数内部/整个注释/不带,的arg       |
| ma/mi+(/\[/" | 选中整个Pair，ma闭区间，mi开区间      |
| ms (         | 给选中区域前后添加()               |
| mr ( {       | 给选中区域最近的()替换为{}           |
| md (         | 删除选中区域最近的()               |

## Zed自定义键位

| 键位      | 含义         |
| ------- | ---------- |
| f5      | cargo run  |
| f6      | cargo test |
| alt + f | cargo fmt  |
