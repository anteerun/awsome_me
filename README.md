# 这是一个整理、统计网络资源，以备自己找时间来查看。

这是首页 MarkDown 语法测试

-----------

1. 各级标题不用单独测试
1. 普通文本就比较简单
    * **这里是强调1**，__这里是强调2__
    * *这里是斜体1*， _这里是斜体2_
    * _斜体和**强调**混合使用_
    * __强调和*斜体*混合使用__
    * __*~~我是强调、斜体、中划线~~*__
1. 网页超链接的话有两种:
    1. 直接行内: [我是百度](https://www.baidu.com) 这样的链接在原文里会特别长
    1. 外面标注形式: 我是 [Google][1] 这样的话可以不影响整个文章的阅读
        > 标注的链接要隔行，不然不生效;
        > 标的链接不能放在列表中间，不然列表因为隔行的原因，会重新开始计数;

        > 引用如果不手动换行，会追加在一起，如果手动换行的话，显示的引用中间就是断开的。引用段落分行的问题需要再关注。<br>
        > 当然，如果在行内使用`<br>`标签的话，是可以达到换行的目的，但编辑器也会产生警告。。。；
1. 列表:
    1. 有序列表是以数字+英文句点组成，可以是全部一样的`1. 1. 1.`, 也可以是 `1. 2. 3.`, 也可以是 `1. 5. 3.`，只要是数字+句点就行; 但语法检查时，会提示使用统一的方式；
    1. 无序列表是以`` `*`, `-`, `+` ``等都可以构成无序列表；可以混合使用。但语法错误提示会检查并警告；
        * 这是无序
        - 这呢？
        + 这也是哟。
1. 任务列表
    * - [ ] 任务如果没被勾选，中间也是需要空格的，不然无法识别；
    * * [X] 任务勾选的情况是这样的；
    * - [x] 可以使用小 `x`, `X` 来完成；尝试使用其他字母时，checkbox 无效；
    * * [ ] 任务前面可以是 `-` 或是 `*` ，但有的语法会提示 `-` 不合法，会建议使用 `*` 来打头。
1. 表格

    我是表头1 | 我是表头2 | 我是表头3
    |:--------|:----------:|--------:|
    行1|行2|行3
    列表看起来还是比较完全是你|完全的自动伸缩呀，一行可以很长，只需要使用 `|` 管道分开，就可以自成一列|太棒了
    上一行只是测试|短|哈哈
    还可以空着||
    |对齐的话，在表头的下一行|
    |如果第一列、最后一列要向外对齐的话， `:`  的两边都需要追加一个 `|` 不然表格会不完整|
    我是一个很随性的表格||再见
1. 代码块
    ```sql
        select *, b.`complete_amount`-a.total from (
        select sum(`complete_amount`) as total, `parent_id` from `subject` where `parent_id` > 0 group by `parent_id` 
        ) a join (select `complete_amount`, `id` from `subject` where `loan_id` < 0) b
        on a.`parent_id` = b.`id`
        where a.total != b.`complete_amount`
        ;
    ```

[1]: https://www.google.com
