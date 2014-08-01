安全,稳定,防火防盗的新接口文档
==============

API List:

http://w.hihwei.com/?/ （默认）

http://w.hihwei.com/api/ （如果是这个会有说明）

- 话题图片文件夹：http://w.hihwei.com/uploads/topic/
- 头像图片文件夹：http://w.hihwei.com/uploads/avatar/

##说在前面
> 接口总是会返回三个字段

- rsm (成功时包含返回的数据，失败时此字段为null)
- errno (1:成功 -1:失败)
- err (成功时此字段为null，失败时此字段包含错误原因，可原样输出)

![Image](https://raw.githubusercontent.com/ifLab/FMobile-Design/master/api/success.png)

![Image](https://raw.githubusercontent.com/ifLab/FMobile-Design/master/api/error.png)


##用户账号相关接口

https://github.com/ifLab/FMobile-Design/blob/master/API_Account.md
（一个文件有点乱有点大，故，愉快的分居了）

##发布相关接口

https://github.com/ifLab/FMobile-Design/blob/master/API_Publish.md

##发现相关接口

https://github.com/ifLab/FMobile-Design/blob/master/API_Explore.md


#以下列表接口一般都接收三个参数：uid(必须)，page(可选)，per_page(可选) 不明白的在讨论组里交流，炎炎夏日，写代码不易

##获取我的文章列表

> URL：my_article.php （http://w.hihwei.com/api/my_article.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(文章ID)

> > String(文章标题)

> > String(文章预览)

> > Date(发表日期)

> )

> 可能返回的错误原因：

- 参数不完整

##获取我的提问列表

> URL：my_question.php （http://w.hihwei.com/api/my_question.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > String(问题预览)

> > Date(提问时间)

> )

> 可能返回的错误原因：

- 参数不完整

## 获取我的关注问题列表

> URL：my_focus_question.php （http://w.hihwei.com/api/my_focus_question.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > Date(提问时间)

> > Int(关注人数)

> > Int(答案数)

> )

## 获取我的回复列表

> URL：my_answer.php （http://w.hihwei.com/api/my_answer.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > String(回复用户头像URI)

> > Int(回复ID)

> > String(回复预览)

> > Int(回复赞同数)

> )

## 我关注的用户列表

> URL：my_focus_user.php （http://w.hihwei.com/api/my_focus_user.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(UID)

> [In] Int(页数)

> [Out] String(用户头像URI)

> [Out] String(用户名)

> [Out] String(签名singnature)

> edit by huangchen

## 关注我的用户列表

> URL：my_fans_user.php （http://w.hihwei.com/api/my_fans_user.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(UID)

> [In] Int(页数)

> 与我关注的用户列表字段相同 

## 获取职位列表

用于展示／修改个人从属行业等信息  （默认全部返回，可以加per_page和page参数）

> URL：job_list.php （http://w.hihwei.com/api/job_list.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(页数)

> [Out] Array(

> > Int(职业ID)

> > String(职业名称)

> )


## 我关注的话题列表

> URL：my_focus_topic.php （http://w.hihwei.com/api/my_focus_topic.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(UID)

> [In] Int(页数)

> [Out] String(图片url) （话题图片路径：http://w.hihwei.com/uploads/topic/）

> [Out] String(标题)

> [Out] String(描述)

## 单个话题列表

> URL：topic.php （http://w.hihwei.com/api/topic.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int uid （必须）

> [In] Int topic_id （必须）

> [Out] String(图片url) （话题图片路径：http://w.hihwei.com/uploads/topic/）

> [Out] String(标题)

> [Out] String(描述)

> [Out] Int(当前用户是否已关注，关注：1  未关注：0)

## 关注或取消关注某个话题操作

> URL：focus_topic.php （http://w.hihwei.com/api/focus_topic.php）

> HTTP请求方式

- POST

> 请求参数：

> [In] Int uid （必须）

> [In] Int topic_id （必须）

> [In] String type （选，如果是取消关注，此值设为 'cancel' ）

> 如果成功，errno为1，不多解释，因“说在前面”有解释


##问题详情

> URL：api/question/question/   （  DEMO: view-source:http://w.hihwei.com/?/api/question/question/?id=2  ）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int(问题ID)

> [Out] String(问题标题)

> [Out] String(问题正文)

> [Out] Int(问题关注数)

> [Out] 回答列表(

> > Int(ID)
 
> > Int(用户ID)

> > String(用户姓名)

> > Int(赞同的人数)

> > String(回答预览)
 
> )

> [Out] Tag列表(

> > Int(ID)

> > Int(名称)

> )

## 关注该问题的用户列表

> URL：question_fans_user.php   （  DEMO: http://w.hihwei.com/api/question_fans_user.php?id=2  ）

> HTTP请求方式

- GET

> 请求参数：

> [in] id 问题编号

> [out] 用户id

> [out] 用户名

> [out] 用户头像

> [out] 用户一句话签名


## 回答的详细

