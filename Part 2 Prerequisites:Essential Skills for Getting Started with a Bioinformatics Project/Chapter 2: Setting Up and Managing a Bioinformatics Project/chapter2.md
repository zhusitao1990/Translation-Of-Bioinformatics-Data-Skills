#第二章 建立和管理生物信息学项目

    正如一个组织良好的实验室使科学家的生活更轻松一样，一个组织良好、记录充分的项目也使生物信息学家的生活更轻松。
不管你在做什么样的项目，你的项目目录都应该以一种一致的、可理解的方式来安排。清晰的项目组织使您和合作者更容易准确
地确定所有内容的位置和内容。此外，当文件被组织和清楚地命名时，自动化任务要容易得多。例如，如果300个基因序列存储
在单独的FASTA文件中，并且这些文件被组织在一个目录中并且命名一致，那么用一个脚本来处理这些文件是很简单的。
    每个生物信息学项目开始于一个空的目录，所以本书从项目组织的一章开始是非常合适的。在本章中，一些组织你生信项目
目录的实际操作，和怎样用Markdown的方式记录你自己的工作。我们还将了解为什么项目目录组织不仅仅是为了保持整洁，而是
对于跨大量文件自动执行任务的方式至关重要。
    项目目录和目录结构
    创建一个好的生物信息项目结构是实现可复现的项目的基础。实际处理非常简单，布局一个项目只需要使用mkdir创建几个
目录，并使用touch创建空的自述文件（稍后我们将更深入地了解这些命令）。但这种简单的初步计划从长远来看是有回报的。
研究人员可以花数年的时间在这个目录中工作，其他研究者也会注意到一个好的项目组织重要性。虽然最终你会开发出一个适合
你的项目组织方案，但在本章中，我们将从我在工作中使用的方案（类似于Noble的方案）开始。
    项目中使用的所有文件和目录都应该位于具有明确名称。在一个项目的过程中，你会积累数据文件、笔记、脚本等等，如果
这些文件分散在你的硬盘上（或者更糟的是，在许多计算机的硬盘上），那么跟踪所有的东西都将是一场噩梦。更糟糕的是，这样
一个无序的项目会让你的研究变得几乎无法复制。
    将您的所有文件保存在一个目录中将大大简化您和你的合作者，以及促进可复制性（我们将讨论如何协作
在第5章中使用Git编写一个项目目录）。假设你在找寻玉米SNP。你的第一步是选择一个短的，合适的项目名
称并创建一些基本目录：
```bash
$ mkdir zmays-snps
$ cd zmays-snps
$ mkdir data
$ mkdir data/seqs scripts analysis
$ ls -l
total 0
drwxr-xr-x 2 vinceb staff 68 Apr 15 01:10 analysis
drwxr-xr-x 3 vinceb staff 102 Apr 15 01:10 data
drwxr-xr-x 2 vinceb staff 68 Apr 15 01:10 scripts
```
    这是一个明智的项目布局方案。在这里，数据/包含所有原始和中间数据数据。正如我们将看到的，
在data/，数据处理步骤被视为独立的子目录。我将一般项目需要的脚本保存在scripts/目录中。
如果脚本包含许多文件（例如，多个Python模块），它们应该驻留在自己的文件中子目录。将脚本隔离
在自己的子目录中也会保留项目目录在开发这些脚本时保持整洁（当它们生成测试输出文件时）。
    生物信息学项目包含许多较小的分析，例如，分析原始序列的质量，比对输出，以及将产生的最终
数据一篇论文的图表。我喜欢将这些分析放在一个analysis/的目录中，因为它允许合作者无需深入研
究就可以看到这些高层次的分析到子项目目录中。
    什么是名称？
    命名计算机上的文件和目录比你想象的要重要。从可视化的操作系统转移到unix命令行上来，许多
人养成了在文件名和目录名中使用空格的坏习惯。这在基于Unix的环境中不合适，因为空格用于分隔命
令中的参数。例如，假设您从GUI创建一个名为raw sequences的目录（例如，通过OS X的Finder），
然后尝试使用以下命令删除它及其内容：
```bash
$ rm -rf raw sequences
```
    如果幸运的话，会警告您raw和sequences“没有这样的文件或目录”。这是怎么回事？空间很重要：
