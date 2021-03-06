# *Translation-Of-Bioinformatics-Data-Skills*

# 第一章 怎样学习生物信息学

&ensp;&ensp;当前，世界上的实验室正在测序地球上所有生物的基因组。尽管测序的成本快速下降和巨大的
科技进步，我们仅能看到的每个细胞，组织，器官和生态系统的生物信息。然而，大量的生物信息的数据被收
集后，就需要生物学家来解析。在人类历史上，我们了解生命复杂性的能力依赖于我们分析数据的能力。本书
就是通过开发数据的技巧来学习生物信息学。 在本章中，我们将看到什么是数据技巧，为什么学习数据技巧是
学习生物信息的最好方式。我们还将关注什么是可靠可重复性的研究需求。

## 为什么是生物信息学？生物学的数据不断增长
&ensp;&ensp;生物信息学家关注使用特定的技巧和工具从大量数据中或得生物学理解。在生物学的历史早期，
数据集非常小且容易管理。在学过一些统计学的课程后，大多数生物学家能够使用EXCEl在个人笔记本上进行数
据分析。然而，现在的变化已经天翻地覆。大量的测序数据被广泛应用，在未来会变得更加普遍。分析这些数据
需要不同的工具和技巧，需要电脑有大的内存，计算能力和磁盘空间。
&ensp;&ensp;在一个相对短的时间里，测序价格急速下降，允许研究者利用测序数据来回答重要的生物学问题。
早期的测序通量低，成本高。全基因组测序的价格更加昂贵（人类基因组花27亿美元）而且只能通过大量的合作
才能完成。自从人类基因组的发布，测序的价格呈现指数的下降趋势，如图1.1所示。随和下一代测序技术的应用，
GB级的DNA测序成本急速下降。在这个关键时期，测序，只有大型协作才能负担得起的测序工作，成为所有生物学
研究领域的研究人员都能承受得起的。你读本书来学习处理测序数据，这些测序数据的成本比10年前便宜的多。
&ensp;&ensp;测序技术中测序成本的下降会导致什么结果呢？正如你所想，大量的数据。测序数据指数级增长后
的结果导致生物学数据库的激增。然而以前小的数据库研究者之间共享就足够使用，现在在全世界的服务器上坐拥
PB级的数据。生物学问题的关键，不仅仅储存在本地磁盘未经分析的试验数据上，而且还在千里之外的数据中心的
磁盘上。
&ensp;&ensp;生物数据库的增长与测序成本的下降一样惊人。例如，the sequence Read Archive, 一个原始
的测序数据库。到2010年，他经历了显著的增长，如图1.2。
&ensp;&ensp;上面的增长符合摩尔法则。戈登，摩尔（因特尔的创始人之一）观察到，计算机芯片中的晶体管数量
每2翻一番。每块芯片中更多的晶体管会加速电脑的计算和随机访问内存的能力，从而产生更强的算力。这种非凡的技
术速度改进-产出每两年翻一番-可能是最快的增长人类从未见过的技术领域。然而，自2011年以来，测序数据量短读
档案中存储的数据甚至超过了这一令人难以置信的增长，每年翻一番。

&ensp;&ensp;使得事情变得更加复杂的是，分析数据的新工具被开发，但是他们的基础算法一直在进步。2012年的
一篇综述列出了超过70种的短序列比对软件。然而，在过去五年，我们组装基因组的方法变化非常大，长序列组装方法
由于短reads的出现而被抛弃。现在，新的长reads的测序技术的出现，使得新的算法又开始取代几年的算法。

&ensp;&ensp;不幸的是，生物信息工具的快速和冗余的开发带来了一些严重的问题。通常，生物信息工具。通常生物
信息工具没有所谓的基准线，通常是在某个组织中是基准的。这种情况就对新的生物学家选择工具去分析他们的数据造
成困难。更为严重的是，一些生物信息学的程序没有开发好，导致程序本身缺少联系和带有一些BUG从而对分析产生负向
的结果。所有的这些让你在分析数据时选择合适的程序带来困难。更为严重的是，这些将不可避免地去评估软件在你数据
上产生的结果。在第二部分，我们将会一些数据处理的技巧帮助我们评估产生的结果。