> URL：answer_detail.php   （  DEMO: http://w.hihwei.com/api/answer_detail.php?id=4  ）

> HTTP请求方式

- GET

> 请求参数：

> [In] id 回答编号

> [Out] Int(用户ID)

> [Out] Int(赞同数)

> [Out] String(正文)

> [Out] Int(评论数)

> [Out] Date(日期) 

## 回答的评论列表

> URL：answer_comment.php  （  DEMO: http://w.hihwei.com/api/answer_comment.php?id=4  ）

> HTTP请求方式

- GET

> 请求参数：

> [In] id 回答编号

> [Out] Int(评论人ID)

> [Out] String(评论人姓名)

> [Out] String(评论正文)

> [Out] Date(日期)

> [Out] Array at_user (被@用户信息，如果有则会返回这个信息)   

> 图释：

![image](https://raw.githubusercontent.com/ifLab/FMobile-Design/master/api/at_user.png)


## 文章的详细 

> URL： api/article/article/  （  DEMO: http://w.hihwei.com/?/api/article/article/?id=2  ）

> HTTP请求方式

- GET

> 请求参数 

> [in] int(文章的id)

> [out] 文章的信息(

> > 文章的标题及详细信息

> > 点赞的人数

> > 相关的话题

> )

## 文章的评论列表

> URL： api/article/comment/  （  DEMO: http://w.hihwei.com/?/api/article/comment/?id=2  ）

> HTTP请求方式

- GET

> 请求参数 

- id (文章ID)

- page (分页页码)

>  [out] 评论(

> > 评论的id

> > 评论用户的用户名

> > 评论用户的用户id

> > 评论用户的头像

> > 发布的时间

> > 点赞人数

> > 评论＠的人信息（如果有则有）

> )

> 图释：

![image](https://raw.githubusercontent.com/ifLab/FMobile-Design/master/api/at_comment.png)

## 发表文章评论

> URL：api/publish/save_comment/

> HTTP请求方式

- POST

> Header

- COOKIE

> 请求参数：

- article_id (文章ID)

- message (评论的内容)

- at_uid (可选，如果是回复某条评论，则要指定被回复者uid)

> 返回结果：

- comment_id (评论ID)

> 可能返回的错误信息：

- 指定文章不存在

- 已经锁定的文章不能回复

- 请输入回复内容

- 你所在的用户组不允许发布站外链接

## 对文章评论点赞和取消操作

> URL： article/ajax/article_vote/  （http://w.hihwei.com/?/article/ajax/article_vote/）

> HTTP请求方式

- POST

> Header

- COOKIE

> 请求参数 

- type ( 对文章评论操作，参数值是: comment )

- item_id (comment的id)

- rating  ( 有三种值，1（赞）0（取消赞） )


## 文章点赞,踩，及取消操作

> URL： article/ajax/article_vote/  （http://w.hihwei.com/?/article/ajax/article_vote/）

> HTTP请求方式

- POST

> Header

- COOKIE

> 请求参数 

- type ( 对文章操作，参数值是: article )

- item_id (article的id)

- rating  ( 有三种值，1（赞） -1（踩）  0（取消赞或者取消踩） )

## 话题关注，取消关注操作

> URL： topic/ajax/focus_topic/  （DEMO：http://w.hihwei.com/?/topic/ajax/focus_topic/?topic_id=17）

> HTTP请求方式

- GET

> Header

- COOKIE

> 请求参数 

- topic_id (话题ID)

- NOTE：不需要传其他参数，如果当前用户已经关注该话题，会取消关注，反之则关注

## 用户关注，取消关注操作

> URL：follow/ajax/follow_people/  （DEMO：http://w.hihwei.com/?/follow/ajax/follow_people/?uid=5）

> HTTP请求方式

- GET

> Header

- COOKIE

> 请求参数 

- uid (用户ID)

- NOTE：不需要传其他参数，如果当前用户已经关注该用户，会取消关注，反之则关注

############################################################



##话题广场 （待修改）

> URL：api/topic/square/

> HTTP请求方式

- GET

> Header

- COOKIE

> 请求参数：

- id (string) [可能的值：focus（我关注的话题）hot（热门话题）today（今日话题）]
- page (页码)

> 返回结果：

- 话题列表

##单个话题信息 （待修改）

> URL：api/topic/topic/

> HTTP请求方式

- GET

> Header

- COOKIE

> 请求参数：

- id (string) [可以是topic的id或title]
> 返回结果：

- topic_info 话题信息

> 可能返回的错误原因：

- 话题不存在


##单篇文章信息（待修改）

> URL：api/article/article/

> HTTP请求方式

- GET

> Header

- COOKIE

> 请求参数：

- id (string) [article的id]

- page (int) [评论分页页码]

> 返回结果：

- article 文章信息 [包括文章信息，评论数目，评论内容，作者等信息]

> 可能返回的错误原因：

- 错误请求,缺少问题id

- 文章不存在或已被删除
 