您的shell将rm命令解释为“同时删除原始和序列文件”，而不是“删除一个名为raw sequences的文件或目录”。
    如果你不幸的有一个文件或目录原始或序列，此rm命令将删除它。有可能通过使用引号
（例如，rm-r“raw sequences”）来转义它，但是最好不要在文件名或目录名中使用空格。最好只使用字母、
数字、下划线和目录和文件名中的破折号。
    尽管Unix不需要文件扩展名，包括扩展名帮助指示每个文件的类型。例如，一个文件叫osativa-genes.fasta
很清楚这是一个序列文件以FASTA格式。相反，一个名为osativa genes的文件可以是一个基因模型的文件，关于
这些水稻基因在哪里的注释来自或序列数据。有疑问时，直截了当总是更好 在文件名、文档和正在编写代码。

    脚本和分析通常需要引用项目层次结构中的其他文件（如数据)。这可能需要指向父目录，在你的目录层级结构里面。
在这种情况下，使用相对路径是非常重要的，而不是使用绝对路径。只要你中间项目目录的结构保持一致，这些相对路径
就会一致起作用。相反，绝对路径依赖你个别用户的权限，和目录结构细节，在项目的目录层级之上。使用绝对路径会让你的
工作在合作者之间不是很方便，，会降低可复现的能力。
    我的项目目录方案绝不是唯一可能的方案。我和生物信息学家合作过，他们的项目使用完全不同的方案，并做得很好。
但是，无论组织方案如何，一位优秀的生物信息学家都将始终广泛记录所有内容，并使用可以由计算机解析的清晰文件名，
这是我们将要提到的两点。
    项目文档
    除了一个好的目录结构外，你的项目也应该有好的记录文档。差的文档会使得项目难以附复现和产生严重的问题。在
生信项目里有大量潜在的复杂文件，：复杂的工作流程，大量的文件，不可计算的参数，不同的软件版本。最好的方法来解
决复杂性造成的问题就是记录他们。当你需要回过头看看和重新分析时，文档会让变得更加容易，给文章写每一步详细的方法，
在目录中找到原始的数据。那么什么东西是你该记录的呢？下面有一些建议：
    记录方法和工作流
    你应该记录全部的命令行，包括你产生数据的和结果的。尽管你使用的是软件默认的参数，你也应该把它记录。因为新的
软件版本会使用不同的默认参数.Scripts 应该记录所有的步骤，和参数，确保记录在这个脚本中所有的命令行。一般情况下，
你工作中产生的结果的所有命令行都应该被记录。
    记录所有数据的来源
    你必学溯源所有的数据，从哪里下载？谁给的？和一些其他的相关信息。数据不仅仅指你的项目实验数据。是你程序产生结果
使用的全部数据。包括你合作者分享的文件，基因注释溯源，参考基因组，等等。记录有关您的数据或元数据的重要数据至关重要。
例如，如果你下载了基因组区间文件，你应该记录下下载的网址。这看起来是比较显而易见的建议，但是很多次，我们遇到一个分析
步骤，却很难复现，因为我门忘记记录了他的数据来源。
    记录你下载数据的时间
    记录下载数据的时间非常重要，因为那些数据会变化。例如，在数据库更新之后，你的脚本从数据库下载的数据将会产生不同的结果。
所以，记录你项目中数据下载的时间非常重要。
    记录数据版本信息
    许多数据库已经释放了多个版本，版本数，和名字。（TAIR10 就是拟南芥基因组注释版本，WS231就是线虫的版本）。在你的文档中
记录所有版本信息，包括小的版本号。
    描述怎样下载数据
    例如，你是否用MySQL下载基因？或者使用UCSC基因组浏览器？这些细节在你溯源下游分析时非常有用。
    记录你所使用的的软件版本
    这似乎不重要，但是记住之前的例子，你的合作者和你溯源没有达到共识的结果时，就是因为一个小的软件版本的变化。这些细节很重要。
好的生信软件通常有一个命令行参数返回软件版本信息。软件版本管理应该使用一个好的管理系统，例如Git，能够准确的记录每一个版本。
也能被用来记录你正在使用的软件版本。如果版本信息不可获取，发布时间，软件的链接，下载的时间就足够了。
    这些所有的时间最好储存在文本文件README中。纯文本可以很容易地直接从命令行读取，搜索和编辑，使其完美