## 学习数据技巧来学习生物信息学
&ensp;&ensp;在生物学的数据变化迅速的特性下，如何学习生物信息学呢？在大量生物学软件和真在大量被开发的软
件的前提下，生物学家怎样确定一个程序是否能够正确分析自己的数据呢？
&ensp;&ensp;解决方案就是做一个生物信息人员该做的，大量尝试,然后评估结果。通过这种方式，生物信息学就是
具备利用计算机去给数据做实验的能力，然后弄懂自己的数据。实验部分很简单，这对于所有的科学家来说
是自然的。对所有生物学家限制的因素是数据处理的技巧。本书的目的就是教你必须的生物信息数据处理技
巧让你更好的使用电脑处理实验室产生的数据。

&ensp;&ensp;不幸的是，很对生物学家的计算工具不能够处理现代生物学数据，在数据大小和复杂性上都能以胜任。复杂的
数据格式，多种交互性程序，评估软件和数据让大量的生物学数据难以处理。学习核心的生物信息学处理技巧，
能让你有基础去学习，使用和评估生物信息学程序和分析方法。在过去十年中，生物信息学家使用了很少的生
物信息学软件。但是，我们将会利用数据使用技巧和实验来评估数据和方法。

&ensp;&ensp;那什么是数据技巧？它们是一些能够让你快速查看复杂数据的数据处理技巧的集合。一个很好的比喻就是
爵士乐音乐家所说的拥有“排骨”.有着高超技艺的爵士音乐家可以走进夜总会，听到一首熟悉的标准歌曲被演奏
时，识别和弦的变化，并开始播放音乐的想法这些和弦。同样，一个拥有良好数据技能的生物信息学家可以收到
对数据集进行排序，然后立即开始使用一组工具来查看数据表明。
&ensp;&ensp;就像一个精通乐器的爵士音乐家，一个优秀的生物信息学家数据掌握了一套工具。学习一个工具是必须额的
，但是这不做够掌握开发数据技巧的能力。（类似的，学习乐器很容易，但是不足够演奏音乐）。通过这本书，
我们将开发我们数据的技巧，通过建立生物信息学项目和数据在第二部分内容中。学习一些小的和大的工具在第
三章。然而，本书只能让你找到正确的方向，精通学习通过重复的运用数据技巧到真正的问题上。

## 对于可重复性和健壮研究的新挑战

&ensp;&ensp;生物学越来越多地使用大型测序数据集，这比我们需要的工具和技能要大得多。它也改变了我们的科学发现
是多么的可重复性和健壮性。当我们采用新的软件和技巧来分析基因组学数据时，也必须保证我们方法在其他实
验条件下的可重复性和健壮性。不信的是，在基因组学中，我们巨大的数据和复杂的分析流程让这个目标难以实现。
&ensp;&ensp;重复性的必要条件是我们共享我们的数据和方法。在基因组学早期，这个很容易实现。文章要包含方法的细节
和整个数据集，例如Kreitman’s在1986年的文章中分享了Adh基因的4713bp的基因侧翼序列。现在文章有很长的
附件方法，代码，数据。分享数据不再是琐碎的，因为测序项目通常会包括TB级别的数据。参考基因组，注释数据集，
在分析中通常会实时更新，这让可重复性非常棘手。杂志中的附件材料，方法和数据链接的失效，网站上的材料会随着
人员的移动和更新而消失，当开发者再更新代码时软件版本越来越旧。通过这本书，我们将会看到在怎样做来提高项目
的可重复性。我相信这些将会是很必要的补充。

