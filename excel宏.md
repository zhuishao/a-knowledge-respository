#EXCEL同色相加
##利用查找
1. 打开excel按ctrl+f
2. 格式右边的小三角，从单元格查找格式
3. 点击颜色
4. 查找全部
5. 点击下方之后alt+a
6. 再excel看求和
##使用宏
###打开宏
1. 文件->选项->自定义功能区->勾选开发工具->确定
2. 文件->选项->信任中心->信任中心设置
3. 点击“宏设置”，勾选“启用所有宏”、“信任对VBA工程对象模型的访问”，点击“确定”。
###使用宏
1. alt+f11
2. 右击模块，插入模块
3. Function sumcolor(rng1 As Range, rng2 As Range) As Single
Dim cell As Range
sumcolor = 0
For Each cell In rng1
If cell.interior.Color = rng2.interior.Color Then sumcolor = sumcolor + cell
Next cell
End Function
4. =sumcolor(A1:A2,C3)