便携式和可访问的读取文件的选择。文本也会在所有的操作系统上适用，意味着你能够在你正在工作的电脑上记录你工作路程的每一个步骤。
纯文本也缺少复杂的格式，这可能会在将文档中的命令复制并粘贴回命令行时产生问题。最好避免使用Microsoft Word for README文
档等格式，因为这些格式不易移植到生物信息学中常见的Unix系统。
    哪里需要有README文件呢？一个好的做法就是子你项目的主目录中设置README。这些自述文件不一定需要冗长，但它们至少应该解释
此目录中的内容以及它是如何到达那里的。这个小的努力可以节省很多时间探索你的项目目录，并防止混淆。在你搬到另一个实验室后，这个
人可能是你的顾问或合作者，一位同事试图复制你的工作，甚至六个月之后，你完全忘记你所做的（这会发生在每个人身上）。
    例如data/README 文件会会包括你data/下面使用的所有数据。当你想要回忆起你项目中所有数据信息时，将这些信息放在README中
是比较容易的。我们说touch 创建readme.touch 会更新文件修改时间，创建新的文件。我们使用的是touch后面的那个功能来创建空文件
放在我们的目录结构中。
```bash
$ touch README data/README
```
    遵循刚刚讨论的文档指南，data/README 包含从哪里下载的数据，什么时候下载的，怎样下载的。我们在第六章将会学习更多的的数据
的知识，我们看到怎么下载数据，怎样记录数的的例子。
    通过记录这些信息，我们就记录了实验和分析的全部信息，这样使得项目有很好的可重复性。请记住，随着您的项目的发展和数据文件的积累
，为了您自己的方便，它也可以得到回报。
    使用目录将你的项目分子目录
    生物信息学项目包含许多子目录和子分析。例如，在使用比对和组装软件之前，实验数据的质量应该被评估，低质量的区间要被移除。甚至，
在你分析序列时，你的项目目录可以用中间结果来进行聚类。
    用创建目录的方式进行子项目的分类能让复杂的项目简单化，也能组织好文件。它還有助於降低意外風險
使用錯誤的腳本破壞文件，因為子目錄有助於隔離故障。將項目分解為子項目並將其保存在單獨的子目錄中，也使記錄工作變得更加容易。
每個README都與它所在的目錄有關。最重要的就是，你会创建一个很好的项目管理为你工作。要點是：利用目錄幫助保持井井有條。
    组织数据来自动进行文件处理。
    由于自动化文件处理是生信不可或缺的部分，因此组织我们的项目来实现自动化是必须的。将数据分散到子目录中，利用简单一致的文件名
是非常重要的。这两者都会让我们更好的自动化处理文件，第一步就是自动化一个任务。自动化做一些事情，就是要让程序来执行，而不是手动。
使用可以轻松应用到多个对象的方法。与把他们全部打印出来相比，自动化处理文件是非常简单安全的。
    Shell 通配符技巧
    生物信息学家，软件工程师，系统管理员花很多时间在命令行打字。所以有一些小技巧来更快的处理这些事一点也不奇怪。如果你在shell
中花很多的时间，你会发现花一点时间来学习这些技巧会给你节约更多的时间。
    一个重要的技巧就是shell通配符。shell通配符就是在shell中找文件时不用讲其打印出来。如果你 cd ~ 进入自己的家目录，你将会使
用通配符。像星号这样的通配符（*）也會被您的shell扩展到所有匹配的文件。
    另外一个shell通配符就是括号通配符。使用一个命令，快速创建zmays/snps项目结构。括号通配就是通过在括号中创建用逗号分隔的字符串。
例子如下：
```bash 
$ echo dog-{gone,bowl,bark}
dog-gone dog-bowl dog-bark
```
    利用同样的方式，你可以创建下面的目录结构
```bash 
$ mkdir -p zmays-snps/{data/seqs,scripts,analysis}
```
    我们将会用例子来阐述每一个点，学习一些重要的shell通配符技巧。例如，组织数据目录到一个目录，使用一致的命名为我们
使用这个技巧你能够轻松的移动60个文件像6个文件一样轻松。你也可以选择特定的文件，将他们作为附件添加到邮件发送。利用一致性的命名方式和
目录结构，你能在shell和其他语言中轻松实现。
    我们会看到使用星号自动创建任务。后面再第十二章中，我们将会看到更多高级的批量处理文件的用法。