&ensp;&ensp;此外，生物信息学分析的复杂性会导致研究结果容易出现错误和技术混淆。相当常规的基因组项目会使用许多不同的
程序软件，复杂的参数输入，许多样本和注释数据集。此外，项目也会分散在服务器和工作站上。所有的这些计算机操作步
骤生成的结果将会运用到更高层面的分析上进而得到我们的生物学结论。最终的结果是，研究结果可以建立在一个由无数处
理步骤组成的摇摇欲坠的支架上。让事情变得更糟的是，生物学流程和分析通常运行一次来发表，后面就不再运行和测试。
这些分析依赖特定的软件版本，导致在其他系统上难以重复实现。在学习生物数据处理技巧时，有必要学习再现性和重复性
的实践。下面我们来依次看看再现性和健壮性。


## 可重复性研究

&ensp;&ensp;再现性科学发现是确认其准确性的唯一途径，而不是单一实验或分析的产物。卡尔·波普尔，《科学的逻辑》这一发现有
一句名言：“不可复制的单一事件没有意义对于科学”。实验和分析的独立重复性是评价科学发现正确性的黄金标准。不幸的是
大多数测序实验太昂贵导致难以从实验中重复，所以我们越来越依赖体外的试验。生物信息学项目的复杂性通常会破坏可重复性，
所以作为一个好的科研人员我们必须使体外试验的可重复性更加容易。我们稍后会看到，采用好的再现性实践也可以让你作为一个
研究者的生活更轻松。

&ensp;&ensp;因此，什么是一个可重复的生信项目。至少，我们能够分享我们的代码和数据。大多数杂志和基金代理需要你分享你的项目数据，
提供NCBI Sequence Read Rrchive, SRA项目编号。现在编辑和审稿人通常会建议项目的代码要共享，特别是代码是你项目结果
中重要的一环。然而，还有很多我们要做和需要做的来保证我们项目的可重复性。通过复现生物信息学分析来验证结果，我们已经从这
写联系中得知，真理就在细节当中。
&ensp;&ensp;例如，同事和我就曾经很难复现我们之前RNAseq差异分析的结果。我们几周前分析一些样本得到了一个初步的结果，出乎我们意
料的是，我们目前分析的产生了非常小的差异基因集。在我们检查我们之前的结果后，比较数据版本，文件创建时间，分析代码的差异，
我们仍然难以找出问题的所在。不能解释我们两次不同结果之间的差异。最后，我们检查了R软件包的版本，发现它在我们服务器上更新
了。我们重新安装了老的软件版本，发现了差异的原因，确实就是它。这里的教训就是经常复制，不管是自己还是其他人，信任的不只是
数据和代码，也包括软件版本的细节，数据下载的时间和版本。这些海量的数据，数据的数据，是非常重要的细节，是保证可重复性的
关键细节。
&ensp;&ensp;另外一个然我们学习生信可重复性的原因就是所谓的“公爵传奇”。在杜克大学，Potti和其他研究人员创造了一种方法利用高通量
芯片的表达量数据来检测和预测不同化疗药物的反应。这种方法是新的个性化药物的开端，用于医疗上病人采用哪种方式。然而，两个
生物统计学家Keith和Kevin，在他们复现这篇文章中的结论时候，发现了文章中的致命缺陷。这里需要的是两位命名的辩证生物信息学。
复现文章中的发现，当没有足够的文档来支持溯源时候。总之，他们发现了多个致命错误，如下：
* 这是一个错误，因为基因表达值的整个列表被向下移动与正确的标识符相关。
* 使用的微阵列中没有两个生物学意义上的异常基因。
* 治疗与微阵列运行的日期存在混淆。
* 样本名混淆了。
* 他两的工作是做好的总结关于开放性的文章。
&ensp;&ensp;从细胞系获得化学敏感性：辩证生物信息学和可重复性高通量生物学研究。两位工作给的教训就是“平常的错误很简单，简单的错误很平常”
稳当的缺乏会导致错误和难以复现。方法，数据版本和代码的文档不仅仅要有可复现性，也要阻止文章中一些致命错误的出现。
对最大可重复性的追求也会让你的项目更加健壮。

## 健壮性研究和生物信息学的黄金标准

&ensp;&ensp;由于电脑是一个足够锋利的工具，你可以用它来割伤自己。

