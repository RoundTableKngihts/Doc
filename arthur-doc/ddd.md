#DDD(领域驱动设计)
>记录这个模式的原因：目前项目中有用到这个模式，之前只是听同事介绍一下，真正编写的时候有不少问题。其次，最关键的，我很讨厌被人教育说如何去用xxx，这惹到我了

##学习前的准备
>从soa的模式中跳出，不要从用户角度去考虑问题，而是从业务角度去事先生成对应的场景，供用户去使用

###领域
>其产生的原理就是由于不同行业的业务有实际应用意义（这些程序员不可能全部理解），讲这些行业的业务定义为领域可以让不同行业的专家与程序员可以跨行业的沟通。

###模型
>这是领域的内部展现方式，可以这样讲，领域的概念通过模型的方式实现，也就是说要预定义模型中相关内容的业务，而不是当用户需要某些的时候再去实现业务，当用户需要某些业务的时候应该是通过获取模型中的内容。

##