```bash
$ cd data
$ touch seqs/zmays{A,B,C}_R{1,2}.fastq
$ ls seqs/
zmaysA_R1.fastq zmaysB_R1.fastq zmaysC_R1.fastq
zmaysA_R2.fastq zmaysB_R2.fastq zmaysC_R2.fastq
```
    在命名策略方面，每个文件名有两个变量，样本变量和测序read变量。假设你想获得所有变量名有zmayB(不管是那一条read)
可以使用下面的方式：
```bash
$ ls seqs/zmaysB*
zmaysB_R1.fastq zmaysB_R2.fastq
```
    星号会匹配所有的文件和目录名（这个过程叫全局匹配），在前面的例子中，你的通配符zmaysB*匹配zmaysB_R1.fastq,匹配zmaysB_R1.fastq,
因为这两个文件是zmaysB开头的。如果你的目录中有几百个zmaysB 文件，可以用星号通配符轻松操作。
    星号和参数太长
    OS X和Windows中，限制了命令行参数的数目。当使用星号通配符匹配许多文件时候，我们有些时候超过了这个数目。一旦这些发生，你会看到参数量
太多的报错，因为你超过了这个数目。幸运的是，有一个很明智的方式处理这个（411页中，利用find和xargs）。
    一般情况下，最好是限制性使用星号。这会避免一些错误的匹配。例如，你的同事创建了一个zmaysB-interesting-SNPs-found.xls文件，当使用
zmaysB*会错误匹配。如果你想处理zmaysB FASTQ 文件，使用ZmaysB*会匹配Excel文件而导致这些问题。这就是为什么要限制性使用星号通配符。
可以使用zmaysB*fastq 或者 zmaysB_R?.fastq取代zmaysB*。

    还有其他一些简单的shell通配符，它​​們在編程上非常方便访问文件。假设一个合作者告诉你C的样本的测序质量很差，因此你只想对A，B分析，对C进行
重新测序。你在没有获得C的新样本之前，不想删除原先的文件，所以你应该忽略他。发明通配符的人意识到了这个问题，所以他们允许通配符可以匹配特定字段，
或者指定字符的范围。例如，你可以[UVWXY]或者[U-Y]匹配 U,V,W,X,Y。回到我们的例子，你可以使用如下命令匹配C之外的样本。
```bash 
$ ls zmays[AB]_R1.fastq
zmaysA_R1.fastq zmaysB_R1.fastq
$ ls zmays[A-B]_R1.fastq
zmaysA_R1.fastq zmaysB_R1.fastq
```

    使用[A-B]看起来没有必要，但是当我们有A至I这么多样本时，像zmays[C-I]_R1.fastq比打印出[CDEFGHI]_R1.fastq要方便的多。还有一个很重要的
警告就是，区间只能读字符进行操作，对数字不行。这意味着，你想使用通配符snps_[10-13].txt 它不会匹配 snps_10.txt,snps_11.txt,snps_12.txt,
和 snps_13.txt.
    但是，shell也提供了数字的解决方案。通过使用..来进行数字区间匹配。在我们看到快捷方式之前，请注意，匹配和{}匹配相似，但是又略有不同。星号匹配
存在的文件，然而..匹配时，它不管文件和目录是否存在。我们知道snps_10.txt到snps_13.txt存在，我们可以使用snps_{10..13}.txt匹配它们。这个可以
拓展到10至13的整数。
    下表就是Unix下面的通配符
    通配符  匹配的内容
    *       匹配零或任意字符（忽略隐藏文件）
    ？      匹配一个字符（忽略隐藏文件）
    [A-Z]   在两者之间的任意字符数字，[A-Z]匹配 A和Z之间的任意字符，[0-9]匹配0到9之间的任意数字

    到目前为止，我们应该看到shell通配符的作用。他们允许我们轻松处理多个文件，因为大多数生物信息日常就是