&ensp;&ensp;在湿试验的生物学中，当实验失败时，它就会很明显，但是在计算机中就不是这样的。电泳凝胶看起来像罗夏斑点
比整齐的带子清楚地表明出了问题。但是在科学计算中，错误通常很不明显。代码和程序能够产生输出，但是这个输出
可能不是正确的。当你学习生物信息学时，这是一个非常重要的概念。
&ensp;&ensp;此外科学计算通常只运行一次，当研究者得到他们想要的结果后，就进行下一步操作了。相反，一个视频游戏，它
会在不同的机器上测试上千次，同时也会让不同的使用者测试。如果一个BUG会导致用户的分数被删除，会被快速的发现
然后报告给使用者。不幸的是，这些大多数生物信息项目没有做到。
&ensp;&ensp;基因组学对健壮性研究提出了挑战。第一，大多数生物信息学分析产生的中间结果非常大，很难查看和可视化。很多
分析包括很多步骤，如果每步的中间结果能被查看，但是很难做到每一个步骤都这样操作。第二，在湿实验室中，通产有一个
关于实验结果都会有一个猜想。例如，研究者期待看到特定的MRNA在某个组织中低丰度表达和看家基因相比。在这些猜想的背景下，
异常结果可归因于试验失败，而非生物学。相反，基因组的高纬度使得实验结果不会像人们预期的一样。对通过RNA序列实验分析的
成千上万个基因中的每一个基因的表达形成特定的先验期望是不切实际的。不幸的是，没有这些先验的猜想，从不好的结果中区分好的
结果变得非常困难。
&ensp;&ensp;生物信息学家通常会谨慎选用的生物信息学工具，甚至是大社区审核的工具像比对工具，组装工具，但是在特定组织上也可能
不起作用。组织是奇妙的，不同的，但是他们的基因组相同。许多生物信息学工具都是在一些二倍体生物（如人类）上进行测试的，
而在生命树其他部分的复杂基因组上却没有得到很好的测试。难道我们期望比对到人类基因组上的大量的短reads所使用的大量参数能对4
倍于人类基因组的多倍体物种适用吗？显然不行。
&ensp;&ensp;确保所有的事运行正常的就是使用谨慎的态度，检查计算的每一步。此外，你也应该对生物学数据保持怀疑的态度，因为他可能出错。
在计算机中，这个和一个错进错出的概念相关，分析的好坏取决于输入数据。
&ensp;&ensp;永远不要相信你的工具和数据
这不是让你认为生物信息学不可信，而是必须在你的数据上测试每一个程序和参数。这是训练你成为一个严谨软件工程师和生物信息分析人员
的必经之路。简单检查输入数据和中间结果，运行的完整检查，保持正确的控制，测序程序是一个好的开始。这也会减少你后面遇到的bug,
修复bug意味着你重复做了大量的工作。你本能的会测试是否实验技术正常执行，给出固定结果。采取健全的学习方法学习生物信息就是做相
同的工作。

## 采取健全的可重复性的训练会让你的生活变得更加简单

&ensp;&ensp;从事科学研究会让我们中很多人学到一些艰难的生活事实。就像墨菲定理，每件事都会出错。生物信息学也如此。在这个领域进行工作，
和同行们讨论一些故事，我们试着保证下面的将要发生。
&ensp;&ensp;你必须尝试着多次运行自己的流程，也可以尝试新的和变化的数据。这些会经常发生，因为你会遇到bug,合作者会添加和更新文件，你可
能会尝试一些上游的步骤。不管在哪种情况下，下游分析依赖着前面的结果，意味着所有的分析步骤都要重新运行。
&ensp;&ensp;在未来，你（或者你的合作者，或者顾问）几乎肯定需要重新审视一个项目的一部分，它看起来完全是神秘的。你唯一能做的就是回去看文
档，没够关键步骤的信息的话，你会忘记如何操作。记录你的计算步骤和记录实验记录本一样，是科研中相当重要的一个环节。
&ensp;&ensp;幸运的是，采取这些练习会让你的项目具有可重复性，也会帮助你解决很多问题。在一定意义上，生物信息学中好的练习会让你的项目具有
可重复性，会让你的生活变得更加简单。原因就是简单，如果你项目的每个步骤都能被复现，而且都被记录好，那么你的项目就会变得具有很好的
可重复性。
&ensp;&ensp;例如，我们用程序自动执行一些任务，记录输入数据和软件版本，使用键盘我们就能重现这个分析。重现所有的步骤是非常简单的，因为好
的脚本会记录分析步骤。这种方式会节约很多时间，，如果你收到了新的数据和更新的数据，你必须用新的数据重现脚本。在实际中这很难实现，
脚本不难写，计算机擅长做重复新的工作。

