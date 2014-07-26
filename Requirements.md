## 接口需求文档

> 对于每个需要返回的字段，格式为

> [Out] 类型(字段描述)

> 对于每个需要设置的字段，格式为：

> [In] 类型(字段描述)

+ PS: POST/GET 根据需求而定

+ PPS: 在非网络问题情况下，验证和错误描述字段总是存在

含两类接口需求：

1. 未实现过非安全、稳定、防火防盗版本，需要实现的接口

2. 实现过非安全、稳定、防火防盗版本，需要升级的接口

### 未实现过非安全、稳定、防火防盗版本，需要实现的接口

#### 问题详细

> [in] int(问题id)

> [in] int(回答分页页码)

> [out] 问题的信息(

> > String(问题及问题的描述)

> > 问题相关的话题

> > 点赞的功能

> > int(关注及回答的人数)

> )

> [out] 回答用户列表(

> >  回答的id
 
> >  用户的头像

> >  用户的id

> >  该问题回答的id

> >  点赞的人数

> >  用户回答的预览
 
> )

#### 添加回答

> [in] int(问题id)

> [in] 详细的回答

> [in] 与问题相关的图片

> [out] 成功与否

#### 关注该问题的用户列表

> [in] int(问题id)

> [out] 用户id

> [out] 用户名

> [out] 用户一句话签名

#### 回答的详细

> [in] int(回答的id)

> [out] 回答的信息(

> > 回答的问题及回答内容

> > 点赞的人数及不赞的人数

> )

> 功能：

> > 点赞和不赞的功能

> > 收藏的功能

#### 回答的评论列表

>  [in] int(回答的id)

>  [in] int(评论分页页码)

>  [out] 评论(

> > 评论的id

> > 评论用户的用户名

> > 评论用户的用户id

> > 评论用户的头像

> > 发布的时间

> > 点赞和回复的人数

> )

#### 添加回答评论

> [in] 评论的id

> [in] 评论内容

> [in] 成功与否

> 功能：

> > 点赞该评论的功能

> > 回复该评论的功能


#### 文章的详细

> [in] int(文章的id)

> [out] 文章的信息(

> > 文章的标题及详细信息

> > 点赞的人数

> > 相关的话题

> )

> 功能：

> > 点赞和不赞的功能

> > 收藏的功能

#### 文章的评论列表

>  [in] int(文章的id)

>  [in] int(评论分页页码)

>  [out] 评论(

> > 评论的id

> > 评论用户的用户名

> > 评论用户的用户id

> > 评论用户的头像

> > 发布的时间

> > 点赞和回复的人数

> )

#### 添加文章评论

> [in] 评论的id

> [in] 评论内容

> [in] 成功与否

> 功能：

> > 点赞该评论的功能

> > 回复该评论的功能

#### 发现列表

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > Int(回答ID)

> > String(回答预览)

> > Int(回答者UID)

> > URI(回答者头像)

> > Int(顶的个数)

> )

#### 获取我的提问列表  (已完成)

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > String(问题预览)

> > Date(提问时间)

> )

#### 获取我的回复列表 (已完成)

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

#### 获取我的文章列表 (已完成)

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(文章ID)

> > String(文章标题)

> > String(文章预览)

> > Date(发表日期)

> )

#### 获取我的关注问题列表 (已完成)

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > Date(提问时间)

> > Int(关注人数)

> > Int(答案数)

> )


#### 我的动态列表

占位

#### 首页动态列表

占位

#### 图片

> [In] Binary(图片)

> [Out] Int(图片ID)

#### 搜索话题

> [In] String(关键词)

> [Out] Array(

> > Int(话题ID)

> > String(话题标题)

> > String(话题描述)

> > URI(话题图片)

> )

#### 提问

> [In] String(标题)

> [In] Array(话题ID)

> [In] Array(图片ID)

> [In] String(问题描述)

> [Out] Int(问题ID)

#### 搜索

占位


#### 我关注的用户列表 （已完成）

> [Out] String(用户头像URI)

> [Out] String(用户名)

> [Out] String(签名singnature)

> edit by huangchen

#### 关注我的用户列表（已完成）

> 与我关注的用户列表字段相同 


#### 我关注的话题列表 (已完成)

> [Out] String(图片url)

> [Out] String(标题)

> [Out] String(关于话题预览)

#### 话题资料

> [Out] (String)关于话题详情

> [Out] String(关于话题预览)

> [Out] (int)关注的人数

> [Out]  是否已经关注  

 
#### 关注操作、

> 实现对一个话题的操作

#### 精华列表

> [Out] String(问题)

> [Out] String(图片url)

> [Out] String(赞的人数)

> [Out] String(回复预览)

### 实现过非安全、稳定、防火防盗版本，需要升级的接口

#### 用获取户信息 (已完成)

> [In] Int(UID)

> [Out] String(用户头像URI)

> [Out] String(用户名)

> [Out] Int(我的话题数)

> [Out] Int(我关注的人数)

> [Out] Int(关注我的人数)

> [Out] Int(赞同我的次数)

> [Out] Int(感谢我的次数)

> [Out] Int(答案被收藏次数)

> [Out] Int(答案被分享次数)

用于展示用户信息  (已完成)
 
> [In] Int(UID)

> [Out] String(用户名)

> [Out] Int(性别ID)

> [Out] String(个人简介)

> [Out] Int(行业ID)

> [Out] Date(生日)

用于修改用户信息 （已完成）


> [In] Int(UID)

> [In] String(用户名)

> [In] Int(性别ID)

> [In] String(个人简介)

> [In] Int(行业ID)

> [In] Date(生日)

> [Out] Bool(成功／失败)

#### 获取职位列表 (已完成)

用于展示／修改个人从属行业等信息 

> [In] Int(页数)

> [Out] Array(

> > Int(职业ID)

> > String(职业名称)

> )
