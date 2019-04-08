2019-4-8 18:29:19
## 关于空格(http://www.cnblogs.com/52cik/p/js-regexp-s.html)
```javascript
    const rspace = /[\s\uFEFF\xA0]+/g
    
```
浅谈 js 字符串 trim 方法之正则篇
关于 trim 其实没啥好说的，无非就是去除首位空格，对于现代浏览器来说只是简单的正则 /^\s+|\s+$/ 就可以搞定了。
而且支持中文空格 &nbsp; 等等。
什么 \s 支持 中文空格？
是的。

打开 RegExp#character-classes 往下拉一点，找到 \s 这个解释。

原文：
Matches a single white space character, including space, tab, form feed, line feed and other Unicode spaces. Equivalent to [ \f\n\r\t\v\u00a0\u1680\u180e\u2000\u2001\u2002\u2003\u2004\u2005\u2006\u2007\u2008\u2009\u200a\u2028\u2029\u202f\u205f\u3000].

谷歌译文:
匹配单个空白字符，包括空格，制表符，换页，换行等Unicode的空格。
相当于 [ \f\n\r\t\v\u00a0\u1680\u180e\u2000\u2001\u2002\u2003\u2004\u2005\u2006\u2007\u2008\u2009\u200a\u2028\u2029\u202f\u205f\u3000]

其中 \u00a0 是 &nbsp; \u3000 是 中文空格，其他是什么，我也不知道，有兴趣的可以自己去翻 unicode 表。

看到这，已经颠覆了我们传统正则的规范了，以前，我们只知道 \s 等价于 [ \f\n\r\t\v]，但却不知道现在的js里却等价于所有空白字符。
话虽如此，但是低版本却一直是 [ \f\n\r\t\v]，甚至连 trim 都木有，所以我们要兼容低版本的话，不能简单的用 /^\s+|\s+$/ 处理了，要加上中文空格 和 &nbsp; 
所以要 /^[\s\u3000\u00A0]+|[\s\u3000\u00A0]+$/ 才行，这样常用的就有了，至于那些 \u2000 之类的，我也不知道是什么，可以按需添加进去。
常用的无非就中文空格和实体空格了。

我们看下 jQuery 是怎么处理这个的。
```javascript
    // 1.4.1
rtrim = /^(\s|\u00A0)+|(\s|\u00A0)+$/g,

// 1.5.1, 1.6.1, 1.7.1
trimLeft = /^[\s\xA0]+/;
trimRight = /[\s\xA0]+$/;

// 1.8.1, 1.9.1, 1.10.1, 1.11.1
rtrim = /^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g,
```

好吧，1.4-1.7 都一样，值去除普通空格和实体空格。
1.8-1.11 加了一个 \uFEFF ，这个是什么东西呢？
jQuery 的注释写到 Make sure we trim BOM and NBSP (here's looking at you, Safari 5.0 and IE)
译为： 确保去除 BOM 和 &nbsp; (请看你的 Safari 5.0 and IE)
什么 BOM ？为什么会出现 BOM ？
这东西一般人是打不出来的，为什么要去除这个呢? 
PS：这里的BOM是 字节顺序标记(byte-order mark)，不清楚的，请翻阅这里 字节顺序标记 。

我也不知道，最近翻不了墙，所以懒得找了。
但是他不去除中文空格这有点说不过去了，难道他们不会中文，就无视中文空格么？
所以我们应该优化下这个正则 /^[\s\u3000\uFEFF\xA0]+|[\s\u3000\uFEFF\xA0]+$/g 这样才对嘛。

来看下原生 trim 和我们正则去除结果如何吧:

var rtrim = /^[\s\u3000\uFEFF\xA0]+|[\s\u3000\uFEFF\xA0]+$/g;
console.log( "普通空格测试:" );
console.log( "'" + " 普通空格 ".replace(rtrim, "") + "'" );
console.log( "'" + " 普通空格 ".trim() + "'" );

console.log( "实体空格测试:" );
console.log( "'" + " \u00a0 实体空格 \u00a0 ".replace(rtrim, "") + "'" );
console.log( "'" + " \u00a0 实体空格 \u00a0 ".trim() + "'" );

console.log( "中文空格测试:" );
console.log( "'" + " 　 中文空格 　 \u3000".replace(rtrim, "") + "'" );
console.log( "'" + " 　 中文空格 　 \u3000".trim() + "'" );
结果很明显，都去除干净了，说明 trim 也是支持中文空格的。