## 稳健性研究的建议

&ensp;&ensp;稳健的研究主要是采用一系列的实践，这些实践将有利于你的几率叠加起来，即一个无声的错误不会混淆你的结果。正如上面提到的，如上
所述，除了防止可怕的无声错误外，大多数这些实践也是有益的。这是所有更多的理由包括在你的日常生物信息学工作中应用下面的建议。

### 关注实验设计

&ensp;&ensp;稳健性研究开始于好的实验设计，不幸的是，没有哪个好的研究会有一个不好的实验设计。引用一个著名的统计学家和遗传学佳的话：
&ensp;&ensp;实验结束后咨询统计学家，往往只是要求他进行尸检。他也许能说出实验失败的原因。--R.A. Fisher
&ensp;&ensp;将这句话记在心中。在花费了数千美元的测序费用之后，我见过项目落在我桌上准备分析，，他们却一无所获
到达。好的实验设计不会很困难，但从根本上来说一个统计学的话题这不在这本书的范围之内。我之所以提到这个话题，是因为不幸的是，本书中
没有其他任何东西可以拯救一个设计糟糕的实验。实验设计在研究中最为重要。
&ensp;&ensp;大多数统计学导论课程和书籍基本覆盖了实验设计。Experimental Design and Data Analysis for Biologists 2002是关于这个
话题非常优秀的书籍。Chapter 18 of O’Reilly’s Statistics in a Nutshell, 2nd Edition也是一个很好的参考。不过，请注意，
基因组学实验中的实验设计是另一回事，正在积极研究和改进。确保你的几千美元的实验能够发挥其潜力的最好方法是看看你的特定项目目前的最佳
设计实践是什么。当任何实验设计问题或你在计划实验时的顾虑，咨询你当地友好的统计员是一个好主意。

### 给人写代码，给计算机写数据

&ensp;&ensp;调试的难度是编写代码的两倍。因此，如果您尽可能聪明地编写代码，那么根据定义，您不够聪明，无法调试它。--布莱恩·柯林汉
生物信息学项目包含大量的代码，我们最好的解决bug的方式就是写代码给人看，而不是给计算机。人才是来检测bug的，所以写简单的、
清楚的代码会让debug更加容易。
&ensp;&ensp;代码应该是易读的，能模块化，再现使用的能力强。在软件工程领域相当重要，所以在生物信息学领域也应当遵循。代码注释和采用
引导风格会增加代码的可阅读能性。谷歌公布了很多语言的代码风格https://github.com/google/styleguide，可以作为非常优秀
的模板。为什么代码的可阅读性如此重要。首先，阅读性强的代码让项目变得更容易复现，因为别人能够容易的读懂你的代码和代码所进行的
操作。第二，好的注释信息比凌乱的注释信息，更容易的发现改正软件的错误。第三，如果有一个好的注释，后面再回来看代码时会变得更加
容易。写模块化和可复用的代码，我们在本书中会看到一些例子。
&ensp;&ensp;与代码相反，数据是应该以某种格式被计算机读取。作为人类，我们记录数据的方式往往能最大限度地提高数据的可读性，但在数据被计算机
处理之前需要大量的清理和整理。计算机可读的数据（和元数据）越多，我们就越能利用计算机处理这些数据。

### 让你的计算机为你工作