对文件的处理，以编程的方式快速获取文件会让我们的工作更加简单，消除因为打印文件名和忘记样本名带来的错误。
然而，用编程的方式使用通配符获取文件只适用于文件名高度一致的情况。尽管通配符和强大，它们在文件名不高度一致的
情况下，用处不大。例如，处理一些如下的文件，zmays sampleA - 1.fastq, zmays_sampleA-2.fastq, sampleB1.fastq,
sample-B2.fastq比较复杂，因为它们的文件名高度不一致。不幸的是，生物学中文件名普遍不一致，这也是生物信息学研究者
到处能碰到的灾难。总的来说，生物信息研究者可能已经花了上千小时来处理这些名称不一致的文件，基因。
    前置0 和排序
    另外一个技巧就是命名时使用前置0，（file-0021.txt而不是file-21.txt）。这是有用的，因为从词典学的角度来看
对文件进行排序（就像ls一样）可以得到正确的排序。例如，如果我们有诸如gene-1.txt、gene-2.txt、…、gene-14.txt
等文件名，按字典顺序对这些文件进行排序将得到：
```bash
$ ls -l
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:24 genes-1.txt
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:24 genes-11.txt
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:24 genes-12.txt
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:24 genes-13.txt
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:24 genes-14.txt
[...]
```
    但是，如果我们使用前导零（例如，gene-001.txt、gene-002.txt、…、gene-014.txt），则文件按正确的顺序排序：
```bash 
$ ls -l
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:23 genes-001.txt
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:23 genes-002.txt
[...]
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:23 genes-013.txt
-rw-r--r-- 1 vinceb staff 0 Feb 21 21:23 genes-014.txt
```
    使用前导零不仅仅在命名文件名时有用；这也是命名基因、转录本等的最佳方法。像Ensembl这样的项目在命名他们的基因时
使用这个命名方案（例如，ensg0000164256）。
    除了简化对文件的处理外，一致的文件命名是健壮的生物信息学中经常被忽视的一个组成部分。错误的样本命名方案很容易导致样本混淆。
当您或合作者认为您使用的数据是正确的，但实际上是过时的或错误的文件时，选择不当的文件名也会导致严重错误。
我保证，在过去十年发表的所有论文中，至少有几篇甚至更多的论文因为文件命名问题而包含错误的结果。
    Markdown 项目笔记
    保存一个项目笔记本是非常重要的，它包含关于你的计算工作的时间顺序的详细信息，你已经采取的步骤，关于
为什么你要做决定，当然还有所有相关的信息来重现你的工作。一些科学家在手写笔记本上这样做，而另一些科学家在
microsoftword文档中这样做。与自述文件一样，生物信息学家通常喜欢将项目笔记本保存在简单的纯文本中，因为
可以通过命令行和通过网络连接到服务器来读取、搜索和编辑这些笔记本。纯文本也是一种经得起未来考验的格式
20世纪60年代的纯文本文件在今天仍然可以阅读，而来自只有10年历史的文字处理程序的文件很难或不可能打开并编辑。
此外，纯文本项目笔记本也可以置于版本控制之下，这一点我们将在第5章中讨论。
    虽然纯文本很容易在文本编辑器中编写，但对于不熟悉命令行的协作者来说，阅读起来可能不方便。一种称为Markdown
的轻量级标记语言是一种易于阅读和轻松合并的纯文本格式，也可以呈现为HTML或PDF格式。
    MarkDown源于纯文本电子邮件中使用的简单格式约定。早在HTML潜入电子邮件之前，电子邮件就被简单的强调标记、
列表和文本块加以修饰。随着时间的推移，这已成为事实纯文本电子邮件格式方案。这个方案非常直观：文本旁边的下划线
或星号表示强调，列表只是以破折号开头的文本行。
    Markdown只是纯文本，这意味着它是可移植的，编辑和读取它的程序将存在。任何用旧版本的文字处理器写笔记或论
文的人都可能熟悉共享或更新过时的专有格式的麻烦。基于这些原因，Markdown使得笔记本格式变得简单而优雅。
    Markdown基本格式
    Markdown的格式化功能符合生物信息学笔记本的所有需求：文本可以分解成层次结构，代码块和内联代码都有语法，
而且很容易嵌入链接和图像。虽然MarkDown格式非常简单，但有一些不同的变体。在我们的例子中,我们将使用原始的MarkDown
格式，由约翰·格鲁伯发明.下面是一些MarkDown的基本语法。

