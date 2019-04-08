## [github的10个功能](https://chenxuehu.com/article/2014/11/3718.html)
	有时候我们需要在自己的文件项目中分享或者输出特殊行。
	Github可以实现，我们只需要添加"#L "放在URL行号后面  
	
[实例](https://github.com/tikazyq/crawlab/blob/master/crawlab/bin/run_worker.py#L10#L15)  

## table 
##### [参考](https://www.jianshu.com/p/abaff828100d)
```markdown
| 左对齐标题 | 右对齐标题 | 居中对齐标题 |
|:------|---:|:----:|
| 短文本 | 中等文本 | 稍微长一点的文本 |
| 稍微长一点的文本 | 短文本 | 中等文本 |
```  
  
  

| 左对齐标题 | 右对齐标题 | 居中对齐标题 |
| :------ | ---: | :----: |
| 短文本 | 中等文本 | 稍微长一点的文本 |
| 稍微长一点的文本 | 短文本 | 中等文本 |  

#### 语法说明
1）|、-、:之间的多余空格会被忽略，不影响布局。  
2）默认标题栏居中对齐，内容居左对齐。  
3）-:表示内容和标题栏居右对齐，:-表示内容和标题栏居左对齐，:-:表示内容和标题栏居中对齐。  
4）内容和|之间的多余空格会被忽略，每行第一个|和最后一个|可以省略，-的数量至少有一个。    

 <table>
        <tr>
            <th>设备</th>
            <th>设备文件名</th>
            <th>文件描述符</th>
            <th>类型</th>
        </tr>
        <tr>
            <th>键盘</th>
            <th>/dev/stdin</th>
            <th>0</th>
            <th>标准输入</th>
        </tr>
        <tr>
            <th>显示器</th>
            <th>/dev/stdout</th>
            <th>1</th>
            <th>标准输出</th>
        </tr>
        <tr>
            <th>显示器</th>
            <th>/dev/stderr</th>
            <th>2</th>
            <th>标准错误输出</th>
        </tr>
    </table>

	

