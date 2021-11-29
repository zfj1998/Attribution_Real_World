# 特征提取步骤

## 1. 数据准备

### 1.1 运行 ASTCount

1. Eclipse 打开 ASTCount
2. 修改文件夹目录(共3处)至存放Java源码文件的dir
3. 运行 ASTCount.class

> 可以忽略不管该错误 "java.nio.file.NoSuchFileException: \home\amatyukh\Desktop\datachanging\Zminify\CN17.bi"

- 共生成六种后缀的文件:
    1. *.max (max tree depth)
    2. *.nf (node frequences)
    3. *.bi (AST bigrams)
    4. *.lf (leaves frequences)
    5. *.dl (leaves depth)
    6. *.nd (nodes depth)

### 1.2 运行 Leaves

1. Eclipse 打开 Leaves
2. 修改文件夹目录(共1处)至存放Java源码文件的dir
3. 运行 Leaves.class

- 生成 *.txt(contains the parsed tree of the program) 后缀格式的文件

### 1.3 运行 vacowin.author.util

1. Eclipse打开 vacowin.author.util
2. 修改 ComVacowinAuthorUtil.java 中的文件夹目录(共1处)至存放Java源码文件的dir
3. 在Eclipse中修改Build Path, 添加 "dist/lib" 中的 *.jar 包
4. 运行 ComVacowinAuthorUtil.class

- 生成 *.com (source code with no comments) 后缀格式的文件

## 2. 特征集提取

### 2.1 Ding's 特征集

1. 进入存放Java源码文件的dir
2. 运行 `python path_to_ding/ding.py`

- 生成 results.arff (每一行是一个author的特征)

### 2.2 Caliskan's 特征集

1. 进入存放Java源码文件的dir
2. 运行 `python path_to_ding/caliskan.py`

- 生成：
  - term_freq_unigram.arff -term frequency of word unigrams in source code.
  - ast.arff -term frequency AST node bigrams.
  - keywords.arff -term frequency of keywords.
  - max_depth.arff -maximum depth of an AST node.
  - av_node_depth.arff -average depth of AST node types excluding leaves.
  - term_freq_node.arff -term frequency of AST node type excluding leaves.
  - av_depth_leaves.arff -average depth of code unigrams in AST leaves.
  - term_freq_leaves.arff -term frequency of code unigrams in AST leaves.
  - term_freq_unigram.arff -term frequency of word unigrams in source code.
  - term_fr_inv_fr_leaf.arff -term frequency inverse document frequency of code unigrams in AST leaves.
  - term_fr_inv_fr_node.arff -term frequency inverse document frequency of possible AST node type excluding leaves.
