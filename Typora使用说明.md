

### 文本

**代码：**

```
*斜体*
**粗体**
***斜体加粗体***
~~删除线~~
<u>下划线</u>
*** 分割线
```

**显示效果**

*斜体* 

 **粗体**

 **斜体加粗体**

 ~~删除线~~

<u>下划线</u>

***



### 标题

```
# 标题1
## 标题2
### 标题3
...
###### 标题6
[toc]  自动生成目录
```

### 超链接

#### 行内超链接

```
[百度搜索](www.baidu.com)
[USB官网](www.usb.org)
```

[百度搜索](www.baidu.com)
[USB官网](www.usb.org)

#### 参考式

```
[id]: <http://example.com/>  "Optional Title Here"
链接内容定义的形式为：
    方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
    接着一个冒号
    接着一个以上的空格或制表符
    接着链接的网址
    选择性地接着 title 内容，可以用单引号、双引号或是括弧包着
[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)
```

[id]: <http://example.com/>  "Optional Title Here"

#### 自动链接式

```
<www.baidu.com>
```

<[www.baidu.com](http://www.baidu.com)>

### 锚点

```
锚点：#超链接
跳转内容：[](#超链接)
注意：需要CTRL+左键才能跳转
```

跳转到[超链接](#超链接)

### 列表

#### 无序列表

```
使用 * + - 都可以表示无序列表。当然还可以使用table键来创建多级列表
```

- 一级列表 
  - 二级列表 
    - 三级列表

#### 有序列表

```
直接使用数字或者字母序号
1. 内容1
2. 内容2
```

1. 一级列表 
   - 二级列表

### 引用

```
在引用的文本前面加上>,可以加多重>
> this is a quote
```

> this is a quote
>
> > haha quote is quote

### 插入图片

```
![图片描述](url)]  也可以直接复制粘贴的 
```



![img](https:////upload-images.jianshu.io/upload_images/2596949-3dfcff0c7d7f19fe.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/176/format/webp)

### 脚注

语法：

```
某些人用过才知道注释[^注释]的好
[^注释]: 注释是对陌生名词的解释
```

某些人用过才知道注释[[1\]](#fn1)的好

再问，再问就两开花[[2\]](#fn2)

### 代码

```
使用英文中的三个波浪号 ~~~
单行可以使用 ``
```

` git fetch`

### LaTex公式

```
快捷键Ctrl+Shift+m  公式块但是因为和输入冲突了
使用 $$+回车代替
行内公式可以用$ $
```

![e^{i\pi}+1=0](https://math.jianshu.com/math?formula=e%5E%7Bi%5Cpi%7D%2B1%3D0)

#### 常用公式的代码

| 格式     | 效果                                                         | 语法                                                         |
| -------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 上标     | ![x^2](https://math.jianshu.com/math?formula=x%5E2)          | `$ x^2 $`                                                    |
| 下标     | ![y_1](https://math.jianshu.com/math?formula=y_1)            | `$ y_1 $`                                                    |
| 左右分式 | ![1/2](https://math.jianshu.com/math?formula=1%2F2)          | `$ 1/2 $`                                                    |
| 上下分式 | ![\frac{1}{2}](https://math.jianshu.com/math?formula=%5Cfrac%7B1%7D%7B2%7D) | `$ \frac{1}{2} $`                                            |
| 省略号   | ![\cdots](https://math.jianshu.com/math?formula=%5Ccdots)    | `$ \cdots $`                                                 |
| 开根号   | ![\sqrt{2}](https://math.jianshu.com/math?formula=%5Csqrt%7B2%7D) | `$ \sqrt{2} $`                                               |
| 矢量     | ![\vec{a}](https://math.jianshu.com/math?formula=%5Cvec%7Ba%7D) | `$ \vec{a} $`                                                |
| 积分     | ![\int_{1}^{2}xdx](https://math.jianshu.com/math?formula=%5Cint_%7B1%7D%5E%7B2%7Dxdx) | `$ \int_{1}^{2}xdx $`                                        |
| 极限     | ![\lim{a+b}](https://math.jianshu.com/math?formula=%5Clim%7Ba%2Bb%7D) | `$ \lim{a+b} $`                                              |
|          | ![\lim_{n\rightarrow+\infty}](https://math.jianshu.com/math?formula=%5Clim_%7Bn%5Crightarrow%2B%5Cinfty%7D) | `$ \lim_{n\rightarrow+\infty} $`                             |
| 累加     | ![\sum{a}](https://math.jianshu.com/math?formula=%5Csum%7Ba%7D) | `$ \sum{a} $`                                                |
|          | ![\sum_{n=1}^{100}{a_n}](https://math.jianshu.com/math?formula=%5Csum_%7Bn%3D1%7D%5E%7B100%7D%7Ba_n%7D) | `$ \sum_{n=1}^{100}{a_n} $`                                  |
| 累乘     | ![\prod{x}](https://math.jianshu.com/math?formula=%5Cprod%7Bx%7D) | `$ \prod{x} $`                                               |
|          | ![\prod_{n=1}^{99}{x_n}](https://math.jianshu.com/math?formula=%5Cprod_%7Bn%3D1%7D%5E%7B99%7D%7Bx_n%7D) | `$ \prod_{n=1}^{99}{x_n} $`                                  |
| 综合     | ![\frac{1}{\pi}=\frac{2\sqrt{2}}{9801}\sum^{\infty}_{k=0}\frac{(4k)!(1103+26390k)}{(k!)^4396^{4k}}](https://math.jianshu.com/math?formula=%5Cfrac%7B1%7D%7B%5Cpi%7D%3D%5Cfrac%7B2%5Csqrt%7B2%7D%7D%7B9801%7D%5Csum%5E%7B%5Cinfty%7D_%7Bk%3D0%7D%5Cfrac%7B(4k)!(1103%2B26390k)%7D%7B(k!)%5E4396%5E%7B4k%7D%7D) | `$ \frac{1}{\pi}=\frac{2\sqrt{2}}{9801}\sum^{\infty}_{k=0}\frac{(4k)!(1103+26390k)}{(k!)^4396^{4k}} $` |

#### 希腊字母

| 大写 | Markdown | 小写 | Markdown    |
| ---- | :------: | ---- | ----------- |
| A    |    A     | α    | \alpha      |
| B    |    B     | β    | \beta       |
| Γ    |  \Gamma  | γ    | \gamma      |
| Δ    |  \Delta  | δ    | \delta      |
| E    |    E     | ϵ    | \epsilon    |
|      |          | ε    | \varepsilon |
| Z    |    Z     | ζ    | \zeta       |
| H    |    H     | η    | \eta        |
| Θ    |  \Theta  | θ    | \theta      |
| I    |    I     | ι    | \iota       |
| K    |    K     | κ    | \kappa      |
| Λ    | \Lambda  | λ    | \lambda     |
| M    |    M     | μ    | \mu         |
| N    |    N     | ν    | \nu         |
| Ξ    |   \Xi    | ξ    | \xi         |
| O    |    O     | ο    | \omicron    |
| Π    |   \Pi    | π    | \pi         |
| P    |    P     | ρ    | \rho        |
| Σ    |  \Sigma  | σ    | \sigma      |
| T    |    T     | τ    | \tau        |
| Υ    | \Upsilon | υ    | \upsilon    |
| Φ    |   \Phi   | ϕ    | \phi        |
|      |          | φ    | \varphi     |
| X    |    X     | χ    | \chi        |
| Ψ    |   \Psi   | ψ    | \psi        |
| Ω    |  \Omega  | ω    | \omega      |
|      |          |      |             |

#### 三角函数

| 三角函数 | Markdown |
| -------- | -------- |
| sin      | \sin     |
| cos      | \cos     |
| tan      | \tan     |

#### 对数函数

| 算式                                                        | Markdown |
| ----------------------------------------------------------- | -------- |
| ![\ln2](https://math.jianshu.com/math?formula=%5Cln2)       | \ln2     |
| ![\log_28](https://math.jianshu.com/math?formula=%5Clog_28) | \log_28  |
| ![\lg10](https://math.jianshu.com/math?formula=%5Clg10)     | \lg 10   |

#### 关系运算符

| 算式                                                      | mArkdown |
| --------------------------------------------------------- | -------- |
| ![\pm](https://math.jianshu.com/math?formula=%5Cpm)       | \pm      |
| ![\times](https://math.jianshu.com/math?formula=%5Ctimes) | \times   |
| ![\cdot](https://math.jianshu.com/math?formula=%5Ccdot)   | \cdot    |
| ![\div](https://math.jianshu.com/math?formula=%5Cdiv)     | \div     |
| $ \neq  ￥                                                | \neq     |
| ![\equiv](https://math.jianshu.com/math?formula=%5Cequiv) | \equiv   |
| ![\leq](https://math.jianshu.com/math?formula=%5Cleq)     | \leq     |
| ![\geq](https://math.jianshu.com/math?formula=%5Cgeq)     | \geq     |

#### 其他特殊字符

| 算式                                                         | mArkdown   |
| ------------------------------------------------------------ | ---------- |
| ![\forall](https://math.jianshu.com/math?formula=%5Cforall)  | \forall    |
| ![\infty](https://math.jianshu.com/math?formula=%5Cinfty)    | \infty     |
| ![\emptyset](https://math.jianshu.com/math?formula=%5Cemptyset) | \emptyset  |
| ![\exists](https://math.jianshu.com/math?formula=%5Cexists)  | \exists    |
| ![\nabla](https://math.jianshu.com/math?formula=%5Cnabla)    | \nabla     |
| ![\bot](https://math.jianshu.com/math?formula=%5Cbot)        | \bot       |
| ![\angle](https://math.jianshu.com/math?formula=%5Cangle)    | \angle     |
| ![\because](https://math.jianshu.com/math?formula=%5Cbecause) | \because   |
| ![\therefore](https://math.jianshu.com/math?formula=%5Ctherefore) | \therefore |

#### 行间公式和行内公式

```
行间公式 $$ 公式 $$
行内公式 $公式$
```

### 插入表情

```
:happy: 高兴
:weary: 悲伤
:cry:哭

输入: 再输入字母会自动带出图案
```

:happy:  :weary: :cry: :+1::star:

[表情列表](https://blog.todaycoder.cn/2018/11/18/Typora-Emoji/)

### 任务列表

```
- [ ] do homework
```

- [ ] do homework

### 高亮

~~~
需 Preference Panel -> Markdown Tab启动，
~~~

== Abcde  ==

------

### 注脚[^1]

~~~
添加注脚：[^1]
注脚说明：[^1]: 这是注脚说明
~~~



1. [^1]: 注释是对陌生名词的解释 [↩](#fnref1)

2. 文体两开花，<西游是我家。 [↩](#fnref2)