&ensp;&ensp;人类做一些死记硬背的工作经常会出错。最简单的方法让你的工作变得稳健就是让计算机给你做这些事。这种自动化任务的方法更健壮，
因为它减少了您犯一个小错误的几率，例如意外地忽略了一个文件或错误地命名输出。
&ensp;&ensp;例如，通过分别键入（或复制和粘贴）每个命令来在20个不同文件上运行程序是脆弱的–犯了粗心的错误的几率
随着您处理的每个文件增加。而不是粘贴相同的命令20次，而只是更改输入和输出文件，写一个脚本来完成。这不仅更容易，
而且不太可能导致错误，但它也提高了可重复性，因为脚本可作为您对每个文件所做操作的参考。
&ensp;&ensp;要利用自动化任务的好处，在组织项目，数据和代码时需要考虑一些思想。简单的习惯，例如以一致的方式命名数据文件
计算机（而不仅仅是人类）可以理解的信息可以极大地促进自动化任务并使工作更加轻松。

### 在你的代码和方法中断言

&ensp;&ensp;当我们编写代码时，往往对数据有隐藏的假设。例如，我们希望只有三个DNA链的选项，正链，负链和未知。或者基因的
起始位置小于终止位置，或者不能有负的位置。这些隐含关于的数据的假设会影响我们写的代码。例如，我们不会想到处理我们认为
不会发生的情况。不幸的是，这会让我们产生致命的隐藏错误。我们的代码和程序接收我们意料之外的值，仍然有返回值而不报错。
我们最好的方法阻止这类错误就是明确状态，测试我们的假设，在代码中使用断言的申明，像Python 中的 assert()和R语言中的
stopinfo().
&ensp;&ensp;几乎每种编程语言都有自己的断言函数。这些断言函数都有相同的操作。如果返回错误，则断言函数就会中断程序，抛出错误。
这些似乎简单，但是这些断言在稳健性的研究中必不可少。早期，一个导师告诉我要采取使用断言的习惯，我一直惊讶于有多
少次这些都发现了一个细微的错误。在生物信息领域，我们尽可能的将隐藏的错误打印出来是至关重要的。

### 测试代码，最好是让代码测试代码

&ensp;&ensp;软件工程师是一个聪明的分支，他们有一个想法就是让计算机做工作达到一个新的水平。一个方式就是他们使用代码测试代码。
而不是自己手动来做这个。一个常用的测试代码的方式就是单元测试。在单元测试中，我们把代码分成若干个子部分，然后写而外的代码
来测试他们。在实践中，意味着好像我们有一个函数add(),,test_add()函数使用特定的输入执行add()，判断它的输出是否符合预期。
在Python中，看起来好像是：
```bash
EPS = 0.00001
def add(x,y):
    """Add two things together"""
    return x+y
def test_add():
    """Test that the add() function works for a variety of numeric types"""
    assert(add(2,3) == 5)
    assert(add(-2,3) == 1)
    assert(add(-1,-1) == -2)
    assert(abs(add(2.4,0.1) - 2.5) < EPS)
```
&ensp;&ensp;最后一行test_add()函数和其他相比看起来非常复杂，因为它在比较浮点数值。在计算机上比较浮点数值非常复杂，因为存在
表示和舍入的差别。然而，这是一个很好的提醒，我们总是受到我们的机器所能做的事情的限制，我们必须在分析中注意这些限制。
&ensp;&ensp;单元测试在科研编码中使用的比工业软件中要少。实际上科研编码通常含有很多的bug(因为我们的代码跑一次生成了结果就发表了
，所以代码中隐藏了很多错误)。我认为这就是科研编码的潘多拉之盒，科研编码自带bug的属性，意味着我们要比工业界使用更多的测试，
但是我们实际上做的更少。这非常遗憾，因为现在很多的科研结论来来自于大量这样的代码。
&ensp;&ensp;尽管测试代码是最好的方式发现，修复和阻止软件的bug,测试却不便宜。测试代码让我们的结果更加健壮，但是需要占用我们大量的
时间。不幸的是，测试每个代码单元也会花费大量的时间。科学发展迅速，在编写和执行单元测试所需的时间内，你的研究可能会过时或被
淘汰。一个更明智的策略是每次编写一段代码时考虑三个重要的变量：
* 这个代码多少次被其他的代码调用？
* 如果这个代码错误，对最终结果会有多大的危害？
* 如果发生错误，会有多明显？
&ensp;&ensp;测试代码的重要性和前两个变量成正比，和第三个变量成反比。我们将使用这个策略贯穿整本书。