# *Zea Mays* SNP Calling
We sequenced three lines of *zea mays*, using paired-end
sequencing. This sequencing was done by our sequencing core and we
received the data on 2013-05-10. Each variety should have **two**
sequences files, with suffixes `_R1.fastq` and `_R2.fastq`, indicating
which member of the pair it is.

## Sequencing Files
All raw FASTQ sequences are in `data/seqs/`:
$ find data/seqs -name "*.fastq"
data/seqs/zmaysA_R1.fastq
data/seqs/zmaysA_R2.fastq
data/seqs/zmaysB_R1.fastq
data/seqs/zmaysB_R2.fastq
data/seqs/zmaysC_R1.fastq
data/seqs/zmaysC_R2.fastq
## Quality Control Steps
After the sequencing data was received, our first stage of analysis
was to ensure the sequences were high quality. We ran each of the
three lines' two paired-end FASTQ files through a quality diagnostic
and control pipeline. Our planned pipeline is:
1. Create base quality diagnostic graphs.
2. Check reads for adapter sequences.
3. Trim adapter sequences.
4. Trim poor quality bases.
Recommended trimming programs:
- Trimmomatic
- Scythe

    图2-1显示了Pandoc在HTML5中呈现的MarkDown笔记本示例。Markdown是一种很好的实验室笔记本格式，它同样易于阅读
在呈现的HTML中未呈现的纯文本。接下来，我们来看看MarkDown本例中使用的语法（参考表2-2）。
    MarkDown 行中的语法
    Markdown语法    结果
    *emphasis*      emphasis      # 强调
    **bold**        bold          # 加粗
    `inline code`   inline code   # 内链编码
    <http://website.com/link>   Hyperlink to http://website.com/link  #超链接网页
    [link text](http://website.com/link)    Hyperlink to http://website.com/link, with text “linktext”  # 使用字符来超链接网页
    ![alt text](path/to/figure.png)     Image, with alternative text “alt text”
    像标题，列表，代码块是比较简单的。不同层级的标题用行前面的#的个数区分。例如
    # Header level 1
    ## Header level 2
    ### Header level 3 
    MarkDown的标题最多使用6级。也可以使用另外一种语法表示两级标题：
    Header level 1
    ==============
    Header level 2
    --------------
    有序和无序的列表也很简单。对于无序列表，请使用破折号、星号或加号作为列表元素标记。例如，使用破折号：
    - Francis Crick
    - James D. Watson
    - Rosalind Franklin
    要排序，只需使用数字（即1、2、3等）。排序并不重要，因为HTML会自动为您增加这些值。但是，清晰地编号
您的要点仍然是一个好主意，这样纯文本版本是可读的。
    代码块非常简单，只需在每行代码前添加四个空格或一个制表符：
    I ran the following command:
        $ find seqs/ -name "*.fastq"
    如果要在列表项中放置代码块，请使用八个空格或两个制表符：
    1. I searched for all FASTQ files using:
        find seqs/ -name "*.fastq"
    2. And finally, VCF files with:
        find vcf/ -name "*.vcf"
    我们这里介绍的应该足够你去开始记录的你的生信项目。此外，还有MarkDown的扩展，比如MultiMarkdown和GitHub Markdown。
这些变体会添加功能并更改某些默认渲染选项。如果您喜欢基于GUI的编辑器，还有许多专门的MarkDown编辑应用程序。

    使用Pandoc将Markdown呈现为HTML
    我们将使用流行的文档转换器Pandoc将我们的MarkDown文档呈现为有效的HTML。然后可以与这些协作者共享这些文件，
在网站上托管。有关如何操作的说明，请参见Pandoc安装页面在系统上安装Pandoc。
    Pandoc可以在各种不同的标记和输出格式之间进行转换.使用Pandoc很容易将Markdown转换为HTML，使用--from 
Markdown和--to HTML选项并将输入文件作为最后一个参数：
    $ pandoc --from markdown --to html notebook.md > output.html
    默认情况下，Pandoc将输出写入标准输出，我们可以将其重定向到一个文件（我们将在第3章中了解有关标准输出和重定向的更多信息）。
我们还可以使用--output指定输出文件输出.html.最后，请注意Pandoc可以在多种格式之间进行转换，而不仅仅是将Markdown转换为HTML。
在本章的GitHub自述中，我还提供了更多的例子，包括如何从HTML转换成PDF。
