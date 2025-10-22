知识工程：利用基于知识的系统解决特定领域问题的所有技术；人工智能的一个重要分支
知识图谱：万维网不断发展背景下最具代表性的知识工程技术
知识图谱项目：DBpedia、YAGO、Wikidata、BabelNet、知是网...
知识图谱技术：知识表征、知识推理、知识提取、知识融合、知识存储与查询、基于知识的问答等...
知识图谱应用：金融、数字图书馆、法律、出版商...
KR:knowledge representation

Knowledge Representation

Knowledge representation is to use the representation that computer can deal with
to express human knowledge.

Knowledge ==graph== representation is to use the representation that computer can deal with to express the knowledge in ==knowledge graph==.


XML（可拓展标记语言）:
存储和传输数据，描述数据内容
后端，在系统间传递数据
没有预定义的标签，语法严格
HTML（超文本标记语言）：
显示数据和布局内容，有预定义的标签



Authoring guidelines:

1. All elements must have an end tag. 

2. All elements must be cleanly nested (overlapping elements are not allowed).（正确嵌套）

3. All attribute values must be enclosed in quotation marks.（属性要加引号）

4. Each document must have a unique first element, the root node  （根结点！！）


XML命名空间：
用xmlns属性来区别同名标签；
![[Pasted image 20251009151625.png]]

==uri=url/urn==

![[Pasted image 20251009151827.png]]

XML架构：指定如何正式描述XML文档中的元素

RDF：资源描述框架
核心思想：用机器能直接理解的方式来表达信息
三元组（主，谓，宾）


sw:ChildlessPerson 
    rdf:type owl:Class ;
    owl:intersectionOf (
        sw:Person
        owl:complementOf sw:Parent)