### 尽可能的使用现存的软件包

&ensp;&ensp;每个初出茅庐的程序员都可有这样一个转折点，他们写代码和思考会觉得很舒适。为什么要用这个库呢，我自己写的比它还要简单。
这是一个很振奋的感觉，但是有更多的原因使用一个现存的包。
&ensp;&ensp;现存的开源的包和你自己写的相比有两个优势。长的历史和广泛的受众。这两个优势意味着更少的bug.软件中的bug类似于大海捞
针这一众所周知的问题。如果你写自己的库，就像一个人在大海里捞针。相反，开源的软件包意味着有更多的人，花更多的时间在大海里
捞针。因此，开源软件包里面很多bug都被发现、报道和修复。
&ensp;&ensp;这方面的一个很好的例子是在编写脚本将核苷酸翻译成蛋白质时出现的一个潜在的微妙问题。大多数有一些编程经验的生物学家都能
比较容易的写出这个脚本。但是这个简答的程序隐藏着你意想不到的复杂性。序列中的Ns是什么？Ys?Ws?，Ns,Ys，Ws可能是一些不正常
的序列。更具IUPAC的标准，这些序列是非正常的核苷酸。在很多情况下，这个软件包已经发现和解决了这些隐藏的问题。

### 对待数据只能读

&ensp;&ensp;许多科学家花了大量时间使用Excel，不费吹灰之力就能改变单元格中的值并保存结果。我强烈反对这样修改数据。
相反，更好的方法是将所有数据视为只读，只允许程序读取数据并创建新的、单独的结果文件。
&ensp;&ensp;为什么把数据视为只读对生物信息如此重要。首先，原地修改数据会导致坏的结果。例如，假设你写了一个程序直接
修改一个文件，中途产生大量的中间文件，你的程序会报错和崩溃。因为你修改了原始文件，这个做是不允许的。基本上，
你的文件会被破坏，以后都不能使用。
&ensp;&ensp;第二，当我们原地修改文件时，我们就会会很难追踪我们是怎么修改文件的。不像工作流程，每个输入输出都是一个文件
，原地修改文件不会给我们任何指示。如果我们难以溯源文件是如何被修改的，同时我们也没有原始文件的备份，我们的操作
基本上就是难以重现的。
&ensp;&ensp;对于熟悉在Excel中广泛工作的科学家来说，将数据视为只读似乎有悖常理，但这对于稳健的研究至关重要。最初的困难
是值得的；除了保护数据不受损坏和不正确的更改之外，它还可以促进可重复性。此外，分析的每一个步骤都会很容易实现，因为
输入数据没有被程序改变。

### 将常用的脚本开发成工具

&ensp;&ensp;通过开发成为一个高级的生物信息研究人员，你必须不再写一些重复写的代码。这些代码可能是你从数据库中下载，处理特定的
文件，或者是仅仅生成一些好看的图。这些脚本能够分享给团队里的其他成员，或者是跨实验室分享。你应该花而外的时间和精力把这些
经常使用的和分享比较多的脚本变得越来越健壮。在实践中，我认为这个过程是将一次性脚本转换为工具。
&ensp;&ensp;和脚本相比，工具被设计来一次次运行。他们有很好的注释文档，有明确的版本，有容易理解的命令行参数，保存在共享的存储库中。
这看起来似乎只有微小的差异，但是健壮性研究就是做这些小事，让你避免研究中出错。根据定义，反复应用于大量数据集的脚本会影响更
多的结果，因此应该对其进行更深入的开发，使其更加健壮和用户友好。尤其是与其他研究人员共享的脚本，他们需要能够查阅文档并将工
具安全地应用于自己的数据。尽管，开发工具和写脚本相比是一个劳动集约型的过程，在这个过程中你会节省很多时间，避免很多麻烦时刻。

