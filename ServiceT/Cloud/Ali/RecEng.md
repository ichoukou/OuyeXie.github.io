# 产品介绍

 - [概念解释](https://help.aliyun.com/document_detail/shujia/RE/intro/re-intro3.html?spm=5176.docshujia/RE/intro/re-intro2.6.242.djl87F)
    - org (shengupiao)
    - user
    - item
    - biz, 业务针对数据集定义，定义了算法所能使用的数据范围。一个客户在RecEng上可以有多个业务，不同的业务必然有不同的数据集。RecEng要求每个业务提供四类数据（不要求全部提供）：用户数据，物品数据，用户行为数据，推荐效果数据。每一组这样的数据就构成一个业务。系统中常用biz表示业务。一个业务最好只推荐一类物品，强行把多类物品放在一个业务中推荐，虽然RecEng不禁止这种做法，但是效果可能会打折扣。
    - scn, 场景指的是推荐的上下文，说的更直白一点，场景由推荐时可用的参数决定。有两种场景最为常见，分别是首页推荐场景和详情页推荐场景。顾名思义，在执行首页推荐时，可用的参数只有用户信息；而在执行详情页推荐时，可用的参数除了用户信息，还包括当前详情页上所展示的物品信息。系统中常用scn表示场景。
    - path
    - rec_path
        - offline flow
        - online flow
    - alg, 算法从使用环境上分，可以分为离线算法和在线算法两类。离线算法运行在ODPS平台上，用Java编写；在线算法运行在Node.js环境中，用Node.js编写。RecEng中所有的离线算法都用于推荐流程（rec_path）的离线流程（offline_flow），按功能的不同分为三类：
        业务算法：用于推荐业务相关的算法，包括特征抽取，兴趣分析，相似计算等，这些算法通常会有一组可以调整的参数。
        质检算法：用于进行数据质量检测的算法，检查离线算法每一步产出的结果是否满足某些业务定义的规则。
        效果算法：用于计算效果报表中所展示指标的算法。
      RecEng没有提供太多的在线算法，一般被用于推荐流程（rec_path）的在线流程（online_flow）部分，以及实时修正流程（mod_path）。online_flow中用到的在线算法相对简单，主要是对推荐结果的评分，过滤和排序，mod_path中用到的在线算法会复杂一些，如何取舍视具体的需求而定。
    - 流程模板
    - job, 作业指运行中的离线流程实例，作业和离线流程的关系完全等同于进程和程序的关系。每个作业都是不可重入的，即对每个离线流程，同一时间只允许运行一份实例。
 - [部署和接入](https://help.aliyun.com/document_detail/shujia/RE/intro/re-intro4.html?spm=5176.docshujia/RE/intro/re-intro3.6.243.YuTQJ5)
    - 和RecEng的API对接。RecEng提供了一组功能API，推荐API只是其中之一。这些API包括启动离线计算作业，实时更新可被推荐的物品等，详见“API说明”一节。
    - 上传离线数据到公有云ODPS。RecEng没有提供上传离线数据到ODPS的功能，需要客户自己把用户数据、物品数据，以及每日的用户行为日志按照RecEng的规范要求整理好，上传到预先开通的公有云ODPS中。
 - [全流程规范](https://help.aliyun.com/document_detail/shujia/RE/intro/re-intro5.html?spm=5176.docshujia/RE/intro/re-intro4.6.244.uKWAv9)
    - [日志埋点规范](https://help.aliyun.com/document_detail/shujia/RE/dataspec/logspec.html?spm=5176.docshujia/RE/intro/re-intro5.2.1.mnuPpz)
        - method: GET
            - login
            - item
            - view *
            - click *
            - consume
            - use
            - grade
            - like/dislike
            - collect/uncollect
            - comment
            - share
            - search click
        - RecEng支持两条日志上报通道，实时上报和离线上报。实时上报通过Restful API提交，离线上报按照数据格式规范的格式提交到ODPS。日志埋点规范包括通过Restful接口提交的日志格式，不包括ODPS上离线日志表的格式。
        - 日志埋点规范在内容方面要求客户记录交易行为和准备行为，并且在记录用户行为日志时区分开这两种行为。
        - 此外为了便于计算由推荐服务带来的转换率，日志埋点规范要求客户记录traceid。traceid将用户在推荐坑位的点击与最终成交关联起来，用于判断成交是否是由推荐服务带来的。traceid由RecEng在返回实时返回推荐结果时返回
    
    - [数据格式规范](https://help.aliyun.com/document_detail/shujia/RE/dataspec/datauploadspec.html?spm=5176.docshujia/RE/intro/re-intro5.2.3.mnuPpz)
        - 离线数据规范, 一般情况下，离线计算的输入和输出都是ODPS表，所以离线数据规范其实上是一组ODPS表的格式规范，包括接入数据、中间数据和输出数据三类数据的格式规范。
            - 接入数据指客户离线提供的用户、物品、日志等数据
                - 日志数据离线和在线基本上一致，日志埋点规范中已有说明，参见规范的详细定义即可
                - 物品数据由类别、属性和关键字几部分组成, RecEng要求这三个字段不全为空
                - 用户数据类似，有一个叫做tags的多值字段，tags字段可以为空
                - !!!为了让RecEng了解物品的属性字段和用户的tags字段中各个key-value的数据类型，客户还需要补充两张数据结构说明表，分别解释物品的属性字段中每个key-value的数据类型，以及用户的tags字段中每个key-value的数据类型。当客户提供的物品数据、用户数据的内容没有变化时，这两张表可以一直沿用。!!!
            - 如果客户要自定义离线算法，需要了解中间和输出数据格式规范
        - 在线数据规范, 不像离线算法，天然以ODPS表作为输入和输出，在线程序的输入数据可以来自多个数据源，如在线存储OTS，以及用户的API请求，又或者是程序中的变量；输出可以是程序变量，或者写回在线存储，或者返回给用户。
            - online_flow
            - mod_path
        - user_meta
        - user_meta_config
            - config_value取值为mv_enum，kv_num，sv_enum，sv_num，分别代表多值枚举型，KV数值型，单值枚举型，单值数值型四种标签取值类型。
        - item_meta
        - item_meta_config
        - user_behavior
        - rec_item_info
            - is a sub set of item_meta? usually
            
    - 算法规范, 在RecEng中，算法是把数据串接起来的逻辑。这里的数据指离线的标准表，或在线的标准数据集。算法除了输入输出数据之外，通常还会包括一系列参数
        - RecEng要求每个算法只能有一份输出数据，不限制输入数据的数目
    - 算法流程
        - offline_flow
        - online_flow
        - 在RecEng中，推荐流程（rec_path）属于场景（scn），客户可在场景下新建推荐流程，每个推荐流程由离线流程（offline_flow）和在线流程（online_flow）组成，是相对独立的两个部分。所以每个rec_path由两个有向无环图组成。实时修正流程（mod_path）则属于业务，两类mod_path各自最多只有一个实例，所以每个业务下最多只有两个实时修正流程的有向无环图。
 
 - [测试和效果测试](https://help.aliyun.com/document_detail/shujia/RE/intro/re-intro6.html?spm=5176.docshujia/RE/intro/re-intro5.6.245.mnuPpz)
    - 集成测试通过测试路径实现
    - 效果测试则是在算法通过集成测试后，检查算法在实际应用中的效果，最常用的方法是AB Test
    - !!!普通用户在请求推荐结果时需要向RecEng传递其所在的业务和场景的参数，不需要指明rec_path；而要请求测试流程的产出结果，用户需要向RecEng传递rec_path的标识，即其对应的path_code。RecEng用这种方式区分测试流程和正常的业务流程!!!
        - 目前RecEng只支持在每个场景下建立一条测试流程，未来可以考虑放开这个限制
 - [运维和运营](https://help.aliyun.com/document_detail/shujia/RE/intro/re-intro7.html?spm=5176.docshujia/RE/intro/re-intro6.6.246.e9n42k)
    - 数据质检和告警
        - 对于离线计算，RecEng支持客户为每种标准表编写质检算法，用于校验数据是否符合要求。这些要求可以是空值的占比，数据范围等等
    - 效果报表 
        - 支持效果指标的自定义
        - 支持报表内容的自定义
 - [系统规格](https://help.aliyun.com/document_detail/shujia/RE/intro/re-intro8.html?spm=5176.docshujia/RE/intro/re-intro7.6.247.KxbCyy)
    - RecEng支持每个客户最多创建5个业务（biz），每个业务最多20个推荐流程（rec_path）
    - API说明, 4个API分别用于启动离线计算，启动数据导入，查询离线计算状态，实时获取推荐结果
    - RecEng的预置算法中包括热门物品推荐的算法，客户可直接使用
    - 默认流程模板会根据用户在过去三十天的行为分析用户兴趣，当客户首次接入RecEng时，通常只导入了最近一天的用户行为数据
    
# 快速入门

 - [准备工作](https://help.aliyun.com/document_detail/shujia/RE/startup/re-startup-pre1.html?spm=5176.docshujia/RE/api.6.251.jxrpxA)
 - [添加资源](https://help.aliyun.com/document_detail/shujia/RE/startup/re-startup-pre5.html?spm=5176.docshujia/RE/startup/re-startup-pre4.6.255.BhdNxF)
    - 大数据计算服务（原ODPS）
    - 表格存储（原OTS）
    - 云监控（可选）
 - [配置业务和场景](https://help.aliyun.com/document_detail/shujia/RE/startup/re-startup-pre6.html?spm=5176.docshujia/RE/startup/re-startup-pre5.6.256.efUbLT)
    - 添加业务, 推荐业务是推荐引擎的基本管理单元，业务定义了算法所能使用的数据范围
    - 查看系统预设的场景和算法流程, 一个推荐业务支持包含多个推荐场景，每个推荐场景可以看做是APP或网站中提供个性化推荐的功能模块。场景隶属于某一个业务，使用到的数据就是在业务中配置的数据。
        - 场景包含一个或多个算法流程，每一个算法流程代表一种推荐物品的逻辑，由离线流程和在线流程组合而成，离线流程和在线流程分别由多个算法拼装组成。
    - 发布算法流程
    - 添加推荐场景
 - [启动离线计算](https://help.aliyun.com/document_detail/shujia/RE/startup/re-startup-pre7.html?spm=5176.docshujia/RE/startup/re-startup-pre6.6.257.mDXub0)
    - 您可以通过手动方式或调用API方式启动离线计算
 - [API对接](https://help.aliyun.com/document_detail/shujia/RE/startup/re-startup-pre8.html?spm=5176.docshujia/RE/startup/re-startup-pre7.6.258.kTOAtr)
 - [添加自定义算法和流程模板](https://help.aliyun.com/document_detail/shujia/RE/startup/re-startup-pre10.html?spm=5176.docshujia/RE/startup/re-startup-pre8.6.259.DmoHAM)
    - 添加自定义算法
    - 添加流程模板, 通过搭建模板，您能够预先定义常用的算法流程，在场景中添加算法流程时可直接选择预先设定好的模板
    
# 算法规范
 
 - [离线算法开发手册](https://help.aliyun.com/document_detail/shujia/RE/algdev/offlinealg.html?spm=5176.docshujia/RE/startup/re-startup-pre10.6.264.vX32B6)
    - DataForm, 推荐引擎对整个离线推荐算法流程做了数据抽象。每种数据抽象就是一种DataForm，DataForm实体存储对应ODPS的一张表
    - 算法类目, 我们把一组特定输入输出的算法归到同一个算法分类，新建算法的时候必须要指定算法类目，这样推荐引擎才知道如何给你需要的参数，已经如何把这个算法放到算法流程的合适位置
    - 进阶的ODPS开发
    - 离线算法开发
        - RecAlgorithmPlugIn, 客户开发的每个算法都要继承这个基类。实现evalute 方法。 传入RecPlatformContext实例化对象
        - RecPlatformContext, 推荐平台上下文，用于获取推荐引擎传入的参数、启动ODPSTask以及上报需要报警错误
        - ActivityNode, Node元信息。包含nodeCode，tableName，alg，nodeWeight，datafrom字段
            - 对于系统内置dataform，tablename是”前缀+dataform“的格式拼接，且会在业务初始化时新建完成
            - 可以试图通过查看ODPS的最后初始化结果推测prefix到底是什么? 在哪里设置?
        - check javadoc
    - 打包
    - 界面注册
    - 配置流程
    - 系统内置DataForm
        - 输入类DataForm, 作为整个算法流程的输入，无法导入在线存储。不区分场景和abtest
            - USER_META
            - ITEM_META
            - REC_ITEM_INFO
            - USER_BEHAVIOR
        - 离线算法类DataForm, 可以作为离线流程的中间数据，也可导出到在线存储
            - USER_ASSET
            - ITEM_POOL
            - ITEM_FEATURE
            - USER_FEATURE
            - SYMMETRIC_FEATURE
            - USER_ITEM_FEATURE
            - USER_ITEM_SCORE
            - ITEM_ITEM_REC_LIST
            - USER_ITEM_REC_LIST
            - DEFAULT_REC_LIST
            - TAG_ITEM_REC_LIST
            - RANKING_MODEL
    - [离线算法开发样例](https://bbs.aliyun.com/read/274300.html?spm=5176.bbsl350.0.0.AjHwXa)
 - [在线算法开发手册](https://help.aliyun.com/document_detail/shujia/RE/algdev/onlinealg.html?spm=5176.docshujia/RE/algdev/offlinealg.6.265.hgcFPa)
    - CTX：SDK内置变量
        - REC_REQ
        - REC_IS
        - REC_UF
        - REC_IF
        - REC_MODEL
    - TOOLBOX：SDK内置方法
        - getRecItemInfo
    - 关于require方法的使用
        - util
          utility
          lodash
 
# API说明
 
 - 获取推荐结果
 - 启动数据预处理任务,启动数据导入任务,与作业管理页面的数据导入功能一样
    - [check circle 4](https://help.aliyun.com/document_detail/shujia/RE/startup/re-startup-pre2.html?spm=5176.docshujia/RE/api.6.252.uNdW2F)
    - should be here (after clicking "启动数据预处理", "作业管理页面" should be referring to the list below):
        - https://dtboost.aliyun.com/re?spm=a2c0j.7906784.0.4.R9r9N1#/myre
        - [check my image](https://help.aliyun.com/document_detail/shujia/RE/startup/re-startup-pre7.html?spm=5176.docshujia/RE/startup/re-startup-pre6.6.257.degZRd)
 - 启动离线算法任务,启动biz或者scn下面所有有效的算法任务
 - 启动效果计算任务,启动biz或者scn下面所有有效的算法任务
 - 查询任务状态,查询离线任务的运行状态
 - 日志埋点
 
# FAQ

 - https://bbs.aliyun.com/read/274288.html?spm=5176.bbsl350.0.0.CbDZia