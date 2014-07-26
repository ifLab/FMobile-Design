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



##用户注册

> URL：api/account/register_process/

> HTTP请求方式

- POST

> 请求参数：

- user_name (string)
- password (string) 
- email (string)

> 返回结果：

- uid 用户编号

> 可能返回的错误原因：

- 本站目前关闭注册
- 本站只能通过邀请注册
- 本站只能通过微信注册
- 请输入用户名
- 用户名已经存在
- 用户名包含无效字符
- 用户名中包含敏感词或系统保留字
- E-Mail 已经被使用, 或格式不正确
- 密码长度不符合规则

##用户登录


> URL：api/account/login_process/

> HTTP请求方式

- POST

> 请求参数：

- user_name (string) [可以是用户名也可以是邮箱]
- password (string) 

> 返回结果：

- uid 用户编号

> 可能返回的错误原因：

- 请输入正确的帐号或密码
- 抱歉, 你的账号已经被禁止登录

##用户头像修改


> URL：api/account/avatar_upload/

> HTTP请求方式

- POST

> Header

- COOKIE

> 请求参数：

- user_avatar (图片文件域) 

> 返回结果：

- preview 头像地址

> 可能返回的错误原因：

- 文件类型无效
- 文件尺寸过大
- 上传失败, 请与管理员联系
- 。。。错误原因太多，没法一一解释，此处省略百万字（By Hwei）

##话题广场

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

##单个话题信息

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

##单个问题信息

> URL：api/question/question/

> HTTP请求方式

- GET

> Header

- COOKIE

> 请求参数：

- id (string) [question的id]

- page (int) [回答分页页码]

> 返回结果：

- question 问题信息 [包括问题信息，回答数目，回答内容，发起人等信息]

> 可能返回的错误原因：

- 错误请求,缺少问题id

- 问题不存在或已被删除

##单篇文章信息

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