### 让数据证明它是高质量的

&ensp;&ensp;当生物学习分析数据时，他通常会考虑分析实验数据来得到生物学结论。然而，为了执行健壮性的生物信息学工作，我们实际上需要分析
的不仅仅是实验数据。它包括检查，分析实验数据的质量，生物信息程序的中间结果，可能是模拟测试数据。做这些事为了确保数据分析过程如
我们期望的进行，体现遵守生物信息的黄金法则，不要相信你的工具和数据。
&ensp;&ensp;永远不要假设你的数据是高质量的。而是，数据质量应该通过数据分析来被验证。EDA不复杂也不花时间，将使你的研究更强大，以隐藏
在大数据集中的惊喜。我们将在第八章R语言中学习EDA.

## 可重复性研究的建议

&ensp;&ensp;采取可重复性研究不会花太多的时间，想健壮性研究一样，可重复性方法会极大的然你的生活简单，即使在你忘记了细节，但是也能够重现
你之前的工作。下面是让你的研究更加可重复的一些建议，

### 释放你的代码和数据

&ensp;&ensp;对于再现性，绝对的最低要求是代码和数据被发布。没有可用的代码和数据，你的研究是不可复制的（参见彭，2001年的一个很好的讨论）。
我们将在本书后面讨论如何共享代码和数据。

### 记录所有内容

&ensp;&ensp;科学家走进实验室的第一天，他们被告知要保存一本实验室笔记本。很遗憾，在计算机领域,这个常常被研究人员抛弃。
释放代码和数据是再现性的最低要求，但是大量的文档是也是再现性的重要组成部分。为了完全重现研究，每一步分析的描
述必须写在文章中。因此，附加文档对于再现性是必不可少的.
&ensp;&ensp;一个好的习惯就是在READEME中记录每一个分析步骤。像实验室记录本一样，好的文档是每个步骤有价值的记录。文件
在哪里，它们来至于哪里，他们包括什么。文档可以和项目数据和代买一起存储，这会帮助实验室人员发现你做了什么。文档应
该包含所有软件的参数，程序的版本，怎么运行。现在的软件像R的knitr 和 IPython Notebooks是非常好的工具进行文档
记录。我在Github上本章的README中列出了这些工具的使用。

### 使用脚本画图和统计

&ensp;&ensp;确保一个科学项目的可复制性不仅仅涉及关键统计测试的可复制性，这些测试对支持论文内容的研究结果很重要
（如图和表）也应是可复制的。确保这些组件是可复制的最好方法是让每个图像或表都是一个或多个脚本的输出。
&ensp;&ensp;编写脚本来生成图像和表格似乎比在Excel或R中以交互方式生成图像和表格更耗时。但是，如果您曾经在更改之
前的步骤后必须手动重新生成多个图形，那么您知道这种方法的优点。可以轻松地重新运行生成表和图像的脚本，节省
你的时间，让你的研究更具重复性。像iPython笔记本和knitr（在上一节中提到）这样的工具也可以极大地帮助完成这些任务。

### 将代码用作文档

&ensp;&ensp;对于复杂的处理管道，最好的文档通常都有很好的文档记录代码。因为代码足以告诉计算机如何执行程序（以及使用哪些参数），
这也足以告诉人类如何去做复制您的工作（其他信息，如软件版本和输入数据也必须是完全可复制的。在许多情况下，编写脚本来执行
分析的关键步骤比输入命令然后在其他地方记录它们要容易得多。同样，代码是一件很好的事情，使用代码来记录分析的每一步意味着
很容易重新运行分析的所有步骤，如果需要，只需重新运行脚本即可。

### 持续提高生物信息学数据技巧

&ensp;&ensp;当你阅读本书的其他部分时，把本章介绍的基本信息放在脑后。我这里介绍的东西已经足够你在生物信息学的健壮性和可移植性方面
开始思考一些核心概念。许多主题在这时候都被提及到，我鼓励感兴趣的读者继续深入。    










